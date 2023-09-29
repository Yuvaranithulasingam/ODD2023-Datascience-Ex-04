# ODD2023-Datascience-Ex-04

## AIM:
To perform Multivariate EDA on the given data set.

## EXPLANATION:
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

## ALGORITHM:
### STEP 1:
Import the built libraries required to perform EDA and outlier removal.
### STEP 2:
Read the given csv file
### STEP 3:
Convert the file into a dataframe and get information of the data.
### STEP 4:
Return the objects containing counts of unique values using (value_counts()).
### STEP 5:
Plot the counts in the form of Histogram or Bar Graph. 
### STEP 6: 
Use seaborn the bar graph comparison of data can be viewed.
### STEP 7:
Find the pairwise correlation of all columns in the dataframe.corr()
### STEP 8:
Save the final data set into the file.

## PROGRAM:
### SuperStore.csv file:
```
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
data=pd.read_csv("/content/SuperStore (2).csv")
df=pd.DataFrame(data)
df.head()
df.info()
df.describe()
df.isnull().sum()
df['Postal Code']=df['Postal Code'].fillna(df['Postal Code'].mode()[0])
df.isnull().sum()

sns.scatterplot(x=df['Region'],y=df['Sales'])

states=df.loc[:,["State","Sales"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Sales")
plt.figure(figsize=(12,5))
plt.xticks(rotation=90)
sns.barplot(x=states.index,y="Sales",data=states)

states=df.loc[:,["Ship Mode","Row ID"]]
states=states.groupby(by=["Ship Mode"]).sum().sort_values(by="Row ID")
sns.barplot(x=states.index,y="Row ID",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("SHIP MODE")
plt.ylabel=("ROW ID")
plt.show()

sns.boxplot(x=df['Ship Date'],y=df['Sales'])
sns.displot(df, x="Region", hue="Category")
df.corr()
sns.heatmap(df.corr(),annot=True)
```
### diabetes.csv file:
```
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
df=pd.read_csv("/content/diabetes.csv")
df
df.describe()
df.info
df.isnull().sum()

sns.scatterplot(x=df['Glucose'],y=df['BloodPressure'])

sns.scatterplot(x=df['Glucose'], y=df['BloodPressure'], hue=df['Outcome'])

Age=df.loc[:,["Age","BMI"]]
Age=Age.groupby(by=["Age"]).sum().sort_values(by="BMI")
plt.figure(figsize=(12,5))
plt.xticks(rotation=90)
sns.barplot(x=Age.index,y="BMI",data=Age)

Age=df.loc[:,["BloodPressure","Glucose"]]
Age=Age.groupby(by=["BloodPressure"]).sum().sort_values(by="Glucose")
sns.barplot(x=Age.index,y="Glucose",data=Age)
plt.xticks(rotation = 90)
plt.xlabel=("BloodPressure")
plt.ylabel=("Glucose")
plt.show()

sns.boxplot(x=df['DiabetesPedigreeFunction'],y=df['Insulin'])

sns.displot(df, x="Glucose", hue="Outcome")

df.corr()

sns.heatmap(df.corr(),annot=True)
```
### OUTPUT:
### Data frame of SuperStore
![image](https://github.com/Yuvaranithulasingam/ODD2023-Datascience-Ex-04/assets/121418522/acb956fc-1b40-4955-bb07-0e9b0d31a231)

### Data information
![image](https://github.com/Yuvaranithulasingam/ODD2023-Datascience-Ex-04/assets/121418522/3eebbafc-ab49-48d9-ab67-6bb422a24226)
 
### Data describing
![image](https://github.com/Yuvaranithulasingam/ODD2023-Datascience-Ex-04/assets/121418522/bd5984a2-df22-41d4-baf0-7677bcef804b)

### Sum of null values
![image](https://github.com/Yuvaranithulasingam/ODD2023-Datascience-Ex-04/assets/121418522/681b6435-7598-41cd-a98c-092bc2c90d43)

### After removing null values
![image](https://github.com/Yuvaranithulasingam/ODD2023-Datascience-Ex-04/assets/121418522/e2ed4b4d-ce2f-40aa-98a5-bdb6d1c0b8cf)

### Scatter plot
![image](https://github.com/Yuvaranithulasingam/ODD2023-Datascience-Ex-04/assets/121418522/80e530ea-92ef-4732-b98b-b91cbea8ef19)

### Bar plot
![image](https://github.com/Yuvaranithulasingam/ODD2023-Datascience-Ex-04/assets/121418522/c2888feb-0360-4c63-a94f-58f5d586a58e)

![image](https://github.com/Yuvaranithulasingam/ODD2023-Datascience-Ex-04/assets/121418522/ef8accf1-29f1-49e3-860b-216142136d71)

### Box plot
![image](https://github.com/Yuvaranithulasingam/ODD2023-Datascience-Ex-04/assets/121418522/ab85e40a-b429-4c3a-87a7-1fd86bb25944)

### Dist plot
![image](https://github.com/Yuvaranithulasingam/ODD2023-Datascience-Ex-04/assets/121418522/f3760f48-560f-4935-884c-49741cf278d2)

### Correlation coefficient interpretation
![image](https://github.com/Yuvaranithulasingam/ODD2023-Datascience-Ex-04/assets/121418522/36c346ad-0e66-473f-b4d6-169211c447eb)

### Heat map
![image](https://github.com/Yuvaranithulasingam/ODD2023-Datascience-Ex-04/assets/121418522/ae1ab6f0-0a6a-4628-ac5c-8eb52323ed1c)

### Data frame for diabetes
![image](https://github.com/Yuvaranithulasingam/ODD2023-Datascience-Ex-04/assets/121418522/d90398df-eb62-40a5-94f2-75efee2e08d7)

### Data information
![image](https://github.com/Yuvaranithulasingam/ODD2023-Datascience-Ex-04/assets/121418522/50c78962-c74e-460d-94cf-9ccb3cd851ed)

### Describing a data set
![image](https://github.com/Yuvaranithulasingam/ODD2023-Datascience-Ex-04/assets/121418522/3af81673-5487-4c18-a380-ce03c7e96c02)

### Sum of null values
![image](https://github.com/Yuvaranithulasingam/ODD2023-Datascience-Ex-04/assets/121418522/27aef17f-5317-42c9-aa78-be6842eadc0c)

### Scatter plot
![image](https://github.com/Yuvaranithulasingam/ODD2023-Datascience-Ex-04/assets/121418522/1dc370d7-8c25-465f-b545-64b64e1b8418)

![image](https://github.com/Yuvaranithulasingam/ODD2023-Datascience-Ex-04/assets/121418522/60e22b70-c3ca-4743-8f61-8bea22a7041d)

### Bar plot
![image](https://github.com/Yuvaranithulasingam/ODD2023-Datascience-Ex-04/assets/121418522/fdf2f177-b115-4211-8ca6-df6d3a0f2a15)

![image](https://github.com/Yuvaranithulasingam/ODD2023-Datascience-Ex-04/assets/121418522/d838a079-7011-4437-ba42-c03ae326dd12)

### Box plot
![image](https://github.com/Yuvaranithulasingam/ODD2023-Datascience-Ex-04/assets/121418522/ce411dc9-3290-48ca-a109-d0f8847af286)

### Dist plot
![image](https://github.com/Yuvaranithulasingam/ODD2023-Datascience-Ex-04/assets/121418522/54e276a2-5e93-4922-b9ea-759a5e33810b)

### Correlation coefficient interpretation
![image](https://github.com/Yuvaranithulasingam/ODD2023-Datascience-Ex-04/assets/121418522/6c091658-a0c9-46b9-be30-8900f2d4f7ed)

### Heat map
![image](https://github.com/Yuvaranithulasingam/ODD2023-Datascience-Ex-04/assets/121418522/566474cc-2156-4ef0-a303-8458b77697c7)

## RESULT:
Thus we have read the given data and performed the multivariate analysis with different types of plots.
