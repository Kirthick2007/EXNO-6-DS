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
# NAME : KIRTHICK SHA R
# REG : 212224230124

```python
import seaborn as sns
import matplotlib.pyplot as plt
import pandas as pd
import numpy as np
x = [1, 2, 3, 4, 5]
y = [3, 6, 2, 7, 1]
sns.lineplot(x=x,y=y)
```
![image](https://github.com/user-attachments/assets/066d5a43-d381-4d6b-ab25-6518def2194f)

```python
df = sns.load_dataset("tips")
df
```
![image](https://github.com/user-attachments/assets/6fcb4f82-682a-4c9c-b8e0-126504179f45)

```python
sns.lineplot(x="total_bill",y="tip", data=df, hue="sex", linestyle='solid', legend="auto")

```
![image](https://github.com/user-attachments/assets/ca16d946-0f49-41ca-b810-e0844ea52aeb)

```python
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
![image](https://github.com/user-attachments/assets/a240f8ec-3a2b-42b1-9baa-119ee82525af)

```python
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
![image](https://github.com/user-attachments/assets/2d6dcad6-607a-4ecb-802f-1f2bc6519a6f)

```python
avg_total_bill = tips.groupby('time')['total_bill'].mean()
avg_tip=tips.groupby('time') ['tip'].mean()
p1= plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill', width=0.4)
p2 = plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label='Tip', width=0.4)
```
![image](https://github.com/user-attachments/assets/1f0bb7e7-7256-4f6d-b6bf-316e95a23bc8)

```python
years=range(2000, 2012)
apples=[0.895, 0.91, 0.919, 0.926, 0.929, 0.931, 0.934, 0.936, 0.937, 0.9375, 0.9372, 0.939]
oranges = [0.962, 0.941, 0.930, 0.923, 0.918, 0.908, 0.907, 0.904, 0.901, 0.898, 0.9, 0.896, ]
plt.bar(years, apples)
plt.bar(years, oranges, bottom=apples)
```

![image](https://github.com/user-attachments/assets/77a7bf93-3c50-4554-b1ba-a84e6cb6b72a)

```python
import seaborn as sns
dt= sns.load_dataset('tips')
sns.barplot(x='day', y='total_bill', hue='sex', data=dt, palette='Set1')
plt.xlabel('Day of the Week')
plt.ylabel("Total Bill")
plt.title('Total Bill by Day and Gender')
```

![image](https://github.com/user-attachments/assets/74df136f-9a8e-4524-9bf0-aac06f431b3d)

```python
tit=pd.read_csv("/content/titanic_dataset.csv")
tit
```

![image](https://github.com/user-attachments/assets/e473806a-ad65-4718-ae38-84dea36a0a7e)

```python

plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=tit, palette='rainbow')
plt.title("Fare of Passenger by Embarked Town")
```

![image](https://github.com/user-attachments/assets/a35963f9-18ac-4358-9303-3313f61c08ef)

```python
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=tit, palette='rainbow', hue='Pclass')
plt.title("Fare of Passenger by Embarked Town, Divided by Class")
```

![image](https://github.com/user-attachments/assets/f3123c9e-792e-4326-bcb2-244f5f1b26d6)

```python

tips=sns.load_dataset('tips')
sns.scatterplot(x='total_bill', y='tip', hue='sex', data=tips)
plt.xlabel('Total Bill')
plt.ylabel("Tip Amount")
plt.title('Scatter Plot of Total Bill vs. Tip Amount')
```

![image](https://github.com/user-attachments/assets/684a89c4-6a10-4a6c-8cd1-957e5130c884)

```python
num_var = np.random.randn(1000)
num_var=pd.Series(num_var, name = "Numerical variable")
num_var
```

![image](https://github.com/user-attachments/assets/cfb54223-7089-470f-ab9b-3e60f117f46a)

```python


sns.histplot(data = num_var, kde = True)
```

![image](https://github.com/user-attachments/assets/772b2d21-9c5f-43cb-a0d8-7b31057be665)

```python
df=pd.read_csv("/content/titanic_dataset.csv")
sns.histplot(data=df,x="Pclass", hue="Survived", kde=True)
```

![image](https://github.com/user-attachments/assets/16468b5d-e064-416b-86da-31d6a7256b14)

```python
tips=sns.load_dataset('tips')
sns.boxplot(x=tips['day'], y=tips ['total_bill'], hue=tips['sex'])
```

![image](https://github.com/user-attachments/assets/d774241d-b3b5-4e52-a0f5-9b7823e8255e)

```python
sns.boxplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, boxprops={"facecolor": "lightblue", "edgecolor": "darkblue"},
whiskerprops={"color": "black", "linestyle": "--", "linewidth": 1.5}, capprops={"color": "black", "linestyle": "--", "linewidth": 1.5})
```

![image](https://github.com/user-attachments/assets/1274a4d7-cf1d-4e00-9577-8e82144274d6)

```python
sns.violinplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, palette="Set3", inner="quartile")
plt.xlabel("Day of the Week")
plt.ylabel("Total Bill")
plt.title("Violin Plot of Total Bill by Day and Smoker Status")
```

![image](https://github.com/user-attachments/assets/90b37006-77cc-4e69-8c62-ac33fe0d5498)

```python
mart=pd.read_csv("/content/titanic_dataset.csv")
mart
```

![image](https://github.com/user-attachments/assets/8d5755d3-309a-456c-94a2-3f243e2ee076)


```python

mart=mart[['PassengerId', 'Survived', 'Age', 'Name', 'Ticket', 'Embarked']]
mart.head(10)
```

![image](https://github.com/user-attachments/assets/2d56a28c-71fd-4837-a21d-bfb7109467a6)

```python
sns.kdeplot(data=mart,x='PassengerId')
```

![image](https://github.com/user-attachments/assets/ce60cd76-62cd-4322-8657-b3946eda2586)

```python
sns.kdeplot(data=mart,x='Age')
```

![image](https://github.com/user-attachments/assets/c25f5be9-e523-4e1c-ab11-e050e7894efa)

```python
sns.kdeplot(data=mart)
```
![image](https://github.com/user-attachments/assets/dbc82740-c120-4556-b44a-02ceac0ceebc)

```python
sns.kdeplot(data=mart,x='PassengerId',hue='Survived',multiple='stack')
```
![image](https://github.com/user-attachments/assets/af816cc1-e642-4639-b82a-d4e762f1c108)

```python
sns.kdeplot(data=mart,x='PassengerId',y='Survived')
```
![image](https://github.com/user-attachments/assets/a350a2ac-d39b-44d6-8d5e-3a297fae46be)

```python
data = np.random.randint(low = 1, high = 100, size = (10,10))
hm=sns.heatmap(data=data,annot=True)
```
![image](https://github.com/user-attachments/assets/31b1a95f-56c5-4eb3-85b5-1e42d6b09e24)

```python
hm=sns.heatmap(data=data)
```
![image](https://github.com/user-attachments/assets/2fec7e51-131a-4b82-ac47-324587130220)

# Result:
 
THUS verified To Perform Data Visualization using seaborn python library for the given datas.
