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
  
  ![bar](https://github.com/sharifahstella/LITA-Capstone-Project2/blob/main/bargra.JPG)

  i)Bar graph showing Total revenue generated in each region being with East having the most generated revenue

 ![bar](https://github.com/sharifahstella/LITA-Capstone-Project2/blob/main/bar3.JPG)

  ii) The line graph showing the monthly trend of subscription which has dropped over the year of 2023 by 41%

  ![](https://github.com/sharifahstella/LITA-Capstone-Project2/blob/main/lineeeeeeeeee.JPG)

  iii) A pie chart showing the number of active and canceled subscription among the customer whereby there was more of active customers than the canceled ones 

  ![](https://github.com/sharifahstella/LITA-Capstone-Project2/blob/main/chart.JPG)

## 2.2 SQL Queries for Analysis

 




