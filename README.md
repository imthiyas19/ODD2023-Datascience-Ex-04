# ODD2023-Datascience-Ex-04
## AIM:
To perform Multivariate EDA on the given data set.

## EXPLANATION:
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

## ALGORITHM:
# STEP 1:
Import the built libraries required to perform EDA and outlier removal.

# STEP 2:
Read the given csv file

# STEP 3:
Convert the file into a dataframe and get information of the data.

# STEP 4 :
Return the objects containing counts of unique values using (value_counts()).

# STEP 5 :
Plot the counts in the form of Histogram or Bar Graph.

# STEP 6:
Use seaborn the bar graph comparison of data can be viewed.

# STEP 7:
Find the pairwise correlation of all columns in the dataframe.corr()

# STEP 8:
Save the final data set into the file.

PROGRAM:
```
Name : MOHAMMED IMTHIYAS.M
Register Number : 212222230083
SuperStore.csv file:
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
data=pd.read_csv("/content/SuperStore (1).csv")
df=pd.DataFrame(data)
df.head()
df.info()
df.describe()
df.isnull().sum()
df['Postal Code']=df['Postal Code'].fillna(df['Postal Code'].mode()[0])
df.isnull().sum()

sns.scatterplot(x=df['Region'],y=df['Sales'])

states=df.loc[:,["State","Sales"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Sales")
plt.figure(figsize=(12,5))
plt.xticks(rotation=90)
sns.barplot(x=states.index,y="Sales",data=states)

states=df.loc[:,["Ship Mode","Row ID"]]
states=states.groupby(by=["Ship Mode"]).sum().sort_values(by="Row ID")
sns.barplot(x=states.index,y="Row ID",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("SHIP MODE")
plt.ylabel=("ROW ID")
plt.show()

sns.boxplot(x=df['Ship Date'],y=df['Sales'])
sns.displot(df, x="Region", hue="Category")
df.corr()
sns.heatmap(df.corr(),annot=True)
diabetes.csv file:
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
df=pd.read_csv("/content/diabetes.csv")
df
df.describe()
df.info
df.isnull().sum()

sns.scatterplot(x=df['Glucose'],y=df['BloodPressure'])

sns.scatterplot(x=df['Glucose'], y=df['BloodPressure'], hue=df['Outcome'])

Age=df.loc[:,["Age","BMI"]]
Age=Age.groupby(by=["Age"]).sum().sort_values(by="BMI")
plt.figure(figsize=(12,5))
plt.xticks(rotation=90)
sns.barplot(x=Age.index,y="BMI",data=Age)

Age=df.loc[:,["BloodPressure","Glucose"]]
Age=Age.groupby(by=["BloodPressure"]).sum().sort_values(by="Glucose")
sns.barplot(x=Age.index,y="Glucose",data=Age)
plt.xticks(rotation = 90)
plt.xlabel=("BloodPressure")
plt.ylabel=("Glucose")
plt.show()

sns.boxplot(x=df['DiabetesPedigreeFunction'],y=df['Insulin'])

sns.displot(df, x="Glucose", hue="Outcome")

df.corr()

sns.heatmap(df.corr(),annot=True)
```
# OUTPUT:
SUPERSTORE:
DATA FRAME OF SUPERSTORE:

