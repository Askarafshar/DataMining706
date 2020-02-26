```python
#!/usr/bin/env python
# coding: utf-8

import numpy as np 
import pandas as pd
import matplotlib.pyplot as plt

df_heart = pd.read_csv("heart.csv")
df_heart.head()
#output
```
<img src="https://github.com/Askarafshar/DataMining706/blob/master/Project-Plan/output/1.png">

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

