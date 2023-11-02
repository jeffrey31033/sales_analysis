# Data analysis in a retail store with SQL and Tableau

## Table of Contents
- [Project Overview](#Project-overview)
- [Data Sources](#Data-sources)
- [First Phase](#First-phase)
- [Second Phase](#Second-phase)
- [Code](#Code)

### Project Overview
---

The objective of this data analysis project is to provide insights into various aspects of the sales performance of a retail store from 1996Q3 to 1998Q4. Through a comprehensive data analysis, our goal is to discern trends, make well-informed, data-driven decisions, and enhance our comprehension of the company's overall performance.

The project unfolds in three different phases. Firstly, we establish a data warehouse by merging and aggregating data from multiple tables to create a unified and informative dataset. In the second phase, we conduct exploratory data analysis by executing specific queries to achieve predefined objectives and extract valuable insights from the data. Finally, we employ Tableau to create visualizations that effectively convey the findings derived from the data warehouse.

### Data Sources
---
Sales Data: The primary dataset used for analysis derived from the final project in data management course, containing detailed information about each order made by the company

### Tools

-	MYSQL – Building Data Warehouse and Execute Queries  
-	Tableau – Visualizing Data from Data Warehouse

### First Phase 
---
During the initial phase, I focused on constructing a data warehouse, gaining deeper insights into customer behavior and product-related trends. I began by selecting the order id as the primary column. Following this, I aggregated various aspects of revenue and discounts linked to different product types, spanning across numerous orders. 
<br />
(The table only screen shot for 25 rows among 830 rows)
<br />
<img width="1032" alt="data warehouse 1" src="https://github.com/jeffrey31033/sales_analysis/assets/149200070/3a38cdfd-ade9-4dd6-bcb6-9543f308de0b">
<img width="1006" alt="data warehouse 2" src="https://github.com/jeffrey31033/sales_analysis/assets/149200070/e40ec6aa-f74a-4f53-8626-624e8056ae2b">
<img width="269" alt="data warehouse 3" src="https://github.com/jeffrey31033/sales_analysis/assets/149200070/759598c4-6b95-42ce-ab38-1d426f0a5ca3">


### Second Phase
---
In the second phase, my attention shifted to performing exploratory data analysis and utilized queries on the newly established data warehouse. I organized these queries into three key areas: customer, country, and product

#### Customer

1. Should discounts be offered to these customers?
   <img width="525" alt="query_1-Should we give discounts to these customers" src="https://github.com/jeffrey31033/sales_analysis/assets/149200070/2b9a0c95-081b-4759-96e9-bed87f067d1a"> <br>
   The table provides insights into which customers haven't delivered the value we anticipated. It's organized by the rank of the discount percentage. Typically, larger discounts are reserved for customers who buy more products from us. However, there's a noticeable discrepancy in the volume of products purchased by Piccolo und mehr and LILA-Supermercado compared to the discounts they receive. Unless there are specific reasons for this anomaly, we should consider reducing their discount percentages.

2. What is the predominant product type purchased by each customer? <br>
   (The table only screen shot for three customers among eighty-nine customers in total)
   <img width="389" alt="query_3-What product type does a customer buy the most" src="https://github.com/jeffrey31033/sales_analysis/assets/149200070/203bb7f6-610c-4cb0-994a-f20e2a018dba"> <br> 
The table offers a detailed view of each customer's revenue composition. With this knowledge of their revenue structure, we're equipped to tailor our pricing strategies according to different customer tiers. This approach allows us to create a product portfolio and implement bundle pricing for our clients. Take Bon app’ as an example, considering that seafood and meat/poultry are ranked first and eighth in sales respectively, a strategic move would be to combine select offerings from both categories into a bundled product portfolio. This strategy could potentially enhance our sales in the meat/poultry category.

3. Could we be losing key customers due to delayed shipments?
   <img width="595" alt="query_4-Are we possible losing our important due to the late shipment" src="https://github.com/jeffrey31033/sales_analysis/assets/149200070/3cb5e954-ec1f-468f-8602-42c50435c955"> <br>
Ensuring order processing on time is key to enhancing customer experience, especially for our most valuable clients. The data reveals a discrepancy between the required and actual shipping dates. The table highlights the proportion of late orders for each customer. Notably, among our top 20 customers by total revenue, eleven have experienced delays in receiving their orders. It's crucial for us to minimize these late deliveries, as the primary cause appears to be internal processing inefficiencies rather than shipping delays. Addressing this issue will improve customer satisfaction.

4. Is our dependence on a particular shipper excessively high for each individual customer?
   <img width="773" alt="query_5-Do we rely too much on one specific shipper" src="https://github.com/jeffrey31033/sales_analysis/assets/149200070/09fcd972-55cb-478c-bb00-429cf43f8c46"> <br>
The data presented provides valuable perspectives on risk distribution. Take Norway as an example: a significant portion of the total shipments predominantly depends on United Package. This scenario highlights a considerable risk: if United Package were to face any operational challenges, it would be difficult for us to find an alternative promptly. Such a dependency means that any disruption in United Package's services could impede our ability to deliver products efficiently, potentially resulting in customer dissatisfaction. It's important for us to consider diversifying our shipping partners to mitigate these risks.

5. Which other customers are significant to our business?
   <img width="646" alt="query_7-Which customers are also important to us" src="https://github.com/jeffrey31033/sales_analysis/assets/149200070/3a03ff93-5de6-45de-b4ba-c6180c1fd7f1"> <br>
The table clearly illustrates that there isn't a direct correlation between the rank based on total actual revenue and the rank based on average subtotal per order for each customer. For instance, Simons bistro ranks 35th in terms of subtotal, yet its average subtotal per order is impressively higher, at rank 6. This disparity suggests that customers like Simons bistro, who may not be top-ranked in overall spending but place large orders on average, should also be a focus for our sales strategy. Increasing the purchase frequency of such customers could significantly benefit our company due to the substantial value of each order they place.

#### Country

1. The top 10 countries have been the highest revenue generators for the past three years
   <img width="544" alt="query_8-The top 10 countries produce the most revenue for 3 years" src="https://github.com/jeffrey31033/sales_analysis/assets/149200070/b24337ce-c8e6-4811-bf4a-d6486b6c4891"> <br>
   This query provides vital data on the top 10 countries contributing the most to our revenue, including the specific percentage each country contributes to our total revenue. Such information is instrumental in guiding our resource allocation decisions, particularly in areas like advertising and marketing, enabling us to strategize our efforts more effectively in these key markets.

2. Which market holds the greatest potential?
   <img width="680" alt="query_2-Which market has the most potential" src="https://github.com/jeffrey31033/sales_analysis/assets/149200070/e9cb959d-d469-48a1-9ffb-89d63a30022b"> <br>
   Understanding growth rates across various markets is crucial in determining the focus countries for a company and in assessing the effectiveness of our strategies. If a significant investment in advertising in a particular country doesn't yield an increase in sales, it's a clear indicator that our marketing approach needs recalibration as the return on investment is not aligning with expectations. Moreover, it's important to recognize that while some countries such as Italy and Poland might not be among the top 10 countries in terms of overall contribution to our business, their high growth rates shouldn't be overlooked. Such markets demand greater attention due to their potential for rapid expansion.

#### Product

1. Are the discounts offered on various product types justified?
   <img width="506" alt="query_6-Are the discounts on different product type reasonable" src="https://github.com/jeffrey31033/sales_analysis/assets/149200070/fbf2c28d-3543-47cd-8fe6-267420fb71d8"> <br>
   The table provides a comparative analysis of the ranking based on percentage discounts and the ranking in terms of total revenue. Though meat/poultry and seafood categories are not among the most valuable for our company, they still receive significant discounts. Unless there are some specific reasons justifying this strategy, it may be prudent to reevaluate our discount policies for these products.

### Code
---
#### First phase – Building Data Warehouse
```sql
SET sql_mode = (SELECT REPLACE(@@SQL_MODE, "ONLY_FULL_GROUP_BY", ""));

CREATE OR REPLACE VIEW datawarehouse_portfolio2  AS
SELECT sub1.OrderID, sub1.CustomerID, sub2.CompanyName AS CustomerName, sub2.Country AS CustomerCountry, sub1.OrderDate, sub1.RequiredDate, sub1.ShippedDate, sub1.TotalFreight, sub1.ShipperCompanyName, 
       sub1.OriginalRevenue, sub1.TotalDiscount,
       sub3.RevenueInBeverages, sub3.RevenueInCondiments, sub3.RevenueInConfections, sub3.RevenueInDairyProducts, sub3.RevenueInGrainsAndCereals, sub3.RevenueInMeatAndPoultry,
       sub3.RevenueInProduce, sub3.RevenueInSeafood,
       sub4.DiscountInBeverages, sub4.DiscountInCondiments, sub4.DiscountInConfections, sub4.DiscountInDairyProducts, sub4.DiscountInGrainsAndCereals, sub4.DiscountInMeatAndPoultry,
       sub4.DiscountInProduce, sub4.DiscountInSeafood
FROM (SELECT o.OrderID, o.CustomerID, STR_TO_DATE(OrderDate, '%m/%d/%Y') AS OrderDate, STR_TO_DATE(RequiredDate, '%m/%d/%Y') AS RequiredDate, STR_TO_DATE(ShippedDate, '%m/%d/%Y') AS ShippedDate,
             o.Freight AS TotalFreight, sh.CompanyName AS ShipperCompanyName,
			 ROUND(SUM(Quantity*UnitPrice),2) AS OriginalRevenue, ROUND(SUM(Quantity*UnitPrice*Discount),2) AS TotalDiscount
	  FROM orders AS o
	  JOIN order_details AS od
	  ON o.OrderID = od.OrderID
      JOIN shippers AS sh
      ON sh.ShipperID = o.ShipVia
	  GROUP By OrderID) AS sub1
JOIN (SELECT o.OrderID, o.CustomerID, c.CompanyName, c.Country AS Country, STR_TO_DATE(OrderDate, '%m/%d/%Y') AS OrderDate, 
             STR_TO_DATE(RequiredDate, '%m/%d/%Y') AS RequiredDate, STR_TO_DATE(ShippedDate, '%m/%d/%Y') AS ShippedDate
	  FROM orders AS o
	  JOIN customers AS c
	  ON c.CustomerID = o.CustomerID) AS sub2
ON sub1.orderID = sub2.orderID
JOIN (SELECT s.OrderID, 
             ROUND(SUM(CASE WHEN categoryName = 'Beverages' THEN subtotal ELSE 0 END),2) AS RevenueInBeverages,
			 ROUND(SUM(CASE WHEN CategoryName = 'Condiments' THEN subtotal ELSE 0 END),2) AS RevenueInCondiments,
			 ROUND(SUM(CASE WHEN CategoryName = 'Confections' THEN subtotal ELSE 0 END),2) AS RevenueInConfections,
			 ROUND(SUM(CASE WHEN CategoryName = 'Dairy Products' THEN subtotal ELSE 0 END),2) AS RevenueInDairyProducts,
			 ROUND(SUM(CASE WHEN CategoryName = 'Grains/Cereals' THEN subtotal ELSE 0 END),2) AS RevenueInGrainsAndCereals,
			 ROUND(SUM(CASE WHEN CategoryName = 'Meat/Poultry' THEN subtotal ELSE 0 END),2) RevenueInMeatAndPoultry,
			 ROUND(SUM(CASE WHEN CategoryName = 'Produce' THEN subtotal ELSE 0 END),2) AS RevenueInProduce,
		     ROUND(SUM(CASE WHEN CategoryName = 'Seafood' THEN subtotal ELSE 0 END),2) AS RevenueInSeafood
FROM (SELECT o.OrderID, c.CategoryName , SUM(od.UnitPrice * (1 - od.Discount) * od.Quantity) AS subtotal
      FROM orders AS o
      JOIN order_details AS od
      USING (OrderID)
      JOIN products AS p
      USING (ProductID)
      JOIN categories AS c
      USING (CategoryID)
      GROUP BY OrderID, CategoryID
      ORDER BY OrderID) AS s
      GROUP BY OrderID) AS sub3
ON sub1.OrderID = sub3.OrderID
JOIN (SELECT OrderID,
			 ROUND(SUM(CASE WHEN categoryName = 'Beverages' THEN Discount ELSE 0 END),2) AS DiscountInBeverages,
			 ROUND(SUM(CASE WHEN CategoryName = 'Condiments' THEN Discount ELSE 0 END),2) AS DiscountInCondiments,
			 ROUND(SUM(CASE WHEN CategoryName = 'Confections' THEN Discount ELSE 0 END),2) AS DiscountInConfections,
			 ROUND(SUM(CASE WHEN CategoryName = 'Dairy Products' THEN Discount ELSE 0 END),2) AS DiscountInDairyProducts,
			 ROUND(SUM(CASE WHEN CategoryName = 'Grains/Cereals' THEN Discount ELSE 0 END),2) AS DiscountInGrainsAndCereals,
			 ROUND(SUM(CASE WHEN CategoryName = 'Meat/Poultry' THEN Discount ELSE 0 END),2) DiscountInMeatAndPoultry,
			 ROUND(SUM(CASE WHEN CategoryName = 'Produce' THEN Discount ELSE 0 END),2) AS DiscountInProduce,
			 ROUND(SUM(CASE WHEN CategoryName = 'Seafood' THEN Discount ELSE 0 END),2) AS DiscountInSeafood
		FROM (SELECT o.OrderID, c.CategoryName , ROUND(SUM(od.UnitPrice * (od.Discount) * od.Quantity),2) AS Discount
			  FROM orders AS o
			  JOIN order_details AS od
			  USING (OrderID)
			  JOIN products AS p
			  USING (ProductID)
			  JOIN categories AS c
			  USING (CategoryID)
			  GROUP BY OrderID, CategoryID
			  ORDER BY OrderID) AS sub1
GROUP BY OrderID) AS sub4
ON sub1.OrderID = sub4.OrderID
ORDER BY OrderID;
```

#### Second Phase – Exploratory Data Analysis

##### Customer

1. Should discounts be offered to these customers?
```sql
WITH sub1 AS ( 
SELECT CustomerID, CustomerName, ROUND(SUM(OriginalRevenue),2) AS TotalRevenue, ROUND(SUM(TotalDiscount),2) AS TotalDiscount, 
			  ROUND(SUM(TotalDiscount) / SUM(OriginalRevenue) * 100, 2) AS DiscountPercent
FROM datawarehouse_portfolio2
GROUP BY CustomerID
ORDER BY CustomerID)
SELECT CustomerName, TotalRevenue, TotalDiscount, DiscountPercent,
       RANK() OVER(ORDER BY TotalRevenue DESC) AS RankOnTotalRevenue,
       RANK() OVER(ORDER BY DiscountPercent DESC) AS RankOnDiscountPercent
FROM sub1
WHERE sub1.TotalRevenue > (SELECT AVG(TotalRevenue)
						   FROM sub1)
ORDER BY RankOnDiscountPercent;
```
2. What is the predominant product type purchased by each customer?
```sql
WITH sub1 AS ( 
SELECT CustomerID, CustomerName, ROUND(SUM(OriginalRevenue),2) AS TotalRevenue, ROUND(SUM(TotalDiscount),2) AS TotalDiscount, 
			  ROUND(SUM(TotalDiscount) / SUM(OriginalRevenue) * 100, 2) AS DiscountPercent
FROM datawarehouse_portfolio2
GROUP BY CustomerID
ORDER BY CustomerID), 
sub2 AS (
SELECT CustomerName, CustomerCountry, ROUND(SUM(RevenueInBeverages),2) AS RevenueInBeverages, ROUND(SUM(RevenueInCondiments),2) AS RevenueInCondiments, 
       ROUND(SUM(RevenueInConfections),2) AS RevenueInConfections, ROUND(SUM(RevenueInDairyProducts),2) AS RevenueInDairyProducts,
       ROUND(SUM(RevenueInGrainsAndCereals),2) AS RevenueInGrainsAndCereals, ROUND(SUM(RevenueInMeatAndPoultry),2) AS RevenueInMeatAndPoultry, 
       ROUND(SUM(RevenueInProduce),2) AS RevenueInProduce, ROUND(SUM(RevenueInSeafood),2) AS RevenueInSeafood
FROM datawarehouse_portfolio2
WHERE CustomerID IN (SELECT CustomerID FROM sub1 WHERE TotalRevenue > (SELECT AVG(TotalRevenue) FROM sub1))
GROUP BY CustomerID
ORDER BY CustomerID), 
sub3 AS (
SELECT CustomerName, CustomerCountry, 'Beverages' AS Category, RevenueInBeverages AS Revenue
FROM sub2
UNION ALL
SELECT CustomerName, CustomerCountry, 'Condiments' AS Category, RevenueInCondiments AS Revenue
FROM sub2
UNION ALL
SELECT CustomerName, CustomerCountry, 'Confections' AS Category, RevenueInConfections AS Revenue
FROM sub2
UNION ALL 
SELECT CustomerName, CustomerCountry, 'Grains And Cereals' AS Category, RevenueInGrainsAndCereals AS Revenue
FROM sub2
UNION
SELECT CustomerName, CustomerCountry, 'DairyProducts' AS Category, RevenueInDairyProducts AS Revenue
FROM sub2
UNION ALL
SELECT CustomerName, CustomerCountry, 'Meat And Poultry' AS Category, RevenueInMeatAndPoultry AS Revenue
FROM sub2
UNION ALL
SELECT CustomerName, CustomerCountry, 'Produce' AS Category, RevenueInProduce AS Revenue
FROM sub2
UNION ALL
SELECT CustomerName, CustomerCountry, 'Seafood' AS Category, RevenueInSeafood AS Revenue
FROM sub2
ORDER BY CustomerName)
SELECT CustomerName, CustomerCountry, Category, Revenue,
       Rank() OVER(PARTITION BY CustomerName ORDER BY Revenue DESC) AS RankOnCategory
FROM sub3
ORDER BY CustomerName;
```
3. Could we be losing key customers due to delayed shipments?
```sql
SELECT sub2.CustomerName, sub2.CustomerCountry, sub2.NumberOfAdvance, sub2.NumberOfOnTime, sub2.NumberOfLate, sub2.PercentOfLate,
       sub4.RankOnTotalRevenue
FROM (SELECT CustomerName, CustomerCountry,
		     SUM(CASE WHEN Time = 'Advance' THEN 1 ELSE 0 END) AS NumberOfAdvance,
			 SUM(CASE WHEN Time = 'On Time' THEN 1 ELSE 0 END) AS NumberOfOnTime,
		     SUM(CASE WHEN Time = 'Late' THEN 1 ELSE 0 END) AS NumberOfLate,
			 ROUND(SUM(CASE WHEN Time = 'Late' THEN 1 ELSE 0 END) / (SUM(CASE WHEN Time = 'Advance' THEN 1 ELSE 0 END) + SUM(CASE WHEN Time = 'On Time' THEN 1 ELSE 0 END) + SUM(CASE WHEN Time = 'Late' THEN 1 ELSE 0 END)) * 100, 2) AS PercentOfLate
	  FROM (SELECT OrderID, CustomerName, CustomerCountry,
                   CASE WHEN RequiredDate < ShippedDate THEN 'Late' 
				   WHEN RequiredDate = ShippedDate THEN 'On Time'
				   WHEN RequiredDate > ShippedDate THEN 'Advance' 
				   ELSE 'No Data' END AS Time
			FROM datawarehouse_portfolio2
			ORDER BY CustomerName) AS sub1
GROUP BY CustomerName) sub2
JOIN (SELECT CustomerName,
			 TotalRevenue,
			 RANK() OVER(ORDER BY TotalRevenue DESC) AS RankOnTotalRevenue
      FROM(SELECT CustomerName, SUM(OriginalRevenue) AS TotalRevenue
	       FROM datawarehouse_portfolio2
	       GROUP BY CustomerID
	       ORDER BY CustomerID) AS sub3) AS sub4
ON sub2.CustomerName =sub4.CustomerName
ORDER BY PercentOfLate DESC;
```
4. Is our dependence on a particular shipper excessively high for each individual customer?
```sql
SELECT Country, TotalRevenueOnFederalShipping, TotalRevenueOnSpeedyExpress, TotalRevenueOnUnitedPackage,
       ROUND(TotalRevenueOnFederalShipping / (TotalRevenueOnFederalShipping + TotalRevenueOnSpeedyExpress + TotalRevenueOnUnitedPackage) * 100,2) AS PercentOnFederalShipping,
       ROUND(TotalRevenueOnSpeedyExpress / (TotalRevenueOnFederalShipping + TotalRevenueOnSpeedyExpress + TotalRevenueOnUnitedPackage) * 100,2) AS PercentOnSpeedyExpress,
        ROUND(TotalRevenueOnUnitedPackage / (TotalRevenueOnFederalShipping + TotalRevenueOnSpeedyExpress + TotalRevenueOnUnitedPackage) * 100,2) AS PercentOnUnitedPackage
FROM (SELECT Country,
             SUM(CASE WHEN ShipperCompanyName = 'Federal Shipping' THEN TotalRevenue ELSE 0 END) AS TotalRevenueOnFederalShipping,
			 SUM(CASE WHEN ShipperCompanyName = 'Speedy Express' THEN TotalRevenue ELSE 0 END) AS TotalRevenueOnSpeedyExpress,
			 SUM(CASE WHEN ShipperCompanyName = 'United Package' THEN TotalRevenue ELSE 0 END) AS TotalRevenueOnUnitedPackage
	  FROM (SELECT CustomerCountry AS Country, ShipperCompanyName, SUM(OriginalRevenue) AS TotalRevenue
			FROM datawarehouse_portfolio2
			GROUP BY CustomerCountry, ShipperCompanyName
			ORDER BY CustomerCountry) AS sub1
	  GROUP BY Country
	  ORDER BY Country) AS sub1;
```
6. Which other customers are significant to our business?
```sql
WITH sub1 AS (
SELECT CustomerName, COUNT(OrderID) AS NumberOfOrder, ROUND(SUM(OriginalRevenue) - SUM(TotalDiscount),2) AS TotalActualRevenue,
       ROUND((SUM(OriginalRevenue) - SUM(TotalDiscount)) / COUNT(OrderID),2) AS AverageAmountPerOrder
FROM datawarehouse_portfolio2
GROUP BY CustomerID)
SELECT *,
       RANK() OVER(ORDER BY TotalActualRevenue DESC) AS RankOnTotalActualRevenue,
       RANK() OVER(ORDER BY AverageAmountPerOrder DESC) AS RankOnAverageAmountPerOrder
FROM sub1;
```

##### Country

1. The top 10 countries have been the highest revenue generators for the past three years
```sql
WITH sub1 AS (
SELECT CustomerCountry AS Country, SUM(OriginalRevenue) AS CountryOriginalRevenue, ROUND(SUM(TotalDiscount),2) AS CountryTotalDiscount,
       ROUND(SUM(OriginalRevenue) - SUM(TotalDiscount),2) AS CountryTotalActualRevenue,
       (SELECT ROUND(SUM(OriginalRevenue) - SUM(TotalDiscount),2) FROM datawarehouse_portfolio2) AS TotalActualRevenue
FROM datawarehouse_portfolio2
GROUP BY CustomerCountry)
SELECT *,
       ROUND(CountryTotalActualRevenue / TotalActualRevenue * 100,2) AS PercentOfRevenue
FROM sub1
ORDER BY PercentOfRevenue DESC;
```
2. Which market holds the greatest potential?
```sql
SELECT sub2.Country, RevenueIn1996, RevenueIn1997, RevenueIn1998,
       RevenueIn1996 + RevenueIn1997 + RevenueIn1998 AS TotalRevenue,
       ROUND((RevenueIn1997 - RevenueIn1996) / RevenueIn1996 * 100,2) AS GrowthRateIn1997,
       ROUND((RevenueIn1998 - RevenueIn1997) / RevenueIn1997 * 100,2) AS GrowthRateIn1998,
       ROUND((RevenueIn1998 - RevenueIn1996) / RevenueIn1996 * 100,2) AS TotalGrowthRate,
       sub4.RankOnTotalRevenue
FROM (SELECT Country,
			 SUM(CASE WHEN Year = 1996 THEN OriginalRevenue ELSE 0 END) AS RevenueIn1996, 
			 SUM(CASE WHEN Year = 1997 THEN OriginalRevenue ELSE 0 END) AS RevenueIn1997,
			 SUM(CASE WHEN Year = 1998 THEN OriginalRevenue ELSE 0 END) AS RevenueIn1998
	  FROM (SELECT CustomerCountry AS Country, year(OrderDate) AS Year, SUM(OriginalRevenue) AS OriginalRevenue
	        FROM datawarehouse_portfolio2
	        GROUP BY Country, year(OrderDate)
	        ORDER BY Country, Year) AS sub1
      GROUP BY Country) AS sub2
JOIN (SELECT Country, 
       RANK() OVER(ORDER BY TotalRevenue DESC) AS RankOnTotalRevenue
      FROM (SELECT CustomerCountry AS Country, SUM(OriginalRevenue) AS TotalRevenue
	        FROM datawarehouse_portfolio2
            GROUP BY CustomerCountry) AS sub3) AS sub4
ON sub2.Country = sub4.Country
ORDER BY TotalGrowthRate DESC;
```

##### Product

1. Are the discounts offered on various product types justified?
```sql
WITH sub2 AS (
SELECT Category, ROUND(SUM(Revenue),2) AS TotalRevenue, ROUND(SUM(Discount),2) AS TotalDiscount,
       ROUND(SUM(Discount) / SUM(Revenue) * 100,2) AS PercentOfDiscount
FROM ( SELECT 'Beverages' AS Category, RevenueInBeverages AS Revenue, DiscountInBeverages AS Discount
	   FROM datawarehouse_portfolio2
	   UNION ALL
	   SELECT 'Condiments' AS Category, RevenueInCondiments AS Revenue, DiscountInCondiments AS Discount
	   FROM datawarehouse_portfolio2
       UNION ALL 
	   SELECT 'Confections' AS Category, RevenueInConfections AS Revenue, DiscountInConfections AS Discount
       FROM datawarehouse_portfolio2
	   UNION ALL
	   SELECT 'Dairy Products' AS Category, RevenueInDairyProducts AS Revenue, DiscountInDairyProducts AS Discount
	   FROM datawarehouse_portfolio2
	   UNION ALL
       SELECT 'Grains And Cereals' AS Category, RevenueInGrainsAndCereals AS Revenue, DiscountInGrainsAndCereals AS Discount
	   FROM datawarehouse_portfolio2
	   UNION ALL
	   SELECT 'Meat And Poultry' AS Category, RevenueInMeatAndPoultry AS Revenue, DiscountInMeatAndPoultry AS Discount
	   FROM datawarehouse_portfolio2
	   UNION ALL 
	   SELECT 'Produce' AS Category, RevenueInProduce AS Revenue, DiscountInProduce AS Discount
	   FROM datawarehouse_portfolio2
       UNION ALL 
	   SELECT 'Seafood' AS Category, RevenueInSeafood AS Revenue, DiscountInSeafood AS Discount
	   FROM datawarehouse_portfolio2) AS sub1
GROUP BY Category) 
SELECT *,
       RANK() OVER(ORDER BY TotalRevenue DESC) AS RankOnTotalRevenue,
       RANK() OVER(ORDER BY PercentOfDiscount DESC) AS RankOnPercentOfDiscount
FROM sub2
ORDER BY RankOnPercentOfDiscount;
```

