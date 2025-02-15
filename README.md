# **E-Commerce Data Analysis in Databricks**

## **Project Overview**
This project involves analyzing customer purchasing behavior from an **E-Commerce dataset** using **Databricks, PySpark, and SQL**. The goal was to **ingest, transform, analyze, and optimize** the dataset for business insights. Key tasks include **data ingestion, exploratory data analysis (EDA), data cleaning, feature engineering, and normalization**.

The project is structured to help understand **customer behavior, sales trends, product demand, and payment preferences** using structured data processing techniques.

---

## **Dataset Description**
The dataset consists of **51,290 records** containing transactional information from an e-commerce platform over a **one-year period**. Below are the key features:

| **Column Name**         | **Description** |
|-------------------------|----------------|
| Order_Date             | The date when the order was placed. |
| Time                   | Timestamp of order. |
| Aging                  | Time taken for delivery (days). |
| Customer_Id            | Unique customer identifier. |
| Gender                 | Gender of the customer. |
| Device_Type            | Device used for purchase (Web/Mobile). |
| Customer_Login_Type    | Type of login (Member/Guest). |
| Product_Category       | Category of the purchased product. |
| Product               | Name of the product. |
| Sales                 | Total sales amount. |
| Quantity              | Number of units sold. |
| Discount              | Discount applied. |
| Profit                | Profit earned from the sale. |
| Shipping_Cost         | Cost of shipping. |
| Order_Priority        | Priority level of the order (Critical/High/Medium/Low). |
| Payment_Method        | Method used for payment. |

The dataset was stored and processed in **Delta format in Databricks**.

---

## **Project Workflow**

### **Task 1: Data Ingestion**
- **Uploaded** the CSV file to **Databricks File Store (DBFS)**.
- **Created a Delta table** in the **Hive Metastore** for structured querying.
- **Partitioned the table** by `Order_Date` and `Product_Category` for better performance.

### **Task 2: Exploratory Data Analysis (EDA)**
- Counted the total records.
- Identified **missing values**.
- Calculated **summary statistics** (min, max, mean, standard deviation) for numerical columns.
- Analyzed the **distribution of categorical variables** such as device type, payment method, and product categories.

### **Task 3: Handling Missing Values**
- Identified missing values in `Sales` and filled them using **mean imputation**.
- Used `COALESCE` to replace NULL values in categorical fields.

### **Task 4: Feature Engineering**
- **Standardized date format** (`YYYY-MM-DD`).
- Extracted `Year`, `Month`, and `Day` from `Order_Date`.
- Created a new `Profit_Margin` column.
- Categorized sales values into `Low`, `Medium`, and `High` segments.

### **Task 5: Categorical Variable Encoding**
- Applied **One-Hot Encoding (OHE)** to categorical columns (`Gender`, `Device_Type`, `Payment_Method`, `Order_Priority`).

### **Task 6: Normalization of Numerical Variables**
- Applied **Min-Max Scaling** to standardize `Sales`, `Quantity`, `Discount`, `Profit`, `Shipping_Cost`, and `Aging`.

---

## **Technical Stack Used**
### **Technologies & Tools**
- **Databricks** (for data processing and storage)
- **Apache Spark (PySpark & SQL)** (for big data processing)
- **Delta Lake** (for efficient data storage and retrieval)
- **Python (Pandas, Matplotlib)** (for data visualization)
- **Git & GitHub** (for version control)

---

## **Results & Insights**
### **1. Customer Behavior Insights**
✔ Most customers prefer **Web-based transactions (92.9%)** over Mobile (7.1%).
✔ **Fashion** is the highest-selling product category.
✔ **Credit Cards** are the most popular payment method (74.3% of transactions).

### **2. Sales & Profitability Insights**
✔ **High-priority orders** account for **38.2%**, indicating demand for fast shipping.
✔ **Profit margins are highest in Fashion & Home & Furniture categories**.
✔ **Discounts significantly impact customer purchase behavior.**

### **3. Data Processing Efficiency**
✔ **Partitioning by `Order_Date` and `Product_Category` improved query performance.**
✔ **One-hot encoding enabled categorical variables for machine learning models.**
✔ **Normalization ensured uniform scaling of numerical values.**


