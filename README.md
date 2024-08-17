# Exno:1
Data Cleaning Process

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
df=pd.read_csv("SAMPLEIDS.csv")
df
```
![image](https://github.com/user-attachments/assets/e1c25789-4edf-4888-ae15-1adc8904f051)
```
df.head()
```
![image](https://github.com/user-attachments/assets/1808ec6e-ac64-4766-8053-bc394b35de7f)
```
df.tail()
```
![image](https://github.com/user-attachments/assets/c5df3289-2ad5-4f1b-8622-c939d81a1335)

```
df.isnull()
```

![image](https://github.com/user-attachments/assets/d43b2de0-54c8-4a7e-8b2d-70ef1d5ec5e0)

```
df.isnull().sum()
```

![image](https://github.com/user-attachments/assets/501345b4-aa85-4e5c-8a71-be41d40c73c7)

```
df.isnull().any()
```

![image](https://github.com/user-attachments/assets/c2e9986a-5dd0-4d42-9f65-984dda9befd2)

```
df.dropna(axis=0)
```

![image](https://github.com/user-attachments/assets/22ad9302-8786-408e-8d4b-684afb5ff7cb)

```
df.fillna(0)
```

![image](https://github.com/user-attachments/assets/9e91a2a4-22e6-4147-8850-722d8a48ae3e)

```
df.fillna(method = 'ffill')
```

![image](https://github.com/user-attachments/assets/ceeac0cb-5947-4870-9627-c71daa5c7b8e)

```
df.fillna(method = 'bfill')
```

![image](https://github.com/user-attachments/assets/94c4bd5f-5a42-44f6-a6fe-c237225f6b81)

```
df_dropped = df.dropna()
df_dropped
```

![image](https://github.com/user-attachments/assets/aad7b5bc-53c2-4e81-a3ab-ef5993915ceb)

```
df.fillna({'GENDER':'MALE','NAME':'SRI','ADDRESS':'POONAMALEE','M1':98,'M2':87,'M3':76,'M4':92,'TOTAL':305,'AVG':89.999999})
```

![Screenshot 2024-08-17 085348](https://github.com/user-attachments/assets/a9724e3f-bf9a-45ae-a4a2-caa2d1a7a756)

```
import pandas as pd
ir=pd.read_csv('iris.csv')
ir
```

![image](https://github.com/user-attachments/assets/fe51d98b-0546-45f0-8592-6d8270edf50b)

```
ir.describe()
```

![image](https://github.com/user-attachments/assets/8f90444c-9ed1-4331-99ce-c88e4b5f35ac)

```
import seaborn as sns
sns.boxplot(x='sepal_width',data=ir)
```

![image](https://github.com/user-attachments/assets/5dfd8d65-45ff-40d3-b11b-ca36374cc855)

```
c1=ir.sepal_width.quantile(0.25)
c3=ir.sepal_width.quantile(0.75)
iq=c3-c1
print(c3)
```

![image](https://github.com/user-attachments/assets/3769917c-99a9-4e8f-89f1-4f7fc99d9bee)

```
rid=ir[((ir.sepal_width<(c1-1.5*iq))|(ir.sepal_width>(c3+1.5*iq)))]
rid['sepal_width']
```

![image](https://github.com/user-attachments/assets/ec6e977a-d2e2-4cc2-a402-c12bedf9c00b)

```
delid=ir[~((ir.sepal_width<(c1-1.5*iq))|(ir.sepal_width>(c3+1.5*iq)))]
delid
```

![image](https://github.com/user-attachments/assets/84c394a0-f6cc-48c6-9483-229f8584ffc8)

```
sns.boxplot(x='sepal_width',data=delid)
```

![image](https://github.com/user-attachments/assets/abdd832e-d27f-4236-9b03-c7702be75c00)

```
import matplotlib.pyplot as plt
import pandas as pd
import numpy as np
import scipy.stats as stats
```
```
dataset=pd.read_csv("heights.csv")
dataset
```

![image](https://github.com/user-attachments/assets/1fb29efd-4590-4e54-a2f0-42e1b5b47422)

```
z = np.abs(stats.zscore(dataset['height']))
z
```

![image](https://github.com/user-attachments/assets/9c614357-8ffd-4c30-9b80-535c920b65d5)



# Result

Thus we have cleaned the data and removed the outliers by detection using IQR and Z-score method.
