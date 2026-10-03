## 📊 Customer Segmentation & Cluster Profiling

By applying **K-Means Clustering** on continuous spending categories, we identified 8 distinct customer segments based on their average annual expenditure across six primary product lines:

| Cluster | Persona Description | Fresh ($) | Milk ($) | Grocery ($) | Frozen ($) | Detergents & Paper ($) | Delicatessen ($) |
| :---: | :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| **0** | **Fresh Produce Focus** *(Cafes & Restaurants)* | **18,215.97** | 1,637.18 | 2,526.90 | 1,987.78 | 396.53 | 722.40 |
| **1** | **Medium Retailers** *(Grocery Stores)* | 4,620.60 | **7,421.69** | **10,055.29** | 1,155.89 | **4,199.80** | 1,985.14 |
| **2** | **Low-Volume Accounts** *(Small Local Shops)* | 4,828.80 | 2,038.81 | 2,404.97 | 1,094.03 | 473.73 | 705.02 |
| **3** | **High-Volume Fresh & Frozen** *(Large Caterers)* | **23,070.30** | 3,885.20 | 3,847.10 | **4,634.00** | 548.90 | **2,443.80** |
| **4** | **Large Wholesale Retailers** *(Supermarkets)* | 5,765.22 | **9,338.81** | **15,673.32** | 1,452.30 | **6,655.38** | 954.81 |
| **5** | **Frozen Specialty Buyers** *(Bakeries / Frozen Produce)* | 7,691.87 | 2,320.41 | 3,028.77 | **5,160.82** | 751.67 | 815.92 |
| **6** | **High-Volume Distributors** *(General Wholesalers)* | **20,564.88** | 6,570.84 | **8,400.24** | 1,162.76 | 2,166.48 | **2,236.80** |
| **7** | **Standard Retail Outlets** *(Convenience Stores)* | 6,139.81 | 4,981.65 | **7,745.97** | 838.49 | 2,762.65 | 390.11 |

> **Note:** Values represent the mean spending per category per cluster, derived directly from `df_clean.groupby("Cluster").mean()`.
