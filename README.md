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
df=sns.load_dataset('tips')
df
```
![Screenshot 2024-10-29 112618](https://github.com/user-attachments/assets/847fa634-41f9-49dc-8033-2433de3cf816)
```
sns.lineplot(x='total_bill',y='tip',data=df,hue='sex',linestyle='solid',legend='auto')
```
![Screenshot 2024-10-29 112657](https://github.com/user-attachments/assets/796c7edd-761f-440a-92ee-fdedfad9ffda)
```
avg_tb=df.groupby('day')['total_bill'].mean()
avg_tip=df.groupby('day')['tip'].mean()
print(avg_tb)
print(avg_tip)
```
![Screenshot 2024-10-29 112736](https://github.com/user-attachments/assets/7652e7bd-7019-416f-ada9-55dd279a0dd3)
```
p1=plt.bar(avg_tb.index,avg_tb.values,label='Total Bill')
p2=plt.bar(avg_tip.index,avg_tip.values,label='Tip')
plt.xlabel('Day of the week')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Day')
plt.legend()
```
![Screenshot 2024-10-29 112804](https://github.com/user-attachments/assets/26d4e126-3611-4860-b066-16b3e3f905c3)
```
avg_tb=df.groupby('time')['total_bill'].mean()
avg_tip=df.groupby('time')['tip'].mean()
p1=plt.bar(avg_tb.index,avg_tb.values,label='Total Bill')
p2=plt.bar(avg_tip.index,avg_tip.values,label='Tip')
plt.xlabel('Time of the day')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Day')
plt.legend()
```
![Screenshot 2024-10-29 112843](https://github.com/user-attachments/assets/e66a5317-5d1f-4775-913b-3ff5b68e6d38)
```
sns.barplot(x='day',y='total_bill',hue='sex',data=df,palette='Set1')
plt.xlabel('Day of the week')
plt.ylabel('Total Bill')
plt.title('Average Total Bill by Day and Sex')
```
![Screenshot 2024-10-29 112915](https://github.com/user-attachments/assets/81fe5d24-dd35-4d0c-9ca3-6c6806be9eb0)
```
sns.scatterplot(x='total_bill',y='tip',hue='sex',data=df)
plt.xlabel('Total Bill')
plt.ylabel('Tip Amount')
plt.title('Scatter Plot of Total Bill vs Tip Amount')
```
![Screenshot 2024-10-29 112944](https://github.com/user-attachments/assets/1a5daf50-3a88-4a9a-8f17-3a34746645b1)
```
import pandas as pd
df=pd.read_csv('/content/titanic_dataset.csv')
df
```
![Screenshot 2024-10-29 113025](https://github.com/user-attachments/assets/3198e092-b688-4cd5-9237-ed9857658396)
```
sns.histplot(data=df,x='Pclass',hue='Survived',kde=True)
```
![Screenshot 2024-10-29 113117](https://github.com/user-attachments/assets/781e0c13-68eb-442a-bda4-63dfaa47c33a)
```
df=sns.load_dataset('tips')
sns.boxplot(x=df['day'],y=df['total_bill'],hue=df['sex'])
```
![Screenshot 2024-10-29 113145](https://github.com/user-attachments/assets/63726e77-57a9-4c77-9657-a91ec3062407)
```
sns.boxplot(x='day',y='total_bill',hue='smoker',data=df,linewidth=2,width=0.8,boxprops={"facecolor":"pink","edgecolor":"red"},whiskerprops={"color":"blue","linestyle":"-","linewidth":1.5},capprops={"color":"black","linestyle":"--","linewidth":1.2})
```
![Screenshot 2024-10-29 113214](https://github.com/user-attachments/assets/1d6ef3d8-e658-45ee-b6bb-62fa62aa8cfc)
```
sns.violinplot(x='day',y='total_bill',hue='smoker',data=df,linewidth=2,width=0.6,palette='Set3',inner='quartile')
plt.xlabel("Day of the week")
plt.ylabel("Total Bill")
plt.title("Violin Plot of Total Bill by Day and Smoker Status")
```
![Screenshot 2024-10-29 113247](https://github.com/user-attachments/assets/90fa0c1d-fef7-48ae-9312-dbd168e5f78d)
```
sns.set(style='darkgrid')
tip=sns.load_dataset('tips')
sns.violinplot(x='day',y='tip',data=tip)
```
![Screenshot 2024-10-29 113318](https://github.com/user-attachments/assets/08273d84-4b92-4836-b962-f3acd83c6d02)
```
sns.set(style='darkgrid')
tip=sns.load_dataset('tips')
sns.violinplot(x=tip["total_bill"])
```
![Screenshot 2024-10-29 113351](https://github.com/user-attachments/assets/68073b9b-b6fc-4f8f-848d-e4b02ff5f53e)
```
sns.set(style='darkgrid')
tip=sns.load_dataset('tips')
sns.violinplot(x='tip',y='day',data=tip)
```
![Screenshot 2024-10-29 113423](https://github.com/user-attachments/assets/85b2bbb9-98fa-4472-983e-5e23685ac3af)
```
sns.kdeplot(data=df,x='total_bill',hue='time',multiple='fill',linewidth=3,palette='Set1',alpha=0.8)
```
![Screenshot 2024-10-29 113455](https://github.com/user-attachments/assets/02f19bd7-56d1-4526-9b7a-4de73c90a27f)
```
sns.kdeplot(data=df,x='total_bill',hue='time',multiple='layer',linewidth=3,palette='Set1',alpha=0.8)
```
![Screenshot 2024-10-29 113534](https://github.com/user-attachments/assets/6111a1cf-e4b2-4fb5-84da-bc7d1d76c3cd)
```
sns.kdeplot(data=df,x='total_bill',hue='time',multiple='stack',linewidth=3,palette='Set2',alpha=0.8)
```
![Screenshot 2024-10-29 113620](https://github.com/user-attachments/assets/64dbf889-b3b7-4712-8166-04c588844b67)
```
import matplotlib.pyplot as plt
import numpy as np
df=sns.load_dataset('tips')
numeric_cols=df.select_dtypes(include=[np.number]).columns
corr=df[numeric_cols].corr()
hm=sns.heatmap(corr,annot=True,cmap='YlGnBu',linewidths=0.5)
```
![Screenshot 2024-10-29 113651](https://github.com/user-attachments/assets/e3c2dade-f6a4-4a80-8d1b-32cc1f421f85)

# Result:
Thus the data visualization using seaborn executed successfully.
