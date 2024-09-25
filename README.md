<img width="411" alt="image" src="https://github.com/user-attachments/assets/e3691d18-6e8b-42d5-bd33-c5c8fe7ff0a3"># EXNO2DS
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
import matplotlib.pyplot as plt
import seaborn as sns
dt=pd.read_csv("titanic_dataset.csv")
dt
```
## OUTPUT
<img width="577" alt="image" src="https://github.com/user-attachments/assets/5ab327f3-96ed-41b8-bc07-8825fb122b8a">

```
dt.info()
```
## OUTPUT

<img width="176" alt="image" src="https://github.com/user-attachments/assets/b815b713-7620-4a28-beda-d0f13d512a58">
```
dt
```

## OUTPUT

<img width="592" alt="image" src="https://github.com/user-attachments/assets/b809414d-e7b8-4c24-8227-78155ada0dee">
```
dt.describe()
```

## OUTPUT

<img width="557" alt="image" src="https://github.com/user-attachments/assets/061d35c1-5b54-4102-9db5-9dde2f7096f0">
```
dt.nunique()
```

## OUTPUT

<img width="137" alt="image" src="https://github.com/user-attachments/assets/4c921108-db3b-4538-ae65-53caa0c9b1aa">
```
dt["Survived"].value_counts()
```

## OUTPUT


<img width="158" alt="image" src="https://github.com/user-attachments/assets/3a5676f0-3bdb-404c-8acf-be990dce48d0">
```
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```

## OUTPUT

<img width="500" alt="image" src="https://github.com/user-attachments/assets/7d7313c6-0dd5-42eb-9004-2b2c7f6c524b">
```
sns.countplot(data=dt,x="Survived")
```

## OUTPUT

<img width="523" alt="image" src="https://github.com/user-attachments/assets/1ce6c4ae-f030-4678-b4d0-889fb8299a03">
```
dt.Pclass.unique()
```

## OUTPUT

<img width="275" alt="image" src="https://github.com/user-attachments/assets/585b26b0-0cdc-48b2-b32c-6a7797ebf783">
```
dt.rename(columns={"Sex":"Gender"},inplace=True)
dt
```

## OUTPUT

<img width="590" alt="image" src="https://github.com/user-attachments/assets/6c767bef-c15a-45b0-8da1-a3de1c925fb3">
```
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)
```

## OUTPUT

<img width="558" alt="image" src="https://github.com/user-attachments/assets/100d0b26-3018-492e-baa3-8ad02c9d672a">
```
sns.catplot(x="Survived",hue='Gender',data=dt,kind='count')
```

## OUTPUT

<img width="410" alt="image" src="https://github.com/user-attachments/assets/069dde6d-35d1-42cd-be2a-c884a8867d5d">
```
dt.boxplot(column="Age",by="Survived")
```

## OUTPUT

<img width="394" alt="image" src="https://github.com/user-attachments/assets/703ea61c-cfce-4968-b501-c33ad1be4728">
```
sns.scatterplot(data=dt,x="Age",y="Fare",hue="Survived")
```

## OUTPUT

<img width="395" alt="image" src="https://github.com/user-attachments/assets/00557e9e-f3fc-4b78-9053-7e82de56cc01">
```
sns.jointplot(data=dt,x="Age",y="Fare",hue="Survived")
```

## OUTPUT

<img width="361" alt="image" src="https://github.com/user-attachments/assets/8a5ef5e4-2634-4007-9aa3-bc0d82074dc7">
```
sns.catplot(x="Gender",col="Survived",hue="Pclass",kind="count",data=dt)
```

## OUTPUT

<img width="411" alt="image" src="https://github.com/user-attachments/assets/2bdcf189-db8a-4c79-a69b-53f508837cf7">
```
numeric_dt=dt.select_dtypes(exclude=[object])
corr=numeric_dt.corr()
sns.heatmap(corr,annot=True)
```

## OUTPUT

<img width="310" alt="image" src="https://github.com/user-attachments/assets/d1f9f788-e80d-4d48-abed-daaa879d5b50">
```
sns.pairplot(dt)
```

## OUTPUT 

<img width="434" alt="image" src="https://github.com/user-attachments/assets/316fd558-3dca-4476-a087-8eb7378aa26d">

# RESULT
Thus, the program is executed successfully.

