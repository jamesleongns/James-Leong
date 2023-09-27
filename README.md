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
&#x2022; discount_amount:           amount to be discounted from order price  
&#x2022; tax_amount: 			          tax amount to be added to price for each order.  
&#x2022; Sales: 				            sales price after minus discount_amount, add tax_amount & shipping_cost.  
&#x2022; Duration_OrderToShipDate: 	number of days taken from order date to ship out.  
&#x2022; ShipCost/Price: 		        percentage of shipping cost divided by price for each customer order.  
&#x2022; Price/Qty:			            average price per unit quantity in each customer order.  
&#x2022; ShipCost/Qty:			        average shipping cost per unit quantity in each customer order.  

ProductCat dataset created to assign product_name in Purchase dataset to product category:   
&#x2022; Home Living  
&#x2022; Electronics  
&#x2022; Apparel Fashion  

Customer dataset, added AgeSegment column :    
&#x2022; 1.Mid-Aged Prof_45-54yrs  
&#x2022; 2.Seniors_55-65yrs  
&#x2022; 3.Adult Prof_35-44yrs  
&#x2022; 4.Young Prof_25-34yrs  
&#x2022; 5.College Stu_18-24yrs

Customer dataset, hilight country column and replace with:  
(Below ranked in descending order of Sales)  
&#x2022; Values to find:		Replace with:  
&#x2022; Colombia 		1.Colombia  
&#x2022; Chile 			  2.Chile  
&#x2022; Mexico 			3.Mexico  
&#x2022; Brazil 			4.Brazil  

**Data Cleaning:**  
&#x2022; For Customer and Purchase datasets, verify every data column for any Empty or Error cells under "Column profiling based on entire data set".  
&#x2022; Customer dataset, convert values to "$ Fixed decimal number" currency for "income" column.  
&#x2022; Purchase dataset, convert to "$ Fixed decimal number" currency for 6 columns:  
         shipping_cost, discount_amt, tax_amt, Sales, Price/Qty, ShipCost/Qty  
&#x2022; Purchase dataset, Power Query Editor, Click "%" to convert values to percentage for 3 columns: 
         tax, discount, ShipCost/price

**General Observations:**  
Highest Sales by Age Segment and by product category in descending order:  
&#x2022; 1.Mid-Aged Prof_45-54yrs  	
&#x2022; 2.Seniors_55-65yrs  
&#x2022; 3.Adult Prof_35-44yrs  
&#x2022; 4.Young Prof_25-34yrs  
&#x2022; 5.College Stu_18-24yrs  

Country with highest Sales:  
&#x2022; 1.Colombia (28% or $14.8M)  
&#x2022; 2.Chile (25% or $13.3M)  

Prod Cat with highest Sales:  
&#x2022; Home Living ($34.7M)  
&#x2022; Electronics ($15.2M)  

Across every Country, Age Segment and gender, total Sales is in following descending order of product category:  
&#x2022; Home Living (66% or $34.7M)  
&#x2022; Electronics (29% or $15.2M)  
&#x2022; Apparel Fashion (5% or $2.6M)  

**********
Males overall Sales is slightly higher than females:  
&#x2022; Males (50.5% or $26.5M)   
&#x2022; Females (49.6% or $26M)   

Males accounts for slightly higher Sales than females:  

for each product category:  
&#x2022; Home Living (+$0.71M delta)  
&#x2022; Electronics (+$0.12M delta)  
&#x2022; Apparel Fashion (+$0.05M delta)  

for each country except Mexico   
&#x2022; Colombia (+$0.5M delta)  
&#x2022; Chile (+$0.1M delta)  
&#x2022; Brazil (+$0.5M delta)  

for age segment:  
&#x2022; 1.Mid-Aged Prof_45-54yrs (+$0.8M delta)  
&#x2022; 2.Seniors_55-65yrs (+$0.7M delta)  
