# PowerBI Project: AdventureWorks Dataset Analysis

## Overview
This PowerBI project leverages the AdventureWorks dataset using DirectQuery mode to provide comprehensive insights into sales performance. Through  data transformations, modeling techniques, visualization strategies, analysis perspectives, and utilization of various PowerBI functionalities, this project offers an intuitive interface for users to analyze sales data efficiently.

## Dataset
The dataset comprises several tables from the AdventureWorks database, including `Sales.SalesOrderHeader`, `Sales.SalesOrderDetail`, `Sales.vSalesPerson`, `Sales.SalesTerritory`, `Purchasing.ShipMethod`, `Production.Product`, `Production.ProductSubcategory`, and `Production.ProductCategory`. 

## Preprocessing
### Tables Renaming and Column Cleanup
- Renamed tables and columns for clarity and consistency.
- Removed unused columns to streamline data processing.

### Product Hierarchy
- Created a single table merging `Production.Product`, `Production.ProductSubcategory`, and `Production.ProductCategory` using M Language.
- Output includes ProductID, Product, SubCategory, and Category for enhanced analysis.
- Utilized Power Query to calculate TotalDue, Tax, and Freight.

## Data Modeling
- Implemented a Star Schema for efficient data representation and querying.
- Established a Product Hierarchy for better understanding of product relationships.

## Measures
- Defined various measures to facilitate analysis:
  - # Orders
  - Total SubTotal
  - Total Tax
  - Total Freight
  - Total Due
  - # Qty
- Created a DAX table containing all measures for easy reference.

## Visualizations
- Utilized measures to generate insightful visuals:
  - Drill Down
  - Drill Through
  - Tooltip page
- Implemented visually appealing and informative visuals with meaningful titles and layouts.

## Insights
- Analyzed # Orders by OrderDate, ShipDate, and DueDate.
- Examined # Orders by Status, Shipmethod, Category, SubCategory, and Product.
- Investigated # Orders vs. TotalDue by Territory.
- Identified Top 10 Sales Persons based on # Orders or Total Amount with filter options.

## Dashboard Visuals

![Adventureworks_page-0001](https://github.com/sarax0/adventureworks-sales-analysis-powerbi/assets/122404545/deb16a51-ab32-405e-be4f-56505dc56276)

![Adventureworks_page-0002](https://github.com/sarax0/adventureworks-sales-analysis-powerbi/assets/122404545/c6a257d4-ee4a-4d13-a0c3-feb354818ab9)

## Conclusion
This PowerBI project provides a robust platform for analyzing AdventureWorks sales data. By employing effective data modeling techniques, comprehensive measures, and insightful visualizations, users can gain valuable insights into sales performance, product hierarchy, and key metrics. The intuitive interface and interactive features enhance usability, making it a valuable tool for decision-making and strategic planning.

