# Ex-01_DS_Data_Cleansing
## AIM:
To read the given data and perform data cleaning and save the cleaned data to a file.

## Explanation:
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

## ALGORITHM:
## STEP 1
Read the given Data

### STEP 2
Get the information about the data

### STEP 3
Remove the null values from the data

### STEP 4
Save the Clean data to the file

## PROGRAM:
```
Developed By :Silambarasan K
Reg No: 212221230101
```
```python
import pandas as pd
import numpy as np
import seaborn as sns

df1 = pd.read_csv("/content/drive/MyDrive/Colab Notebooks/Semester 3/19AI403 - Data Science/Ex_1_Data_set.csv")
df1

df1.head()

df1.describe()

df1.info()

df1.tail()

df1.shape

df1.columns

df1.isnull().sum()

df1.duplicated()

#Using mode method to fill the data in columns as Object(String)
#mode()[0] - Takes the most reccuring value and fills the empty cells
df1['show_name'] = df1['show_name'].fillna(df1['show_name'].mode()[0])
df1['aired_on'] = df1['aired_on'].fillna(df1['aired_on'].mode()[0])
df1['original_network'] = df1['original_network'].fillna(df1['original_network'].mode()[0])

sns.boxplot(x="rating",data=df1)

#Using mean method to fill the data
df1['rating'] = df1['rating'].fillna(df1['rating'].mean())
df1['current_overall_rank'] = df1['current_overall_rank'].fillna(df1['current_overall_rank'].mean())
df1['watchers'] = df1['watchers'].fillna(df1['watchers'].mean())

#Checking the total no.of null values again
df1.isnull().sum()

#Checking info of the dataset to check all the columns have entries
df1.info()

```
## OUPUT
### Dataset:
![D1](https://user-images.githubusercontent.com/94525786/226528815-08193f6f-30ef-4862-af58-4eda17561c66.png)
### Head:
![D2](https://user-images.githubusercontent.com/94525786/226528843-cb94ac89-d440-4d69-a469-1029c2f8f579.png)
### Info:
![D3](https://user-images.githubusercontent.com/94525786/226528854-c81e1156-2ca4-41d8-87df-03bd6f8c03ca.png)
### Describe:
![D4](https://user-images.githubusercontent.com/94525786/226528865-7eee9011-aa42-40fe-8d46-503769606b21.png)
### Tail:
![D5](https://user-images.githubusercontent.com/94525786/226528875-68c20779-cc99-4cc4-be0d-a00b06b02774.png)
### Shape:
![D6](https://user-images.githubusercontent.com/94525786/226528923-9efc4766-9068-4367-9f2b-5edaef671370.png)


### isnull().sum() - Pre Cleaning:
![D8](https://user-images.githubusercontent.com/94525786/226529030-e656af8c-20c3-42f5-82df-8a3741250a21.png)
### Duplicates:
![D9](https://user-images.githubusercontent.com/94525786/226529037-1b0b0118-c0f3-4990-ac38-c998f73cf76a.png)
###  SNS Plot - Rating:
![D10](https://user-images.githubusercontent.com/94525786/226529050-f667a2a2-4692-488e-9ee4-dd49e6cec530.png)
### isnull().sum() - Post Cleaning:
![D11](https://user-images.githubusercontent.com/94525786/226529068-8caee3f9-de12-4042-a419-cd8ff5bc4ca3.png)
### Information - Post Cleaning:
![D12](https://user-images.githubusercontent.com/94525786/226529097-3b1ae542-9958-403f-a6a9-636f8255102c.png)

## RESULT:
The given data is read and data cleaning is performed and the cleaned data is saved to a file.
