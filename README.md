# EXNO2DS
# Name : V.Sai Sruthi
# reg no : 212223100061
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
df=pd.read_csv("titanic_dataset.csv")
df
```
![image](https://github.com/user-attachments/assets/bccb13cf-236c-4254-9b01-7e998d48131a)

```
df.info()
```
![image](https://github.com/user-attachments/assets/01be2b87-0eaf-4de3-aee9-350295cbb563)
```
df.shape
```
![image](https://github.com/user-attachments/assets/7812ed8f-2982-4795-9540-e96fe05cc774)
```
df.set_index("PassengerId",inplace=True)
df.describe()
```
![image](https://github.com/user-attachments/assets/32c722a6-537d-428f-9a3c-6b285b52108e)
```
df.shape
```
![image](https://github.com/user-attachments/assets/1c043292-017d-4f30-bdfc-b1dca98e59cf)
```
df.nunique()
```
![image](https://github.com/user-attachments/assets/deb61ffc-2ef5-40ac-a05b-f845c827af28)
```
df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/e6c33c92-2a2f-4e29-9bb5-de8b50b8efb9)
```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/38f7431b-c46b-4ba7-8a5f-5f30238689cb)
```
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/user-attachments/assets/9470aa13-85b7-4b82-806b-c7badb72ecda)
```
df
```
![image](https://github.com/user-attachments/assets/c63ab8d0-6c24-400b-b336-6fcb87547e6c)
```
df.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/8aff3464-eead-4adb-ab7f-e90e9262687d)
```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/8a8a48df-9019-4ed9-84b8-2665490b9424)
```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/f4befbbd-bf79-48e7-8f0c-5f4603c20d42)
```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![image](https://github.com/user-attachments/assets/21cef92f-b08d-4c47-991d-c06db277d68b)
```
df.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/6419c764-8a90-49fc-9152-22243d9bbc2d)
```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![image](https://github.com/user-attachments/assets/7ca9d69d-1081-4fcd-af17-fd6b93621c45)
```
sns.jointplot(x="Age",y="Fare",data=df)
```
![image](https://github.com/user-attachments/assets/4eac53f3-cd15-4b5e-bbb7-d39930167e59)
```
fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![image](https://github.com/user-attachments/assets/b048bc30-1e87-415a-8a89-175b6e76a0c1)
```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/655bafcb-a55d-4ad1-a040-0736a1b7e975)
```
numeric_df = df.select_dtypes(include=np.number)
corr = numeric_df.corr()
sns.heatmap(corr, annot=True)
```
![image](https://github.com/user-attachments/assets/0b7f74a0-4feb-4a1e-b961-5afe4482dc53)
```
sns.pairplot(df)
```
![image](https://github.com/user-attachments/assets/0aae289a-a574-43c9-9927-e830123312e2)

# RESULT
We have performed Exploratory Data Analysis on the given data set successfully
