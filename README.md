# Ex-08-Data-Visualization-

## AIM
To Perform Data Visualization on a complex dataset and save the data to a file.

## Explanation
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

## ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature generation and selection techniques to all the features of the data set
### STEP 4
Apply data visualization techniques to identify the patterns of the data.

## CODE
### inserting libraries
```
import pandas as pd
import seaborn as sns
from matplotlib import pyplot as plt
df=pd.read_csv("/content/Superstore - Superstore.csv (1).csv")
df.head()
df.info()
df.isnull().sum()
```
###  Data Visualization using seaborn
#### lineplot
```
sns.lineplot(x="Category",y="Sales",data=df,marker='o')

sns.lineplot(x='Ship Mode', y='Category',hue="Segment",data=df)
plt.title("Multiline Plot")
plt.show()
```
#### barplot
```
sns.barplot(x="Category",y="Sales",data=df)

sns.barplot(x='Region', y='Sales', data=df,palette='Set1')
plt.title("Sales in different Regions")
plt.show()
```
#### scatterplot
```
sns.scatterplot(x='Category',y='Sub-Category',data=df)
plt.title("Scatterplot")
plt.show()

sns.scatterplot(x='Category',y='Sub-Category',hue='Segment',data=df)
plt.show()
```
#### boxplot
```
sns.boxplot(x="Sub-Category",y="Discount",data=df)
plt.xticks(rotation=90)

sns.boxplot( x="Profit", y="Category",data=df)
```
#### pointplot
```
sns.pointplot(x=df["Quantity"],y=df["Discount"])
```
#### violinplot
```
sns.violinplot(x="Profit",data=df)
```
#### countplot
```
sns.countplot(x="Category",data=df)

sns.countplot(x="Sub-Category",data=df)
plt.xticks(rotation=90)
 ```
#### histogram
```
sns.histplot(data=df,x ='Ship Mode',hue='Sub-Category')
```
#### KDEplot
```
sns.kdeplot(x="Discount", data = df,hue='Category')
```
### Data Visualization using Matplotlib
#### plot
```
plt.plot(df['Region'], df['Sales'])
plt.show()
```
#### Heatmap
```
df.corr()
plt.subplots(figsize=(12,7))
sns.heatmap(df.corr(),annot=True)
```
#### piechart
```
df1=df.groupby(by=["Ship Mode"]).sum()
labels=[]
for i in df1.index:
    labels.append(i)
colors=sns.color_palette("bright")
plt.pie(df1["Sales"],labels=labels,autopct="%0.0f%%")
plt.show()

df3=df.groupby(by=["Category"]).sum()
labels=[]
for i in df3.index:
    labels.append(i) 
plt.figure(figsize=(8,8))
colors = sns.color_palette('pastel')
plt.pie(df3["Profit"],colors = colors,labels=labels, autopct = '%0.0f%%')
plt.show()
```
#### Histogram
```
plt.hist(df["Sub-Category"],facecolor="peru",edgecolor="black",bins=10)
plt.xticks(rotation =90)
plt.show()
```
#### barplot
```
plt.bar(df['Category'],df.index)
plt.show()
```
#### scatterplot
```
plt.scatter(df["Region"],df["Profit"], c ="red")
plt.show() 
```
#### boxplot
```
plt.boxplot(x="Sales",data=df)
plt.show()
```
# OUTPUT

