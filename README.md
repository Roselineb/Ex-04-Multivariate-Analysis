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
# ![image](https://user-images.githubusercontent.com/128909895/231135523-d886c3de-bf33-47f1-860a-f5a69b97976c.png)
# DATA INFORMATION
# ![image](https://user-images.githubusercontent.com/128909895/231135727-62ff4685-f611-4908-83c6-0e56f428fd0d.png)
# DATA DESCRIBE
# ![image](https://user-images.githubusercontent.com/128909895/231136237-f42425ff-db3b-4bb4-a2f4-572bac3be02b.png)
# Checking the null values and Cleaning it
# ![image](https://user-images.githubusercontent.com/128909895/231136393-79518b8f-98d7-4732-9b28-16da9de87554.png)
# ![image](https://user-images.githubusercontent.com/128909895/231136436-0d1cc465-fa82-4da0-91a7-7dc51af73ba1.png)
# DATA TYPES
# ![image](https://user-images.githubusercontent.com/128909895/231136541-f226ccc7-73a9-41ea-b906-bc2c007fd4f5.png)
# SCATTERPLOT
# ![image](https://user-images.githubusercontent.com/128909895/231136692-46388b5b-f9f5-4b11-91e0-7e0ca39c83de.png)
# BARPLOT
# ![image](https://user-images.githubusercontent.com/128909895/231137834-9072784f-8ab2-451f-a9b6-8b6a21300ee5.png)
# ![image](https://user-images.githubusercontent.com/128909895/231137878-3fdf5819-5a12-4b4e-b7f6-29ba2558d511.png)
# ![image](https://user-images.githubusercontent.com/128909895/231137961-8b41afd8-0310-474f-9563-67db591acd3c.png)
# ![image](https://user-images.githubusercontent.com/128909895/231138052-71a47491-7ffc-4e21-bd25-cf3dd9745fe0.png)
# CORRELATION COEFFICIENT INTERPRETATION
# ![image](https://user-images.githubusercontent.com/128909895/231138222-f0a11f0a-9e81-4a0d-a0eb-e76ddd052ea9.png)
# HEATMAP
# ![image](https://user-images.githubusercontent.com/128909895/231138305-86bbad72-8a79-48e0-ba2a-9ee7cb761734.png)
# RESULT
Thus we have read the given data and performed the multivariate analysis with different types of plots.

