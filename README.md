# Ex-04-Multivariate-Analysis
#Aim

To perform Multivariate EDA on the given data set.

#Explaination

Exploratory data analysis is used to understand the messages within a dataset. This technique
involves many iterative processes to ensure that the cleaned data is further sorted to better
understand the useful meaning.The primary aim with exploratory analysis is to examine the data for
distribution, outliers and anomalies to direct specific testing of your hypothesis

#Algorithm

STEP 1 Import the built libraries required to perform EDA and outlier removal.

STEP 2 Read the given csv file.

STEP 3 Convert the file into a dataframe and get information of the data.

STEP 4 Return the objects containing counts of unique values using (value_counts()).

STEP 5 Plot the counts in the form of Histogram or Bar Graph.

STEP 6 Use seaborn the bar graph comparison of data can be viewed.

STEP 7 Find the pairwise correlation of all columns in the dataframe.corr()

STEP 8 Save the final data set into the file.

#Program

Developed by:M DINESH KUMAR

Register number:212221220011

import pandas as pd

import numpy as np

import seaborn as sns

import matplotlib.pyplot as plt

from google.colab import files

uploaded = files.upload()

df = pd.read_csv("SuperStore.csv")

df


df.info()

df.describe()

df.isnull().sum()

df['Sales'] = df["Sales"].fillna(df['Sales'].mode()[0])

df.isnull().sum()

df.dtypes

sns.scatterplot(df['Sales'])

states=df.loc[:,["State","Sales"]]

states=states.groupby(by=["State"]).sum().sort_values(by="Sales")

plt.figure(figsize=(17,7))

sns.barplot(x=states.index,y="Sales",data=states)

df.info()

states=df.loc[:,["Postal Code","Sales"]]

states=states.groupby(by=["Postal Code"]).sum().sort_values(by="Sales")

sns.barplot(x=states.index,y="Sales",data=states)

plt.xticks(rotation = 90)

plt.xlabel=("Postal Code")

plt.ylabel=("SALES")

plt.show()

states=df.loc[:,["Segment","Sales"]]

states=states.groupby(by=["Segment"]).sum().sort_values(by="Sales")

sns.barplot(x=states.index,y="Sales",data=states)

plt.xticks(rotation = 90)

plt.xlabel=("Segment")

plt.ylabel=("Sales")

plt.show()


df.corr()

sns.heatmap(df.corr(),annot=True)

#output

dataset

![image](https://user-images.githubusercontent.com/104413084/231067976-e01199e4-a73c-4d24-bc65-14eafee2b448.png)


Dataset information

![image](https://user-images.githubusercontent.com/104413084/231068069-99c68699-fe43-4f32-867e-0e222c3d1843.png)


Data describe

![image](https://user-images.githubusercontent.com/104413084/231068235-3c2bf29e-409e-4fa2-9d96-bb3e06daf11b.png)

Checking and cleaning of null values

![image](https://user-images.githubusercontent.com/104413084/231068332-92b6603e-7955-4c72-8af1-630733de91a1.png)


Data types

![image](https://user-images.githubusercontent.com/104413084/231068443-bf9d4e93-ccf4-4fd2-815f-dc3e86a14671.png)


Scatterplot

![image](https://user-images.githubusercontent.com/104413084/231068674-7ac5003c-178e-430f-9e42-b7f6485e3429.png)

Barplot

![image](https://user-images.githubusercontent.com/104413084/231068782-cac775b7-40e2-4512-a98e-29c88b62999a.png)


Correlation coefficient interpretation

![image](https://user-images.githubusercontent.com/104413084/231068901-ccecbfab-ffce-4bfd-8b01-07676e12e511.png)

Heatmap

![image](https://user-images.githubusercontent.com/104413084/231068995-5c59f5a1-7adc-4e7a-bcb7-0130ec252916.png)

#Result

Thus we have read the given data and performed the multivariate analysis with different types of
plots.

