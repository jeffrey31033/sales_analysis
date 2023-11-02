# Data analysis in a retail store with SQL and Tableau

### Project Overview

The objective of this data analysis project is to provide insights into various aspects of the sales performance of a retail store from 1996Q3 to 1998Q4. Through a comprehensive data analysis, our goal is to discern trends, make well-informed, data-driven decisions, and enhance our comprehension of the company's overall performance.

The project unfolds in three different phases. Firstly, we establish a data warehouse by merging and aggregating data from multiple tables to create a unified and informative dataset. In the second phase, we conduct exploratory data analysis by executing specific queries to achieve predefined objectives and extract valuable insights from the data. Finally, we employ Tableau to create visualizations that effectively convey the findings derived from the data warehouse.

### Data Sources

Sales Data: The primary dataset used for analysis derived from the final project in data management course, containing detailed information about each order made by the company

### Tools

-	MYSQL – Building Data Warehouse and Execute Queries  
-	Tableau – Visualizing Data from Data Warehouse

### First Phase – Building Data Warehouse

To acquire a more profound understanding of customer behavior and product-related insights, my initial choice for the first column is order id. I then aggregate diverse facets of revenue and discounts associated with different product types across various orders.

### Second Phase – Exploratory Data Analysis

#### Customers

1. Should discounts be offered to these customers?
   <img width="525" alt="query_1-Should we give discounts to these customers" src="https://github.com/jeffrey31033/sales_analysis/assets/149200070/2b9a0c95-081b-4759-96e9-bed87f067d1a">  <br> 
The table provides insights into which customers haven't delivered the value we anticipated. It's organized by the rank of the discount percentage. Typically, larger discounts are reserved for customers who buy more products from us. However, there's a noticeable discrepancy in the volume of products purchased by Piccolo und mehr and LILA-Supermercado compared to the discounts they receive. Unless there are specific reasons for this anomaly, we should consider reducing their discount percentages.

2. What is the predominant product type purchased by each customer?
   <img width="389" alt="query_3-What product type does a customer buy the most" src="https://github.com/jeffrey31033/sales_analysis/assets/149200070/203bb7f6-610c-4cb0-994a-f20e2a018dba">
 <br> 
The table offers a detailed view of each customer's revenue composition. With this knowledge of their revenue structure, we're equipped to tailor our pricing strategies according to different customer tiers. This approach allows us to create a product portfolio and implement bundle pricing for our clients. Take Bon app’ as an example, considering that seafood and meat/poultry are ranked first and eighth in sales respectively, a strategic move would be to combine select offerings from both categories into a bundled product portfolio. This strategy could potentially enhance our sales in the meat/poultry category.

3. Could we be losing key customers due to delayed shipments?
   <img width="595" alt="query_4-Are we possible losing our important due to the late shipment" src="https://github.com/jeffrey31033/sales_analysis/assets/149200070/3cb5e954-ec1f-468f-8602-42c50435c955">
<br>
Ensuring order processing on time is key to enhancing customer experience, especially for our most valuable clients. The data reveals a discrepancy between the required and actual shipping dates. The table highlights the proportion of late orders for each customer. Notably, among our top 20 customers by total revenue, eleven have experienced delays in receiving their orders. It's crucial for us to minimize these late deliveries, as the primary cause appears to be internal processing inefficiencies rather than shipping delays. Addressing this issue will improve customer satisfaction.

4. Is our dependence on a particular shipper excessively high for each individual customer?
   <img width="773" alt="query_5-Do we rely too much on one specific shipper" src="https://github.com/jeffrey31033/sales_analysis/assets/149200070/09fcd972-55cb-478c-bb00-429cf43f8c46">
<br>
The data presented provides valuable perspectives on risk distribution. Take Norway as an example: a significant portion of the total shipments predominantly depends on United Package. This scenario highlights a considerable risk: if United Package were to face any operational challenges, it would be difficult for us to find an alternative promptly. Such a dependency means that any disruption in United Package's services could impede our ability to deliver products efficiently, potentially resulting in customer dissatisfaction. It's important for us to consider diversifying our shipping partners to mitigate these risks.

5. Which other customers are significant to our business?
   <img width="646" alt="query_7-Which customers are also important to us" src="https://github.com/jeffrey31033/sales_analysis/assets/149200070/3a03ff93-5de6-45de-b4ba-c6180c1fd7f1">
<br>
The table clearly illustrates that there isn't a direct correlation between the rank based on total actual revenue and the rank based on average subtotal per order for each customer. For instance, Simons bistro ranks 35th in terms of subtotal, yet its average subtotal per order is impressively higher, at rank 6. This disparity suggests that customers like Simons bistro, who may not be top-ranked in overall spending but place large orders on average, should also be a focus for our sales strategy. Increasing the purchase frequency of such customers could significantly benefit our company due to the substantial value of each order they place.

#### Country

1. The top 10 countries have been the highest revenue generators for the past three years
   <img width="544" alt="query_8-The top 10 countries produce the most revenue for 3 years" src="https://github.com/jeffrey31033/sales_analysis/assets/149200070/b24337ce-c8e6-4811-bf4a-d6486b6c4891">
<br>
This query provides vital data on the top 10 countries contributing the most to our revenue, including the specific percentage each country contributes to our total revenue. Such information is instrumental in guiding our resource allocation decisions, particularly in areas like advertising and marketing, enabling us to strategize our efforts more effectively in these key markets.

2. Which market holds the greatest potential?
   <img width="680" alt="query_2-Which market has the most potential" src="https://github.com/jeffrey31033/sales_analysis/assets/149200070/e9cb959d-d469-48a1-9ffb-89d63a30022b">
<br>
Understanding growth rates across various markets is crucial in determining the focus countries for a company and in assessing the effectiveness of our strategies. If a significant investment in advertising in a particular country doesn't yield an increase in sales, it's a clear indicator that our marketing approach needs recalibration as the return on investment is not aligning with expectations. Moreover, it's important to recognize that while some countries such as Italy and Poland might not be among the top 10 countries in terms of overall contribution to our business, their high growth rates shouldn't be overlooked. Such markets demand greater attention due to their potential for rapid expansion.

#### Product

1. Are the discounts offered on various product types justified?
   <img width="506" alt="query_6-Are the discounts on different product type reasonable" src="https://github.com/jeffrey31033/sales_analysis/assets/149200070/fbf2c28d-3543-47cd-8fe6-267420fb71d8">
<br>
The table provides a comparative analysis of the ranking based on percentage discounts and the ranking in terms of total revenue. Though meat/poultry and seafood categories are not among the most valuable for our company, they still receive significant discounts. Unless there are some specific reasons justifying this strategy, it may be prudent to reevaluate our discount policies for these products.


