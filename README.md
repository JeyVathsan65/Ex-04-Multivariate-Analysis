# Ex-04-Multivariate-Analysis

# AIM :

To apply multivariate analysis on a give data set.

# ALGORITHM :

1.start

2.read the dta from the file

3.clean the data a)remove outliers b)fill the null value or drop the column

4.perform multivariate analysis a)scatter plot b)box plot c)heat map

# CODE :

## Read and cleaned the null value: 

import pandas as pd

df=pd.read_csv("/content/SuperStore.csv")

df['Postal Code']=df['Postal Code'].fillna(df['Postal Code'].mode()[0])

df.isnull().sum()

df.dtypes

## Kurtosis:

df.kurtosis()

## Scatter plot:

import pandas as pd

import seaborn as sns

sns.boxplot(df['Sales'],df['Postal Code'])

## Bar plot:

sns.barplot(x=df["Sales"],y=df["Postal Code"],data=df)

## Bar plot

import pandas as pd

import seaborn as sns

import matplotlib.pyplot as plt

states=df.loc[:,["Postal Code","Sales"]]

states=states.groupby(by=["Postal Code"]).sum().sort_values(by="Sales")

plt.figure(figsize=(17,7))

sns.barplot(x=states.index,y="Sales",data=states)

plt.xticks(rotation = 90)

plt.xlabel=("Postal Code")

plt.ylabel=("Sales")

plt.show()

import pandas as pd

import seaborn as sns import matplotlib.pyplot as plt

states=df.loc[:,["State","Postal Code"]]

states=states.groupby(by=["State"]).sum().sort_values(by="Postal Code")

plt.figure(figsize=(17,7))

sns.barplot(x=states.index,y="Postal Code",data=states)

plt.xticks(rotation = 90)

plt.xlabel=("Sales")

plt.ylabel=("Postal Code")

plt.show()


## Corr:

df.corr()

## Heatmap:

import numpy as np

import seaborn as sn

import matplotlib.pyplot as plt

data=pd.read_csv("/content/SuperStore.csv")

data = np.random.randint(low = 1, high = 100, size = (10, 10))

print("The data to be plotted:\n")

print(data)

hm = sn.heatmap(data = data)

plt.show()

# OUTPUT:

## Null Sum:

![image](https://user-images.githubusercontent.com/95520655/229963909-7b6653d4-3b6e-4cad-8d02-ca18b4b5ef0d.png)

## DataTypes:

![image](https://user-images.githubusercontent.com/95520655/229963965-da15bdc3-a3f3-45da-9287-98bb71e2594a.png)

## Kurtosis:

![image](https://user-images.githubusercontent.com/95520655/229964022-8709b940-e889-4a2f-9900-77a487f6a70d.png)

## Scatter plot:

![image](https://user-images.githubusercontent.com/95520655/229964093-8070b642-2459-454b-a40c-48dc0ac35aae.png)

## Bar plot:

![image](https://user-images.githubusercontent.com/95520655/229964262-6574bc21-0914-4eee-8df0-c09b3784842e.png)

## Bar plot

![image](https://user-images.githubusercontent.com/95520655/229964484-4a9e81f7-9943-44d3-981d-71daba303361.png)

## Corr:

![image](https://user-images.githubusercontent.com/95520655/229964541-119d182a-da4f-4231-a013-27b9be91618f.png)

## Heatmap:

![image](https://user-images.githubusercontent.com/95520655/229964580-680a7376-5e03-41a2-9fad-d886ff5b7884.png)

# RESULT:

Thus we have applied the multiivariate analysis sucessfully


