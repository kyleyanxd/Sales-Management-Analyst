# 📊 Sales Management & Internet Sales Performance Analysis

## 📌 Project Overview
This end-to-end data analytics project transforms raw database records into actionable business insights and interactive dashboards. Built to satisfy a real-world business request from executive sales management, the project cleanses, models, and visualizes internet sales performance against targeted budgets across products, customers, and time periods.

---

## 📩 Business Request & User Stories

### Business Request
The executive team requested a transition from static spreadsheet reporting to interactive Power BI dashboards. The key goal is to track **who** is buying, **what** products are driving revenue, and **how** actual performance compares against predefined **2021 budget targets** across a multi-year timeline.

### User Stories
| No | As a (Role) | I want (Request / Demand) | So that I (User Value) | Acceptance Criteria |
|:---|:---|:---|:---|:---|
| **1** | Sales Manager | A dashboard overview of internet sales | Better track top-performing products and customers | Power BI dashboard updated daily |
| **2** | Sales Representative | Detailed customer sales overview | Identify top accounts and expansion opportunities | Dynamic filtering per customer |
| **3** | Sales Representative | Detailed product sales overview | Focus sales efforts on highest-grossing items | Dynamic filtering per product |
| **4** | Sales Manager | Visual sales tracking vs. budget targets | Evaluate revenue performance against targets over time | KPI cards and comparative line charts |

---

## 🛠️ Data Architecture & Process Flow

```text
[ Microsoft SQL Database ] ➔ [ SQL Cleansing & Transformation ] ➔ [ CSV Export ] ➔ [ Data Modeling in Power BI ] ➔ [ Interactive Dashboards ]

1. Database Setup & SQL Maintenance
Data Source: Microsoft AdventureWorksDW2019.bak database. (Note: Due to GitHub's file size limit, download the .bak file directly from Microsoft's Sample Database Documentation).

Executed maintenance scripts (Update_table.sql) to prepare table structures for analysis.

2. Data Cleansing & Transformation (SQL)
Using SQL scripts (available in the Sql Queries/ directory), raw data tables were cleaned, joined, and standardized:

DIM_Calendar_v2.sql: Filtered relevant date attributes (Year, Quarter, Month, Weekday) spanning the 2-year lookback period.

DIM_Customer_v2.sql: Joined customer details with geography dimensions to produce full names and geographic locations.

DIM_Productv2.sql: Joined product master tables with subcategories and main categories; replaced null values with standardized category labels.

DIM_FactInternetSales.sql: Extracted transaction-level sales data restricted to the required hi<img width="889" height="503" alt="Sales Report Dashboard" src="https://github.com/user-attachments/assets/658fdbd9-6774-4bcb-a0ee-6144515b1093" />
storical time frame.

3. Data Integration & Modeling
Filtered datasets were exported to CSV format and loaded into Power BI.

Integrated Excel-based budget targets for fiscal year 2021.

Established star-schema relationships between Fact and Dimension tables in Power BI.

📉 Power BI Dashboards & Visual Insights
1. Sales Overview Dashboard
<img width="889" height="503" alt="Sales Report Dashboard" src="https://github.com/user-attachments/assets/a095b3cc-9a50-402e-88d5-57814146f7c5" />

KPI Highlights: Tracks total revenue ($22M) vs. target budget ($21M) with variance percentage (+24.94% over current targets).

Sales Trends: Tracks actual sales against monthly budget baselines.

Product Breakdown: Donut chart highlighting Bikes as the primary revenue driver (~95.3%).

2. Customer Details Dashboard
<img width="867" height="485" alt="Customer Details" src="https://github.com/user-attachments/assets/9a1eba3c-d272-4489-9fca-566fc5bade6a" />

Customer Leaderboard: Visualizes the Top 10 revenue-generating customers (led by Jordan Turner).

Geographic Mapping: Displays customer density across global sales regions.

Granular Matrix: Interactive table showing month-by-month spending patterns per customer.

3. Product Details Dashboard
<img width="865" height="477" alt="product Details" src="https://github.com/user-attachments/assets/afa6a044-2bd4-41aa-ad1a-2e994b5a8edc" />

Top Performers: Ranks top-selling product models (featuring Mountain-200 and Road-250 lines).

Monthly Demand Matrix: Categorical breakdown table tracking product performance month-by-month to uncover seasonality.
