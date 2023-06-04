# Ex-09-Data-Visualization-

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
import pandas as pd

import seaborn as sns

import matplotlib.pyplot as plt

df = sns.load_dataset("tips")

df.head()

df.isnull().sum()

plt.figure(figsize=(5,5))

plt.title("Data with Outliers")

df.boxplot()

plt.show()

plt.figure(figsize=(5,5))

cols = ['size','tip','total_bill']

Q1 = df[cols].quantile(0.25)

Q3 = df[cols].quantile(0.75)

IQR = Q3 - Q1

df = df[~((df[cols] < (Q1 - 1.5 * IQR)) |(df[cols] > (Q3 + 1.5 * IQR))).any
(axis=1)]

plt.title("Dataset after removing outliers")

df.boxplot()

plt.show()

sns.barplot(x=df['day'], y=df['total_bill'])

plt.title("Highest Total Bill Amount by day")

plt.show()

sns.boxplot(x=df['smoker'], y=df['tip'],hue=df['smoker'])

plt.title("Average Tip Amount given by smokers and non-smokers")


plt.show()

df["tip_percent"] = df["tip"] / df["total_bill"]

sns.barplot(x=df['size'],y=df['tip_percent'],data=df)

plt.title("Tip Percentage by Dining Party Size")

plt.show()

sns.barplot(x=df['sex'], y=df['tip'])

plt.title("Highest tips based on gender")

plt.show()

sns.barplot(x=df['day'],y=df['total_bill'])

plt.title("Total bill amount by day of the week")

plt.show()

sns.histplot(data=df, x="total_bill", hue="time", element="step", 
stat="density")

plt.title("Distribution of Total Bill Amounts by Time of Day")

plt.show()

sns.barplotdata=df,(x=df['size'],y=df['total_bill'])

plt.title("Average Total Bill Amount by Dining Party Size")

plt.show()

sns.violinplot(x="day", y="tip", data=df)

plt.title("Tip Amount by Day of Week")

plt.show()

sns.barplot(x="time", y="tip", data=df)

plt.title("Tip Amount by Time of Day")

plt.show()

sns.scatterplot(x="total_bill", y="tip", data=df)

plt.title("Correlation between Tip Amount and Total Bill Amount")

plt.show()
# OUPUT

