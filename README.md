# Olist E-Commerce Sales Analysis Dashboard

## Project Overview

The dashboard is designed to help analyze retail operations across the Brazilian e-commerce landscape.
It highlights key performance indicators (KPIs), seasonal sales trends, product category performance, and geographic customer distribution.

The project demonstrates skills in:
- Excel Data Cleaning (Power Query)
- Data Modeling (Power Pivot)
- KPI Cards & Conditional Formatting
- Slicers & Interactive Filters
- Data Visualization
- Dashboard Formatting

## Dataset Description

The dataset consists of 9 relational CSV files provided by Olist. It covers the entire order journey: from purchase to payment, shipping, and customer review.

## Data Dictionary

| Table Name | Description |
|:---|:---|
| olist_orders_dataset | Core table containing Order ID, status, timestamps (purchase, approval, delivery). |
| olist_order_items_dataset | Details of items within an order (Product ID, Price, Freight Value, Seller ID). |
| olist_products_dataset | Product metadata including category name, weight, and dimensions. |
| olist_customers_dataset | Customer demographic info (City, State, Zip Code). |
| olist_order_payments_dataset | Payment details (Method: Credit Card/Voucher, Installments, Transaction Value). |
| olist_order_reviews_dataset | Customer satisfaction data (Review Score 1-5, Comments). |
| olist_sellers_dataset | Seller location and ID information. |
| olist_geolocation_dataset | Latitude and Longitude coordinates for mapping customers and sellers. |
| product_category_translation | Translations of category names from Portuguese to English. |

## Dashboard Preview

![Olist Dashboard Screenshot](https://github.com/AnveshDhamane/Olist-Store-Analysis-Excel/blob/b1c0dc543a9626e286355b1ac105ad71ab98f24e/Screenshot/Olist%20%20Store%20Excel%20Dashboard.png)

## Data Modeling

The data model follows a **Star Schema** architecture to optimize performance and simplify DAX calculations.

- **Fact Table:** `Order_Items` (Contains transactional data like Price, Freight, and Quantity).
- **Dimension Tables:** `Customers`, `Products`, `Sellers`, `Payments`, `Reviews`, and `Date` (Calendar).

![Data Model Screenshot](https://github.com/AnveshDhamane/Olist-Store-Analysis-Excel/blob/b1c0dc543a9626e286355b1ac105ad71ab98f24e/Screenshot/olist%20%20store%20data%20model.png)

### Model Details:
- **Relationships:** One-to-Many relationships are established between Dimension tables and the Fact table.
- **Star Schema:** The `Order_Items` table acts as the central fact table, connected to `Products`, `Sellers`, and `Orders`.
- **Snowflake Schema:** Used for the `Product_Category_Translation` table, which filters the `Products` table to provide English category names.
- **Date Table:** A dedicated Date table was created using DAX to handle time-intelligence functions accurately.

## Features

### 1. Key KPIs
- Total Revenue (15.42M)
- Total Orders (96K+)
- Average Order Value (120.65)
- Total Freight Cost (2.2M)
- Delivery Success Rate

### 2. Visual Insights
- Monthly Sales & Seasonality Trends
- Top 5 Revenue-Generating Categories
- Geographic Heatmap (Sales by State)
- Payment Method Distribution
- Customer Satisfaction (Review Scores)

### 3. Interactive Filters
- Year & Month
- Customer State (Region)
- Product Category
- Order Status

## Tools Used

- Microsoft Excel
- Power Query (ETL)
- Power Pivot (Data Modeling)
- PivotTables & PivotCharts
- Slicers and Timelines

## Key Insights

### 1. Strong Seasonality
Sales show a consistent upward trend with a significant spike in **November 2017**, attributed to Black Friday promotions.

### 2. Top Performing Categories
"Bed, Bath & Table" and "Health & Beauty" are the highest revenue-generating categories.

### 3. Geographic Concentration
**Sao Paulo (SP)** is the dominant market, accounting for the vast majority of orders compared to other states.

### 4. Credit Card Dominance
Customers overwhelmingly prefer **Credit Cards** for transactions, likely due to installment options.

### 5. High Delivery Success
Over 97% of orders are successfully delivered, indicating a stable logistics network.

### 6. Customer Satisfaction
Review scores are skewed towards 5 stars, showing general satisfaction with the products and service.

## Recommendations

### 1. Optimize Q4 Inventory
Prepare higher stock levels for "Bed & Bath" and "Beauty" categories specifically for November.

### 2. Expand Logistics Outside SP
While Sao Paulo is well-served, high freight costs in other states may be limiting growth.

### 3. Promote Installment Plans
Marketing campaigns should highlight installment payment options to increase Average Order Value (AOV).

### 4. Target Under-Performing States
Launch localized marketing campaigns in Rio de Janeiro (RJ) and Minas Gerais (MG) to capture market share.

### 5. Cross-Selling Strategy
Implement bundle offers for top categories to further increase the 120.65 Average Order Value.

### 6. Monitor Freight Costs
Analyze item dimensions and courier contracts to reduce the significant 2.2M total freight expense.
