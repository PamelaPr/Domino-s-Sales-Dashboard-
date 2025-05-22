# Domino-s-Sales-Dashboard-
 Project Overview
Objective: The purpose of the Power BI dashboard is to provide insights into Domino's sales, operational performance.
Target Users: This dashboard will be used by regional managers, corporate executives, and store owners to track KPIs and make data-driven decisions.

Data Source:
Sales Data: CSV file containing time based data, including order details, prices, and quantity.
Data Preparation:
Data Transformation Tool: Power Query was used for ETL (Extract, Transform, Load) processes.
Data Cleansing:
Removed duplicates from the sales data.
Filled missing values.
Standardized delivery time formats.

Calculated Columns:
Order Value: Calculated as Quantity * Price.
Ordered Time: Calculated based on order timestamp as
Let
hour = Time.Hour([order_time]),
minute = Time.Minute([order_time]),
roundedHour = if minute >= 30 then hour + 1 else hour,
adjustedHour = if roundedHour = 0 then 12 else if roundedHour > 12 then roundedHour - 12 else roundedHour,
suffix = if roundedHour < 12 then "AM" else "PM",
finalHour = if roundedHour = 12 and minute >= 30 then 12 else adjustedHour 
In
Text.From(finalHour) & ":00 " & suffix

KPIs & Metrics
The dashboard will focus on the following Key Performance Indicators (KPIs):
Total Sales: Total revenue generated over a specific period.
Average Order Value (AOV): Average amount spent per order.
Total Order: Total order generated over a specific period.
Total Pizza Sold: Total Pizza sold over a specific period .

Dashboard Overview
Total Sales, Average Order Value (AOV),Total Order, Total Pizza Sold
 : Displayed using a card visual.
Order by Day & Peak Time:
 A Stacked Column Chart showing day wise sales and another one for showing  peak time(hours of a day) of the sale.
Top 5 Selling Pizza: Multi-row card for displaying 5 highest & lowest  selling pizzas. 

User Interaction
Slicers: Users can filter the data by:
Time period
Product category

Future Enhancements
Predictive Analytics: Implement machine learning models to predict customer churn and delivery times.

Conclusion
This Power BI dashboard offers a comprehensive view of Domino's key business metrics. The tool will help decision-makers track performance, identify trends, and make data-driven decisions to enhance operational efficiency and customer satisfaction.
