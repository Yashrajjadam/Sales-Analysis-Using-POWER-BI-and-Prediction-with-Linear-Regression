# Sales Analysis and Prediction with Linear Regression.
===========================================================

# Overview
==========
We have a dataset named sales_data, downloaded from Kaggle. The sales analysis is done using Power BI, and the prediction is performed using linear regression.

# Steps for Analysis.
====================== 

1. Download the dataset:

Download the file sales_data.sql and the Power BI report raj.pbix.

2. View the dataset:

Open the sales_data.sql file in SQL Workbench (or any compatible SQL platform) to examine the tables, columns, and raw  data.

3. Analyze the data in Power BI:

Open the raj.pbix file in Power BI.

Review the graphs and visualizations to analyze the sales data.


# Steps for Prediction.
====================== 

1. Download prediction files:

Download the new_sales_data.csv file and the Python script new.ipynb.

2. Set up your Python environment:

Set up your Python environment to run the prediction script.

3. Run the analysis and prediction:

Execute the Jupyter Notebook or any compatible platform with the provided files.

4. Optional: Use Google Colab:

You can also use the provided Google Colab link to directly run the files.

"https://colab.research.google.com/drive/1ZKSeXAoHHsjC41oQis6UgyzHFAykeaA_?usp=sharing"



# Data Analysis Using SQL Workbench

1. Show all customer records

    `SELECT * FROM customers;`

1. Show total number of customers

    `SELECT count(*) FROM customers;`

1. Show transactions for Chennai market (market code for chennai is Mark001)

    `SELECT * FROM transactions where market_code='Mark001';`

1. Show distrinct product codes that were sold in chennai

    `SELECT distinct product_code FROM transactions where market_code='Mark001';`

1. Show transactions where currency is US dollars

    `SELECT * from transactions where currency="USD"`

1. Show transactions in 2020 join by date table

    `SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;`

1. Show total revenue in year 2020,

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";`
	
1. Show total revenue in year 2020, January Month,

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");`

1. Show total revenue in year 2020 in Chennai

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020
and transactions.market_code="Mark001";`


Data Analysis Using Power BI
============================

1. Formula to create norml_amount column

`= Table.AddColumn(#"Filtered Rows", "norm_amount", each if [currency] = "USD" or [currency] ="USD#(cr)" then [sales_amount]*75 else [sales_amount], type any)`





