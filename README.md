# Sales Analysis: Power BI Dashboard 

## Project Overview

This dashboard is built to analyze and visualize sales data from AdventureWorksDW2019 using Direct Query mode, allowing for real-time data interaction. The goal is to provide clear insights into reseller sales, employee performance, product sales, and more across various dimensions such as time, territory, and reseller information.

## Dashboard Screenshots

Here are the main pages of the dashboard for visual reference:

### 1. Overview Page

The Overview Page provides a summary of key metrics like Total Sales, YoY %, QTD, and YTD sales. It also features a drillthrough button for exploring employee data.

![Overview](https://github.com/user-attachments/assets/0acc41ed-db16-4cc3-b17c-9417928be439)

### 2. Employee Drillthrough Page

The Employee Drillthrough Page shows detailed sales performance for a selected employee. This page is accessible via the drillthrough button on the Overview Page.

![Employees Dashboard](https://github.com/user-attachments/assets/3439c36a-8e7a-4159-b592-09061df000f9)


### 3. Sales Breakdown Page

The Sales Breakdown Page explains total sales across different dimensions, including product categories, subcategories, and regions.

![Sales Breakdown](https://github.com/user-attachments/assets/f2ab3a08-c50e-47b5-9913-99c8bb4de1c7)


## Data Setup

### Connecting to AdventureWorksDW2019

The dashboard uses **Direct Query mode** to connect with `AdventureWorksDW2019`. After connecting, I performed data transformations like removing unnecessary columns renaming columns for clarity, and more. A `_Measure` table was created to store all custom measures used in the report.

**Data Warehouse Link:** [AdventureWorksDW2019](https://learn.microsoft.com/en-us/sql/samples/adventureworks-install-configure?view=sql-server-ver16&tabs=ssms)

![PowerQuery](https://github.com/user-attachments/assets/c2ba3391-e7f5-4104-a75a-ff0a436ab8d2)


### Converting Binary Data to Base64 for Image Display

To display images stored as binary data in SQL Server, I converted the binary column to **Base64** format. This conversion allows images to be visualized directly within Power BI visuals Direct Query Mode.

![Binary Data to Base64](https://github.com/user-attachments/assets/e53c20a4-b478-4ad9-9f6a-8796de36f673)


### Dimensional Modeling & Star Schema

The core of this dashboard is built using a **star schema**. The **FactResellerSales** table acts as the fact table, linked to several dimension tables:
- Date Dimensions: `Ship Date`, `Order Date`, `Due Date` (role-playing dates)
- `Employee`
- `Product`
- `Reseller`
- `Sales Territory`

This setup allows for efficient querying and supports complex analysis.
![Modeling](https://github.com/user-attachments/assets/a273c5ad-d0a6-46dd-9910-4e414a4427b5)

## Key Components

### Date Dimension and Role-Playing Tables

**Role-playing dimensions** are used to manage different date filters (`Order Date`, `Ship Date`, `Due Date`) for sales analysis, allowing the same date table to filter data in various contexts.


### Time Intelligence Using DAX

**DAX time intelligence functions** include:
- `TOTALYTD` for year-to-date sales.
- `SAMEPERIODLASTYEAR` for year-over-year comparisons.

These functions help analyze sales trends over time.

### Row-Level Security

**Row-Level Security (RLS)** restricts data access based on user roles, ensuring sensitive information is only visible to authorized users.

![Row-Level Security](https://github.com/user-attachments/assets/0faad402-6b89-422b-a15d-355c1ca8c5d7)


### Report Pages & Drillthroughs

The dashboard includes:
- **Overview Page**: Displays key metrics and includes a drillthrough button.
- **Employee Drillthrough Page**: Shows detailed employee performance metrics.
- **Sales Breakdown Page**: Total sales explained across different dimensions
  
#### Employee Drillthrough Button

On the **Overview Page**, there is a button for users to **drill through to the Employee Drillthrough Page**. This feature provides detailed sales metrics for the selected employee.

![Drillthrough Button Page](https://github.com/user-attachments/assets/9a081542-e375-4ad3-9438-a296aea2be28)


### Custom Visuals and User Interaction

- **Custom Visuals**: Includes bullet charts and images for enhanced data visualization.
- **Slicer Panel**: Features buttons and bookmarks to toggle slicer visibility.

![Slicer Panel](https://github.com/user-attachments/assets/9379724d-087a-4505-a3b3-8e800675757b)


## Additional Features

- **Quick Measures**: Explored the concept of Quick Measure.
- **Drillthrough Buttons**: Facilitates smooth navigation between report pages.
- **Email Links in Tables**: Added clickable email links for direct communication with employees.

## Conclusion

This Power BI dashboard provides an interactive and detailed view of reseller sales, helping stakeholders understand sales performance through various dimensions. The use of DAX, custom visuals, dimensional modeling, and interactive features like the slicer panel and bookmarks ensures a practical tool for sales analysis.

