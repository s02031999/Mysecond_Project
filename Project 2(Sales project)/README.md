Sales Insights Data Analysis Project

 SQL database dump is in db_dump.sql file and download `db_dump.sql` file to your local computer.


Data Analysis Using SQL
=======================

1. Show all customer records

  `SELECT * FROM customers;`

2. Show total number of customers

  `SELECT count(*) FROM customers;`

3. Show transactions for Chennai market (market code for chennai is      Mark001

  `SELECT * FROM transactions where market_code='Mark001';`

4. Show distrinct product codes that were sold in chennai

  `SELECT distinct product_code FROM transactions where   market_code='Mark001';`

5. Show transactions where currency is US dollars

  `SELECT * from transactions where currency="USD"`

6. Show transactions in 2020 join by date table

  `SELECT transactions.*, date.* FROM transactions INNER JOIN date ON   transactions.order_date=date.date where date.year=2020;`

7. Show total revenue in year 2020,

  `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";`
	
8. Show total revenue in year 2020, January Month,

  `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");`

9. Show total revenue in year 2020 in Chennai

  `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020
and transactions.market_code="Mark001";`











Data Analysis Using Power BI
============================

1.Formula to create Revenue

     Revenue = sum(‘sales transactions’[sales_amount])

2. Formula to create Sales Qty

   Sales Qty = sum(‘Sales transactions’[sales Qty])

3. Formula to create Total Profit Margin 

   Total Profit Margin = sum(‘sales transactions’[Profit_Margin])

4. Formula to create Profit Margin% 

   Profit Margin% = DIVIDE([Total Profit Margin],[Revenue],0)

5. Formula to create Profit Margin Contribution %

   Profit Margin Contribution % = DIVIDE([Total Profit  Margin],CALCULATE([Total Profit Margin],ALL(‘sales Products’),ALL(‘sales customers’),ALL(‘sales markets’)))

6. Formula to create Revenue Contribution % 
   
   Revenue Contribution% =DIVIDE([Revenue],CALCULATE([Revenue],ALL(‘sales Products’),ALL(‘sales customers’),ALL(‘sales markets’)))

7. Formula to create Revenue Last year

   Revenue LY = CALCULATE([Revenue],SAMEPERIODLASTYEAR(‘sales  Data’[date]))

   

   



