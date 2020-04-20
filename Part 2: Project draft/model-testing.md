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
df_heart.describe()
#output
```
<img src="https://github.com/Askarafshar/DataMining706/blob/master/Project-Plan/output/attributes.png">

```python
age =  df_heart['age'].plot.box(grid=True)
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

