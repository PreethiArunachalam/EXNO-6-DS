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
 import seaborn as sns
import matplotlib.pyplot as plt
df=sns.load_dataset('tips')
df
Screenshot 2024-10-29 112618

sns.lineplot(x='total_bill',y='tip',data=df,hue='sex',linestyle='solid',legend='auto')
Screenshot 2024-10-29 112657

avg_tb=df.groupby('day')['total_bill'].mean()
avg_tip=df.groupby('day')['tip'].mean()
print(avg_tb)
print(avg_tip)
Screenshot 2024-10-29 112736

p1=plt.bar(avg_tb.index,avg_tb.values,label='Total Bill')
p2=plt.bar(avg_tip.index,avg_tip.values,label='Tip')
plt.xlabel('Day of the week')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Day')
plt.legend()
Screenshot 2024-10-29 112804

avg_tb=df.groupby('time')['total_bill'].mean()
avg_tip=df.groupby('time')['tip'].mean()
p1=plt.bar(avg_tb.index,avg_tb.values,label='Total Bill')
p2=plt.bar(avg_tip.index,avg_tip.values,label='Tip')
plt.xlabel('Time of the day')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Day')
plt.legend()
Screenshot 2024-10-29 112843

sns.barplot(x='day',y='total_bill',hue='sex',data=df,palette='Set1')
plt.xlabel('Day of the week')
plt.ylabel('Total Bill')
plt.title('Average Total Bill by Day and Sex')
Screenshot 2024-10-29 112915

sns.scatterplot(x='total_bill',y='tip',hue='sex',data=df)
plt.xlabel('Total Bill')
plt.ylabel('Tip Amount')
plt.title('Scatter Plot of Total Bill vs Tip Amount')
Screenshot 2024-10-29 112944

import pandas as pd
df=pd.read_csv('/content/titanic_dataset.csv')
df
Screenshot 2024-10-29 113025

sns.histplot(data=df,x='Pclass',hue='Survived',kde=True)
Screenshot 2024-10-29 113117

df=sns.load_dataset('tips')
sns.boxplot(x=df['day'],y=df['total_bill'],hue=df['sex'])
Screenshot 2024-10-29 113145

sns.boxplot(x='day',y='total_bill',hue='smoker',data=df,linewidth=2,width=0.8,boxprops={"facecolor":"pink","edgecolor":"red"},whiskerprops={"color":"blue","linestyle":"-","linewidth":1.5},capprops={"color":"black","linestyle":"--","linewidth":1.2})
Screenshot 2024-10-29 113214

sns.violinplot(x='day',y='total_bill',hue='smoker',data=df,linewidth=2,width=0.6,palette='Set3',inner='quartile')
plt.xlabel("Day of the week")
plt.ylabel("Total Bill")
plt.title("Violin Plot of Total Bill by Day and Smoker Status")
Screenshot 2024-10-29 113247

sns.set(style='darkgrid')
tip=sns.load_dataset('tips')
sns.violinplot(x='day',y='tip',data=tip)
Screenshot 2024-10-29 113318

sns.set(style='darkgrid')
tip=sns.load_dataset('tips')
sns.violinplot(x=tip["total_bill"])
Screenshot 2024-10-29 113351

sns.set(style='darkgrid')
tip=sns.load_dataset('tips')
sns.violinplot(x='tip',y='day',data=tip)
Screenshot 2024-10-29 113423

sns.kdeplot(data=df,x='total_bill',hue='time',multiple='fill',linewidth=3,palette='Set1',alpha=0.8)
Screenshot 2024-10-29 113455

sns.kdeplot(data=df,x='total_bill',hue='time',multiple='layer',linewidth=3,palette='Set1',alpha=0.8)
Screenshot 2024-10-29 113534

sns.kdeplot(data=df,x='total_bill',hue='time',multiple='stack',linewidth=3,palette='Set2',alpha=0.8)
Screenshot 2024-10-29 113620

import matplotlib.pyplot as plt
import numpy as np
df=sns.load_dataset('tips')
numeric_cols=df.select_dtypes(include=[np.number]).columns
corr=df[numeric_cols].corr()
hm=sns.heatmap(corr,annot=True,cmap='YlGnBu',linewidths=0.5)
Screenshot 2024-10-29 113651

# Result:
Thus the data visualization using seaborn executed successfully.
