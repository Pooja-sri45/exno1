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

# Result
          <<include your Result here>>
