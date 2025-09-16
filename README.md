# EXNO2DS
# AIM:
      To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT
```
import pandas as pd
import numpy as np
import seaborn as sns
df=pd.read_csv('titanic_dataset.csv')
df
```

<img width="1356" height="489" alt="1st" src="https://github.com/user-attachments/assets/7993d507-0af5-4d77-a0d9-b1bec864fb1b" />

```
df.info()
```

<img width="1023" height="385" alt="Screenshot 2025-09-13 153956" src="https://github.com/user-attachments/assets/678a184c-8460-44f5-a4dd-9d7284a5c8c3" />

```
df.describe()
```

<img width="801" height="324" alt="Screenshot 2025-09-13 154223" src="https://github.com/user-attachments/assets/e5a443b3-9086-49c0-8211-10da997f372b" />

```
df.dtypes
```

<img width="332" height="479" alt="Screenshot 2025-09-13 154249" src="https://github.com/user-attachments/assets/15cf410b-ee99-4d6c-b255-68b94e558423" />

```
df.shape
```

<img width="819" height="92" alt="Screenshot 2025-09-13 154332" src="https://github.com/user-attachments/assets/e4cd75a5-8ed3-46a8-a8d7-af3693501882" />


```
df['Age'].value_counts()
```

<img width="706" height="594" alt="Screenshot 2025-09-13 154554" src="https://github.com/user-attachments/assets/e517e201-ca89-4d47-a880-d2bd1a384b17" />


```
df.set_index('PassengerId',inplace=True)
df
```

<img width="1382" height="498" alt="Screenshot 2025-09-13 154756" src="https://github.com/user-attachments/assets/93828877-77a5-482b-b150-db428f3d2331" />


```
df.nunique()
```

<img width="320" height="477" alt="Screenshot 2025-09-13 155101" src="https://github.com/user-attachments/assets/90209e56-9947-4405-b36c-d8ac15dffe1a" />


```
sns.countplot(data=df,x='Survived')
```

<img width="1066" height="566" alt="Screenshot 2025-09-13 155332" src="https://github.com/user-attachments/assets/e55cb6fa-4296-4420-9962-68a79989b687" />

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```

<img width="1331" height="500" alt="image" src="https://github.com/user-attachments/assets/eda425b4-053a-42e9-9fb0-621c663844d7" />


```
sns.catplot(x='Gender',col='Survived',kind='count',data=df,height=5,aspect=0.7)
```


<img width="1319" height="607" alt="Screenshot 2025-09-13 160156" src="https://github.com/user-attachments/assets/6d06d865-c306-4758-8446-dbd5143a13fb" />

```
df.boxplot(column='Age',by='Survived')
```

<img width="1003" height="535" alt="Screenshot 2025-09-13 160526" src="https://github.com/user-attachments/assets/20e1fd4e-58ac-4bb9-9e27-fbde2bb50ca4" />


```
sns.scatterplot(x=df['Age'],y=df['Fare'])
```

<img width="943" height="526" alt="Screenshot 2025-09-13 161237" src="https://github.com/user-attachments/assets/f3c4ef32-d14e-4e4f-9935-ab32a5ecd889" />


```
plt=sns.boxplot(x='Pclass',y='Age',hue='Gender',data=df)
```

<img width="904" height="555" alt="Screenshot 2025-09-13 161244" src="https://github.com/user-attachments/assets/922d6804-81ce-41c0-8c5c-f4e38cdbbe40" />

```
sns.catplot(x='Gender',col='Survived',hue='Pclass',kind='count',data=df)
```

<img width="1413" height="664" alt="Screenshot 2025-09-13 161612" src="https://github.com/user-attachments/assets/2bd50d6c-40ba-4c81-bd86-ed840664ac76" />


```
corr=df.corr(numeric_only=True)
sns.heatmap(corr,annot=True)
```

<img width="1087" height="498" alt="Screenshot 2025-09-13 162043" src="https://github.com/user-attachments/assets/2a29b769-616d-4070-973b-2044d7369534" />


# RESULT
        Hence the program to perform Exploratory Data Analysis on the given data set has been done successfully.


