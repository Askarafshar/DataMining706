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
```
