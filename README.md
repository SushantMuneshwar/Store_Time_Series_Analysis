# Store_Time_Series_Analysis
This is the project which is based on time series analysis. 
where expection is to predict the next year's Sales and profit. 
we are using the Facebook Prophet library to carry out the project.

Firstly, the data was analysed and some questions were answered which were expected by the clients to ask, the aim of this analysis is to get th most useful insights which can be helpful in solving the business problems. So, trying to get some insights from the data using Exploratory Data Analysis. This is Time Series problem which mainly focuses on the analysing the hot selling products, sales trends considering demand of the customer and supply by the seller.

Data contains the date (Day, Month, Year) – Order date and shipping date, ship model (4 types of shipment options), segment (3 categories), city (529 cities), state (49 states), Region (4 Regions), category (3 categories), sub-categories  (17 subcategories).

What can we derive from the data

Q1. Which is the Most selling product ?

When we calculate most selling product, we can either derive it by number of products being sold or the greatest number of sales generated by the resp. products. Either go with number of product or sum of sales or both.
For displaying the list of products, we’ve used bar plot of matplotlib library.

 Q2. Which is the Least selling product ?

Again, here we can add least selling product, not really necessary but we can add a simple line of code. In this code there are several products having the least amount of sale i.e., lot of categories are having sale of 1 product each
There is no such need to display the least selling products because least number is 1 for all the 10 products.
There is no need to plot this graph as there are almost 94 products whose count is just 1. (Not demanding products or not trendy products)

Q3. Which is the Preferred shipment mode ?

Derived the sales wrt shipping categories using groupby () function. We got to know that the highest sales revenue coming from the customers who are using standard class as their preferred shipment mode.

We’ve plotted the graph showing the same results using matplotlib library
The results for the revenue generated from the Shipment model:

•	Standard Class: 1.3 Mill
•	Second class: 449k
•	First Class: 345k
•	Same Day: 125k

Least revenue is getting generated from the same day delivery, which is conditional or situational sometimes so, business can’t do anything about it. One thing business can do is focus on improving the standard class delivery. Lots of customers are preferring standard class delivery, compromising with this mode can hamper the customer satisfaction.

And so on...

After completing the analysis of data, next step in the project is to predict the future of the trend in the data. Here we don't have any dependent feature in the datset but the dates. So, considering this we are going to find trends and seasonality in the data using Prophet library.
