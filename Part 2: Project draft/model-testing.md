```python
#!/usr/bin/env python
# coding: utf-8

from IPython.core.interactiveshell import InteractiveShell
from sklearn.ensemble import GradientBoostingRegressor
from sklearn.ensemble import RandomForestClassifier
from sklearn.model_selection import train_test_split
from sklearn.tree import DecisionTreeClassifier
from sklearn.linear_model import LogisticRegression
from sklearn.neighbors import KNeighborsClassifier
from sklearn.metrics import classification_report
from sklearn.metrics import accuracy_score
from sklearn.feature_selection import RFE
from sklearn.metrics import roc_auc_score
from sklearn.tree import export_graphviz
from sklearn.metrics import roc_curve
from matplotlib import pyplot as plt
from tabulate import tabulate
from pprint import pprint
import seaborn as sns
import pandas as pd
import numpy as np
import time
import arff
import eli5
import os
import csv

data = pd.read_csv("heart.csv")
data.head()
#output
```
<img src="https://github.com/Askarafshar/DataMining706/blob/master/Part%202:%20Project%20draft/img/data.png">

```python
data.describe()
#output
```
<img src="https://github.com/Askarafshar/DataMining706/blob/master/Project-Plan/output/attributes.png">

 The '_split_stratified_into_train_val_test_' function that splits a Pandas dataframe into train, validation, and test dataframes with stratified sampling.[link](https://stackoverflow.com/questions/38250710/how-to-split-data-into-3-sets-train-validation-and-test)
```python
def split_stratified_into_train_val_test(df_input, stratify_colname='y',
                                         frac_train=0.6, frac_val=0.15, frac_test=0.25,
                                         random_state=None):
    '''
    Splits a Pandas dataframe into three subsets (train, val, and test)
    following fractional ratios provided by the user, where each subset is
    stratified by the values in a specific column (that is, each subset has
    the same relative frequency of the values in the column). It performs this
    splitting by running train_test_split() twice.

    Parameters
    ----------
    df_input : Pandas dataframe
        Input dataframe to be split.
    stratify_colname : str
        The name of the column that will be used for stratification. Usually
        this column would be for the label.
    frac_train : float
    frac_val   : float
    frac_test  : float
        The ratios with which the dataframe will be split into train, val, and
        test data. The values should be expressed as float fractions and should
        sum to 1.0.
    random_state : int, None, or RandomStateInstance
        Value to be passed to train_test_split().

    Returns
    -------
    df_train, df_val, df_test :
        Dataframes containing the three splits.
    '''

    if frac_train + frac_val + frac_test != 1.0:
        raise ValueError('fractions %f, %f, %f do not add up to 1.0' % \
                         (frac_train, frac_val, frac_test))

    if stratify_colname not in df.columns:
        raise ValueError('%s is not a column in the dataframe' % (stratify_colname))

    X = df_input # Contains all columns.
    y = df_input[[stratify_colname]] # Dataframe of just the column on which to stratify.

    # Split original dataframe into train and temp dataframes.
    df_train, df_temp, y_train, y_temp = train_test_split(X,
                                                          y,
                                                          stratify=y,
                                                          test_size=(1.0 - frac_train),
                                                          random_state=random_state)

    # Split the temp dataframe into val and test dataframes.
    relative_frac_test = frac_test / (frac_val + frac_test)
    df_val, df_test, y_val, y_test = train_test_split(df_temp,
                                                      y_temp,
                                                      stratify=y_temp,
                                                      test_size=relative_frac_test,
                                                      random_state=random_state)

    assert len(df_input) == len(df_train) + len(df_val) + len(df_test)

    return df_train, df_val, df_test
    
# Using the above function to split data into train, test, and validation subsets by stratifying on 'ca' attribute, with 60, 20, and 20 fractional ratios, respectively.
data_train, data_val, data_test = split_stratified_into_train_val_test(data, stratify_colname='ca', frac_train=0.60, frac_val=0.20, frac_test=0.20)
#output
```
<img src="https://github.com/Askarafshar/DataMining706/blob/master/Project-Plan/output/age.png">

```python
sex =  df_heart['sex'].plot.hist()
#output
```
<img src="https://github.com/Askarafshar/DataMining706/blob/master/Project-Plan/output/sex.png">

```python
cp =  df_heart['cp'].plot.hist()
#output
```
<img src="https://github.com/Askarafshar/DataMining706/blob/master/Project-Plan/output/cp.png">

```python
trestbps =  df_heart['trestbps'].plot.box(grid=True)
#output
```
<img src="https://github.com/Askarafshar/DataMining706/blob/master/Project-Plan/output/trestbps.png">

```python
chol =  df_heart['chol'].plot.box(grid=True)
#output
```
<img src="https://github.com/Askarafshar/DataMining706/blob/master/Project-Plan/output/chol.png">

```python
fbs =  df_heart['fbs'].plot.hist()
#output
```
<img src="https://github.com/Askarafshar/DataMining706/blob/master/Project-Plan/output/fbs.png">

```python
restecg = df_heart['restecg'].plot.hist()
#output
```
<img src="https://github.com/Askarafshar/DataMining706/blob/master/Project-Plan/output/restecg.png">

```python
thalach = df_heart['thalach'].plot.box(grid=True)
#output
```
<img src="https://github.com/Askarafshar/DataMining706/blob/master/Project-Plan/output/thalach.png">

```python
exang = df_heart['exang'].plot.hist()
#output
```
<img src="https://github.com/Askarafshar/DataMining706/blob/master/Project-Plan/output/exang.png">

```python
oldpeak = df_heart['oldpeak'].plot.box(grid=True)
#output
```
<img src="https://github.com/Askarafshar/DataMining706/blob/master/Project-Plan/output/oldpeak.png">

```python
slope = df_heart['slope'].plot.hist()
#output
```
<img src="https://github.com/Askarafshar/DataMining706/blob/master/Project-Plan/output/slope.png">

```python
ca = df_heart['ca'].plot.hist()
#output
```
<img src="https://github.com/Askarafshar/DataMining706/blob/master/Project-Plan/output/ca.png">

```python
thal = df_heart['thal'].plot.hist()
#output
```
<img src="https://github.com/Askarafshar/DataMining706/blob/master/Project-Plan/output/thal.png">

```python
target = df_heart['target'].plot.hist()
#output
```
<img src="https://github.com/Askarafshar/DataMining706/blob/master/Project-Plan/output/target.png">

