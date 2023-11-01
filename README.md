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
