                           EX NO 4 : Multivariate Analysis
   AIM:
       To Perform Multivariate Analysis
  Algorithm:
  1.Read the given data 
  2.Get information from the data 
  3.Perform the Multivariate Analysis
  4.Save the clean data to file

Program:
1) reading the file

import pandas as pd

import seaborn as sns

df=pd.read_csv("/content/SuperStore.csv")

data=df

2) Scatterplot

import pandas as pd

import seaborn as sns

import matplotlib.pyplot as plt

sns.scatterplot (df['Postal Code'],df['Sales'])

![image](https://user-images.githubusercontent.com/113016781/191926755-ead2fccc-990c-4649-8f64-0406d1df2b67.png)

3) Barplot

import pandas as pd

import seaborn as sns

sns.barplot (x=df["Postal Code"], y=df["Sales"], data=df)

![image](https://user-images.githubusercontent.com/113016781/191926917-a6ba74c0-3d80-4d8a-a53b-1e6400af9007.png)

4) Scatterplot

import pandas as pd

import seaborn as sns

sns.scatterplot(df["Postal Code"], y=df["Sales"], hue=df['Row ID'])

![image](https://user-images.githubusercontent.com/113016781/191927062-2f57d1b7-d799-409f-8b08-0503bffab285.png)

5)
df.info()

![image](https://user-images.githubusercontent.com/113016781/191927208-2faaee85-9dd5-43dc-8d33-4eb1a74a64ec.png)

6)

states=df.loc[:,["Postal Code","Sales"]]

states=states.groupby(by=["Postal Code"]).sum().sort_values(by="Sales")

sns.barplot(x=states.index,y="Sales",data=states)

plt.xticks(rotation = 90)

plt.xlabel=("Postal Code")

plt.ylabel=("SALES")

plt.show()

![image](https://user-images.githubusercontent.com/113016781/191927389-dd26ac3d-e6d9-430e-92fa-2066143e4f20.png)

7) 
states=df.loc[:,["Segment","Sales"]]

states=states.groupby(by=["Segment"]).sum().sort_values(by="Sales")

#plt.figure(figsize=(10,7))

sns.barplot(x=states.index,y="Sales",data=states)

plt.xticks(rotation = 90)

plt.xlabel=("Segment")

plt.ylabel=("Sales")

plt.show()

![image](https://user-images.githubusercontent.com/113016781/191927599-debe4106-acc6-4483-897e-e26fabb6373f.png)


8)

import numpy as np

import seaborn as sn

import matplotlib.pyplot as plt

data=pd.read_csv("/content/SuperStore.csv")

data = np.random.randint(low = 1, high = 100, size = (10, 10))

print("The data to be plotted:\n")

print(data)

hm = sn.heatmap(data = data)

plt.show()

![image](https://user-images.githubusercontent.com/113016781/192075897-5f01a6d1-e903-4d77-97a9-1fd150498bee.png)

Result:
     Multivariate-Analysis is performed on given data and saved

