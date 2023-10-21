# ODD2023-DataScience-Ex-03
# Ex03-Univariate-Analysis
# Aim
To read the given data and perform the univariate analysis with different types of plots.

# Explanation
Univariate analysis is basically the simplest form to analyze data. Uni means one and this means that the data has only one kind of variable. The major reason for univariate analysis is to use the data to describe. The analysis will take data, summarise it, and then find some pattern in the data.

# Algorithm :
## Step 1:
Read the given data.

## Step 2:
Get the information about the data.

## Step 3:
Remove the null values from the data.

## Step 4:
Mention the datatypes from the data.

## Step5
Count the values from the data.

## Step6
Do plots like boxplots,countplot,distribution plot,histogram plot.

# Program:
```
import pandas as pd
from scipy import stats
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```
```
from google.colab import files
uploaded = files.upload()
```
```
df = pd.read_csv('diabetes.csv')
df
```
![image](https://github.com/Sudhar2303/ODD2023-DataScience-Ex-03/assets/133684710/6639d5b3-0247-4229-a013-5b5df2f988a9)

```
df.isnull().sum()
```
![image](https://github.com/Sudhar2303/ODD2023-DataScience-Ex-03/assets/133684710/ca821800-f2d1-4519-bfd7-6c8c47796c3e)

```
q1 = df.quantile(0.25)
q3 = df.quantile(0.75)
iqr = q3 - q1
iqr
```
![image](https://github.com/Sudhar2303/ODD2023-DataScience-Ex-03/assets/133684710/04bf6e66-7869-4df6-a93e-b024a2a94c4e)

```
low = q1 - 1.5*iqr
high = q1 + 1.5*iqr
df = df[(df >= low) & (df <= high)]
df
```
![image](https://github.com/Sudhar2303/ODD2023-DataScience-Ex-03/assets/133684710/2416c545-e7fe-4e19-8b7d-ed7c6ccfa1a7)

```
sns.boxplot(df)
```
![image](https://github.com/Sudhar2303/ODD2023-DataScience-Ex-03/assets/133684710/20060fa0-365d-4ec4-880f-83e546a79bca)

```
sns.displot(x ="Glucose", data = df)
```
![image](https://github.com/Sudhar2303/ODD2023-DataScience-Ex-03/assets/133684710/14f23a86-af73-46ef-9221-cbe66f828cb5)

```
sns.displot(x ="BloodPressure", data = df)
```
![image](https://github.com/Sudhar2303/ODD2023-DataScience-Ex-03/assets/133684710/2e431df3-8961-4411-86c8-e05195483356)

```
sns.displot(x ="BMI", data = df)
```
![image](https://github.com/Sudhar2303/ODD2023-DataScience-Ex-03/assets/133684710/a5b98b9b-7bd8-449a-aa95-f7c24d1ec0a5)

```
sns.displot(x ="DiabetesPedigreeFunction", data = df)
```
![image](https://github.com/Sudhar2303/ODD2023-DataScience-Ex-03/assets/133684710/6abac0da-18a5-4d1a-85cb-11849a535161)

```
sns.displot(x ="Age", data = df)
```
![image](https://github.com/Sudhar2303/ODD2023-DataScience-Ex-03/assets/133684710/8d78678d-05be-4cc4-a3f2-3c111aaae317)

```
from google.colab import files
uploaded = files.upload()
```

![image](https://github.com/Sudhar2303/ODD2023-DataScience-Ex-03/assets/133684710/182ad41a-320b-491e-95a9-2305360626c3)

```
df = pd.read_csv('employeesal.csv')
df
```
![image](https://github.com/Sudhar2303/ODD2023-DataScience-Ex-03/assets/133684710/e13cdff9-23b0-4b22-bdf7-d1f1416ed34e)
```
df.isnull().sum()
```
![image](https://github.com/Sudhar2303/ODD2023-DataScience-Ex-03/assets/133684710/d539ec26-cda5-44aa-81c8-e5e76abdf85c)
```
numeric_cols = df.select_dtypes(include=[int, float])
q1 = numeric_cols.quantile(0.25);
q3 = numeric_cols.quantile(0.75);
iqr = q3 - q1
iqr
```
![image](https://github.com/Sudhar2303/ODD2023-DataScience-Ex-03/assets/133684710/95e1206e-1724-4cb8-829b-b81e17461159)
```
low = q1 - 1.5*iqr
high = q1 + 1.5*iqr
numeric_cols = numeric_cols[(numeric_cols >= low) & (numeric_cols <= high)]
numeric_cols.dropna()
```
![image](https://github.com/Sudhar2303/ODD2023-DataScience-Ex-03/assets/133684710/580e9953-e738-4423-a90e-657d8ee8bbd9)
```
sns.boxplot(numeric_cols)
```
![image](https://github.com/Sudhar2303/ODD2023-DataScience-Ex-03/assets/133684710/1ee42732-7e09-483a-9146-f164e131bee3)
```
sns.histplot(x = 'Experience_Years',data = numeric_cols)
```
![image](https://github.com/Sudhar2303/ODD2023-DataScience-Ex-03/assets/133684710/0fd9857a-96d2-4521-b13f-6c596a3ded8c)
```
sns.histplot(x = 'Age',data = numeric_cols)
```
![image](https://github.com/Sudhar2303/ODD2023-DataScience-Ex-03/assets/133684710/d619d743-4e6f-4fc4-a697-f9350bf8ef33)
```
sns.histplot(x = 'Salary',data = numeric_cols)
```
![image](https://github.com/Sudhar2303/ODD2023-DataScience-Ex-03/assets/133684710/3a8a2b57-0975-445c-bda7-265d1a8e343f)
```
from google.colab import files
uploaded = files.upload()
```
![image](https://github.com/Sudhar2303/ODD2023-DataScience-Ex-03/assets/133684710/71385dd4-9cf9-4265-a907-9367fbde8433)
```
df = pd.read_csv('SuperStore.csv')
df
```
![image](https://github.com/Sudhar2303/ODD2023-DataScience-Ex-03/assets/133684710/493f94e8-af89-4ef2-85d1-d06236d7e0eb)
```
df.isnull().sum()
```
![image](https://github.com/Sudhar2303/ODD2023-DataScience-Ex-03/assets/133684710/59f287e0-b89b-4ade-acc7-ae0e8784bb69)
```
df.dropna()
```
![image](https://github.com/Sudhar2303/ODD2023-DataScience-Ex-03/assets/133684710/53da63ff-e8ca-47ef-811c-3e9ff7c8eaf8)
```
df.dtypes
```
![image](https://github.com/Sudhar2303/ODD2023-DataScience-Ex-03/assets/133684710/fc381094-6498-4715-9f43-2633825467f9)
```
numeric_cols = df.select_dtypes(include=[float])
q1 = numeric_cols.quantile(0.25);
q3 = numeric_cols.quantile(0.75);
iqr = q3 - q1
iqr
```
![image](https://github.com/Sudhar2303/ODD2023-DataScience-Ex-03/assets/133684710/52f89cf3-23d0-44b2-8510-7d3cb3448075)
```
low = q1 - 1.5*iqr
high = q1 + 1.5*iqr
numeric_cols = numeric_cols[(numeric_cols >= low) & (numeric_cols <= high)]
```
```
sns.boxplot(numeric_cols)
```
![image](https://github.com/Sudhar2303/ODD2023-DataScience-Ex-03/assets/133684710/050f5c44-7ec7-4f17-ba77-cc29823f6aa1)
```
sns.histplot(x = 'Sales',data = numeric_cols)
```
![image](https://github.com/Sudhar2303/ODD2023-DataScience-Ex-03/assets/133684710/bed3393c-427b-4fa9-a0bb-f068d558ae8a)
```
sns.countplot(x="Postal Code", data=numeric_cols)
```
![image](https://github.com/Sudhar2303/ODD2023-DataScience-Ex-03/assets/133684710/e0fc4c98-8309-43f4-a2c6-a50cf03b12b6)

# RESULT:
Thus we have read the given data and performed the univariate analysis with different types of plots.
