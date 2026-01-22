### Customer Analytics & Churn Prediction - SQL Queries All in One

import pandas as pd
import sqlite3
import os

# 1️⃣ Create folder for SQL outputs
os.makedirs("sql_outputs", exist_ok=True)

# 2️⃣ Load cleaned datasets from data folder
retail = pd.read_csv("data/retail_cleaned.csv")
support = pd.read_csv("data/support_cleaned.csv")
telco = pd.read_csv("data/telco_cleaned.csv")

# 3️⃣ Create SQLite in-memory database
conn = sqlite3.connect(":memory:")

# Load dataframes into SQLite
retail.to_sql("retail", conn, index=False, if_exists="replace")
support.to_sql("support", conn, index=False, if_exists="replace")
telco.to_sql("telco", conn, index=False, if_exists="replace")

# -------------------------------
# 4️⃣ QUERY 1: Total Revenue by Country
query1 = """
SELECT Country,
       ROUND(SUM(TotalAmount), 2) AS TotalRevenue
FROM retail
WHERE Country IS NOT NULL
GROUP BY Country
ORDER BY TotalRevenue DESC;
"""
revenue_country = pd.read_sql(query1, conn)
revenue_country.to_csv("sql_outputs/revenue_country.csv", index=False)
print("Query 1 executed and saved: revenue_country.csv")

# -------------------------------
# 5️⃣ QUERY 2: Top 10 Customers by Total Spent
query2 = """
SELECT "Customer ID",
       ROUND(SUM(TotalAmount), 2) AS TotalSpent,
       COUNT(*) AS TotalOrders
FROM retail
GROUP BY "Customer ID"
ORDER BY TotalSpent DESC
LIMIT 10;
"""
top_customers = pd.read_sql(query2, conn)
top_customers.to_csv("sql_outputs/top_customers.csv", index=False)
print("Query 2 executed and saved: top_customers.csv")

# -------------------------------
# 6️⃣ QUERY 3: Monthly Revenue Trends
query3 = """
SELECT STRFTIME('%Y-%m', InvoiceDate) AS YearMonth,
       ROUND(SUM(TotalAmount), 2) AS MonthlyRevenue
FROM retail
GROUP BY YearMonth
ORDER BY YearMonth;
"""
monthly_revenue = pd.read_sql(query3, conn)
monthly_revenue.to_csv("sql_outputs/monthly_revenue.csv", index=False)
print("Query 3 executed and saved: monthly_revenue.csv")

# -------------------------------
# 7️⃣ QUERY 4: Customers with Most Support Tickets
query4 = """
SELECT s."Customer Name",
       COUNT(s."Ticket ID") AS TotalTickets
FROM support s
GROUP BY s."Customer Name"
ORDER BY TotalTickets DESC
LIMIT 10;
"""
top_support_customers = pd.read_sql(query4, conn)
top_support_customers.to_csv("sql_outputs/top_support_customers.csv", index=False)
print("Query 4 executed and saved: top_support_customers.csv")

# -------------------------------
# 8️⃣ QUERY 5: Top Products by Revenue
query5 = """
SELECT Description AS ProductName,
       SUM(TotalAmount) AS RevenueGenerated,
       COUNT(*) AS UnitsSold
FROM retail
GROUP BY ProductName
ORDER BY RevenueGenerated DESC
LIMIT 10;
"""
top_products = pd.read_sql(query5, conn)
top_products.to_csv("sql_outputs/top_products.csv", index=False)
print("Query 5 executed and saved: top_products.csv")

# -------------------------------
# 9️⃣ QUERY 6: Top 5 Ticket Types
query6 = """
SELECT [Ticket Type] AS TicketType,
       COUNT(*) AS TotalTickets
FROM support
GROUP BY [Ticket Type]
ORDER BY TotalTickets DESC
LIMIT 5;
"""
ticket_type = pd.read_sql(query6, conn)
ticket_type.to_csv("sql_outputs/ticket_type.csv", index=False)
print("Query 6 executed and saved: ticket_type.csv")

# -------------------------------
# 1️⃣0️⃣ QUERY 7: Average Resolution Time by Ticket Type
query7 = """
SELECT [Ticket Type] AS TicketType,
       ROUND(AVG([Time to Resolution]),2) AS AvgResolutionHours,
       COUNT(*) AS TotalTickets
FROM support
GROUP BY [Ticket Type]
ORDER BY AvgResolutionHours DESC;
"""
resolution_time = pd.read_sql(query7, conn)
resolution_time.to_csv("sql_outputs/resolution_time.csv", index=False)
print("Query 7 executed and saved: resolution_time.csv")

# -------------------------------
# 1️⃣1️⃣ QUERY 8: Customer Satisfaction by Ticket Priority
query8 = """
SELECT [Ticket Priority] AS Priority,
       ROUND(AVG([Customer Satisfaction Rating]),2) AS AvgSatisfaction,
       COUNT(*) AS TotalTickets
FROM support
GROUP BY [Ticket Priority]
ORDER BY AvgSatisfaction DESC;
"""
satisfaction_priority = pd.read_sql(query8, conn)
satisfaction_priority.to_csv("sql_outputs/satisfaction_priority.csv", index=False)
print("Query 8 executed and saved: satisfaction_priority.csv")

# -------------------------------
# 1️⃣2️⃣ QUERY 9: Churn Rate by Contract Type
query9 = """
SELECT Contract,
       ROUND(AVG(Churn_flag)*100,2) AS ChurnRatePercentage,
       COUNT(*) AS TotalCustomers
FROM telco
GROUP BY Contract
ORDER BY ChurnRatePercentage DESC;
"""
churn_contract = pd.read_sql(query9, conn)
churn_contract.to_csv("sql_outputs/churn_contract.csv", index=False)
print("Query 9 executed and saved: churn_contract.csv")

# -------------------------------
# 1️⃣3️⃣ QUERY 10: Monthly Charges by Contract Type
query10 = """
SELECT Contract,
       ROUND(AVG(MonthlyCharges),2) AS AvgMonthlyCharges,
       COUNT(*) AS TotalCustomers
FROM telco
GROUP BY Contract
ORDER BY AvgMonthlyCharges DESC;
"""
monthly_contract = pd.read_sql(query10, conn)
monthly_contract.to_csv("sql_outputs/monthly_contract.csv", index=False)
print("Query 10 executed and saved: monthly_contract.csv")

# -------------------------------
print("\n All 10 queries executed successfully! Outputs saved.")
