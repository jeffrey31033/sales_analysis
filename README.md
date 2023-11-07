# Data analysis in wholesales with SQL and Tableau

## Table of Contents
- [Project Overview](#Project-overview)
- [Data Sources](#Data-sources)
- [First Phase: Building Data Warehouse](#first-phase-building-data-warehouse)
- [Second Phase: Exploratory Data Analysis](#second-phase-exploratory-data-analysis)
- [Third Phase: Visualization](#third-phase-visualization)
- [Code](#Code)

### Project Overview
---

The objective of this data analysis project is to provide insights into various aspects of the sales performance of a wholesaler from 1996Q3 to 1998Q4. Through a comprehensive data analysis, our goal is to discern trends, make well-informed, data-driven decisions, and enhance our comprehension of the company's overall performance.

The project categorize in three different phases. Firstly, we establish a data warehouse by merging and aggregating data from multiple tables to create a unified and informative dataset. In the second phase, I conduct exploratory data analysis by executing specific queries to achieve predefined objectives and extract valuable insights from the data. Finally, I use Tableau to create visualizations that effectively convey the findings derived from the data warehouse.

### Data Sources
---
Sales Data: The primary dataset used for analysis derived from the final project in data management course, containing detailed information about each order made by the company

### Tools
---
-	MYSQL – Building Data Warehouse and Execute Queries  
-	Tableau – Visualizing Data from Data Warehouse

### First Phase: Building Data Warehouse
---
During the initial phase, I focused on constructing a data warehouse, gaining deeper insights into customer behavior and product-related trends. I began by selecting the order id as the primary column. Following this, I aggregated various aspects of sales and discounts linked to different product types, spanning across numerous orders. 
<br />
(The table only screen shot for 25 rows among 830 rows)
<br />
<img width="980" alt="data warehouse 1" src="https://github.com/jeffrey31033/sales_analysis/assets/149200070/fe0ec181-30b9-4457-8fd1-e34058a68099">
<img width="1049" alt="data warehouse 2" src="https://github.com/jeffrey31033/sales_analysis/assets/149200070/5102cfc8-327e-4d6d-9103-6fb9517375f5">
<img width="163" alt="data warehouse 3" src="https://github.com/jeffrey31033/sales_analysis/assets/149200070/5ef04de0-407b-48c2-8789-594d6d2b854d">


### Second Phase: Exploratory Data Analysis
---
In the second phase, my attention shifted to performing exploratory data analysis and utilized queries on the newly established data warehouse. I organized these queries into three key areas: customer, country, and product

#### Customer

**1. Should discounts be offered to these customers?** 
<br>
(Here, I only track the customers whoose sales exceed average sales among all the customers)
<br>
<img width="497" alt="query_1-Should we give discounts to these customers" src="https://github.com/jeffrey31033/sales_analysis/assets/149200070/595bfd9a-42dc-433d-ac57-0e213f7b4bdb">
<br>
The table provides insights into which customers haven't delivered the value we anticipated. It's organized by the rank of the discount percentage. Typically, larger discounts are reserved for customers who buy more products from us. However, there's a noticeable discrepancy in the volume of products purchased by Piccolo und mehr and LILA-Supermercado compared to the discounts they receive. Unless there are specific reasons for this anomaly, we should consider reducing their discount percentages.

**2. What is the predominant product type purchased by each customer?** 
<br>
(The table only screen shot for three customers among eighty-nine customers in total)
<br>
<img width="613" alt="query_2-Which market has the most potential" src="https://github.com/jeffrey31033/sales_analysis/assets/149200070/6cd1ee2d-179f-4033-891d-b9bcea6ecbcd">
<br> 
The table offers a detailed view of each customer's sales composition. With this knowledge of their sales structure, we're equipped to tailor our pricing strategies according to different customer tiers. This approach allows us to create a product portfolio and implement bundle pricing for our clients. Take Bon app’ as an example, considering that seafood and meat/poultry are ranked first and eighth in sales respectively, a strategic move would be to combine select offerings from both categories into a bundled product portfolio. This strategy could potentially enhance our sales in the meat/poultry category.

**3. Could we be losing key customers due to delayed shipments?** 
<br>
(Here, I only screen shot for those customers who experience dalys in receiving their orders)
<br>
<img width="578" alt="query_4-Are we possible losing our important due to the late shipment" src="https://github.com/jeffrey31033/sales_analysis/assets/149200070/a8d5007f-b8f8-4ddc-a29d-49222186b454">
<br>
Ensuring order processing on time is key to enhancing customer experience, especially for our most valuable clients. The data reveals a discrepancy between the required and actual shipping dates. The table highlights the proportion of late orders for each customer. Notably, among our top 20 customers by total sales, eleven have experienced delays in receiving their orders. It's crucial for us to minimize these late deliveries, as the primary cause appears to be internal processing inefficiencies rather than shipping delays. Addressing this issue will improve customer satisfaction.


**4. Which other customers are significant to our business?** 
<br>
(Here, I only screen shot for 20 observations)
<br>
<img width="619" alt="query_7-Which customers are also important to us" src="https://github.com/jeffrey31033/sales_analysis/assets/149200070/72c2ce86-4afc-4e2b-87ce-f5e705d7d2af">
<br>
The table clearly illustrates that there isn't a direct correlation between the rank based on total actual revenue and the rank based on average subtotal per order for each customer. For instance, Simons bistro ranks 35th in terms of subtotal, yet its average subtotal per order is impressively higher, at rank 6. This disparity suggests that customers like Simons bistro, who may not be top-ranked in overall spending but place large orders on average, should also be a focus for our sales strategy. Increasing the purchase frequency of such customers could significantly benefit our company due to the substantial value of each order they place.

#### Country

**1. The top 10 countries have been the highest revenue generators for the past three years**
<br>
<img width="491" alt="query_8-The top 10 countries produce the most revenue for 3 years" src="https://github.com/jeffrey31033/sales_analysis/assets/149200070/10262606-ae74-4f25-94d9-078e7612e8b9">
<br>
This query provides vital data on the top 10 countries contributing the most to our sales, including the specific percentage each country contributes to our total sales. Such information is instrumental in guiding our resource allocation decisions, particularly in areas like advertising and marketing, enabling us to strategize our efforts more effectively in these key markets.

**2. Which market holds the greatest potential?**
<br>
<img width="613" alt="query_2-Which market has the most potential" src="https://github.com/jeffrey31033/sales_analysis/assets/149200070/79590b8b-aee0-40c1-896e-8f25a9a82446">
<br>
Understanding growth rates across various markets is crucial in determining the focus countries for a company and in assessing the effectiveness of our strategies. If a significant investment in advertising in a particular country doesn't yield an increase in sales, it's a clear indicator that our marketing approach needs recalibration as the return on investment is not aligning with expectations. Moreover, it's important to recognize that while some countries such as Italy and Poland might not be among the top 10 countries in terms of overall contribution to our business, their high growth rates shouldn't be overlooked. Such markets demand greater attention due to their potential for rapid expansion.

**3. Is our dependence on a particular shipper excessively high for each contry?**
<br>
<img width="735" alt="query_5-Do we rely too much on one specific shipper" src="https://github.com/jeffrey31033/sales_analysis/assets/149200070/fc6b1279-2e17-4397-bc70-2ead792fe052">
<br>
The data presented provides valuable perspectives on risk distribution. Take Norway as an example: a significant portion of the total shipments predominantly depends on United Package. This scenario highlights a considerable risk: if United Package were to face any operational challenges, it would be difficult for us to find an alternative promptly. Such a dependency means that any disruption in United Package's services could impede our ability to deliver products efficiently, potentially resulting in customer dissatisfaction. It's important for us to consider diversifying our shipping partners to mitigate these risks.


#### Product

**1. Are the discounts offered on various product types justified?** 
<br>
<img width="484" alt="query_6-Are the discounts on different product type reasonable" src="https://github.com/jeffrey31033/sales_analysis/assets/149200070/a8885b50-e029-4abf-a601-200300ee7cff">
<br>
The table provides a comparative analysis of the ranking based on percentage discounts and the ranking in terms of total sales. Though meat/poultry and seafood categories are not among the most valuable for our company, they still receive significant discounts. Unless there are some specific reasons justifying this strategy, it may be prudent to reevaluate our discount policies for these products.

### Third Phase: Visualization
---
In this phase, I focused on visualization to develop an insightful dashboard. Initially, I integrate various tables by each order ID to create a comprehensive view and classify our customers into five tiers according to their contribution to our business. Subsequently, I utilize Tableau to craft several graphical representations. Finally, I congregated these graphs into a coherent and informative dashboard.

**1. Sales and Discount**
<br>
![Sales and Discout](https://github.com/jeffrey31033/sales_analysis/assets/149200070/95730aa8-1dc3-49b4-ba02-80f4ed61f0e6)
<br>
Analyzing sales data alongside discount rates is crucial for refining marketing strategies. Take, for instance, the grains/cereals category, which presents a notably higher discount percentage relative to other product groups. This observation prompts a strategic evaluation: is it justifiable to offer such substantial discounts in this category? Such insights can inform whether these incentives are effectively stimulating sales and profitability or if they require adjustment.

**2. Sales Given by Countries**
<br>
![Country Revenue ](https://github.com/jeffrey31033/sales_analysis/assets/149200070/7df17ee6-b270-45c7-b9f5-9c9308f1eef8)
<br>
The graph serves as a tool to discern the sales contributions of various countries to our business. By examining this sales structure, we can pinpoint the markets that warrant our focus and track the sales on each country.

**3. Sales Change by Quarter**
<br>
![Quarter Sales](https://github.com/jeffrey31033/sales_analysis/assets/149200070/377cf72f-5916-4e46-beda-f497acd750f2)
<br>
The line graph offers a visual representation of sales fluctuations across quarters, allowing us to discern trends in our revenue stream. Access to this trend data enables us to evaluate the impact of our marketing strategies over time. For example, we should identify the reason why there is a huge deduction in sales in 1998Q2.

**4. Product Composition Given by Different Class of Customers**
<br>
![Sales in Different Class of Customer](https://github.com/jeffrey31033/sales_analysis/assets/149200070/5b2f7316-4140-40c4-9c00-75f9b1fcfa93)
<br>
The graph shows the product mix purchased by varying customer segments. With this information, we can tailor distinct strategies for each segment. For instance, in the first class of customers, our strategy should concentrate on enhancing the beverages category. Conversely, for the second class, dairy products are predominant and warrant focused attention. Additionally, we can employ a product bundling approach, creating portfolios that pair complementary goods, potentially increasing sales in less dominant categories.

**5. Number Of Orders by quarter**
<br>
![Number of  orders](https://github.com/jeffrey31033/sales_analysis/assets/149200070/1117ae50-2688-481a-abf5-ffdb7fb0c11c)
<br>
The data on quarterly order volumes facilitates forecasting future order counts, which is useful for planning logistics and inventory based on specific country filters. Moreover, this information allows us to delve into the factors influencing order fluctuations. We can analyze whether these variations are seasonal trends or if they reflect customer dissatisfaction with our services, enabling targeted improvements.

**6. Dashboard**
<img width="1001" alt="Dashboard" src="https://github.com/jeffrey31033/sales_analysis/assets/149200070/95ace936-1706-4637-8a97-7d31c1dff611">

### Code
---
#### First phase – Building Data Warehouse
```sql
SET sql_mode = (SELECT REPLACE(@@SQL_MODE, "ONLY_FULL_GROUP_BY", ""));

CREATE OR REPLACE VIEW datawarehouse_portfolio2  AS
SELECT sub1.OrderID, sub1.CustomerID, sub2.CompanyName AS CustomerName, sub2.Country AS CustomerCountry, sub1.OrderDate, sub1.RequiredDate, sub1.ShippedDate, sub1.TotalFreight, sub1.ShipperCompanyName, 
       sub1.OriginalSales, sub1.TotalDiscount,
       sub3.SalesInBeverages, sub3.SalesInCondiments, sub3.SalesInConfections, sub3.SalesInDairyProducts, sub3.SalesInGrainsAndCereals, sub3.SalesInMeatAndPoultry,
       sub3.SalesInProduce, sub3.SalesInSeafood,
       sub4.DiscountInBeverages, sub4.DiscountInCondiments, sub4.DiscountInConfections, sub4.DiscountInDairyProducts, sub4.DiscountInGrainsAndCereals, sub4.DiscountInMeatAndPoultry,
       sub4.DiscountInProduce, sub4.DiscountInSeafood
FROM (SELECT o.OrderID, o.CustomerID, STR_TO_DATE(OrderDate, '%m/%d/%Y') AS OrderDate, STR_TO_DATE(RequiredDate, '%m/%d/%Y') AS RequiredDate, STR_TO_DATE(ShippedDate, '%m/%d/%Y') AS ShippedDate,
             o.Freight AS TotalFreight, sh.CompanyName AS ShipperCompanyName,
			 ROUND(SUM(Quantity*UnitPrice),2) AS OriginalSales, ROUND(SUM(Quantity*UnitPrice*Discount),2) AS TotalDiscount
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
             ROUND(SUM(CASE WHEN categoryName = 'Beverages' THEN subtotal ELSE 0 END),2) AS SalesInBeverages,
			 ROUND(SUM(CASE WHEN CategoryName = 'Condiments' THEN subtotal ELSE 0 END),2) AS SalesInCondiments,
			 ROUND(SUM(CASE WHEN CategoryName = 'Confections' THEN subtotal ELSE 0 END),2) AS SalesInConfections,
			 ROUND(SUM(CASE WHEN CategoryName = 'Dairy Products' THEN subtotal ELSE 0 END),2) AS SalesInDairyProducts,
			 ROUND(SUM(CASE WHEN CategoryName = 'Grains/Cereals' THEN subtotal ELSE 0 END),2) AS SalesInGrainsAndCereals,
			 ROUND(SUM(CASE WHEN CategoryName = 'Meat/Poultry' THEN subtotal ELSE 0 END),2) SalesInMeatAndPoultry,
			 ROUND(SUM(CASE WHEN CategoryName = 'Produce' THEN subtotal ELSE 0 END),2) AS SalesInProduce,
		     ROUND(SUM(CASE WHEN CategoryName = 'Seafood' THEN subtotal ELSE 0 END),2) AS SalesInSeafood
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

#### Second Phase: Exploratory Data Analysis

##### Customer

1. Should discounts be offered to these customers?
```sql
WITH sub1 AS ( 
SELECT CustomerID, CustomerName, ROUND(SUM(OriginalSales),2) AS TotalSales, ROUND(SUM(TotalDiscount),2) AS TotalDiscount, 
			  ROUND(SUM(TotalDiscount) / SUM(OriginalSales) * 100, 2) AS DiscountPercent
FROM datawarehouse_portfolio2
GROUP BY CustomerID
ORDER BY CustomerID)
SELECT CustomerName, TotalSales, TotalDiscount, DiscountPercent,
       RANK() OVER(ORDER BY TotalSales DESC) AS RankOnTotalSales,
       RANK() OVER(ORDER BY DiscountPercent DESC) AS RankOnDiscountPercent
FROM sub1
WHERE sub1.TotalSales > (SELECT AVG(TotalSales)
						   FROM sub1)
ORDER BY RankOnDiscountPercent;
```
2. What is the predominant product type purchased by each customer?
```sql
WITH sub1 AS ( 
SELECT CustomerID, CustomerName, ROUND(SUM(OriginalSales),2) AS TotalSales, ROUND(SUM(TotalDiscount),2) AS TotalDiscount, 
			  ROUND(SUM(TotalDiscount) / SUM(OriginalSales) * 100, 2) AS DiscountPercent
FROM datawarehouse_portfolio2
GROUP BY CustomerID
ORDER BY CustomerID), 
sub2 AS (
SELECT CustomerName, CustomerCountry, ROUND(SUM(SalesInBeverages),2) AS SalesInBeverages, ROUND(SUM(SalesInCondiments),2) AS SalesInCondiments, 
       ROUND(SUM(SalesInConfections),2) AS SalesInConfections, ROUND(SUM(SalesInDairyProducts),2) AS SalesInDairyProducts,
       ROUND(SUM(SalesInGrainsAndCereals),2) AS SalesInGrainsAndCereals, ROUND(SUM(SalesInMeatAndPoultry),2) AS SalesInMeatAndPoultry, 
       ROUND(SUM(SalesInProduce),2) AS SalesInProduce, ROUND(SUM(SalesInSeafood),2) AS SalesInSeafood
FROM datawarehouse_portfolio2
WHERE CustomerID IN (SELECT CustomerID FROM sub1 WHERE TotalSales > (SELECT AVG(TotalSales) FROM sub1))
GROUP BY CustomerID
ORDER BY CustomerID), 
sub3 AS (
SELECT CustomerName, CustomerCountry, 'Beverages' AS Category, SalesInBeverages AS Sales
FROM sub2
UNION ALL
SELECT CustomerName, CustomerCountry, 'Condiments' AS Category, SalesInCondiments AS Sales
FROM sub2
UNION ALL
SELECT CustomerName, CustomerCountry, 'Confections' AS Category, SalesInConfections AS Sales
FROM sub2
UNION ALL 
SELECT CustomerName, CustomerCountry, 'Grains And Cereals' AS Category, SalesInGrainsAndCereals AS Sales
FROM sub2
UNION
SELECT CustomerName, CustomerCountry, 'DairyProducts' AS Category, SalesInDairyProducts AS Sales
FROM sub2
UNION ALL
SELECT CustomerName, CustomerCountry, 'Meat And Poultry' AS Category, SalesInMeatAndPoultry AS Sales
FROM sub2
UNION ALL
SELECT CustomerName, CustomerCountry, 'Produce' AS Category, SalesInProduce AS Sales
FROM sub2
UNION ALL
SELECT CustomerName, CustomerCountry, 'Seafood' AS Category, SalesInSeafood AS Sales
FROM sub2
ORDER BY CustomerName)
SELECT CustomerName, CustomerCountry, Category, Sales,
       Rank() OVER(PARTITION BY CustomerName ORDER BY Sales DESC) AS RankOnCategory
FROM sub3
ORDER BY CustomerName;
```
3. Could we be losing key customers due to delayed shipments?
```sql
SELECT sub2.CustomerName, sub2.CustomerCountry, sub2.NumberOfAdvance, sub2.NumberOfOnTime, sub2.NumberOfLate, sub2.PercentOfLate,
       sub4.RankOnTotalSales
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
			 TotalSales,
			 RANK() OVER(ORDER BY TotalSales DESC) AS RankOnTotalSales
      FROM(SELECT CustomerName, SUM(OriginalSales) AS TotalSales
	       FROM datawarehouse_portfolio2
	       GROUP BY CustomerID
	       ORDER BY CustomerID) AS sub3) AS sub4
ON sub2.CustomerName =sub4.CustomerName
ORDER BY PercentOfLate DESC;
```

4. Which other customers are significant to our business?
```sql
WITH sub1 AS (
SELECT CustomerName, COUNT(OrderID) AS NumberOfOrder, ROUND(SUM(OriginalSales) - SUM(TotalDiscount),2) AS TotalActualSales,
       ROUND((SUM(OriginalSales) - SUM(TotalDiscount)) / COUNT(OrderID),2) AS AverageAmountPerOrder
FROM datawarehouse_portfolio2
GROUP BY CustomerID)
SELECT *,
       RANK() OVER(ORDER BY TotalActualSales DESC) AS RankOnTotalActualSales,
       RANK() OVER(ORDER BY AverageAmountPerOrder DESC) AS RankOnAverageAmountPerOrder
FROM sub1;
```

##### Country

1. The top 10 countries have been the highest revenue generators for the past three years
```sql
WITH sub1 AS (
SELECT CustomerCountry AS Country, SUM(OriginalSales) AS CountryOriginalSales, ROUND(SUM(TotalDiscount),2) AS CountryTotalDiscount,
       ROUND(SUM(OriginalSales) - SUM(TotalDiscount),2) AS CountryTotalActualSales,
       (SELECT ROUND(SUM(OriginalSales) - SUM(TotalDiscount),2) FROM datawarehouse_portfolio2) AS TotalActualSales
FROM datawarehouse_portfolio2
GROUP BY CustomerCountry)
SELECT *,
       ROUND(CountryTotalActualSales / TotalActualSales * 100,2) AS PercentOfSales
FROM sub1
ORDER BY PercentOfSales DESC;
```
2. Which market holds the greatest potential?
```sql
SELECT sub2.Country, SalesIn1996, SalesIn1997, SalesIn1998,
       SalesIn1996 + SalesIn1997 + SalesIn1998 AS TotalSales,
       ROUND((SalesIn1997 - SalesIn1996) / SalesIn1996 * 100,2) AS GrowthRateIn1997,
       ROUND((SalesIn1998 - SalesIn1997) / SalesIn1997 * 100,2) AS GrowthRateIn1998,
       ROUND((SalesIn1998 - SalesIn1996) / SalesIn1996 * 100,2) AS TotalGrowthRate,
       sub4.RankOnTotalSales
FROM (SELECT Country,
			 SUM(CASE WHEN Year = 1996 THEN OriginalSales ELSE 0 END) AS SalesIn1996, 
			 SUM(CASE WHEN Year = 1997 THEN OriginalSales ELSE 0 END) AS SalesIn1997,
			 SUM(CASE WHEN Year = 1998 THEN OriginalSales ELSE 0 END) AS SalesIn1998
	  FROM (SELECT CustomerCountry AS Country, year(OrderDate) AS Year, SUM(OriginalSales) AS OriginalSales
	        FROM datawarehouse_portfolio2
	        GROUP BY Country, year(OrderDate)
	        ORDER BY Country, Year) AS sub1
      GROUP BY Country) AS sub2
JOIN (SELECT Country, 
       RANK() OVER(ORDER BY TotalSales DESC) AS RankOnTotalSales
      FROM (SELECT CustomerCountry AS Country, SUM(OriginalSales) AS TotalSales
	        FROM datawarehouse_portfolio2
            GROUP BY CustomerCountry) AS sub3) AS sub4
ON sub2.Country = sub4.Country
ORDER BY TotalGrowthRate DESC;
```

3. Is our dependence on a particular shipper excessively high for each country?
```sql
SELECT Country, TotalSalesOnFederalShipping, TotalSalesOnSpeedyExpress, TotalSalesOnUnitedPackage,
       ROUND(TotalSalesOnFederalShipping / (TotalSalesOnFederalShipping + TotalSalesOnSpeedyExpress + TotalSalesOnUnitedPackage) * 100,2) AS PercentOnFederalShipping,
       ROUND(TotalSalesOnSpeedyExpress / (TotalSalesOnFederalShipping + TotalSalesOnSpeedyExpress + TotalSalesOnUnitedPackage) * 100,2) AS PercentOnSpeedyExpress,
       ROUND(TotalSalesOnUnitedPackage / (TotalSalesOnFederalShipping + TotalSalesOnSpeedyExpress + TotalSalesOnUnitedPackage) * 100,2) AS PercentOnUnitedPackage
FROM (SELECT Country,
             SUM(CASE WHEN ShipperCompanyName = 'Federal Shipping' THEN TotalSales ELSE 0 END) AS TotalSalesOnFederalShipping,
             SUM(CASE WHEN ShipperCompanyName = 'Speedy Express' THEN TotalSales ELSE 0 END) AS TotalSalesOnSpeedyExpress,
             SUM(CASE WHEN ShipperCompanyName = 'United Package' THEN TotalSales ELSE 0 END) AS TotalSalesOnUnitedPackage
	  FROM (SELECT CustomerCountry AS Country, ShipperCompanyName, SUM(OriginalSales) AS TotalSales
			FROM datawarehouse_portfolio2
			GROUP BY CustomerCountry, ShipperCompanyName
			ORDER BY CustomerCountry) AS sub1
	  GROUP BY Country
	  ORDER BY Country) AS sub1;
```
##### Product

1. Are the discounts offered on various product types justified?
```sql
WITH sub2 AS (
SELECT Category, ROUND(SUM(Sales),2) AS TotalSales, ROUND(SUM(Discount),2) AS TotalDiscount,
       ROUND(SUM(Discount) / SUM(Sales) * 100,2) AS PercentOfDiscount
FROM ( SELECT 'Beverages' AS Category, SalesInBeverages AS Sales, DiscountInBeverages AS Discount
	   FROM datawarehouse_portfolio2
	   UNION ALL
	   SELECT 'Condiments' AS Category, SalesInCondiments AS Sales, DiscountInCondiments AS Discount
	   FROM datawarehouse_portfolio2
       UNION ALL 
	   SELECT 'Confections' AS Category, SalesInConfections AS Sales, DiscountInConfections AS Discount
       FROM datawarehouse_portfolio2
	   UNION ALL
	   SELECT 'Dairy Products' AS Category, SalesInDairyProducts AS Sales, DiscountInDairyProducts AS Discount
	   FROM datawarehouse_portfolio2
	   UNION ALL
       SELECT 'Grains And Cereals' AS Category, SalesInGrainsAndCereals AS Sales, DiscountInGrainsAndCereals AS Discount
	   FROM datawarehouse_portfolio2
	   UNION ALL
	   SELECT 'Meat And Poultry' AS Category, SalesInMeatAndPoultry AS Sales, DiscountInMeatAndPoultry AS Discount
	   FROM datawarehouse_portfolio2
	   UNION ALL 
	   SELECT 'Produce' AS Category, SalesInProduce AS Sales, DiscountInProduce AS Discount
	   FROM datawarehouse_portfolio2
       UNION ALL 
	   SELECT 'Seafood' AS Category, SalesInSeafood AS Sales, DiscountInSeafood AS Discount
	   FROM datawarehouse_portfolio2) AS sub1
GROUP BY Category) 
SELECT *,
       RANK() OVER(ORDER BY TotalSales DESC) AS RankOnTotalSales,
       RANK() OVER(ORDER BY PercentOfDiscount DESC) AS RankOnPercentOfDiscount
FROM sub2
ORDER BY RankOnPercentOfDiscount;
```
#### Third phase – Buiding View for Visualization
```sql
USE cis467_final_project;

CREATE OR REPLACE VIEW Aggregation_tableau AS
SELECT o.OrderID, c.CustomerID, c.Country,
       CASE WHEN sub2.GroupNumber = 1 THEN 'First Class Of Customer' 
       WHEN sub2.GroupNumber = 2 THEN 'Second Class Of Customer' 
       WHEN sub2.GroupNumber = 3 THEN 'Thrid Class Of Customer' 
       WHEN sub2.GroupNumber = 4 THEN 'Forth Class Of Customer' 
       WHEN sub2.GroupNumber = 5 THEN 'Fifth Class Of Customer' 
       END AS ClassOfCustomer,
       STR_TO_DATE(OrderDate, '%m/%d/%Y') AS OrderDate, STR_TO_DATE(RequiredDate, '%m/%d/%Y') AS RequiredDate,
       STR_TO_DATE(ShippedDate, '%m/%d/%Y') AS ShippedDate, s.CompanyName,
       od.ProductID, ca.CategoryName, od.UnitPrice, od.Quantity,
       ROUND(od.UnitPrice * od.Quantity, 2) AS TotalSales,
       ROUND(od.UnitPrice * od.Discount * od.Quantity, 2) AS TotalDiscount,
       su.CompanyName AS SupplierName,
       CONCAT(e.FirstName, "  " ,e.LastName) AS EmployeeName,
       r.RegionDescription AS EmployeeRegion
FROM orders AS o
JOIN customers AS c
ON o.CustomerID = c.CustomerID
JOIN shippers AS s
ON o.ShipVia = s.ShipperID
JOIN order_details AS od
ON o.OrderID = od.OrderID
JOIN products AS p
ON od.ProductID = p.ProductID
JOIN categories AS ca
ON p.CategoryID = ca.CategoryID
JOIN suppliers AS su
ON p.SupplierID = su.SupplierID
JOIN employees AS e
ON o.EmployeeID = e.EmployeeID
JOIN employeeterritories AS et
ON e.EmployeeID = et.EmployeeID
JOIN territories AS t
ON et.TerritoryID = t.TerritoryID
JOIN region AS r
ON t.RegionID = r.RegionID
JOIN (SELECT CustomerID, SUM(TotalSales) AS TotalSales,
      NTILE(5) OVER(ORDER BY SUM(TotalSales) DESC) AS GroupNumber
      FROM (SELECT o.OrderID, o.CustomerID, ROUND(od.UnitPrice * od.Quantity, 2) AS TotalSales
            FROM orders AS o
            JOIN order_details AS od
            ON o.OrderID = od.OrderID) AS sub1
      GROUP BY CustomerID) AS sub2
ON sub2.CustomerID = o.CustomerID
ORDER BY OrderID;
```
