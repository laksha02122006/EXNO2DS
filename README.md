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

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("titanic_dataset.csv")
df

<img width="1812" height="755" alt="image" src="https://github.com/user-attachments/assets/89b8fe53-2b2c-4d59-8024-23b314c4548c" />


df.info()


<img width="1776" height="491" alt="image" src="https://github.com/user-attachments/assets/effcb126-70e4-4398-afb6-efa0ee110f49" />


df.describe()


<img width="1745" height="427" alt="image" src="https://github.com/user-attachments/assets/a807fb22-31fb-42b9-aded-2b06c04da029" />


df.dtypes


<img width="1782" height="617" alt="image" src="https://github.com/user-attachments/assets/eca84436-beed-4555-a279-8a9bfd3e8a97" />


df.value_counts()

<img width="1779" height="649" alt="image" src="https://github.com/user-attachments/assets/cdbec377-4f28-47d3-8acd-41738c4d5604" />


df['Age'].value_counts()


<img width="1733" height="649" alt="image" src="https://github.com/user-attachments/assets/62869b8e-b3d1-4b9f-9bc3-facad248efca" />

df.set_index("PassengerId",inplace=True)
df.describe()

<img width="1784" height="440" alt="image" src="https://github.com/user-attachments/assets/17917c6f-3f87-4c9d-ba3d-245837052729" />

df.shape

<img width="1822" height="121" alt="image" src="https://github.com/user-attachments/assets/995fb158-1ec5-4463-a9e6-0db80b590db3" />


df.nunique()

<img width="1168" height="709" alt="image" src="https://github.com/user-attachments/assets/e5e368f0-d110-4434-b573-3a2e14bc846e" />


sns.countplot(data=df,x='Survived')

<img width="1503" height="772" alt="image" src="https://github.com/user-attachments/assets/842785ba-2f25-400c-88fc-46fc525262c8" />

df.Pclass.unique()

<img width="1664" height="125" alt="image" src="https://github.com/user-attachments/assets/f2ecacd5-89fb-433e-8e05-8e4541c9ec12" />

df.rename(columns={'Sex':'Gender'},inplace=True)
df

<img width="1692" height="776" alt="image" src="https://github.com/user-attachments/assets/f77da8a0-d54b-496f-b81c-c2b74c1bb13f" />


sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=7,aspect=.7)

<img width="1489" height="802" alt="image" src="https://github.com/user-attachments/assets/c96f883c-3126-473e-a173-b2ed914d4656" />


df.boxplot(column="Age",by="Survived")

<img width="1369" height="798" alt="image" src="https://github.com/user-attachments/assets/79b2a51c-44d6-498a-ac66-5771c90ff615" />


sns.scatterplot(x=df["Age"],y=df["Fare"])


<img width="1193" height="743" alt="image" src="https://github.com/user-attachments/assets/20bc2d96-f4e7-4b58-9368-2223152ab97d" />


fig,ax1=plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)


<img width="1672" height="778" alt="image" src="https://github.com/user-attachments/assets/7affb91e-0a00-41a8-8a49-47921acb9e3d" />


plt = sns.boxplot(x='Pclass',y='Age',hue='Gender',data=df)


<img width="1310" height="738" alt="image" src="https://github.com/user-attachments/assets/4b939d29-43a1-427c-a3a8-b9e92791d9d4" />


sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")


<img width="1573" height="764" alt="image" src="https://github.com/user-attachments/assets/05f6a6ab-1fea-433a-b128-da91c8b3a7b4" />


corr=df.select_dtypes(include=np.number).corr()
sns.heatmap(corr,annot=True)

<img width="1152" height="716" alt="image" src="https://github.com/user-attachments/assets/540c37eb-8d3c-4c8b-9d72-634094d7c643" />


# RESULT:
 Thus the data analysis has been implemented successfully.
