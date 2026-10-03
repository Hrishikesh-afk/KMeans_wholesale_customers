%pip install seaborn
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

df= pd.read_csv("Wholesale_customers_data[1].csv")

df.info()

drop=df.drop(columns=["Channel","Region"])
plt.hist(drop)
plt.show()

sns.boxplot(drop)
plt.xticks(rotation=45)
plt.show()

sns.heatmap(drop)
plt.show

df.describe()

out=["Fresh", "Milk", "Grocery", "Frozen", "Detergents_Paper", "Delicassen"]
q1=df[out].quantile(0.25)
q3=df[out].quantile(0.75)
iqr=q3-q1
minimum=q1-1.5*iqr
maximum=q3+1.5*iqr
df_clean=df[((df[out]<=maximum)&(df[out]>=minimum)).all(axis=1)]
df_clean.describe()

X=df_clean[["Fresh","Milk","Grocery","Frozen","Detergents_Paper","Delicassen"]]

from sklearn.preprocessing import StandardScaler
scaler=StandardScaler()
X_scaled=scaler.fit_transform(X)

from sklearn.cluster import KMeans
kmeans=KMeans()
kmeans.fit(X_scaled)

inertia=[]
for k in range(1, 10):
    km=KMeans(n_clusters=k,random_state=42)
    km.fit(X_scaled)
    inertia.append(km.inertia_)

plt.plot(inertia)
plt.show()

mean = df_clean.groupby("Cluster")[["Fresh", "Milk", "Grocery", "Frozen", "Detergents_Paper", "Delicassen"]].mean()
print(mean)
