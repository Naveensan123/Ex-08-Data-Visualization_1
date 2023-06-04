# Ex-09-Data-Visualization-

## AIM:
To Perform Data Visualization on a complex dataset and save the data to a file. 

# Explanation:
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# ALGORITHM:
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature generation and selection techniques to all the features of the data set
### STEP 4
Apply data visualization techniques to identify the patterns of the data.


# CODE:
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
# OUPUT:
![2023-06-04 (1)](https://github.com/Naveensan123/Ex-08-Data-Visualization_1/assets/95761973/be9cccab-04bf-4080-9b2b-2cb13827f7cb)
![2023-06-04 (2)](https://github.com/Naveensan123/Ex-08-Data-Visualization_1/assets/95761973/965ac6aa-5b41-42c4-8fc7-ca6d3c43f4e0)
![2023-06-04 (3)](https://github.com/Naveensan123/Ex-08-Data-Visualization_1/assets/95761973/f91bfc62-cf6e-4e53-b37a-4c7252a688e0)
![2023-06-04 (4)](https://github.com/Naveensan123/Ex-08-Data-Visualization_1/assets/95761973/e036689a-ad40-415c-8a3c-735c88aa3058)
![2023-06-04 (5)](https://github.com/Naveensan123/Ex-08-Data-Visualization_1/assets/95761973/0bba9b5b-04f9-4d6b-9236-cd9c6cea828f)
![2023-06-04 (6)](https://github.com/Naveensan123/Ex-08-Data-Visualization_1/assets/95761973/d46a0f3d-54bd-4a66-a095-f218cfd1d4c1)
![2023-06-04 (7)](https://github.com/Naveensan123/Ex-08-Data-Visualization_1/assets/95761973/d7fdd9b6-a251-4677-a0e8-c635c825527a)
![2023-06-04 (8)](https://github.com/Naveensan123/Ex-08-Data-Visualization_1/assets/95761973/8852c2fa-7480-4ade-a9b3-52892d5506ef)
![2023-06-04 (9)](https://github.com/Naveensan123/Ex-08-Data-Visualization_1/assets/95761973/8e08108b-c819-4d2d-ac62-cc9925c0fd89)
![2023-06-04](https://github.com/Naveensan123/Ex-08-Data-Visualization_1/assets/95761973/f71adda9-eb2d-4db9-9179-65d1e0693b4b)

