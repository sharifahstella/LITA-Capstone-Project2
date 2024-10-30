# Customer Segmentation for a Subscription Service

## Project Overview
This project aims to analyze customer data for a subscription service to identify segments and trends. The Key metrics are to understand customer behavior, track subscription types, and detect key trends in cancellations and renewals. The tools used include Excel for data exploration, SQL for data extraction and manipulation, and Power BI for data visualization and reporting.


### Goals:
  - To track customer behavior
  - Monitor subscription types
  - Understand trends in cancellations and renewals.
    
## 1.1 Data Preparation in Excel
###  Data Overview

The Customer data includes the following columns:

- CustomerID: Unique identifier for each customer.
- SubscriptionType: The type of subscription each customer has.
- SubscriptionStart: The date the subscription started.
- SubscriptionEnd: The date the subscription ended.
- SubscriptionDuration: Duration of the subscription in days.
- CustomerName: The name of the customer.
- Region: The geographical location of the customer.
- Canceled: Indicates if the subscription was canceled (Yes/No).
- Revenue: The total revenue generated by the customer’s subscription.

#### Data Example:

![Customerdata set](https://github.com/sharifahstella/LITA-Capstone-Project2/blob/main/customerTable.JPG)

  - Used pivot tables to summarize the data set 

i) Calculate the average subscription duration using pivot Table 

![Monthly sales](https://github.com/sharifahstella/LITA-Capstone-Project2/blob/main/subscription.JPG)

ii) identify the most popular subscription types.

![salesProduct](https://github.com/sharifahstella/LITA-Capstone-Project2/blob/main/sub.JPG)

Also made some other additional reports using a pivot table which include :

i) Total revenue by each region

![Monthly sales](https://github.com/sharifahstella/LITA-Capstone-Project2/blob/main/revenue.JPG)

ii) The number of cancelled and active subscriptions by customers

![Monthly sales](https://github.com/sharifahstella/LITA-Capstone-Project2/blob/main/canceled.JPG)

iii) Monthly Subscription Counts

I found out that subcription have been varying from month to month so therefore the trend has reduced from 2022 to 20233 by 41%

![Monthly sales](https://github.com/sharifahstella/LITA-Capstone-Project2/blob/main/monthcount.JPG)

- Used bar graph,pie chart and a line graph to represent the summary of the total sales in the dataset as follows

  i) Bar graph showing Most popular subscription being basic with the most customers
  
  ![bar](https://github.com/sharifahstella/LITA-Capstone-Project2/blob/main/bar2.JPG)

  ii)Bar graph showing Total revenue generated in each region being with East having the most generated revenue

 ![bar](https://github.com/sharifahstella/LITA-Capstone-Project2/blob/main/bar3.JPG)

  iii) The line graph showing the monthly trend of subscription which has dropped over the year of 2023 by 41%

  ![](https://github.com/sharifahstella/LITA-Capstone-Project2/blob/main/line2.JPG)

  iv) A pie chart showing the number of active and canceled subscription among the customer whereby there was more of active customers than the canceled ones 

  ![](https://github.com/sharifahstella/LITA-Capstone-Project2/blob/main/pieee.JPG)

## 2.2 SQL Queries for Analysis

- Retrieve the total number of customers from each region

```
SELECT Region, COUNT(CustomerID) AS Total_Customers
FROM [dbo].[LITA Capstone Dataset2]
GROUP BY Region;

```

![](https://github.com/sharifahstella/LITA-Capstone-Project2/blob/main/res1.PNG)

This code provides an insight into regional customer distribution with NORTH having the most unique distributed customers


- Find the most popular subscription type by the number of customers

```
SELECT SubscriptionType, COUNT(CustomerID) AS Customer_Count
FROM [dbo].[LITA Capstone Dataset2]
GROUP BY SubscriptionType
ORDER BY Customer_Count DESC;

```
![](https://github.com/sharifahstella/LITA-Capstone-Project2/blob/main/res2.PNG)

This query calculates the count of customers for each SubscriptionType, sorted in descending order to show the most popular type at the top which the Basic subscription Type with the most customer counts 


- Find customers who canceled their subscription within 6 months

 ```
  SELECT CustomerID, CustomerName, SubscriptionType, SubscriptionStart, SubscriptionEnd
FROM [dbo].[LITA Capstone Dataset2]
WHERE Canceled = 'Yes' 
    AND DATEDIFF(DAY, SubscriptionStart, SubscriptionEnd) <= 180;
    
```
This query identifies customers who canceled their subscription within six months (180 days), providing early churn data of which there was no customer found thatcanceled their subscriptions with six months in the customer segimentation dataset.

- Calculate the average subscription duration for all customers

```
SELECT AVG(DATEDIFF(DAY, SubscriptionStart, SubscriptionEnd)) AS Avg_Subscription_Duration
FROM [dbo].[LITA Capstone Dataset2]
WHERE SubscriptionEnd IS NOT NULL;

```
![](https://github.com/sharifahstella/LITA-Capstone-Project2/blob/main/res4.PNG)

This query calculates the average subscription duration (in days) across all customers, which can help identify general customer retention length of which it is 365 days

- Find customers with subscriptions longer than 12 months

```
SELECT CustomerID, CustomerName, SubscriptionType, DATEDIFF(DAY, SubscriptionStart, SubscriptionEnd) AS Subscription_Duration
FROM [dbo].[LITA Capstone Dataset2]
WHERE DATEDIFF(DAY, SubscriptionStart, SubscriptionEnd) > 365;

```
![](https://github.com/sharifahstella/LITA-Capstone-Project2/blob/main/rres5.PNG)

This query identifies customers whose subscriptions lasted longer than one year (365 days), indicating higher retention.

- Calculate total revenue by subscription type

```
SELECT SubscriptionType, SUM(Revenue) AS Total_Revenue
FROM [dbo].[LITA Capstone Dataset2]
GROUP BY SubscriptionType;

```

This query calculates the total revenue generated by each subscription type, helping to analyze the revenue contribution by product type.

- Find the top 3 regions by subscription cancellations

```
SELECT TOP 3 Region, COUNT(CustomerID) AS Cancellations
FROM [dbo].[LITA Capstone Dataset2]
WHERE Canceled = 'TRUE'
GROUP BY Region
ORDER BY Cancellations DESC;
```

This query identifies the top three regions with the highest number of canceled subscriptions, showing regional cancellation trends.with North,East and South having the most cancellations respectively

- Find the total number of active and canceled subscriptions

```
SELECT Canceled, COUNT(CustomerID) AS Total_Customers
FROM [dbo].[LITA Capstone Dataset2]
GROUP BY Canceled;

```

This query groups customers by subscription status (Canceled), showing counts for both active (FALSE) and canceled (TRUE) subscriptions.With alot of canceled subscriptions copmared to active ones

## Summary of Key Insights


## 3.3 Power BI Dashboard


 




