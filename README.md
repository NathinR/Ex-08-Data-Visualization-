# Ex-08-Data-Visualization-

## AIM
To Perform Data Visualization on the given dataset and save the data to a file. 

# Explanation
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature generation and selection techniques to all the features of the data set
### STEP 4
Apply data visualization techniques to identify the patterns of the data.
```
DEVELOPED BY: Nathin R
REGISTER NO: 212222230090
```
# CODE
```
import pandas as pd
df=pd.read_csv('/Superstore.csv',encoding='windows-1252')
df

df.isnull().sum()

import pandas as pd
import matplotlib.pyplot as plt
df.drop('Row ID',axis=1,inplace=True)
df.drop('Order ID',axis=1,inplace=True)
df.drop('Customer ID',axis=1,inplace=True)
df.drop('Customer Name',axis=1,inplace=True)
df.drop('Country',axis=1,inplace=True)
df.drop('Postal Code',axis=1,inplace=True)
df.drop('Product ID',axis=1,inplace=True)
df.drop('Product Name',axis=1,inplace=True)
df.drop('Order Date',axis=1,inplace=True)
df.drop('Ship Date',axis=1,inplace=True)
print("Updated dataset")
df

plt.figure(figsize=(12,10))
plt.title("Data with outliers")
df.boxplot()
plt.show()

cols=['Sales','Quantity','Discount','Profit']
q1=df[cols].quantile(0.75)
q3=df[cols].quantile(0.25)
iqr=q3-q1
low=q1+1.5*iqr
high=q3-1.5*iqr
df2=df[(df[cols]>low)&(df[cols]<high)]
plt.title("Data after removing outlier")
df2.boxplot()
plt.show()

import pandas as pd
import matplotlib.pyplot as plt
df2.drop(['Region','State','City','Segment','Ship Mode','Category','Sub-Category'],axis=1,inplace=True)
print("Updated dataset")
df2

#data visualization
#line plots
import seaborn as sns
sns.lineplot(x="Sub-Category",y="Sales",data=df,marker='o')
plt.title("Sub Categories vs Sales")
plt.xticks(rotation = 90)
plt.show()

sns.lineplot(x="Category",y="Profit",data=df,marker='o')
plt.xticks(rotation = 90)
plt.title("Categories vs Profit")
plt.show()

sns.lineplot(x="Region",y="Sales",data=df,marker='o')
plt.xticks(rotation = 90)
plt.title("Region area vs Sales")
plt.show()

sns.lineplot(x="Category",y="Discount",data=df,marker='o')
plt.title("Categories vs Discount")
plt.show()

sns.lineplot(x="Sub-Category",y="Quantity",data=df,marker='o')
plt.xticks(rotation = 90)
plt.title("Sub Categories vs Quantity")
plt.show()

#count plot
plt.figure(figsize=(10,7))
sns.countplot(x ='Segment', data = df,hue = 'Sub-Category')
sns.countplot(x ='Region', data = df,hue = 'Segment')
sns.countplot(x ='Category', data = df,hue='Discount')
sns.countplot(x ='Ship Mode', data = df,hue = 'Quantity')

#Histogram
sns.histplot(data = df,x = 'Region',hue='Ship Mode')
sns.histplot(data = df,x = 'Category',hue='Quantity')
sns.histplot(data = df,x = 'Sub-Category',hue='Category')
plt.xticks(rotation = 90)
plt.show()
sns.histplot(data = df,x = 'Quantity',hue='Segment')
plt.hist(data = df,x = 'Profit')
plt.show()

#bar plots
sns.barplot(x="Sub-Category",y="Sales",data=df)
plt.title("Sub Categories vs Sales")
plt.xticks(rotation = 90)
plt.show()

sns.barplot(x="Category",y="Profit",data=df)
plt.title("Categories vs Profit")
plt.show()

sns.barplot(x="Sub-Category",y="Quantity",data=df)
plt.title("Sub Categories vs Quantity")
plt.xticks(rotation = 90)
plt.show()

sns.barplot(x="Category",y="Discount",data=df)
plt.title("Categories vs Discount")
plt.show()

plt.figure(figsize=(12,7))
sns.barplot(x="State",y="Sales",data=df)
plt.title("States vs Sales")
plt.xticks(rotation = 90)
plt.show()

plt.figure(figsize=(25,8))
sns.barplot(x="State",y="Sales",hue="Region",data=df)
plt.title("State vs Sales based on Region")
plt.xticks(rotation = 90)
plt.show()

#KDE plot
sns.kdeplot(x="Profit", data = df,hue='Category')
sns.kdeplot(x="Sales", data = df,hue='Region')
sns.kdeplot(x="Quantity", data = df,hue='Segment')
sns.kdeplot(x="Discount", data = df,hue='Segment')

#violin plot
sns.violinplot(x="Profit",data=df)
sns.violinplot(x="Discount",y="Ship Mode",data=df)
sns.violinplot(x="Quantity",y="Ship Mode",data=df)
```
# OUPUT
![image](https://github.com/NathinR/Ex-08-Data-Visualization-/assets/118679646/22b5b7f3-8cf5-4c19-9487-bc37f68ccf98)
![image](https://github.com/NathinR/Ex-08-Data-Visualization-/assets/118679646/a5f91317-f3ac-4876-922c-46df5b4be991)
![image](https://github.com/NathinR/Ex-08-Data-Visualization-/assets/118679646/f1f38606-79fb-482b-84a7-ccf9175015e0)
![image](https://github.com/NathinR/Ex-08-Data-Visualization-/assets/118679646/26505730-b64e-461a-9f9f-70f5f799b0e1)
![image](https://github.com/NathinR/Ex-08-Data-Visualization-/assets/118679646/c6df9c9e-074d-46b6-9f7b-2f8d6d3c0228)
![image](https://github.com/NathinR/Ex-08-Data-Visualization-/assets/118679646/bda4fa16-2d82-4dec-a06b-2cdc78fed634)
![image](https://github.com/NathinR/Ex-08-Data-Visualization-/assets/118679646/2caa8ef2-8836-47a8-8ecb-dda09a7d5ecf)
![Screenshot 2023-05-30 211035](https://github.com/NathinR/Ex-08-Data-Visualization-/assets/118679646/61e76cc3-1c50-4464-b624-0620b3835dc6)
![image](https://github.com/NathinR/Ex-08-Data-Visualization-/assets/118679646/4c7422fe-b504-401f-8e1b-b48d8056a88f)
![image](https://github.com/NathinR/Ex-08-Data-Visualization-/assets/118679646/c5f2c7cf-477a-470d-863a-ef405c9cd011)
![image](https://github.com/NathinR/Ex-08-Data-Visualization-/assets/118679646/b7312b72-b157-448d-925b-6700e25e940a)
![image](https://github.com/NathinR/Ex-08-Data-Visualization-/assets/118679646/ffe6cff2-4598-4da0-b930-8b3ba8bdd36b)
![image](https://github.com/NathinR/Ex-08-Data-Visualization-/assets/118679646/fad8355c-0c2c-4c4e-ab5e-cd44fd84be36)
![image](https://github.com/NathinR/Ex-08-Data-Visualization-/assets/118679646/3ea4525a-f5c2-4777-8cdf-0a891391386f)
![image](https://github.com/NathinR/Ex-08-Data-Visualization-/assets/118679646/2d9c73c8-af71-42e2-98c7-acca89b70630)
![image](https://github.com/NathinR/Ex-08-Data-Visualization-/assets/118679646/08759218-854f-4981-9d27-ffa011477171)
![image](https://github.com/NathinR/Ex-08-Data-Visualization-/assets/118679646/534becd1-ee12-4180-a55a-c4aa1b326912)
![image](https://github.com/NathinR/Ex-08-Data-Visualization-/assets/118679646/fe5c18c4-dc6f-4e69-9497-2cbcc855d4fd)
![image](https://github.com/NathinR/Ex-08-Data-Visualization-/assets/118679646/b3de64a4-2380-4123-9435-487cdc7c0fd6)
![image](https://github.com/NathinR/Ex-08-Data-Visualization-/assets/118679646/e500f7e5-5fb1-4caf-a927-e220a8812a7b)
![image](https://github.com/NathinR/Ex-08-Data-Visualization-/assets/118679646/1c1d618f-e3ac-44f0-847f-fdab5001d769)
![image](https://github.com/NathinR/Ex-08-Data-Visualization-/assets/118679646/c24bb466-5740-41dd-bd44-7dc664dfe2d6)

# RESULT:
Thus the experiment executed sucessfully
