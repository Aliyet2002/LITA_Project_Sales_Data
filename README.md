# LITA_Project_Sales_Data

## TABLE OF CONTENT

[Project Overview](#project-overview)

[Data Sources](#data-sources)

[Tools Used](#tools-used)

[Data Cleaning And Preparation](#data-cleaning-and-preparation)

[Exploratory Data Analysis](#exploratory-data-analysis)

[Data Analysis](#data-analysis)

[Data Visualisation](#data-visualisation)

[Summary](#summary)

## Project Overview
This data analysis project is the sales performance of a retail store.This analysis helps to identify trends, opportunities, and challenges, and provide actionable insights to improve sales performance.

## Data Sources
The type of sales data used is time-series sales data

## Tools Used

- Microsoft Excel

  i.  For Data cleaning

  ii. For Data Analysis

- SQL - Structured Query Language  
- Power Bi for data visualization  
- GitHub for portfolio building

## Data Cleaning and Preparation

In the initial phase of the Data Cleaning and prepartions, we perform the following action;
i. Data loading and Inspection
ii. Removing of duplicates
iii. Data cleaning and formating

## Exploratory Data Analysis

EDA Involves the exploring of Data to answer some questions about the Data such as:
- What is the overall sales trend?
- Which product are top sellers?
- Which products are sold most in each region?

## Data Analysis

![image](https://github.com/user-attachments/assets/41485a18-3406-40e9-abe4-492d4b205dea)

![image](https://github.com/user-attachments/assets/232d986a-7b3c-46da-a2c3-53de720e4c4b)

```SQL
select Top 1 product, SUM(Total_Sales) AS TotalSales from [dbo].[LitaSalesprojectdata]
Group by product
Order by TotalSales desc
```

``` SQL
select orderdate,
SUM(Total_Sales) AS Monthly_Sales from [dbo].[LitaSalesprojectdata]
where orderdate between '01-01-2024' and '12-31-2024'
Group by orderdate
Order by orderdate
```
```SQL
select Top 5 customer_id,
 SUM(Total_Sales) AS Total_Purchase from [dbo].[LitaSalesprojectdata]
Group by customer_id
Order by Total_Purchase desc
```
```SQL
SELECT 
    Region, 
    SUM(Total_Sales) AS Regional_Sales,
    (SUM(Total_Sales) * 100.0 / (SELECT SUM(Total_Sales) FROM [dbo].[LitaSalesprojectdata])) AS Sales_Percentage 
FROM 
    [dbo].[LitaSalesprojectdata]
GROUP BY 
    Region
ORDER BY 
    Regional_Sales DESC;
```
## Data Visualisation

![image](https://github.com/user-attachments/assets/535a2646-65c6-4f06-a2d1-e7a3d9431d88)

## Summary

There is usually a spike in total revenue in february.

Gloves are only sold in the South and West, Hats are not sold in the North, Jackets are sold in East and North, 
Shirts are sold in the East and North, Shoes are not sold in the North, socks are sold in the South and West.

The highest sold product is Shoes and it is sold in February of the two years.

Percentage sales is highest in the south with 44%, East 23%, North 18%, and West 14%

## Recommendation

More effort should be put in the month of April recording a low sales.

Increase marketing for gloves and Socks in the North and East, Hats and Shoes in North, Jackets and Shirts in South and West.

