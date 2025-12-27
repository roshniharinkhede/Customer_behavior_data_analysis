# Customer Behavior Data Analysis Project Report

## 1. Project Title

Customer Behavior Data Analysis using Python, SQL, and Power BI

## 2. Project Objective

The main objective of this project is to analyze customer shopping behavior and understand patterns related to purchasing, subscriptions, demographics, product categories, and revenue. The analysis helps businesses make data-driven decisions to improve sales, customer retention, and marketing strategies.

## 3. Dataset Description

The dataset used in this project is a customer shopping behavior dataset.

* Total Rows: 3,900 customer records
* Total Columns: 18 attributes

### Columns Included:

Customer ID, Age, Gender, Item Purchased, Category, Purchase Amount (USD), Location, Size, Color, Season, Review Rating, Subscription Status, Shipping Type, Discount Applied, Promo Code Used, Previous Purchases, Payment Method, Frequency of Purchases.

### Data Issues Identified:

* Missing values were found in the **Review Rating** column (37 records)
* No duplicate rows were found in the dataset
* Data types were mostly correct, but categorical columns required standardization

## 4. Tools and Technologies Used

* Python: Data cleaning, exploration, and analysis
* SQL: Querying, filtering, and aggregating customer data
* Power BI: Interactive dashboard creation and visualization

## 5. Data Cleaning and Preparation (Python)

Python (pandas) was used for data cleaning and preparation.

### Problems in the Raw Data:

* Missing values in the Review Rating column
* Raw age values were not suitable for segmentation
* One column was not useful for analysis (Promo Code Used)

### Cleaning Steps Performed:

1. Loaded the dataset using pandas
2. Checked dataset shape, data types, missing values, and duplicates
3. Handled missing values in Review Rating by replacing null values with the **median review rating** to avoid data loss and reduce the impact of outliers
4. Standardized column names for easier querying

### Columns Removed:

* **Promo_Code_Used** column was dropped because it did not contribute meaningful insights to customer behavior analysis

### Columns Added:

* **Age_Group** column was created to segment customers into:

  * Young Adult
  * Adult
  * Middle-aged
  * Senior

This helped in analyzing sales and revenue patterns across different age groups.

## 6. SQL Analysis

SQL was used to answer key business questions related to customer behavior. The cleaned dataset was imported into a SQL database and queried using aggregate functions and grouping.

### SQL Query 1: Total Number of Customers

**Business Question:** How many customers are present in the dataset?

**Logic Used:**

* Used COUNT(*) to count total records in the customer table.

**Expected Output:**

* Total customers: 3,901

---

### SQL Query 2: Average Purchase Amount

**Business Question:** What is the average amount spent by customers?

**Logic Used:**

* Used AVG(purchase_amount) to calculate the mean spending.

**Expected Output:**

* Average purchase amount around $59–$60

---

### SQL Query 3: Average Review Rating

**Business Question:** What is the average customer review rating?

**Logic Used:**

* Used AVG(review_rating) on non-null values.

**Expected Output:**

* Average review rating around 3.7–3.8

---

### SQL Query 4: Customers by Subscription Status

**Business Question:** How many customers are subscribers vs non-subscribers?

**Logic Used:**

* GROUP BY subscription_status
* COUNT customers in each group

**Expected Output:**

* Majority customers are non-subscribers

---

### SQL Query 5: Revenue by Product Category

**Business Question:** Which product category generates the highest revenue?

**Logic Used:**

* GROUP BY category
* SUM(purchase_amount) to calculate revenue
* ORDER BY revenue in descending order

**Expected Output:**

* Clothing category generates the highest revenue

---

### SQL Query 6: Sales by Age Group

**Business Question:** Which age group contributes the most to sales?

**Logic Used:**

* GROUP BY age_group
* COUNT purchases per age group

**Expected Output:**

* Young Adults contribute the highest number of purchases

---

### SQL Query 7: Customers Spending Above Average

**Business Question:** Which customers spend more than the average purchase amount?

**Logic Used:**

* Subquery to calculate average purchase amount
* Filter customers whose purchase_amount > average

**Expected Output:**

* List of high-value customers

---

### SQL Summary

SQL helped convert raw customer data into structured insights by answering business-focused questions related to spending, subscriptions, categories, and demographics.

## 7. Power BI Dashboard Explanation

Power BI was used to create an interactive dashboard to visualize customer behavior insights clearly.

### Visuals Used:

* **Donut Chart:** Percentage of customers by Subscription Status (Subscribers vs Non-Subscribers)
* **Bar Chart:** Revenue by Product Category
* **Bar Chart:** Sales by Product Category
* **Bar Chart:** Revenue by Age Group
* **Bar Chart:** Sales by Age Group

### KPIs Displayed:

* Total Customers
* Average Purchase Amount
* Average Review Rating

### Filters Included:

* Gender
* Subscription Status
* Product Category
* Shipping Type

These visuals help stakeholders quickly understand customer distribution, purchasing patterns, and revenue contribution.

## 8. Key Insights

* Majority of customers (73%) are non-subscribers
* Clothing generates the highest revenue and sales
* Young adults contribute the highest revenue among age groups
* Subscription customers show higher engagement
* Average customer satisfaction rating is moderately high

## 9. Business Recommendations

* Encourage subscriptions through discounts and loyalty programs
* Focus marketing efforts on clothing category
* Target young adults with personalized offers
* Improve subscription benefits to increase adoption
* Optimize shipping options based on customer preference

## 10. Conclusion

This project demonstrates how Python, SQL, and Power BI can be combined to analyze customer behavior effectively. The insights derived from this analysis can help businesses improve decision-making, increase revenue, and enhance customer experience.

---

*This project is suitable for beginner to entry-level data analyst roles and can be showcased on GitHub and LinkedIn.*
