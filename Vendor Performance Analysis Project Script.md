Vendor Performance Analysis Project

Tools used: SQL,Python,Power BI

Steps of Analysis:

Business Problem:
Effective inventory and sales management are criticalfor optimizizng profitability in the retail and wholesale industry. Companies need to ensure thata they are not incurring losses due to inefficient pricing. Poor inventory turover,or vendor dependency.

The Goal of this  analysis is to :
1.Identity underperforming brands that require promotional or pricing adjustments.
2.Determine top vendor contributing to sales and gross profit.
3.Analyze the impact of bulk purching on unit costs.
4.Assess inventory turn over to reduce holding costs and improve efficiency.
5.Investigate the profitability variance between high_performing and low-performing vendors. 

 EDA with Python (Matplotlib, Seaborn, Pandas) 
 
Exploratory Data analysis:
Understanding the database to explore how the data is present in the database and if there is a need of creating some aggregate table that can help with:
*Vendor selection of profitability. 
*Product pricing Optimization.

In this phase of EDA,we will analyze the resultant table to gain insights into the distribution of each column.
This  will Help us understand data patterns ,identity anomalies ,and ensure data quality before processing with futher analysis.

Observation:
* The purchases table contains actual purchase dat,including the data of
purchase,products (brands)purchased by vendors.the amount paid (in dollars),and the quantity purchased.
* The purchase  price column is derived from the purchase_price table ,which provides product_wise actual and purchase price. The combination of vendor and brand is unique in this table.
* The vendor_invoice table aggregates data from the purchases table, summarizing quantity and dollar amounts,along with an additionalcolumn for freight,This table maintains uniqueness based on vendor and po number.
* The table captures actual sales transactions,detailing the brands purchased by vendor ,the quantity sold ,the selling price and the revenue earned.

|As the data that we need for analysis is distributed in different tables,we need to create a summarytable containing.

* Purchase transactions made by vendor.
* Sales transaction data
* Freight costs for each vendor
* Actual product prices from vendors.

This query generates a vendor _wise sales and purchase summary ,which is valuble for :
Performanace Optimization:-
* The query involves heavy joins and aggregations on large datasets like sales and purchases.
* Strong the pre-aggregated results avoids repeated expensive computions.
* Helps in analyzing sales,purchases,and pricing for different vendors and brands.
* Future benefits of Strong this data for faster Dashboarding & Reporting.

Insights:
Summary Statistics Insights:
 
 Negtive & Zero Values:-
 1. Gross profit: Minimum values is -52,002.78,indicating losses.Some products or transactions may be selling at a loss due to high costs or selling at discounts lower than the purchase price.....
2. Profit Margin: which suggests cases where revenue is zero or even lower than costs.
3. Total Sales Quantity & Sales Dollars: Minimum values are 0,meaning some products were purchased but never sold.These could be slow moving or odsoelte stock .

Outilers Indicated by High Standard Deviations:
1. Purches & Actual prices: The max values(5,681.81 & 7,499.99)are significantly higher tahn the mean (24.39 & 35.64),indicating potentail premium products.
2. Freigh Cost: Huge variation,from 0.09 to 257,032.07,suggests logistics inefficiencies or bulk shipments.
3. Stock Turnover: Ranges from 0 to 274.5,implying some products sell extremely fast while others remain in stock identifinitely.Value more than 1 indicates that sold quantity ofr that product is higher then purchased quantity due to either are being fullfilled order stock.

Correlation Insights:

* PurchasePrice has weak correlations with TotalSalesDollars (-0.012) and GrossProfit (-0.016), suggesting that price variations do not significantly impact sales revenue or profit.

* Strong correlation between total purchase quantity and total sales quantity (0.999), confirming efficient inventory turnover.

* Negative correlation between profit margin & total sales price (-0.179) suggests that as sales price increases, margins decrease, possibly due to competitive pricing pressures.

* StockTurnover has weak negative correlations with both GrossProfit (-0.038) and ProfitMargin (-0.055), indicating that faster turnover does not necessarily result in higher profitability.





