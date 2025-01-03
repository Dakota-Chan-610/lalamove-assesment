# lalamove-assesment
Lalamove SQL Assesment

# BigQuery Code:
## Part1-a
https://console.cloud.google.com/bigquery?sq=1067343833426:7c8f9566a3944d7e8c087125ed0dc160
## Part1-b
https://console.cloud.google.com/bigquery?sq=1067343833426:d05a344e760f4374ab91d796664313c4
## Part1-c
https://console.cloud.google.com/bigquery?sq=1067343833426:5c4005824647459b949024356bd1917e
## Part1-d
https://console.cloud.google.com/bigquery?sq=1067343833426:1304ace82ae6463cbd21c5fae5c4cdd3
## Part1-e
https://console.cloud.google.com/bigquery?sq=1067343833426:27e5af6592194c269d8ab3a1a090683a
## Part2
https://console.cloud.google.com/bigquery?sq=1067343833426:672af62f4a2b491ebb0c25d4cbaf0494

# Question:
Part (1)
There are two sample tables in this small test, one table called "vanorder" and one table called "vaninterest".

Logic of the sample system: A record is created in van-order when user places an order. Each order starts at order_subset A, and each order can be accepted by multiple drivers. There will be a new record in the vaninterest table when a driver accepts an order. After accepting order, the driver has the option to reject an order, which will go back to the pool and allow other drivers to match this order again.

1) vanorder
- Contains the final status of the orders information
- idvanOrder: The order ID, which is the primary key 
- order_status: The final status of the order.
  -- 2: 'Completed'
  -- 3: 'Cancelled'
  -- 5: 'Expired'
- order_subset: The final order subset of the order
- requestor_client_id: The user account ID
- servicer_auth: The driver ID
- total_price: The price of the order
- order_datetime: The order time of the order
- txCreate: The record creation time, which is the order placed time by the user

2) vaninterest
- Contains the order information for each subset 
- idvanInterest: The primary key of this table 
- idvanOrder: The order ID associated to this record
- order_subset_assigned: The order subset that is associated to this record
- servicer_auth: The driver ID for this subset
- txCreate: The record creation time, which is the time that this driver accepted the order

We are using MySQL for the tables. If you have a MySQL database available, you can run the SQL file, p1_data.sql, to create two tables in the database. The two files, vaninterest.csv and vanorder.csv, contain the same data.

Now we are write a few SQL statement to understand more about our data, users, and drivers. Unless specified otherwise, use all data available in the sample tables. Please use one SQL statement for finding each of the following:

a) For hours with orders, how many orders are there each hour based on order time?
b) What is the percentage of money spent for each of the following group of clients?
	- Clients who completed 1 order
	- Clients who completed more than 1 order
c) List of unique Client ID who completed at least one order, also show each client's total money spent, and the total order(s) completed. Order the list by total money spent (descending), then by total order(s) completed (descending)
d) List of all drivers who took order(s) (regardless of whether they eventually complete the order), also show each driver's total income and total order(s) completed. Order the list by total income (descending), then by total order(s) completed
e) List of driver ID who took orders, but never complete an order?

Part (2)
We would like to test the impact of a change introduced at ‘2017-03-30 12:00:00 AM’ on our Order Allocation system. The objective of the change is to improve order Match Time, which is the duration since the time an order was created to the time the order was accepted by a driver. The file response_data.csv contains the order records you’d need for this part of the challenge.

Feel free to derive your answers to the following questions using any techniques and softwares of your choice:
a) What is the resulting impact from this change?
b) Any additional insights or observations you think are worth noting?
c) Any observations regarding the testing process or environment? How would you improve or redesign this experiment?

Your answer will be evaluated based on the following aspects (you can provide your answers in any form you like):
- Your thought process and how you get to your results
- Your visualization and statistical knowledge
- Your presentation and delivery of results

