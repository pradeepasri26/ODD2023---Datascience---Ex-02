# Ex02-Outlier
## AIM:
To read a given dataset and remove outliers and save a new dataframe.

## ALGORITHM:
(1) Remove outliers using IQR

(2) After removing outliers in step 1, you get a new dataframe.

(3) use zscore of 3 to remove outliers. This is quite similar to IQR and you will get exact same result

(4) for the data set height_weight.csv find the following

(i) Using IQR detect weight outliers and print them

(ii) Using IQR, detect height outliers and print them

## PROGRAM
```
import pandas as pd
import numpy as np
import seaborn as sns
import pandas as pd
from scipy import stats
df = pd.read_csv("/content/heights.csv")
sns.boxplot(data=df)
sns.scatterplot(data=df)
max =df['height'].quantile(0.90)
min =df['height'].quantile(0.15)
max
min
dq = df[((df['height']>=min)&(df['height']<=max))]
dq
low = min-1.5*iqr
high = max+1.5*iqr
dq = df[((df['height']>=min)&(df['height']<=max))]
dq
```
## ZSCORE:
```
import pandas as pd
import numpy as np
import seaborn as sns
import pandas as pd
from scipy import stats
data = {'weight':[12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,66,69,202,72,75,78,81,84,232,87,90,93,96,99,258]}
df = pd.DataFrame(data)
df
sns.boxplot(data=df)
z = np.abs(stats.zscore(df))
print(df[z['weight']>3])
val =[12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,66,69,202,72,75,78,81,84,232,87,90,93,96,99,258]
out=[]
def d_o(val):
ts=3
m=np.mean(val)
sd=np.std(val)
for i in val:
z=(i-m)/sd
if np.abs(z)>ts:
out.append(i)
return out
op = d_o(val)
op
```
## OUTPUT
![image](https://github.com/pradeepasri26/ODD2023---Datascience---Ex-02/assets/131433142/2509df95-a1f4-4f2c-8d3d-c141659d8f38)
![image](https://github.com/pradeepasri26/ODD2023---Datascience---Ex-02/assets/131433142/eb77db5a-a1a6-4910-9180-bc38ab0aa833)
![image](https://github.com/pradeepasri26/ODD2023---Datascience---Ex-02/assets/131433142/a81d817b-acdf-4163-9679-0addb8482832)
![image](https://github.com/pradeepasri26/ODD2023---Datascience---Ex-02/assets/131433142/145d509d-39b1-4681-b4e4-0a99f4669c56)
![image](https://github.com/pradeepasri26/ODD2023---Datascience---Ex-02/assets/131433142/0fce973b-e315-4eff-9a39-8c94876b74f9)
![image](https://github.com/pradeepasri26/ODD2023---Datascience---Ex-02/assets/131433142/ad8b2c6d-8806-4440-91e2-60cd73566b8f)
![image](https://github.com/pradeepasri26/ODD2023---Datascience---Ex-02/assets/131433142/d5394034-b1c8-4511-9395-9541e56d7131)
![image](https://github.com/pradeepasri26/ODD2023---Datascience---Ex-02/assets/131433142/a84e91d7-bf61-455a-a9b6-7fa3d8fb13b1)
![image](https://github.com/pradeepasri26/ODD2023---Datascience---Ex-02/assets/131433142/b076c331-274b-440b-9fa7-a3fc21568d1d)

## RESULT:
Thus, the given data is read,remove outliers and save a new dataframe was created and executed successfully.












