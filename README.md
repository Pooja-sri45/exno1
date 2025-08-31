# Exno:1
# Data Cleaning Process
## NAME: POOJASRI L
## REG.NO:212223220076

# AIM
To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# Algorithm
STEP 1: Read the given Data

STEP 2: Get the information about the data

STEP 3: Remove the null values from the data

STEP 4: Save the Clean data to the file

STEP 5: Remove outliers using IQR

STEP 6: Use zscore of to remove outliers

# Coding and Output

```
import pandas as pd
data=pd.read_csv("SAMPLEIDS.csv")
data
```
<img width="823" height="698" alt="image" src="https://github.com/user-attachments/assets/51fdee35-a72d-4009-a515-1976cfe7ee41" />

```
data.head()
```
<img width="1088" height="282" alt="image" src="https://github.com/user-attachments/assets/a83bf4ba-f830-4a9b-adf1-d00fb308a880" />

```
data.tail()
```
<img width="1130" height="282" alt="image" src="https://github.com/user-attachments/assets/c38c7cb3-09e4-4ead-90f9-e521577ef1e8" />

```
data.head(3)
```
<img width="1075" height="205" alt="image" src="https://github.com/user-attachments/assets/be63cafd-fcd9-4c32-9ff8-075ce4d72f50" />

```
data.tail(2)
```
<img width="1092" height="157" alt="image" src="https://github.com/user-attachments/assets/05e61348-36d2-4336-a01c-ab4d5d53391c" />

```
data.isnull()
```
<img width="857" height="717" alt="image" src="https://github.com/user-attachments/assets/82e43c8e-5482-49b1-b28a-65cfc46254de" />

```
data.notnull()
```
<img width="856" height="722" alt="image" src="https://github.com/user-attachments/assets/838aa1b8-b983-4990-bdfc-15fe76dfcc53" />

```
data.isnull().sum()
```
<img width="392" height="556" alt="image" src="https://github.com/user-attachments/assets/16435468-c5d2-46e7-8d29-405bb66015af" />

```
data.isnull().any()
```
<img width="413" height="592" alt="image" src="https://github.com/user-attachments/assets/6bf611c4-0404-4707-b434-a38a8f147ca7" />

```
data.dropna(axis=0)
```
<img width="1037" height="558" alt="image" src="https://github.com/user-attachments/assets/18c90da4-f18d-4de6-8157-2905d00ea696" />

```
data.dropna(axis=1)
```
<img width="438" height="702" alt="image" src="https://github.com/user-attachments/assets/7bcf4e0a-6fb6-4132-8e6f-25e7666bb760" />

```
data.fillna(5)
```
<img width="827" height="700" alt="image" src="https://github.com/user-attachments/assets/7e0d7b3a-3d26-4e55-a8de-a301b4b366fb" />

```
data.fillna(method = 'ffill')
```
<img width="825" height="700" alt="image" src="https://github.com/user-attachments/assets/1e91315f-0965-4d09-9398-b57ce7a4caeb" />

```
data.fillna(method = 'bfill')
```
<img width="833" height="702" alt="image" src="https://github.com/user-attachments/assets/49e72af9-b11c-446a-b21f-fa860c6d45bc" />

```
data.fillna({'GENDER':'MALE','NAME':'SRI','ADDRESS':'POONAMALEE','M1':98,'M2':87,'M3':76,'M4':92,'TOTAL':305,'AVG':89.999999})
```
<img width="818" height="708" alt="image" src="https://github.com/user-attachments/assets/cd6ef085-9a99-4b4b-aa9a-e020e4b4dcfb" />

```
import pandas as pd
df=pd.read_csv('iris.csv')
df
```
<img width="666" height="518" alt="image" src="https://github.com/user-attachments/assets/33001f20-d436-4116-a313-e9f130b61e79" />

```
df.describe()
```
<img width="598" height="366" alt="image" src="https://github.com/user-attachments/assets/b14a3a71-c97b-49d2-87a4-e6ccc0acfdcb" />

```
import seaborn as sns
sns.boxplot(x='sepal_width',data=df)
```
<img width="731" height="582" alt="image" src="https://github.com/user-attachments/assets/69a63eb2-7423-479b-9bcf-27289fdf4737" />

```
q1=df.sepal_width.quantile(0.25)
q3=df.sepal_width.quantile(0.75)
IQR=q3-q1
print(IQR)
```
<img width="222" height="41" alt="image" src="https://github.com/user-attachments/assets/1fdfc169-3698-4d4d-9ad5-b2488329f73f" />

```
range=df[((df.sepal_width<(q1-1.5*IQR))|(df.sepal_width>(q3+1.5*IQR)))]
range['sepal_width']
```
<img width="476" height="253" alt="image" src="https://github.com/user-attachments/assets/6ac49df8-987d-4b1d-a61c-452c61a9005d" />

```
range=df[~((df.sepal_width<(q1-1.5*IQR))|(df.sepal_width>(q3+1.5*IQR)))]
range['sepal_width']
```
<img width="557" height="572" alt="image" src="https://github.com/user-attachments/assets/eb2403ed-aa15-4eb7-8f3c-c71f314a0ad7" />

```
sns.boxplot(x='sepal_width',data=range)
```
<img width="803" height="582" alt="image" src="https://github.com/user-attachments/assets/becfc4f0-d3bf-40eb-97d0-a21aebe243ec" />

```
import numpy as np
import scipy.stats as stats
z=np.abs(stats.zscore(df['sepal_width']))
z
```
<img width="755" height="671" alt="image" src="https://github.com/user-attachments/assets/71bb00d8-d3d7-45f9-accc-06ff2b5f7135" />

```
df1=df[z<3]
df1
```
<img width="667" height="521" alt="image" src="https://github.com/user-attachments/assets/8665bde0-f63a-4071-a42e-079a629f7361" />



# Result
Thus we have cleaned the data and removed the outliers by detection using IQR and Z-score method.
