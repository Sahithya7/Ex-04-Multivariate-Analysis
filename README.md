# Ex-04-Multivariate-Analysis
# AIM
To perform Multivariate EDA on the given data set.
# Explanation:
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
# ALGORITHM:
# STEP 1
Import the built libraries required to perform EDA and outlier removal.
# STEP 2
Read the given csv file
# STEP 3
Convert the file into a dataframe and get information of the data.
# STEP 4
Return the objects containing counts of unique values using (value_counts()).
# STEP 5
Plot the counts in the form of Histogram or Bar Graph.
# STEP 6
Use seaborn the bar graph comparison of data can be viewed.
# STEP 7
Find the pairwise correlation of all columns in the dataframe.corr()
# STEP 8
Save the final data set into the file
# PROGRAM
```
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
df=pd.read_csv("SuperStore.csv")
df
df.info()
df.describe()
df.isnull().sum()
df['Postal Code'] = df["Postal Code"].fillna(df['Postal Code'].mode()[0])
df.isnull().sum()
df.dtypes
sns.scatterplot(df['Row ID'],df['Sales'])
states=df.loc[:,["State","Sales"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Sales")
plt.figure(figsize=(17,7))
sns.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("SALES")
plt.show()
states=df.loc[:,["State","Row ID"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Row ID")
plt.figure(figsize=(17,7))
sns.barplot(x=states.index,y="Row ID",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("ROW ID")
plt.show()
states=df.loc[:,["Segment","Row ID"]]
states=states.groupby(by=["Segment"]).sum().sort_values(by="Row ID")
sns.barplot(x=states.index,y="Row ID",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("SEGMENT")
plt.ylabel=("ROW ID")
plt.show()
sns.barplot(df['Sales'],df['Ship Mode'],hue=df['Region'])
df.corr()
sns.heatmap(df.corr(),annot=True)
```
# OUTPUT
# DATA
![image](https://github.com/Sahithya7/Ex-04-Multivariate-Analysis/assets/133002193/b6a5aa96-5f78-423e-91bd-69c5901d1c48)
# Data.info
![image](https://github.com/Sahithya7/Ex-04-Multivariate-Analysis/assets/133002193/b113221a-a8b7-49cd-a655-1556c8ba3c92)
# Data.describe
![image](https://github.com/Sahithya7/Ex-04-Multivariate-Analysis/assets/133002193/886a6207-e2de-43fa-801a-1ddcbddfb83e)
# Checking the null values and Cleaning it
![image](https://github.com/Sahithya7/Ex-04-Multivariate-Analysis/assets/133002193/7c2698b6-b884-42bd-baee-c75612828fd4)
![image](https://github.com/Sahithya7/Ex-04-Multivariate-Analysis/assets/133002193/01dbecea-72ee-4890-ab68-08f23b43e8e2)
# DATA TYPES
![image](https://github.com/Sahithya7/Ex-04-Multivariate-Analysis/assets/133002193/5366cb84-289b-415a-8b72-d754fd206287)
# SCATTER PLOT
![image](https://github.com/Sahithya7/Ex-04-Multivariate-Analysis/assets/133002193/0bbebd18-e581-47d0-96a0-6d25b6afaa95)
# BAR PLOT
![image](https://github.com/Sahithya7/Ex-04-Multivariate-Analysis/assets/133002193/cefffd82-e23a-455b-983b-121bc5e029bf)
![image](https://github.com/Sahithya7/Ex-04-Multivariate-Analysis/assets/133002193/5e0e9b5b-60db-40e4-b958-45240b4e007f)
![image](https://github.com/Sahithya7/Ex-04-Multivariate-Analysis/assets/133002193/00cc3341-8a91-4ee9-b3ea-741ef7d54cb9)
![image](https://github.com/Sahithya7/Ex-04-Multivariate-Analysis/assets/133002193/8919f16c-3fc9-4deb-9d7c-cfcf6857a272)
# CORRELATION COEFFICIENT INTERPRETATION
![image](https://github.com/Sahithya7/Ex-04-Multivariate-Analysis/assets/133002193/b3acab71-17ad-4811-b626-c58d08be42e6)
# HEATMAP
![image](https://github.com/Sahithya7/Ex-04-Multivariate-Analysis/assets/133002193/67316c2f-9bfe-434e-a7bb-acff79c713e5)
# RESULT
Thus we have read the given data and performed the multivariate analysis with different types of plots.
