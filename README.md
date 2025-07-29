# SHRA-B-Sales-Analytics-Dashboard
An interactive Power BI dashboard to analyze sales data, identify trends, top-selling products, and revenue metrics — supporting data-driven business decisions.  
> Built as part of the **Meriskill Internship Project**.

---

## Purpose
Analyze sales data to identify trends, best-selling products, and revenue metrics for better business decision-making.

---

## Dataset Overview

The dataset contains these columns:

- ORDER ID  
- PRODUCT  
- QUANTITY ORDERED  
- PRICE EACH  
- ORDER DATE  
- PURCHASE ADDRESS  
- MONTH  
- SALES  
- CITY  
- HOUR  

 Dataset: [Sales Dataset.zip](./Sales%20Dataset.zip)

---

## Project Files

| File Name                  | Description                                  |
|----------------------------|----------------------------------------------|
| `Sales Data Dashboard.png` | Screenshot of the Power BI dashboard          |
| `Sales Data Dashboard.pdf` | PDF export of the Power BI dashboard          |
| `Sales Dataset.zip`        | Compressed sales dataset (CSV inside)         |
| `README.md`                | This documentation file                        |
| `LICENSE`                  | MIT License file                              |

---

##  Step-by-Step Execution

###  Load Data  
- Download and extract the dataset from `Sales Dataset.zip`.  
- Open **Power BI Desktop**.  
- Click **Get Data > Text/CSV**, then select your extracted CSV file to load.

###  Transform Data  
- Promote first row as headers.  
- Use **Transform > Detect Data Type** to automatically set correct types.  
- Split the `ORDER DATE` column into **Date** and **Time** by splitting at the space delimiter:  
  - Select the column → **Split Column** → **By Delimiter** → choose space → split into two columns.  
- After transformations, click **Close & Apply**.

### Create Visualizations  

- **Sales Trend Over Time (Line Chart)**  
  - Drag `MONTH` and `SALES` to the line chart.  
  - Sort months chronologically by selecting `MONTH` column, go to **Column Tools > Sort by Column > MONTH NUMBER**.

- **Best-Selling Products (Tree Map)**  
  - Drag `PRODUCT` and `QUANTITY ORDERED` to create a tree map visualization.  
  - Adjust colors and fonts in the **Format** pane.

- **Top 5 Best-Selling Products (Stacked Bar Chart)**  
  - Drag `PRODUCT` to Y-axis, `QUANTITY ORDERED` to X-axis.  
  - Filter to top 5 products.

- **Top 5 Cities by Sales (Map Visualization)**  
  - Drag `CITY` and `SALES` to map visual.  
  - Format as desired.

- **Weekly Sales Distribution (Column Chart)**  
  - Use weekday data and sales quantity to build a column chart.

- **Slicer for Month Filter**  
  - Drag `MONTH` to the slicer visual.  
  - Adjust slicer to dropdown or vertical list as preferred.

### Revenue Metrics (Cards)

- **Total Sales**  
  - Create a card visual, drag `SALES` field, set aggregation to **SUM**.

- **Sales Quantity**  
  - Card visual with `QUANTITY ORDERED` summed.

- **Profit Margin**  
  - Create a new measure using this formula:

  ```DAX
  Profit Margin = ((SUM(Sales) - SUM(Total Cost)) / SUM(Sales)) * 100
