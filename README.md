# CUSTOMER-DATA-ANALYSIS


Project 2: Customer Segmentation for a Subscription Service
1. Project Objective
•	Analyze customer data to identify behavioral patterns, track subscription types, and discover trends in cancellations and renewals.
2. Dataset
•	File Name: CustomerData
•	Key Columns: CustomerId, Region, SubscriptionType, StartDate, EndDate
•	Data Notes: This dataset includes customer subscription details, tracking metrics like region, subscription type, start and end dates.
3. Tools Used
•	Excel: For data exploration and summary reports.
•	SQL Server: Data querying for insights.
•	Power BI: Visualization of customer segmentation trends.
4. Methodology and Steps
•	Excel Analysis:
o	Created pivot tables to identify subscription patterns and popular subscription types.
o	Calculated metrics such as average subscription duration.
o	Generated additional reports on customer behavior, as outlined in the Excel attachment.
•	SQL Analysis:
o	Queries executed on SQL Server to extract insights:
o	Customers by Region:
Code:
SELECT Region, COUNT(CustomerId) AS TotalCustomers FROM CustomerData GROUP BY Region.
o	Most Popular Subscription Type:
Code:
SELECT SubscriptionType, COUNT(CustomerId) AS Subscribers FROM CustomerData GROUP BY SubscriptionType ORDER BY Subscribers DESC LIMIT 1;
o	Customers with Cancellations Within 6 Months:
Code:
SELECT CustomerId FROM CustomerData WHERE DATEDIFF (Month, StartDate, EndDate) <= 6;
o	Average Subscription Duration:
Code:
SELECT AVG(DATEDIFF(Month, StartDate, EndDate)) AS AvgSubscriptionDuration FROM CustomerData;
o	Top Regions by Cancellations:
Code:
SELECT Region, COUNT(CustomerId) AS Cancellations FROM CustomerData WHERE EndDate IS NOT NULL GROUP BY Region ORDER BY Cancellations DESC LIMIT 3;
o	Total Active vs. Canceled Subscriptions:
Code:
SELECT COUNT(CASE WHEN EndDate IS NULL THEN 1 END) AS ActiveSubscriptions, COUNT(CASE WHEN EndDate IS NOT NULL THEN 1 END) AS CanceledSubscriptions FROM CustomerData;
•	Power BI Dashboard:
o	Designed visuals to showcase:
	Customer segmentation patterns
	Cancellations and subscription trends
	Regional comparisons and popular subscription types
5. Key Insights from Customer Segmentation Analysis
•	Popular Subscription Type: The most popular subscription type was identified as Type X.
•	Average Subscription Duration: The average subscription duration for customers was approximately X months.
•	Cancellation Trends: The highest cancellation rates occurred within the first six months.
•	Top Regions by Cancellations: Regions A, B, and C had the highest rates of subscription cancellations.
________________________________________
Conclusion
This documentation provides an overview of the tools, methods, and findings from the Sales Performance and Customer Segmentation analyses. The Power BI dashboards created offer valuable interactive visuals, enabling stakeholders to understand and act on the data insights.


