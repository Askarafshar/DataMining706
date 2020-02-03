'''python
#!/usr/bin/env python
# coding: utf-8

from scipy.io import arff
import pandas as pd
from matplotlib import pyplot as plt
data = arff.loadarff('cpu.with.vendor.arff')
df = pd.DataFrame(data[0])
df.head()
'''
#output


'''python
df.describe()

ax1 = df['MYCT'].plot.box(grid=True)

ax2 = df['MMIN'].plot.box(grid=True)

ax3 = df['MMAX'].plot.box(grid=True)

ax4 = df['CACH'].plot.box(grid=True)

ax5 = df['CHMIN'].plot.box(grid=True)

ax6 = df['CHMAX'].plot.box(grid=True)

ax7 = df['class'].plot.box(grid=True)
'''
