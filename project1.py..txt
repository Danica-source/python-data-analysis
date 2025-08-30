# Mini Sales Data Analysis Project
# By Davita (Danica-source)

import pandas as pd
import matplotlib.pyplot as plt

# Sample sales dataset
data = {
    "Product": ["Banana", "Orange", "Apple", "Mango", "Banana", "Orange", "Apple", "Mango"],
    "Region": ["North", "North", "South", "East", "West", "South", "East", "West"],
    "Sales": [120, 150, 90, 100, 200, 180, 75, 130],
    "Month": ["Jan", "Jan", "Jan", "Jan", "Feb", "Feb", "Feb", "Feb"]
}

# Create DataFrame
df = pd.DataFrame(data)

# 1. Show first rows
print("Sales Data:")
print(df.head())

# 2. Total sales by product
product_sales = df.groupby("Product")["Sales"].sum().sort_values(ascending=False)
print("\nTotal Sales by Product:")
print(product_sales)

# 3. Total sales by region
region_sales = df.groupby("Region")["Sales"].sum().sort_values(ascending=False)
print("\nTotal Sales by Region:")
print(region_sales)

# 4. Simple visualization
product_sales.plot(kind="bar", title="Total Sales by Product", color="skyblue")
plt.ylabel("Sales")
plt.show()
