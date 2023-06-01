# Ex-08-Data-Visualization-

## AIM :

To Perform Data Visualization on the given dataset and save the data to a file. 

## Explanation :

Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

## ALGORITHM :

### STEP 1 :

Read the given Data

### STEP 2 :

Clean the Data Set using Data Cleaning Process

### STEP 3 :

Apply Feature generation and selection techniques to all the features of the data set
 
### STEP 4 :

Apply data visualization techniques to identify the patterns of the data.

## CODE : 

##### DEVELOPED BY : Rakesh J.S
##### REG NO : 212222230115

### Reading the given dataset :
``` python
import pandas as pd
df=pd.read_csv("/content/Superstore.csv",encoding='unicode_escape')

df.head()
```
### Data Visualization using Seaborn :
``` python
import seaborn as sns
from matplotlib import pyplot as plt
```
### 1.Line Plot :
``` python
plt.figure(figsize=(9,6))
sns.lineplot(x="Segment",y="Region",data=df,marker='o')
plt.xticks(rotation = 90)

sns.lineplot(x='Ship Mode',y='Category', hue ="Segment",data=df)

sns.lineplot(x="Category",y="Sales",data=df,marker='o')
```
### 2.Scatterplot :
``` python

sns.scatterplot(x='Category',y='Sub-Category',data=df)

sns.scatterplot(x='Category', y='Sub-Category', hue ="Segment",data=df)

plt.figure(figsize=(10,7))
sns.scatterplot(x="Region",y="Sales",data=df)
plt.xticks(rotation = 90)
```

### 3.Boxplot :
``` python

sns.boxplot(x="Sub-Category",y="Discount",data=df)

sns.boxplot( x="Profit", y="Category",data=df)
```
### 4.Violin Plot :
``` python

sns.violinplot(x="Profit",data=df)
```
### 5.Barplot :
``` python
sns.barplot(x="Sub-Category",y="Sales",data=df)
plt.xticks(rotation = 90)

sns.barplot(x="Category",y="Sales",data=df)
plt.xticks(rotation = 90)
```
### 6.Pointplot :
``` python
sns.pointplot(x=df["Quantity"],y=df["Discount"])
```
### 7.Count plot :
``` python
sns.countplot(x="Category",data=df)

sns.countplot(x="Sub-Category",data=df)
```
### 8.Histogram :
``` python
sns.histplot(data=df,x ='Ship Mode',hue='Sub-Category')
``` 
### 9.KDE Plot :
``` python
sns.kdeplot(x="Profit", data = df,hue='Category')
```
### Data Visualization Using MatPlotlib :

### 1.Plot :
``` python
plt.plot(df['Category'], df['Sales'])
plt.show()
```

