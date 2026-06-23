# Smart Device Sales Dashboard

## 📊 Project Overview

The **Smart Device Sales Dashboard** is an interactive Power BI project designed to analyze sales performance across various smart devices and accessories. The dashboard provides insights into revenue, orders, customer behavior, delivery status, product ratings, and overall business performance.

This project demonstrates data modeling, DAX calculations, KPI tracking, and interactive visualizations to support data-driven decision-making.

---

## 🎯 Objectives

* Monitor overall sales performance.
* Track total revenue and order volume.
* Analyze delivered and cancelled orders.
* Identify top-performing products.
* Evaluate customer purchasing behavior.
* Understand the impact of product ratings on sales.

---

## 📂 Dataset Information

### Customer Table

Contains customer-related information such as:

* Customer ID
* Customer Name
* Location
* Contact Details

### Orders Table

Contains transaction-related information:

* Order ID
* Customer ID
* Product ID
* Quantity
* Order Status
* Order Date

### Product Table

Contains product-related information:

* Product ID
* Product Name
* Category
* Price
* Rating

---

## 🏗 Data Model

The dashboard follows a star schema model:

* Customer Table → Orders Table
* Product Table → Orders Table

Relationships are created using:

* CustomerID
* ProductID

---

## 📌 Key Performance Indicators (KPIs)

### Total Orders

Tracks the total number of orders placed.

### Delivered Orders

Shows successfully delivered orders.

### Cancelled Orders

Tracks cancelled orders.

### Total Revenue

Calculates revenue generated from product sales.

### Total Customers

Displays the total number of unique customers.

---

## 📈 Dashboard Visualizations

### Revenue by Product Name

Shows revenue contribution from each product.

### Total Orders by Price

Analyzes order distribution across price ranges.

### Orders by Delivery Status

Compares delivered and cancelled orders.

### Orders by Rating

Displays sales distribution based on product ratings.

### Product Performance Analysis

Compares product ratings and order volumes.

### Customer Distribution Treemap

Visualizes customer contribution across products.

---

## 🧮 DAX Measures

### Total Orders

```DAX
Total Orders = COUNTROWS('order')
```

### Total Customers

```DAX
Total Customers = DISTINCTCOUNT(customer[CustomerID])
```

### Revenue

```DAX
Revenue =
SUMX(
    'order',
    'order'[Quantity] * RELATED(Product[Price])
)
```

### Delivered Orders

```DAX
Delivered Orders =
CALCULATE(
    COUNTROWS('order'),
    'order'[Status] = "Delivered"
)
```

### Cancelled Orders

```DAX
Cancelled Orders =
CALCULATE(
    COUNTROWS('order'),
    'order'[Status] = "Cancelled"
)
```

---

## 🔍 Business Insights

* Delivered orders significantly outnumber cancelled orders.
* Revenue is concentrated among a few high-performing products.
* Product ratings influence customer purchasing decisions.
* Premium products contribute a major share of total revenue.
* Interactive filters allow detailed product and category analysis.

---

## 🛠 Tools & Technologies

* Power BI Desktop
* DAX (Data Analysis Expressions)
* Data Modeling
* CSV Files
* Power Query

---

## 🚀 Skills Demonstrated

* Data Cleaning
* Data Modeling
* DAX Calculations
* KPI Development
* Dashboard Design
* Business Intelligence
* Data Visualization

---

## 📷 Dashboard Preview

Add a screenshot of your dashboard here:

```md
![Dashboard Screenshot](dashboard.png)
```

---

## 👨‍💻 Author

**Ayush Kumar Verma**

* Aspiring Data Analyst
* Power BI Enthusiast
* Data Visualization Learner

---

## ⭐ Project Outcome

This dashboard helps businesses monitor sales performance, track operational efficiency, identify top-selling products, and make informed decisions through interactive visual analytics.
