# RESTAURANT--MANAGEMENT
This project is a simple Restaurant Management System using NumPy, Pandas, and Matplotlib. It manages order data, calculates total sales, analyzes item-wise performance, and displays sales trends using graphs to help understand restaurant performance easily.
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt

# Sample restaurant order data
data = {
    "Item": ["Burger", "Pizza", "Pasta", "Burger", "Pizza", "Pasta"],
    "Price": [120, 250, 180, 120, 250, 180],
    "Quantity": [2, 1, 1, 3, 2, 2]
}

# Create DataFrame
df = pd.DataFrame(data)

# Calculate total amount for each order
df["Total"] = df["Price"] * df["Quantity"]

print("Restaurant Orders Data:")
print(df)

# Total sales
total_sales = np.sum(df["Total"])
print("\nTotal Sales: ₹", total_sales)

# Item-wise sales
item_sales = df.groupby("Item")["Total"].sum()
print("\nItem-wise Sales:")
print(item_sales)

# Visualization
plt.figure()
item_sales.plot(kind="bar")
plt.xlabel("Food Item")
plt.ylabel("Total Sales (₹)")
plt.title("Restaurant Sales Analysis")
plt.show()
