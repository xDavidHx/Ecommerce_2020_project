# Ecommerce 2020 Exploratory Analysis

Project involving a data set for a product within the United States in 2020. Data is broken down time-wise by month and year, and location-wise state by state, and US Region by Region. 


First We start with the Data we Want. The Data is from Kaggle and sports Ecommerce Orders across the continental U.S. 
Link Here: https://www.kaggle.com/datasets/ammaraahmad/us-ecommerce-record-2020/data


What We want to Know: <br>
1.) What is the overall performance of our product in the USA? <br>
2.) Break down sales performance State by State, per month. <br>
3.) Reveal which states sold the most during the year 2020. <br>

Uploading the Dataset to Google Bigquery, we Write a SQL Query to conduct some exploratory Data Analysis: 

```
SELECT 
  Extract(YEAR FROM Order_date) AS order_year,
  Extract(MONTH FROM Order_date) AS order_month,
  State, 
  COUNT(*) AS order_count,
  

  FROM dehproject24.US_Ecommerce_Data_2020.US_Ecommerce_Data_2024

  GROUP BY 
    order_year, 
    order_month,
    State
  ORDER BY 
    order_year, 
    order_month, 
    State;
```
 This will get us the answers to 2 last two out of three questions we're asking. 

 After Building a dashboard in Tableau (Link here: https://public.tableau.com/app/profile/david.henderson3096/vizzes) 

 We Can conclude that the Highest Selling States From Greatest to Least are: California, New York, Texas, Washington, and Pennsylvania.

Each State's performance is highlighted in the dashboard created. 

But What about Our Total Sales Performance in the United States in the year 2020? 

Let's write another SQL Query.

Notice each order number, identical or not, is an order for a product. 

By Counting the total number of orders numbers present, we can count the total number of sales. 

```
SELECT COUNT(Order_ID) AS count_order_ids, COUNT(DISTINCT(Order_ID)) AS ct_dist_order_id

FROM dehproject24.US_Ecommerce_Data_2020.US_Ecommerce_Data_2024
```


Resulting in 
3312 Order ID's and 1687 DISTINCT ORDER_ID's. 

We can see here that despite 1687 DISTINCT order_id's, some orders had more than one item. 

To conclude this Leg our our Analysis:<br>
 *We Can conclude that the Highest Selling States From Greatest to Least are: California, New York, Texas, Washington, and Pennsylvania.*
 <br>
 *Each State's performance is highlighted in the dashboard created.*<br>
 *Total number of items bought in 2020 for our brand was 3312* <br>

 THANK YOU KAGGLE FOR A GREAT DATA SET. CREDIT TO **ammaraahmad** FOR IT'S CREATION. 



**This Project is a work in progress. Next Sprint will include an income Analysis.**
