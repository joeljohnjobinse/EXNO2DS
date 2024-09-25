# EXNO2DS
# AIM:
      To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
dt=pd.read_csv("titanic_dataset.csv")
dt
```
![image](https://github.com/user-attachments/assets/283e1ef4-4207-421f-9466-cac675d112f0)

```
dt.info()
```
![image](https://github.com/user-attachments/assets/a5fec46f-74b5-4225-b52b-dfb1ea000978)
```
dt.shape
```
![image](https://github.com/user-attachments/assets/67d43eb0-399a-4c0f-82a1-69f1a974c6eb)
```
dt.set_index("PassengerId",inplace=True)
dt.describe()
```
![image](https://github.com/user-attachments/assets/d8e7092d-8935-4715-96c2-97e86ccdc85f)
```
dt.nunique()
```
![image](https://github.com/user-attachments/assets/c36a20e6-9336-4310-a8a3-69b8e3ea75ea)
```
dt["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/d5db22d6-99fd-4744-9dd6-f488a7617bfa)
```
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/19f4ef77-fe7e-40da-8e50-4a67bdadaed4)

```
sns.countplot(data=dt,x="Survived")
```
![image](https://github.com/user-attachments/assets/233f79b1-3068-4e99-9261-19b515479bc4)
```
dt.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/f7194f5e-f49f-4173-9640-3628bc22f7eb)
```
dt.rename(columns={'Sex':'Gender'}, inplace=True)
sns.catplot(x='Gender',col='Survived',kind="count",data=dt)
```
![image](https://github.com/user-attachments/assets/544c56b9-2018-454b-a3a8-ec36f84f027d)
```
sns.catplot(x='Survived',hue='Gender',kind="count",data=dt)
```
![image](https://github.com/user-attachments/assets/77c49e3d-ab65-4f7d-aaac-89a22a608763)
```
dt.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/178aee75-94d4-4dbb-a0b4-91f8050ddcaf)
```
dt.boxplot(column="Age",by="Pclass")
```
![image](https://github.com/user-attachments/assets/dfafe305-bcfc-4c4b-a1b8-8b693ff9308f)
```
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
```
![image](https://github.com/user-attachments/assets/04a05074-4f63-4225-b6ea-8e2b9aa192d8)
```
sns.jointplot(x="Age",y="Fare",data=dt)
```
![image](https://github.com/user-attachments/assets/3fcd31ec-3b83-4332-afe8-e5aee45b7dfd)
```
sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/42ae990d-4ff9-44f3-a82e-c31a4a325b81)
```
##Co-relation
corr=dt.corr()
sns.heatmap(corr,annot=True)
```
![image](https://github.com/user-attachments/assets/939412d4-8d93-45c9-b6ed-8970750a482e)
```
sns.pairplot(dt)
```
![image](https://github.com/user-attachments/assets/73327e88-eb82-4835-b500-c1dbbcbdf013)

# RESULT
Thus, Exploratory Datwa Analysis has been performed on the dataset.
