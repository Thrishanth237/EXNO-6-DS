# EXNO-6-DS-DATA VISUALIZATION USING SEABORN LIBRARY

# Aim:
  To Perform Data Visualization using seaborn python library for the given datas.

# EXPLANATION:
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# Algorithm:
STEP 1:Include the necessary Library.

STEP 2:Read the given Data.

STEP 3:Apply data visualization techniques to identify the patterns of the data.

STEP 4:Apply the various data visualization tools wherever necessary.

STEP 5:Include Necessary parameters in each functions.

# Coding and Output:

 ```
import seaborn as sns
import matplotlib.pyplot as plt
import pandas as pd
import numpy as np
x = [1, 2, 3, 4, 5]
y = [3, 6, 2, 7, 1]
sns.lineplot(x=x,y=y)
```
![download](https://github.com/user-attachments/assets/0b95a3f0-242b-47bc-8ed3-7733cd910d38)

```
df = sns.load_dataset("tips")
df
```

![image](https://github.com/user-attachments/assets/9dd6bf8f-8653-473e-9544-06f874efee3a)

```
sns.lineplot(x="total_bill",y="tip", data=df, hue="sex", linestyle='solid', legend="auto")
```
![download](https://github.com/user-attachments/assets/dae7d7e7-c2b8-4aca-bad3-09dc5420864f)

```
x=[1, 2, 3, 4, 5]
y1=[3, 5, 2, 6, 1]
y2=[1, 6, 4, 3, 8]
y3=[5, 2, 7, 1, 4]

sns.lineplot(x=x, y=y1)
sns.lineplot(x=x, y=y2)
sns.lineplot(x=x, y=y3)
plt.title("Multi-Line Plot")
plt.xlabel('X Label')
plt.ylabel("Y Label")
```
![download](https://github.com/user-attachments/assets/b2eae518-a018-468a-a5d5-f9bacb281dea)

```
tips=sns.load_dataset('tips')
avg_total_bill = tips.groupby('day')['total_bill'].mean()
avg_tip = tips.groupby('day')['tip'].mean()
plt.figure(figsize=(8, 6))
p1 = plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill')
p2 = plt.bar(avg_tip.index, avg_tip, bottom=avg_total_bill, label='Tip')
plt.xlabel('Day of the Week')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Day')
plt.legend()
```
![download](https://github.com/user-attachments/assets/db8d34b0-eb58-48a4-a612-551acbabfb02)

```
avg_total_bill = tips.groupby('time')['total_bill'].mean()
avg_tip=tips.groupby('time') ['tip'].mean()
p1= plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill', width=0.4)
p2 = plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label='Tip', width=0.4)
```
![download](https://github.com/user-attachments/assets/1b7116ab-c235-4351-8fc3-0de253cbe9ed)

```
years=range(2000, 2012)
apples=[0.895, 0.91, 0.919, 0.926, 0.929, 0.931, 0.934, 0.936, 0.937, 0.9375, 0.9372, 0.939]
oranges = [0.962, 0.941, 0.930, 0.923, 0.918, 0.908, 0.907, 0.904, 0.901, 0.898, 0.9, 0.896, ]
plt.bar(years, apples)
plt.bar(years, oranges, bottom=apples)
```
![download](https://github.com/user-attachments/assets/f20680cd-69fc-4933-808f-94e957b5abb8)

```
import seaborn as sns
dt= sns.load_dataset('tips')
sns.barplot(x='day', y='total_bill', hue='sex', data=dt, palette='Set1')
plt.xlabel('Day of the Week')
plt.ylabel("Total Bill")
plt.title('Total Bill by Day and Gender')
```
![download](https://github.com/user-attachments/assets/3c1b83d6-5287-43f0-819d-0d22281bdd9c)

```
tit=pd.read_csv("/content/titanic_dataset.csv")
tit
```
![image](https://github.com/user-attachments/assets/fd3669ce-fe34-4090-b1d1-d44e46d680fb)

```
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=tit, palette='rainbow')
plt.title("Fare of Passenger by Embarked Town")
```
![download](https://github.com/user-attachments/assets/94de0776-1b37-4d19-8bd8-7fba574307fa)


```
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=tit, palette='rainbow', hue='Pclass')
plt.title("Fare of Passenger by Embarked Town, Divided by Class")
```
![download](https://github.com/user-attachments/assets/c635722a-3a7b-400f-a585-7ee90a727985)


```
tips=sns.load_dataset('tips')
sns.scatterplot(x='total_bill', y='tip', hue='sex', data=tips)
plt.xlabel('Total Bill')
plt.ylabel("Tip Amount")
plt.title('Scatter Plot of Total Bill vs. Tip Amount')
```

![download](https://github.com/user-attachments/assets/ab3f6d1a-995c-4d4f-b35c-6702b31f6a6b)



```
num_var = np.random.randn(1000)
num_var=pd.Series(num_var, name = "Numerical variable")
num_var
```
![image](https://github.com/user-attachments/assets/350f4251-e990-4d2e-8089-16f1c0a863dc)


```
sns.histplot(data = num_var, kde = True)
```
![download](https://github.com/user-attachments/assets/a2ba010b-f9c4-46f8-99de-b61f3288f80b)


```
df=pd.read_csv("/content/titanic_dataset.csv")
sns.histplot(data=df,x="Pclass", hue="Survived", kde=True)
```
![download](https://github.com/user-attachments/assets/ada72c97-790d-4876-8aa8-506ad43dc000)

```
tips=sns.load_dataset('tips')
sns.boxplot(x=tips['day'], y=tips ['total_bill'], hue=tips['sex'])
```
![download](https://github.com/user-attachments/assets/2e3843a1-480b-432d-8bc0-eed00c013be8)

```
sns.boxplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, boxprops={"facecolor": "lightblue", "edgecolor": "darkblue"},
whiskerprops={"color": "black", "linestyle": "--", "linewidth": 1.5}, capprops={"color": "black", "linestyle": "--", "linewidth": 1.5})
```

![download](https://github.com/user-attachments/assets/90864bf9-3a19-4d64-a45b-acf2442e663a)

```
sns.violinplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, palette="Set3", inner="quartile")
plt.xlabel("Day of the Week")
plt.ylabel("Total Bill")
plt.title("Violin Plot of Total Bill by Day and Smoker Status")
```
![download](https://github.com/user-attachments/assets/c0a347f0-1969-4997-a953-3aa2d09f1f61)

```
mart=pd.read_csv("/content/titanic_dataset.csv")
mart
```
![image](https://github.com/user-attachments/assets/fec14f12-b709-400d-8df8-14125e8d214c)

```
mart=mart[['PassengerId', 'Survived', 'Age', 'Name', 'Ticket', 'Embarked']]
mart.head(10)
```
![image](https://github.com/user-attachments/assets/37f92f8e-23e0-4f94-8ee4-5df5b33681b2)
```
sns.kdeplot(data=mart,x='PassengerId')
```
![download](https://github.com/user-attachments/assets/e46510aa-bff0-4393-8fb5-8f6d30988e21)

```
sns.kdeplot(data=mart,x='Age')
```
![download](https://github.com/user-attachments/assets/fe17f0f8-b284-41ad-936d-50ad9850093b)


```
sns.kdeplot(data=mart)
```
![download](https://github.com/user-attachments/assets/38573b66-94b8-4c73-97e8-517ec597ffc3)


```
sns.kdeplot(data=mart,x='PassengerId',hue='Survived',multiple='stack')
```



![download](https://github.com/user-attachments/assets/0df96545-0ed2-4fed-bc25-f7a63b1d1323)

```
sns.kdeplot(data=mart,x='PassengerId',y='Survived')
```
![download](https://github.com/user-attachments/assets/2bfac563-7279-4a8b-973d-143381a71a56)

```
data = np.random.randint(low = 1, high = 100, size = (10,10))
hm=sns.heatmap(data=data,annot=True)
```
![download](https://github.com/user-attachments/assets/7ae5118a-1130-4faf-bb21-0f0be7c4c30f)

```
hm=sns.heatmap(data=data)
```
![download](https://github.com/user-attachments/assets/3c10b08f-44aa-4fc7-9675-a1189e353ba3)





# Result:
Thus, the Data Visualization using seaborn python library for the given data is implemented successfully
