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
x=[1,2,3,4,5]
y=[3,5,2,7,1]
sns.lineplot(x=x,y=y
```
![image](https://github.com/user-attachments/assets/a5a3a62f-956e-4118-9de5-1e98df28014e)

```
df=sns.load_dataset("tips")
df
```

![image](https://github.com/user-attachments/assets/abceb81b-0074-4e3b-ac45-c7062a1985e2)
```
sns.lineplot(x="total_bill",y="tip", data=df, hue="sex", linestyle='solid', legend="auto")
```

![image](https://github.com/user-attachments/assets/6d4e526a-b2ce-494a-801d-eb3ef0ad6e01)

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

![image](https://github.com/user-attachments/assets/10a47522-445d-44ee-8a8b-d640fc2d0e83)

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

![image](https://github.com/user-attachments/assets/d7b33341-f760-4464-a764-d27ca85d6dd9)
```
vg_total_bill = tips.groupby('time')['total_bill'].mean()
avg_tip=tips.groupby('time') ['tip'].mean()
p1= plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill', width=0.4)
p2 = plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label='Tip', width=0.4)
```

![image](https://github.com/user-attachments/assets/9f6742da-2cdb-45ab-9e18-bbe2aef76649)
```
years=range(2000, 2012)
apples=[0.895, 0.91, 0.919, 0.926, 0.929, 0.931, 0.934, 0.936, 0.937, 0.9375, 0.9372, 0.939]
oranges = [0.962, 0.941, 0.930, 0.923, 0.918, 0.908, 0.907, 0.904, 0.901, 0.898, 0.9, 0.896, ]

plt.bar(years, apples)
plt.bar(years, oranges, bottom=apples)
```

![image](https://github.com/user-attachments/assets/55080c30-c1b1-45d2-a13f-8307018d6273)
```
import seaborn as sns
dt= sns.load_dataset('tips')
sns.barplot(x='day', y='total_bill', hue='sex', data=dt, palette='Set1')
plt.xlabel('Day of the Week')
plt.ylabel("Total Bill")
plt.title('Total Bill by Day and Gender')
```

![image](https://github.com/user-attachments/assets/65be2261-e76b-476d-92eb-18aab0496809)
```
from google.colab import drive
drive.mount('/content/drive')
```
```
ls drive/MyDrive/DS2024/titanic_dataset.csv
```
```
tit=pd.read_csv("drive/MyDrive/DS2024/titanic_dataset.csv")
tit
```

![image](https://github.com/user-attachments/assets/1eaef9f1-b563-4d2c-9f53-6c02f3b96323)
```
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=tit, palette='rainbow')
plt.title("Fare of Passenger by Embarked Town")
```

![image](https://github.com/user-attachments/assets/70757975-4c98-4542-ae86-0b9566a396c5)
```
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=tit, palette='rainbow', hue='Pclass')
plt.title("Fare of Passenger by Embarked Town, Divided by Class")
```

![image](https://github.com/user-attachments/assets/f6c8b413-b758-4827-8a9d-81e8458076da)

```
tips=sns.load_dataset('tips')
sns.scatterplot(x='total_bill', y='tip', hue='sex', data=tips)
plt.xlabel('Total Bill')
plt.ylabel("Tip Amount")
plt.title('Scatter Plot of Total Bill vs. Tip Amount')
```

![image](https://github.com/user-attachments/assets/e014614c-bc28-4e4a-8607-70d83a3df151)
```
num_var = np.random.randn(1000)
num_var=pd.Series(num_var, name = "Numerical variable")
num_var
```

![image](https://github.com/user-attachments/assets/0fa1029b-7f71-49c8-9c45-aa4a33f7ae37)
```
sns.histplot(data = num_var, kde = True)
```

![image](https://github.com/user-attachments/assets/799e3338-6c0d-4114-8861-066a2f8a4ad7)

```
df=pd.read_csv("drive/MyDrive/DS2024/titanic_dataset.csv")
sns.histplot(data=df,x="Pclass", hue="Survived", kde=True)
```

![image](https://github.com/user-attachments/assets/083082aa-9d10-46da-bb95-10bb32c830a7)
```
tips=sns.load_dataset('tips')
sns.boxplot(x=tips['day'], y=tips ['total_bill'], hue=tips['sex'])
```

![image](https://github.com/user-attachments/assets/f634434c-b8ab-4b55-910f-9e468e85a2c3)

```
sns.violinplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, palette="Set3", inner="quartile")
plt.xlabel("Day of the Week")
plt.ylabel("Total Bill")
plt.title("Violin Plot of Total Bill by Day and Smoker Status")
```

![image](https://github.com/user-attachments/assets/138933e5-0920-4e9e-9c49-07a0ce862331)
```
mart=pd.read_csv("drive/MyDrive/DS2024/titanic_dataset.csv")
mart
```

![image](https://github.com/user-attachments/assets/6ea4ee85-362f-4cc8-98ff-0ffc1adca87f)
```
mart=mart[['PassengerId', 'Survived', 'Age', 'Name', 'Ticket', 'Embarked']]
mart.head(10)
```

![image](https://github.com/user-attachments/assets/c84394c4-0729-4a14-8ab2-7cb116633550)
```
sns.kdeplot(data=mart,x='PassengerId')
```

![image](https://github.com/user-attachments/assets/b57ff3a1-3c7d-4efd-8c2e-7f7d6e4ba379)
```
sns.kdeplot(data=mart,x='Age')
```

![image](https://github.com/user-attachments/assets/0cd4a653-ce91-4262-92dd-641230296d2d)

```
sns.kdeplot(data=mart)
```

![image](https://github.com/user-attachments/assets/71395e51-89bb-4ee7-9049-b3339a1857e8)
```
sns.kdeplot(data=mart,x='PassengerId',hue='Survived',multiple='stack')
```

![image](https://github.com/user-attachments/assets/ef5ce60d-94a2-4503-bebd-ed69143e2644)
```
sns.kdeplot(data=mart,x='PassengerId',y='Survived')
```

![image](https://github.com/user-attachments/assets/37050016-ffed-4314-bf04-5e8cfb12a754)
```
data = np.random.randint(low = 1, high = 100, size = (10,10))
hm=sns.heatmap(data=data,annot=True)
```

![image](https://github.com/user-attachments/assets/1842672c-630b-4355-8225-0947ec8cb6f4)
```
hm=sns.heatmap(data=data)
```

![image](https://github.com/user-attachments/assets/4d15bfea-074f-4508-99f6-0510c1cb0569)

 Include the necessary coding and corresponding screenshots

# Result:
Thus, all the data visualization techniques of seaborn has been implemented.
 