![276570804-1fa8fce4-890d-4bff-a44b-b8c196b4a3f5](https://github.com/imthiyas19/ODD2023-Datascience-Ex-04/assets/120353416/aa195043-9e21-446b-bf71-6881f6668fe7)

Data information

![276570849-628add2e-c7f1-4d86-b4a3-b1d37c63dbcd](https://github.com/imthiyas19/ODD2023-Datascience-Ex-04/assets/120353416/29511d50-8d7d-4bcc-b829-449fc8140e22)






Data describing:


![276570904-e2906abb-ef3d-4392-838d-3a4f3a46cc6e](https://github.com/imthiyas19/ODD2023-Datascience-Ex-04/assets/120353416/d3cea0a6-43b9-4b8a-8a57-f09524327ca5)



Sum of null values
![276570936-274a4c56-10ce-4fbe-b13c-998fbe78a3bd](https://github.com/imthiyas19/ODD2023-Datascience-Ex-04/assets/120353416/e8a78d81-d2f2-4c20-aeac-a4274dd7e661)





After removing null values:



![276571047-05a5956f-bd7c-45b3-9b48-6d63772c14b2](https://github.com/imthiyas19/ODD2023-Datascience-Ex-04/assets/120353416/8d74888f-f5bb-4cdb-912d-f235e9f410eb)

Scatter plot:

![276571132-fb2790de-ea7f-446d-9d23-a029b9bc669d](https://github.com/imthiyas19/ODD2023-Datascience-Ex-04/assets/120353416/922baf73-a739-49c2-ad42-383205d9d789)






Bar plot: 

![276571205-edc8ab2e-8041-419e-9cb1-9fd3ea431d16](https://github.com/imthiyas19/ODD2023-Datascience-Ex-04/assets/120353416/0754f3a5-6b90-49e2-90e4-0295a4deb77d)




![276571296-7900fa42-ce29-482e-909b-04637967ce6f](https://github.com/imthiyas19/ODD2023-Datascience-Ex-04/assets/120353416/0002bb0a-9445-4e23-b658-de1e553a0839)





Box plot:


![276571367-a97b666a-05bc-49fc-805e-aa6111cd12a3](https://github.com/imthiyas19/ODD2023-Datascience-Ex-04/assets/120353416/dcaf92e6-e178-47d0-9e7c-dfecbe135948)



Dist plot:



![276571442-afff1554-35d8-4d5d-a5c6-2517e41e03e0](https://github.com/imthiyas19/ODD2023-Datascience-Ex-04/assets/120353416/eb821c5e-82cc-40f9-b3c9-ef338719a288)









Correlation coefficient interpretation:



![276571534-64551be3-ca93-4afe-b2b2-94a7485230c5](https://github.com/imthiyas19/ODD2023-Datascience-Ex-04/assets/120353416/5b051494-2d28-4800-bf33-6359ee96e7cf)

# HEAT MAP:

![276571573-a1479ec5-4437-4701-a1f0-37337d78f844](https://github.com/imthiyas19/ODD2023-Datascience-Ex-04/assets/120353416/21b189f5-dc9b-4adf-8a76-ced764dbcdc9)




DIABETES:
DATA FRAME FOR DIABETES:

![276571858-e1f804a2-c461-4e83-82f9-3b44fe285003](https://github.com/imthiyas19/ODD2023-Datascience-Ex-04/assets/120353416/83b0eef5-6926-4d1a-bdc8-32ab55011784)




Data information1:



![276571955-eaaf431f-1e9b-4c88-ac85-2371726ce784](https://github.com/imthiyas19/ODD2023-Datascience-Ex-04/assets/120353416/8038088f-2cd7-4aff-a646-56c47fb3a248)




Data describing:

![276572034-8b794e77-d97f-4fcf-b71b-388ca16df7a4](https://github.com/imthiyas19/ODD2023-Datascience-Ex-04/assets/120353416/7f1e0f52-fab9-43e8-9bb1-0355c797a601)





Sum of null values:


![276572190-04db704b-8eaf-4c53-9f1e-a2fe92d3acaa](https://github.com/imthiyas19/ODD2023-Datascience-Ex-04/assets/120353416/cb1020a9-01da-471e-9173-c439f705765c)




![276572201-cbabb3c2-1b2a-4190-a0d6-b856b7a1f50a](https://github.com/imthiyas19/ODD2023-Datascience-Ex-04/assets/120353416/e17e0946-b93f-4f67-ba43-625989c5e840)






Bar plot:


![276572284-e167acdc-b6b0-4f80-8792-2c96b297cab6](https://github.com/imthiyas19/ODD2023-Datascience-Ex-04/assets/120353416/7ecf1bfd-4b04-4eb7-8f1f-bbb42784e104)

![276572297-8bedfb5b-d600-4045-bf25-117c25128785](https://github.com/imthiyas19/ODD2023-Datascience-Ex-04/assets/120353416/08b087e6-a878-405f-8476-4d7cdf38fd86)




Box plot:




![276572383-dae4ddbc-3786-45b9-a9fe-fff363f05765](https://github.com/imthiyas19/ODD2023-Datascience-Ex-04/assets/120353416/175dcb14-e5fa-409d-8e21-d8a1f344b66d)



Dist plot:

![276572444-a66e4511-fbe9-45a0-8c1d-237aba723673](https://github.com/imthiyas19/ODD2023-Datascience-Ex-04/assets/120353416/60277e2f-d0a0-40df-98e4-9b493593ea6a)






correlation coefficient interpretation:


![276572537-31eff66e-3575-4d6c-99d7-3ee6ed5d4c98](https://github.com/imthiyas19/ODD2023-Datascience-Ex-04/assets/120353416/0130c04d-8b5e-4803-92db-7e15e4ca2edf)


Heat map:





![276572591-52141eca-21e2-47ea-95a7-ba64d1ac8353](https://github.com/imthiyas19/ODD2023-Datascience-Ex-04/assets/120353416/529a4ece-060b-449c-b8ef-f24e201cdaae)

RESULT::
Thus we have read the given data and performed the multivariate analysis with different types of plots.