### 2.Heatmap :
``` python
df.corr()
plt.subplots(figsize=(12,7))
sns.heatmap(df.corr(),annot=True)
```
### 3.Piechart :
``` python
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
### 4.Histogram :
``` python
plt.hist(df["Sub-Category"],facecolor="peru",edgecolor="blue",bins=10)
plt.show()
```
###  5.Bargraph :
``` python
plt.bar(df.index,df['Category'])
plt.show()
```
### 6.Scatterplot :
``` python
plt.scatter(df["Region"],df["Profit"], c ="blue")
plt.show() 
```
### 7.Boxplot :
``` python
plt.boxplot(x="Sales",data=df)
plt.show()
```
## OUTPUT :

### Reading the given dataset :

![Screenshot 2023-05-17 211907](https://github.com/Abrinnisha6/Ex-08-Data-Visualization-/assets/118889454/c3aaf323-2bf6-4d0d-bdad-2b89971e062d)

### Data Visualization Using Seaborn :

### 1.Line Plot :

![Screenshot 2023-05-17 212031](https://github.com/Abrinnisha6/Ex-08-Data-Visualization-/assets/118889454/4d819551-7063-4d35-993f-d101da03ce0c)

![Screenshot 2023-05-17 212111](https://github.com/Abrinnisha6/Ex-08-Data-Visualization-/assets/118889454/a79ecb41-6d84-4a59-983a-1b73a59d3680)

![Screenshot 2023-05-17 212120](https://github.com/Abrinnisha6/Ex-08-Data-Visualization-/assets/118889454/bd33b300-72fa-4614-8ece-fd9c27c00520)


### 2.Scatterplot :
![Screenshot 2023-05-17 212705](https://github.com/Abrinnisha6/Ex-08-Data-Visualization-/assets/118889454/fadc964d-48bc-4732-bb3e-ea0058b23ac4)

![Screenshot 2023-05-17 212714](https://github.com/Abrinnisha6/Ex-08-Data-Visualization-/assets/118889454/fa395176-939d-4527-b8ce-dc50ac140ffa)

![Screenshot 2023-05-17 213147](https://github.com/Abrinnisha6/Ex-08-Data-Visualization-/assets/118889454/3f416c64-15ec-453e-afba-7755a4b99b06)

### 3.Boxplot :

![Screenshot 2023-05-17 213158](https://github.com/Abrinnisha6/Ex-08-Data-Visualization-/assets/118889454/ba5be9c1-edf3-4ada-864f-8156a74c6dde)

![Screenshot 2023-05-17 213208](https://github.com/Abrinnisha6/Ex-08-Data-Visualization-/assets/118889454/9da4c3b3-6554-4dd3-80b8-d4ce3ba7dc6a)

### 4.Violin Plot :

![Screenshot 2023-05-17 213353](https://github.com/Abrinnisha6/Ex-08-Data-Visualization-/assets/118889454/51d5f8fe-0762-482b-a36e-09fec68dd789)

### 5.Barplot :

![Screenshot 2023-05-17 213610](https://github.com/Abrinnisha6/Ex-08-Data-Visualization-/assets/118889454/da3b0ff1-ae32-4d9e-bca9-92f682544e6f)

![Screenshot 2023-05-17 213620](https://github.com/Abrinnisha6/Ex-08-Data-Visualization-/assets/118889454/c83adc3e-205b-45be-9f76-bc3936131729)

### 6.Pointplot :

![Screenshot 2023-05-17 213745](https://github.com/Abrinnisha6/Ex-08-Data-Visualization-/assets/118889454/35e6384c-f912-45a0-bba8-6ec63057a59f)

### 7.Count plot :

![Screenshot 2023-05-17 213840](https://github.com/Abrinnisha6/Ex-08-Data-Visualization-/assets/118889454/fc8a812b-3dbc-42db-b19f-58d26bc6fdf9)

![Screenshot 2023-05-17 213849](https://github.com/Abrinnisha6/Ex-08-Data-Visualization-/assets/118889454/aaf49a47-9e7d-4f43-bf61-a2eb5d0bda21)

### 8.Histogram :

![Screenshot 2023-05-17 213857](https://github.com/Abrinnisha6/Ex-08-Data-Visualization-/assets/118889454/17bc785f-fe2d-4f7e-9a59-a6631af36f81)

### 9.KDE Plot :
![Screenshot 2023-05-17 213907](https://github.com/Abrinnisha6/Ex-08-Data-Visualization-/assets/118889454/5ab4ca53-f31a-4060-a684-38ade896ad0a)

### Data Visualization Using Matplotlib :

### 1.Plot:

![Screenshot 2023-05-17 214140](https://github.com/Abrinnisha6/Ex-08-Data-Visualization-/assets/118889454/eb135463-0275-4ebf-a226-b2539049fea1)

### 2.Heatmap :

![Screenshot 2023-05-17 214508](https://github.com/Abrinnisha6/Ex-08-Data-Visualization-/assets/118889454/265db0eb-13a3-43ef-8a4e-f7a4de10d28c)

### 3.Piechart :
![Screenshot 2023-05-17 214558](https://github.com/Abrinnisha6/Ex-08-Data-Visualization-/assets/118889454/b13fd0bb-4b90-4fe3-96ea-c954ec45a1c6)

![Screenshot 2023-05-17 214621](https://github.com/Abrinnisha6/Ex-08-Data-Visualization-/assets/118889454/7b5111cf-7d72-4eb4-950c-1628a0f3bb38)

### 4..Histogram :

![Screenshot 2023-05-17 215021](https://github.com/Abrinnisha6/Ex-08-Data-Visualization-/assets/118889454/d9b78448-45c3-4262-a1b5-42b3b1ae2669)

### 5.Bargraph :
![Screenshot 2023-05-17 215101](https://github.com/Abrinnisha6/Ex-08-Data-Visualization-/assets/118889454/71cce4d3-937e-45eb-a131-b70f9b9a3f72)

### 6.Scatterplot :
![Screenshot 2023-05-17 215116](https://github.com/Abrinnisha6/Ex-08-Data-Visualization-/assets/118889454/5ad5c079-3e39-4dad-8757-ad3caef4d701)

### 7.Boxplot :

![Screenshot 2023-05-17 215131](https://github.com/Abrinnisha6/Ex-08-Data-Visualization-/assets/118889454/782e54c3-dfd0-4d44-9f04-55bde465e779)

## Result :

Hence,Data Visualization is applied on the complex dataset using libraries like Seaborn and Matplotlib successfully and the data is saved to file.