#### Initial data:
![image](https://github.com/Yuvaranithulasingam/ODD2023-Datascience-Ex-08/assets/121418522/0d5ba5f2-444f-46af-aeee-f6732b7d8290)

#### Data information:
![image](https://github.com/Yuvaranithulasingam/ODD2023-Datascience-Ex-08/assets/121418522/bbf5145e-72ef-4ec0-abaa-1f5fdf7dda31)

#### Null values:
![image](https://github.com/Yuvaranithulasingam/ODD2023-Datascience-Ex-08/assets/121418522/248e390a-386a-4bac-aa93-fe04edc0b152)

### Data visualization using Seaborn

#### Lineplot:
![image](https://github.com/Yuvaranithulasingam/ODD2023-Datascience-Ex-08/assets/121418522/b8f46101-7341-403f-a5e4-377a241442ba)

![image](https://github.com/Yuvaranithulasingam/ODD2023-Datascience-Ex-08/assets/121418522/712d4eed-6dad-4a27-9b0b-01d4eaf8b3d4)

#### Barchart:
![image](https://github.com/Yuvaranithulasingam/ODD2023-Datascience-Ex-08/assets/121418522/1ae3c2c6-0ea8-4606-a8b0-4710616c49c5)

![image](https://github.com/Yuvaranithulasingam/ODD2023-Datascience-Ex-08/assets/121418522/bec47d50-f269-4dd7-9e2b-86338bddf814)

#### Scatterplot:

![image](https://github.com/Yuvaranithulasingam/ODD2023-Datascience-Ex-08/assets/121418522/9109b9d6-3703-4796-9615-e9b9110d44c8)

![image](https://github.com/Yuvaranithulasingam/ODD2023-Datascience-Ex-08/assets/121418522/5ad3e3a2-4057-410b-ac42-08f3d1131416)

#### Boxplot:

![image](https://github.com/Yuvaranithulasingam/ODD2023-Datascience-Ex-08/assets/121418522/88106430-bfb4-4fa9-92aa-74bdc60a8c8d)

![image](https://github.com/Yuvaranithulasingam/ODD2023-Datascience-Ex-08/assets/121418522/08f2de62-e096-4a6c-8f1f-8c6c2d7ff690)

#### Pointplot:
![image](https://github.com/Yuvaranithulasingam/ODD2023-Datascience-Ex-08/assets/121418522/af9f7bf3-617f-4743-b88f-484a7e46c41a)

#### Violinplot:
![image](https://github.com/Yuvaranithulasingam/ODD2023-Datascience-Ex-08/assets/121418522/92a139bf-d99b-474f-a517-f51b1ebdd542)

#### Countplot:
![image](https://github.com/Yuvaranithulasingam/ODD2023-Datascience-Ex-08/assets/121418522/47c060f3-c05a-4c7c-914a-dbd88d85ae78)

#### Histogram:
![image](https://github.com/Yuvaranithulasingam/ODD2023-Datascience-Ex-08/assets/121418522/c39bd74a-a42f-4f7c-943b-78c8fee66961)

![image](https://github.com/Yuvaranithulasingam/ODD2023-Datascience-Ex-08/assets/121418522/ddbbf630-5680-4179-938d-b56e07eb26a0)

#### KDEplot:
![image](https://github.com/Yuvaranithulasingam/ODD2023-Datascience-Ex-08/assets/121418522/0e39ae85-c901-4508-a3a7-8b91c34edf95)

### Data visualization using Matplot

#### Plot:
![image](https://github.com/Yuvaranithulasingam/ODD2023-Datascience-Ex-08/assets/121418522/23304f05-423f-463f-81ea-4d09076637c6)

#### Heatmap:
![image](https://github.com/Yuvaranithulasingam/ODD2023-Datascience-Ex-08/assets/121418522/07ff67be-f7ae-4eaa-9520-c926705583b5)

#### Piechart:
![image](https://github.com/Yuvaranithulasingam/ODD2023-Datascience-Ex-08/assets/121418522/99beb450-b262-4a3e-a7d1-d88980c78f17)

![image](https://github.com/Yuvaranithulasingam/ODD2023-Datascience-Ex-08/assets/121418522/2ee148e7-cc79-4039-bdf0-4fe0555b81d1)

#### Histogram:
[image](https://github.com/Yuvaranithulasingam/ODD2023-Datascience-Ex-08/assets/121418522/5d20a2ab-09b5-4ed0-ab0d-1a5e013a5b6a)

#### Barplot:
![image](https://github.com/Yuvaranithulasingam/ODD2023-Datascience-Ex-08/assets/121418522/cb5899b5-a43b-40af-884c-5bd7056c3f1e)

#### Scatterplot:
![image](https://github.com/Yuvaranithulasingam/ODD2023-Datascience-Ex-08/assets/121418522/afeb8364-a4da-457f-916e-d326f92ef741)

#### Boxplot:
![image](https://github.com/Yuvaranithulasingam/ODD2023-Datascience-Ex-08/assets/121418522/ee388fcb-f049-4aca-9f9b-a191ff35e6fc)

## Result :
Hence,Data Visualization is applied on the complex dataset using libraries like Seaborn and Matplotlib successfully and the data is saved to file.
