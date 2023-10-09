# Data Analyst Capstone Project

![](https://i.imgur.com/0IXxrQ5.png)

### Objective:    
Lazada is looking to create a customer base, by enhancing customer experience and recommending relevant products that will help further increase their revenue.  
  
  
### Role:    
As a Data Analyst to generate a report with critical insights which can help the company to better understand their customers and to provide actionable recommendations to increase revenue.

### Description of Dataset:   
There are 2 datasets source file used here namely Customer and Purchase.  Customer dataset(1000 rows) contain critical values on gender, income, country and age while Purchase(50,000 rows) dataset contain product name, price, discount, tax, order date, quantity and shipping cost. price from Purchase dataset is assumed to be defined as the total price of an order_id inclusive of its total quantity but exclude discount, tax and shipping cost.

### Data Transformation:      
Purchase dataset, added columns to calculate:  
* discount_amount: amount to be discounted from order price  
* tax_amount: tax amount to be added to price for each order.  
* Sales: sales price after minus discount_amount, add tax_amount & shipping_cost.  
* Duration_OrderToShipDate: number of days taken from order date to ship out.   
* ShipCost/Price: percentage of shipping cost divided by price for each customer order.  
* Price/Qty: average price per unit quantity in each customer order.  
* ShipCost/Qty: average shipping cost per unit quantity in each customer order.  

ProductCat dataset separately created to categorize product_name within a broader product category of:   
* Home Living  
* Electronics  
* Apparel Fashion  

Customer dataset, added AgeSegment column to categorize age to:  
(numerically ranked in descending order of Sales contribution)
* 1.Mid-Aged Prof_45-54yrs  
* 2.Seniors_55-65yrs  
* 3.Adult Prof_35-44yrs  
* 4.Young Prof_25-34yrs  
* 5.College Stu_18-24yrs


Customer dataset, hilight country column and perform value replacements:  
(numerically ranked in descending order of Sales contribution)	  
* 1.Colombia replace Colombia  
* 2.Chile replace Chile  
* 3.Mexico replace Mexico  
* 4.Brazil replace Brazil  

Purchase dataset, added MF_SalesDelta column:  
* MF_SalesDelta column reference the other Customer dataset via DAX formula to calculate the nett value of total Sales by Males(+ve values) over Females(-ve values).  Nett MF_SalesDelta positive value denotes the amount that males exceeded female sales while a nett negative values denotes the amount female sales that exceeded male sales.  

### Data Cleaning:     
* Customer and Purchase datasets: verify every data column for any Empty or Error cells under "Column profiling based on entire data set".  
* Customer dataset: convert to "$ Fixed decimal" currency for "income" column.  
* Purchase dataset: convert to "$ Fixed decimal" currency for 6 columns: shipping_cost, discount_amt, tax_amt, Sales, Price/Qty, ShipCost/Qty    
* Purchase dataset, Power Query Editor, Click "%" to convert values to percentage for 3 columns: 
         tax, discount, ShipCost/price

### General Observations:  
Highest Sales by Age Segment and product category in descending order:  
* 1.Mid-Aged Prof_45-54yrs  	
* 2.Seniors_55-65yrs  
* 3.Adult Prof_35-44yrs  
* 4.Young Prof_25-34yrs  
* 5.College Stu_18-24yrs  
  
Country by highest Sales in descending order:  
* 1.Colombia (28% or $14.8M)  
* 2.Chile (25% or $13.3M)  
* 3.Mexico (23.3% or $12.3M)  
* 4.Brazil (23.1% or $12.1M)  

Across every Country, Age Segment and gender, highest Sales in descending order of product category:  
* Home Living (66% or $34.7M)  
* Electronics (29% or $15.2M)  
* Apparel Fashion (5% or $2.6M)  

Males overall Sales is slightly higher than females:  
* Males (50.5% or $26.5M)   
* Females (49.6% or $26M)   

for every product category:  
* Home Living (+$0.30M delta)  
* Electronics (+$0.12M delta)  
* Apparel Fashion (+$0.05M delta)  

for every country except Mexico
* Brazil (+$0.53M delta) 
* Colombia (+$0.48M delta)  
* Chile (+$0.07M delta)  

for age segment:  
* 1.Mid-Aged Prof_45-54yrs (+$0.87M delta)
* 2.Seniors_55-65yrs (+$0.64M delta)

### Insights and Recommendations
* Generally, the older the Age Segment, the higher their disposable income. Hence Seniors_55-65yrs with the highest income but recorded lower sales need to be better marketed.  
* Majority of spenders for Home Living are males and comes from 1.Mid-Aged Prof_45-54yrs and 2.Seniors_55-65yrs.  Hence females who are 3.Adult Prof_35-44yrs needs to be better marketed.  
* Home Living Sales is double of Electronics which in turn is almost 6 times the sales of Apparel Fashion.  Apparel Fashion has market potential if better marketed especially to females from 4.Young Prof_25-34yrs age segment.
* Electronics(e.g. Tablets, Wireless speakers, Camera, Headphones) could be better marketed to younger female age segment 3.Adult Prof_35-44yrs, 4.Young Prof_25-34yrs and 5.College Stu_18-24yrs.
* Home Living sales in Mexico are predominantly made by females from younger age segment 3.Adult Prof_35-44yrs and 5.College Stu_18-24yrs whereas other countries sales are predominantly males from older age segment 1.Mid-Aged Prof_45-54yrs and 2.Seniors_55-65yrs.  Hence marketing may wish to learn from Mexico marketing team how to better target younger female age segment for more sales in other countries.  

Sales to be guided by the following Key Sales influencers in descending order of impact:  
* Average Ship Cost/price =< 0.62%  
* More product category offered that is Home Living  
* Average discount <12%  
* Average Price/Qty >$594.58  
  
### Connect with Me!
Like my work? Send me a DM on [Linkedin!](https://www.linkedin.com/in/jamesleongns/)
