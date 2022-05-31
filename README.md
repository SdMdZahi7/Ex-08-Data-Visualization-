# Ex-08-Data-Visualization-

## AIM
To Perform Data Visualization on a complex dataset and save the data to a file. 

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
# CODE
~~~
Developed by:SYED MUHAMMED ZAHI
Reg no:212221230114
~~~
~~~
import pandas as pd
import numpy as np
df=pd.read_csv("Superstore.csv")

df.head()

#Data Visualization using Seaborn

import seaborn as sns
from matplotlib import pyplot as plt

#1.Line plot

plt.figure(figsize=(8,5))
sns.lineplot(x="Segment",y="Region",data=df,marker='o')
plt.xticks(rotation = 90)
sns.lineplot(x='Ship Mode',y='Category', hue ="Segment",data=df)
sns.lineplot(x="Category",y="Sales",data=df,marker='o')

#2.Scatterplot

sns.scatterplot(x='Category',y='Sub-Category',data=df)
sns.scatterplot(x='Category', y='Sub-Category', hue ="Segment",data=df)
plt.figure(figsize=(10,7))
sns.scatterplot(x="Region",y="Sales",data=df)
plt.xticks(rotation = 90)

#3.Boxplot

sns.boxplot(x="Sub-Category",y="Discount",data=df)
sns.boxplot( x="Profit", y="Category",data=df)

#4.Barplot

sns.barplot(x="Sub-Category",y="Sales",data=df)
plt.xticks(rotation = 90)
sns.barplot(x="Category",y="Sales",data=df)
plt.xticks(rotation = 90)

#5.Pointplot

sns.pointplot(x=df["Quantity"],y=df["Discount"])

#6.Count plot

sns.countplot(x="Category",data=df)
sns.countplot(x="Sub-Category",data=df)

#7.Histogram

sns.histplot(data=df,x ='Ship Mode',hue='Sub-Category')

#8.KDE Plot

sns.kdeplot(x="Profit", data = df,hue='Category')

#Data Visualization Using MatPlotlib

#1.Plot

plt.plot(df['Category'], df['Sales'])
plt.show()

#2.Heatmap

df.corr()
plt.subplots(figsize=(12,7))
sns.heatmap(df.corr(),annot=True)

#3.Piechart

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

#4.Histogram

plt.hist(df["Sub-Category"],facecolor="peru",edgecolor="blue",bins=10)
plt.show()

#5.Bargraph

plt.bar(df.index,df['Category'])
plt.show()

#6.Scatterplot

plt.scatter(df["Region"],df["Profit"], c ="blue")
plt.show()              

#7.Boxplot

plt.boxplot(x="Sales",data=df)
plt.show()
~~~


# OUTPUT
![image](https://user-images.githubusercontent.com/94187572/171085610-553c0f66-7463-44af-a5ad-c82be54c176d.png)
### Data Visualization Using Seaborn:
![image](https://user-images.githubusercontent.com/94187572/171085674-712ab4d8-cb98-4f35-9ade-8b3ba062b532.png)
![image](https://user-images.githubusercontent.com/94187572/171085695-e5cf8239-d0b9-4779-a55a-c8efdbc23ed5.png)
![image](https://user-images.githubusercontent.com/94187572/171085709-508abd39-089d-47fb-b27a-73ae9ec607d2.png)
![image](https://user-images.githubusercontent.com/94187572/171085731-460ee430-6533-43e5-9391-afe6a0d01a9c.png)
![image](https://user-images.githubusercontent.com/94187572/171085742-3d555cbc-be3f-4514-8a2b-4c388abee8ac.png)
![image](https://user-images.githubusercontent.com/94187572/171085796-69cc521c-527e-4139-b54c-b82f4f5af5da.png)
![image](https://user-images.githubusercontent.com/94187572/171085926-5ed0f0a0-1b26-44ce-a14c-2fffdb5c8c1d.png)
![image](https://user-images.githubusercontent.com/94187572/171085941-e6349815-b4ab-4aa9-ba92-aff9b3cb0ce6.png)
![image](https://user-images.githubusercontent.com/94187572/171085965-ed0423ac-6fa6-472c-b082-798f07410e35.png)

### Data Visualization Using Matplotlib:
![image](https://user-images.githubusercontent.com/94187572/171086036-1a625496-e71f-4e90-87f6-f0171d067cfd.png)
![image](https://user-images.githubusercontent.com/94187572/171086061-7b93c8fc-687f-4394-afde-75068d2311eb.png)
![image](https://user-images.githubusercontent.com/94187572/171086075-0a366fba-8f6d-47f4-b30c-a78c77be4e66.png)
![image](https://user-images.githubusercontent.com/94187572/171086083-03534d62-e488-4107-896e-07570f11f19f.png)
![image](https://user-images.githubusercontent.com/94187572/171086098-bff4519d-75fb-4e76-906a-4c4c3b003b6b.png)
![image](https://user-images.githubusercontent.com/94187572/171086124-df611c4a-126f-4af8-8011-3a2a6ea46a3f.png)
![image](https://user-images.githubusercontent.com/94187572/171086148-9da290c6-9c34-4ccf-b3e4-5b78db3b7a45.png)

### RESULT:
Hence, Data Visualization is applied on the complex dataset using libraries like Seaborn and Matplotlib successfully and the data is saved to file.


