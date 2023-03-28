# NorthWind Traders

![alt text](img/NorthWind.png)

Fonte: RodReis, em Unsplash

---

## 1 - Business Problems

### 1.1 - Business Problems

**NorthWind Traders** is a fictional store that manages orders, products, customers, suppliers, and many other aspects of a small business. It has reports made on spreadsheets on demand.

When the company was small, this format worked, but now with the accelerated growth of the company, **data from different areas started to not match**, and meetings became more conflicting. The company also wants to better understand its data to **increase the average ticket** and **reduce churn** (two objectives considered strategic in the medium term).



### 1.3 - About the data

---
|SpreadSheets | Meaning |
| --- | --- |
| orders| A collection of records that represent purchase orders made by customers for specific products. |
| order_details| A collection of records that represent the individual line items in each purchase order, including details such as the product, quantity, and price. |
| products| A collection of records that represent the products available for purchase in the store, including details such as the product name, description, and price. |
| categories| A collection of records that categorize the products, providing an organizational structure for the store's inventory. |
| customer_customer_demo| A table that stores demographic information about the store's customers, such as age, income, and education level. |
| customer_demographics| A collection of records that define various demographic segments for customers, allowing for targeted marketing efforts. |
| customers| A collection of records that represent the store's customers, including details such as their name, address, and contact information. |
| employee_territories| A table that associates employees with specific sales territories, allowing for better management of sales efforts. |
| employees| A collection of records that represent the store's employees, including details such as their name, title, and contact information. |
| region| A collection of records that define various geographic regions, allowing for better management of sales efforts and reporting. |
| shippers| A collection of records that represent the various shipping companies the store uses to fulfill orders, including details such as their name and contact information. |
| suppliers| A collection of records that represent the various suppliers the store uses to purchase products, including details such as their name and contact information. |
| territories| A collection of records that define various sales territories, allowing for better management of sales efforts and reporting. |
| us_states| A collection of records that represent the various states in the US, allowing for better management of sales efforts and reporting based on location. |




---



## 2 - Solution Strategy

**CRISP-DM** stands for Cross Industry Standard Process for Data Mining, which can be translated as Standard Process for Inter-Industry Data Mining. It is a data mining process model that describes commonly used approaches by data mining experts to tackle problems.

<img src="img/crisp.jpg" width="500">

As a basis for this project, we will use CRISP, and once the entire first cycle of CRISP is completed, we can make further iterations, create new features, generate new insights, and improve model performance, all to deliver more value to the company. It is also important to engage with stakeholders in the project throughout the process, to keep them informed and manage their expectations.

All codes, visualizations and analysis of this project can be followed in this [Notebook](notebook/v03.ipynb).

### 2.1 - Data Organizations Problem

1. As a way to better manage the data conflicts generated by the accelerated growth of the company, an Entity-Relationship Model (ERM) was developed so that different areas can have access to more accurate information.
<img src="img/mer.png" width="500">

2. Customer Dataframe: Information such as lifespan, churn, etc. was presented from data unions.
This data frame was created to analyze all customer information.
<img src="img/customer_df.png" width="600">

3. Order Order Dataframe: By unifying tables such as “order” and “order_details”, and generating new information from data combinations, an order data frame was created, facilitating data analysis.
<img src="img/orders_df.png" width="600">


### 2.2 - Exploratory Data Analysis

EDA: To better understand the data, I use techniques such as descriptive statistics, histograms, and other graphs to understand how the data behaves and what drove customers to churn.
<img src="img/hist.png" width="600">

### 2.2 - Cohort Analyses

Retention tables show the group of customers who purchased for the first time during a given period. They also exhibit a progressive "fall" or decline in activity over time for that specific group (a cohort).
<img src="img/cohort.png" width="600">

### 2.3 - Churn Analysis

In churn analysis, I check what assumptions a customer can make to churn and if I have any actionable insights. 

Key actionable insights:

1. The smaller the range of products purchased by the customer, the higher the churn rate. NorthWind has only **77 products**, this low assortment is one of the causes of churn.
<img src="img/hip01.png" width="600">

2. Orders with ship_via 3 have more churn, **is necessary to identify with deliveries what is happening**. 
<img src="img/hip02.png" width="600">

### 2.4 - RFM Analysis ( Recency Frequency Monetary Value )

RFM is a tool used to identify a company's or organization's best customers using certain measures.
<img src="img/rfm.png" width="600">

### 2.5 - Clustering customers by purchasing behavior
For grouping, the KMeans algorithm is used. The best number for clusters is 3.
<img src="img/elbow.png" width="600">
<img src="img/sihoute_score.png" width="600">

### 2.6 - Recommendation System
Based on the clusters, a recommendation system was created using a technique of spatial proximity of customer buying behavior data (by cluster), and the system shows the similarity assessment between customers, and returns a list of recommended products, according to the chosen customer.

In these examples, the customer's 'ID' (BERGS, AROUT) is entered (by the seller), and the program returns the similarity score between the customers ( 0.33, 0.5 ), and the lists of recommended products.
<img src="img/rec_sys.png" width="600">
<img src="img/rec_sys01.png" width="600">

### 2.7 - Elastic Price
Another solution to increase the average ticket would be to increase the value of each product. For this, I calculated the price elasticity, that is, how much it is possible to increase the value of the product without this resulting in a drop in sales of this product.

<img src="img/elastic_price.png" width="600">
<img src="img/elastic_price01.png" width="600">

### 2.8 - KPI's
In the current management model, NorthWind has no way of monitoring its performance indicators and, therefore, its decisions are taken only based on intuition.
To solve this, some KPIs were calculated:
- Revenue
- Numbers of Customers
- Churn Rate
- Average Ticket
- CLTV
- Average Delayed Days
- Assortment

## 3 - Next Steps
1. A sales forecast using the Facebook Prophet framework.

2. Seasonality analysis.

3. Increase customer data collection.
Fetch new data from customer regions.

4. From the increase in the number of data, calculate the price elasticity.

## 4 - Technologies

[![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)](https://www.python.org/)
[![Jupyter Notebook](https://img.shields.io/badge/jupyter-%23FA0F00.svg?style=for-the-badge&logo=jupyter&logoColor=white)](https://jupyter.org/)
[![NumPy](https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white)](https://numpy.org/)
[![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white)](https://pandas.pydata.org/)
[![Plotly](https://img.shields.io/badge/Plotly-%233F4F75.svg?style=for-the-badge&logo=plotly&logoColor=white)](https://plotly.com/python/plotly-express/)
[![Scikit-Learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)
[![SciPy](https://img.shields.io/badge/SciPy-%230C55A5.svg?style=for-the-badge&logo=scipy&logoColor=%white)](https://scipy.org/)
[![Git](https://img.shields.io/badge/git-%23F05033.svg?style=for-the-badge&logo=git&logoColor=white)](https://git-scm.com/)

## 5 - Author

Lucas da Cunha

Data Scientist / Data Analyst

[Project Portfolio](https://jlcunha.github.io/portfolio_projetos/)

[GitHub Profile](https://github.com/jlcunha/)
