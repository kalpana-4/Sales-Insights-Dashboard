# Sales Data Analysis Project
# Author: Kalpana G R

import pandas as pd

print("SALES DATA ANALYSIS PROJECT")

data = {
    "Product": ["Laptop","Mobile","Tablet","Laptop","Mobile","Tablet","Laptop"],
    "Region": ["South","North","East","West","South","North","East"],
    "Revenue": [50000,30000,20000,45000,25000,15000,52000],
    "Quantity": [10,15,8,9,12,5,11]
}

df = pd.DataFrame(data)

print("\nSales Dataset")
print(df)

print("\nTotal Revenue")
print(df["Revenue"].sum())

print("\nAverage Revenue")
print(df["Revenue"].mean())

print("\nTotal Quantity Sold")
print(df["Quantity"].sum())

print("\nRevenue by Region")
print(df.groupby("Region")["Revenue"].sum())

print("\nRevenue by Product")
print(df.groupby("Product")["Revenue"].sum())

top_product = df.groupby("Product")["Revenue"].sum().idxmax()
print("\nTop Selling Product:", top_product)

top_region = df.groupby("Region")["Revenue"].sum().idxmax()
print("Top Performing Region:", top_region)
