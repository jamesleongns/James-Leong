# SCTP-Data Analyst Capstone Project

![](https://i.imgur.com/0IXxrQ5.png)

**Objective:**  
Lazada is looking to create a customer base, by enhancing customer experience and recommending relevant products that will help further increase their revenue.

**Role:**  
As a Data Analyst to generate a report with important insights which can help the company to better understand their customers and to provide actionable recommendations to increase revenue.

**Description of Dataset:**  
There are 2 datasets source file used here namely Customer and Purchase.  Customer dataset(1000 rows) contain critical values on gender, income, country and age while Purchase(50,000 rows) dataset contain product name, price, discount, tax, order date, quantity and shipping cost. price from Purchase dataset is assumed to be defined as the total price of an order_id inclusive of its total quantity but exclude discount, tax and shipping cost.

**Data Transformation:**  
Purchase dataset, added columns to calculate:
-discount_amount: 		      amount to be discounted from order price
-tax_amount: 			          tax amount to be added to price for each order.
-Sales: 				            sales price after minus discount_amount, add tax_amount & shipping_cost.
-Duration_OrderToShipDate: 	number of days taken from order date to ship out .
-ShipCost/Price: 		        percentage of shipping cost divided by price for each customer order.
-Price/Qty:			            average price per unit quantity in each customer order.
-ShipCost/Qty:			        average shipping cost per unit quantity in each customer order.
