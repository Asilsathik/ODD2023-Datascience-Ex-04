# ODD2023-Datascience-Ex-04

Aim:
To perform Multivariate EDA on the given data set.

Explanation:

Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

Algorithm:
Step1: Import the built libraries required to perform EDA and outlier removal.
Step2: Read the given csv file.
Step3: Convert the file into a dataframe and get information of the data.
Step4: Return the objects containing counts of unique values using (value_counts()).
Step5: Plot the counts in the form of Histogram or Bar Graph.

Developed By: 212222230080

Register Number: MOHAMED ASIL .M

Program:

SuperStore.csv
```
import pandas as pd
import seaborn as sns
from scipy import stats
import matplotlib.pyplot as plt
df=pd.read_csv('SuperStore.csv')
df.describe()
df.isnull().sum()
df.info()
# FILLING NULL VALUES
df['Postal Code']=df['Postal Code'].fillna(df['Postal Code'].mode()[0])
sns.boxplot(df)
sns.scatterplot(x=df['Region'],y=df['Sales'])
plt.figure(figsize=(10,3))
sns.barplot(x=df['State'],y=df['Sales'])
plt.xticks(rotation=90)
sns.heatmap(df.corr(),annot=True)
sns.displot(df,x='Region',hue="Category")
```
Output: 
(SuperStorE.csv)

![image](https://github.com/Asilsathik/ODD2023-Datascience-Ex-04/assets/119476247/b40200b5-8fd0-404a-ac9a-07550e7ea537)
![image](https://github.com/Asilsathik/ODD2023-Datascience-Ex-04/assets/119476247/3de09373-d219-4a6c-8705-54dbf182d71e)
![image](https://github.com/Asilsathik/ODD2023-Datascience-Ex-04/assets/119476247/da9dc243-81b2-40fa-87c6-9f71e5e8a21e)
![image](https://github.com/Asilsathik/ODD2023-Datascience-Ex-04/assets/119476247/f7563117-720c-4877-aed5-5533ad30282d)
![image](https://github.com/Asilsathik/ODD2023-Datascience-Ex-04/assets/119476247/d0e4719f-2985-4d5e-b2cb-b8a7bc1eaca7)
![image](https://github.com/Asilsathik/ODD2023-Datascience-Ex-04/assets/119476247/a5ecf235-1cb7-4eac-933b-33942b200481)
![image](https://github.com/Asilsathik/ODD2023-Datascience-Ex-04/assets/119476247/f5eb19d2-b750-4210-acbd-ae18dd5c55a8)

Diabetes.csv :
```
import pandas as pd
import seaborn as sns
from scipy import stats
import matplotlib.pyplot as plt
df=pd.read_csv('diabetes.csv')
df.describe()
df.isnull().sum()
# REMOVING OUTLIER
z = np.abs(stats.zscore(df['Glucose']))
df=df[(z<2)]
z = np.abs(stats.zscore(dfc['BloodPressure']))
df=df[(z<2)]
z = np.abs(stats.zscore(dfc['SkinThickness']))
df=df[(z<3)]
z = np.abs(stats.zscore(dfc['BMI']))
df=df[(z<2)]
z = np.abs(stats.zscore(dfc['Insulin']))
df=df[(z<2)]
z = np.abs(stats.zscore(dfc['DiabetesPedigreeFunction']))
df=df[(z<2)]
z = np.abs(stats.zscore(dfc['Age']))
df=df[(z<2)]
z = np.abs(stats.zscore(dfc['Outcome']))
df=df[(z<3)]
sns.boxplot(data=dfc)
plt.xticks(rotation=90)
sns.boxplot(data=dfc)
plt.xticks(rotation=90)
sns.scatterplot(x=df['Glucose'], y=df['BloodPressure'], hue=df['Outcome'])
Age=df.loc[:,["Age","BMI"]]
Age=Age.groupby(by=["Age"]).sum().sort_values(by="BMI")
plt.figure(figsize=(12,5))
plt.xticks(rotation=90)
sns.barplot(x=Age.index,y="BMI",data=Age)
sns.boxplot(x=df['DiabetesPedigreeFunction'],y=df['Insulin'])
sns.displot(df, x="Glucose", hue="Outcome")
df.corr()
sns.heatmap(df.corr(),annot=True)
```
Output (Diabetes.csv):

![image](https://github.com/Asilsathik/ODD2023-Datascience-Ex-04/assets/119476247/0052f1a8-69b3-4f12-880e-1062359609d0)
![image](https://github.com/Asilsathik/ODD2023-Datascience-Ex-04/assets/119476247/d607d0fc-f555-44fb-92c5-760dad927cf5)
![image](https://github.com/Asilsathik/ODD2023-Datascience-Ex-04/assets/119476247/8272cfc2-d728-4c34-9413-a0ef2a1e1385)
![image](https://github.com/Asilsathik/ODD2023-Datascience-Ex-04/assets/119476247/f9a94487-d7e8-4d6e-9f36-6d8df03c5cd8)
![image](https://github.com/Asilsathik/ODD2023-Datascience-Ex-04/assets/119476247/8b2b070e-f695-40d1-af0a-cfa650118467)
![image](https://github.com/Asilsathik/ODD2023-Datascience-Ex-04/assets/119476247/1ebdb3d1-3f78-476a-9bcd-e4f278a7def4)
![image](https://github.com/Asilsathik/ODD2023-Datascience-Ex-04/assets/119476247/ac5de8d3-481e-41f3-b928-b08a6b860dd6)



RESULT:
Thus we have read the given data and performed the multivariate analysis with different types of plots.




