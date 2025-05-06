# 📊 AdventureWorksLT Sales Report - Power BI

This Power BI report is built using **AdventureWorksLT database** to provide insights into sales data. The report includes data shaping, combining, and visualizations to empower business decision-making.

## ✅ Tasks Completed

### 📥 Data Connection & Shaping
- **Connected to the AdventureWorksLT database**:
  - Loaded **Task 1** and **Task 2** queries from the provided **Labexercise1.SQL** file.
  - Renamed Queries:
    - `Query 1` to **Customers**
    - `Query 2` to **Sales**
  - Data cleanup and transformations in the **Customers** table:
    - Removed columns: `NameStyle`, `SalesPerson`
    - Hidden `CustomerID` column in Report view
    - Changed data categories:
      - `AddressLine1` → Address
      - `City` → City
      - `StateProvince` → State or Province
      - `CountryRegion` → Country/Region
      - `PostalCode` → Postal Code
  - Added a calculated column: **FullAddress** (concatenates `AddressLine1`, `City`, `StateProvince`, `CountryRegion`, `PostalCode`).
  
- Data cleanup and transformations in the **Sales** table:
  - Removed columns: `RevisionNumber`, `SalesOrderNumber`
  - Hidden `CustomerID`, `SalesOrderID`, `SalesOrderDetailID` columns in Report view
  - Added a calculated column: **LineTotal** (multiplying `OrderQty` by `ListPrice` and formatted as Currency)
  - Created a measure: **TargetSales** (LineTotal increased by 2%)

### 🔗 Data Combination
- Created a new table **Sales by States** by importing data from Wikipedia:
  - Removed unnecessary rows (first 3 and last 26).
  - Renamed columns and merged with **Sales by States** using **State Code Long**.
  - Set privacy level to **Organizational**.
  - Renamed new column as **State Code** and hid it in the Report view.

### 📊 Visualizations
- **Gauge Chart**: Created a gauge chart using `LineTotal` for the value and `TargetSales` for the target, with a max value of **1460000** and labeled as **Target Sales**.
- **Pie Chart**: Created a pie chart of **Top Selling Companies** by `CompanyName` and `LineTotal`, center-aligned.
- **Stacked Bar Chart**: Created a stacked bar chart for **Sales by Main Category**, using `MainCategory` and `OrderQty`, center-aligned with a red **Constant Line** at 500.
- **Donut Chart**: Created a donut chart for **Sales by Main Category**, using `MainCategory` and `LineTotal`, center-aligned.
- **Stacked Column Chart**: Created a stacked column chart for **Top Selling Bikes**, filtered to only products with sales greater than $32,000 and filtered to display only ‘bikes’. Added a red constant line at **35000**.
- **Map Visuals**:
  - **World Sales by City**: Created a map visual with `City` and `LineTotal`.
  - **Sales by State**: Created a map visual with `State Code` and `SalesYTD`.

### 📁 File
- `AdventureWorksLT sales 5.pbix`: Power BI report file

## 💻 How to Use
1. Open the `.pbix` file in **Power BI Desktop**.
2. Explore the data transformations, relationships, and visualizations.
3. Customize the visuals and interact with the report to get insights.
