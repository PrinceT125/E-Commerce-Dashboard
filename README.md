# 📊 E-Commerce-Dashboard

## E-Commerce Sales Dashboard – Power BI + Python + SQL Project

---

#  Project Overview

This project is an **E-Commerce Sales Dashboard** built using:

- **SQL** → Data querying & analysis  
- **Python** → Data cleaning & preprocessing  
- **Power BI Desktop** → Dashboard visualization & analytics  

The dashboard helps analyze:

- Sales Performance
- Profit Trends
- Customer Insights
- State-wise Sales
- Product Category Performance
- Payment Mode Analysis

This project demonstrates a complete **Data Analytics Workflow** from raw data processing to business intelligence reporting.

---

# 🖼 Dashboard Preview

![Dashboard Preview](https://github.com/PrinceT125/E-Commerce-Dashboard/blob/main/dashboard%20image.png)

---

#  Technologies Used

## SQL

Used for:

- Data querying
- Joins
- Aggregations
- Business analysis

---

## Python

Used for:

- Data cleaning
- Handling missing values
- Removing duplicates
- Data preprocessing

### Libraries Used

```python
import pandas as pd
import numpy as np
```

---

## Power BI

Used for:

- Dashboard creation
- Data visualization
- DAX calculations
- Interactive reporting

---

# Dataset Information

The project uses two tables:

---

## 1️⃣ Orders Table

| Column Name | Description |
|-------------|-------------|
| Order ID | Unique order ID |
| Order Date | Date of order |
| CustomerName | Customer name |
| State | State |
| City | City |

---

## 2️⃣ OrderDetails Table

| Column Name | Description |
|-------------|-------------|
| Order ID | Unique order ID |
| Amount | Sales amount |
| Profit | Profit |
| Quantity | Product quantity |
| Category | Product category |
| Sub-Category | Product sub-category |
| PaymentMode | Payment method |
| AOV | Average order value |

---

#  Python Data Cleaning

Python was used before importing data into Power BI.

## Tasks Performed

- Removed duplicates
- Handled missing values
- Corrected data types
- Formatted dates
- Cleaned column names

---

##  Python Cleaning Script

```python
import pandas as pd
import numpy as np

# Load datasets
orders = pd.read_csv("Orders.csv")
details = pd.read_csv("OrderDetails.csv")

# Remove duplicates
orders.drop_duplicates(inplace=True)
details.drop_duplicates(inplace=True)

# Remove null values
orders.dropna(inplace=True)
details.dropna(inplace=True)

# Convert date column
orders['Order Date'] = pd.to_datetime(orders['Order Date'])

# Clean column names
orders.columns = orders.columns.str.strip()
details.columns = details.columns.str.strip()

# Export cleaned files
orders.to_csv("Cleaned_Orders.csv", index=False)
details.to_csv("Cleaned_OrderDetails.csv", index=False)

print("Data Cleaning Completed")
```

---

#  SQL Analysis

SQL was used to analyze and query the datasets before visualization.

---

#  SQL Table Creation

## Create Orders Table

```sql
CREATE TABLE Orders (
    Order_ID INT PRIMARY KEY,
    Order_Date DATE,
    CustomerName VARCHAR(100),
    State VARCHAR(50),
    City VARCHAR(50)
);
```

---

## Create OrderDetails Table

```sql
CREATE TABLE OrderDetails (
    Order_ID INT,
    Amount FLOAT,
    Profit FLOAT,
    Quantity INT,
    Category VARCHAR(50),
    Sub_Category VARCHAR(50),
    PaymentMode VARCHAR(50),
    AOV FLOAT
);
```

---

#  SQL Queries for Data Analysis

## 1️⃣ Total Sales

```sql
SELECT SUM(Amount) AS Total_Sales
FROM OrderDetails;
```

---

## 2️⃣ Total Profit

```sql
SELECT SUM(Profit) AS Total_Profit
FROM OrderDetails;
```

---

## 3️⃣ Top States by Sales

```sql
SELECT o.State,
       SUM(d.Amount) AS Total_Sales
FROM Orders o
JOIN OrderDetails d
ON o.Order_ID = d.Order_ID
GROUP BY o.State
ORDER BY Total_Sales DESC;
```

---

## 4️⃣ Category-wise Quantity Sold

```sql
SELECT Category,
       SUM(Quantity) AS Total_Quantity
FROM OrderDetails
GROUP BY Category;
```

---

## 5️⃣ Payment Mode Analysis

```sql
SELECT PaymentMode,
       COUNT(*) AS Total_Orders
FROM OrderDetails
GROUP BY PaymentMode
ORDER BY Total_Orders DESC;
```

---

## 6️⃣ Monthly Profit Analysis

```sql
SELECT MONTH(o.Order_Date) AS Month,
       SUM(d.Profit) AS Monthly_Profit
FROM Orders o
JOIN OrderDetails d
ON o.Order_ID = d.Order_ID
GROUP BY MONTH(o.Order_Date)
ORDER BY Month;
```

---

# 📈 Power BI Dashboard Features

## ✅ KPI Cards

Displays:

- Total Sales
- Total Profit
- Total Quantity
- Average Order Value

---

## ✅ State-wise Sales Analysis

---

## ✅ Category-wise Quantity Analysis

---

## ✅ Monthly Profit Trend

---

## ✅ Customer-wise Sales Analysis

---

## ✅ Payment Mode Analysis

---

## ✅ Sub-Category Profit Analysis

---

# 📊 DAX Calculations in Power BI

## Total Sales

```DAX
Total Sales = SUM(OrderDetails[Amount])
```

---

## Total Profit

```DAX
Total Profit = SUM(OrderDetails[Profit])
```

---

## Total Quantity

```DAX
Total Quantity = SUM(OrderDetails[Quantity])
```

---

## Average Order Value

```DAX
Average AOV = AVERAGE(OrderDetails[AOV])
```

---

# 🔗 Data Modeling

Create relationship between:

- `Orders[Order ID]`
- `OrderDetails[Order ID]`

### Relationship Type

- One-to-Many

---

# 🛠 Step-by-Step Workflow

## Step 1: Collect Dataset

## Step 2: Clean Data Using Python

## Step 3: Analyze Data Using SQL

## Step 4: Import Cleaned Data into Power BI

## Step 5: Create Relationships

## Step 6: Create DAX Measures

## Step 7: Build Dashboard Visualizations

## Step 8: Add Interactive Filters

### Filters Used

- Quarter
- State

---

# Dashboard Design

- Dark Purple Theme
- Interactive Charts
- Clean Layout
- Business Dashboard UI

---

# Key Insights

- Maharashtra generated highest sales.
- Clothing category sold highest quantity.
- COD was most preferred payment mode.
- Printers generated highest profit.
- Monthly profit fluctuated throughout the year.

---

# Skills Demonstrated

## SQL Skills

- Joins
- Aggregations
- Group By
- Business Queries

---

## Python Skills

- Data Cleaning
- Pandas
- NumPy

---

## Power BI Skills

- Data Modeling
- Dashboard Design
- Data Visualization

---

# Learning Outcomes

You will learn:

- SQL for data analysis
- Python for preprocessing
- Power BI dashboard development
- DAX calculations
- Business intelligence reporting

---

# Future Improvements

- Add SQL Database Connection
- Add Predictive Analytics
- Add Forecasting
- Add Customer Segmentation
- Real-time Dashboard Integration

---

#  Conclusion

This project demonstrates a complete end-to-end **Data Analytics workflow** using:

- SQL for querying
- Python for data cleaning
- Power BI for visualization

It is an excellent portfolio project for:

- Data Analyst roles
- Business Analyst roles
- Power BI Developer roles
- Entry-level Data Scientist roles


---

#  Author

**Priyanshu Tiwari**  
Data Analytics & Power BI Enthusiast
