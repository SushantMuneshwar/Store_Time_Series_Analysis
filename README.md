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

Derived the sales wrt shipping categories using 'groupby()' function. We got to know that the highest sales revenue coming from the customers who are using standard class as their preferred shipment mode.

We’ve plotted the graph showing the same results using matplotlib library
The results for the revenue generated from the Shipment model:

-	Standard Class: 1.3 Mill
-	Second class: 449k
-	First Class: 345k
-	Same Day: 125k

Least revenue is getting generated from the same day delivery, which is conditional or situational sometimes so, business can’t do anything about it. One thing business can do is focus on improving the standard class delivery. Lots of customers are preferring standard class delivery, compromising with this mode can hamper the customer satisfaction.

And so on...

After completing the analysis of data, next step in the project is to predict the future of the trend in the data. Here we don't have any dependent feature in the datset but the dates. So, considering this we are going to find trends and seasonality in the data using Prophet library.

Time series data can be difficult and frustrating to work with, and the various algorithms that generate models can be quite finicky and hard to tune. This is particularly true if you are working with data that has multiple seasonalities. In addition, traditional time series models like SARIMAX have many stringent data requirements like stationarity and equally spaced values. Other time series models like Recurring Neural Networks with Long-Short Term Memory (RNN-LSTM) can be highly complex and difficult to work with if you don’t have a significant level of understanding about neural network architecture. So for the average data analyst, there is a high barrier of entry to time series analysis. So in 2017, a few researchers at Facebook published a paper called, “Forecasting at Scale” which introduced the open-source project Facebook Prophet, giving quick, powerful, and accessible time-series modeling to data analysts and data scientists everywhere.

It is particularly good at modeling time series that have multiple seasonalities and doesn’t face some of the above drawbacks of other algorithms. At its core is the sum of three functions of time plus an error term: growthg(t), seasonality s(t), holidays h(t) , and error e_t :

The Prophet library is an open-source library designed for making forecasts for univariate time series datasets. It is easy to use and designed to automatically find a good set of hyperparameters for the model in an effort to make skillful forecasts for data with trends and seasonal structure by default. It is a procedure for forecasting time series data based on an additive model where non-linear trends are fit with yearly, weekly, and daily seasonality, plus holiday effects. It works best with time series that have strong seasonal effects and several seasons of historical data. Prophet is robust to missing data and shifts in the trend, and typically handles outliers well.

- So, Prophet is the facebooks’ open source tool for making time series predictions.

- Prophet decomposes time series data into trend, seasonality and holiday effect.

- Trend models non periodic changes in the time series data.

- Seasonality is caused due to the periodic changes like daily, weekly, or yearly seasonality.

- Holiday effect which occur on irregular schedules over a day or a period of days.

- Error terms is what is not explained by the model.

Prophet is an additive regression model with a piecewise linear or logistic growth curve trend. It includes a yearly seasonal component modeled using Fourier series and a weekly seasonal component modeled using dummy variables.
Amazon Forecast uses the default Prophet hyperparameters. Prophet also supports related time-series as features, provided to Amazon Forecast in the related time-series CSV file.

After reading in data and cleaning using pandas, you are almost ready to use Facebook Prophet. However, Facebook Prophet requires that the dates of your time series are located in a column titled ds and the values of the series in a column titled y. Note that if you are using logistic growth you’ll also need to add additional cap and floor columns with the maximum and minimum values of the possible growth at each specific time entry in the time series.

Facebook Prophet operates similarly to scikit-learn, so first we instantiate the model, then call .fit(ts) passing the time series through it. When calling. predict(ts), Prophet outputs a lot of information. Luckily, the developers added a method called .make_future_dataframe(periods = 10) that will easily collect all of the output in an organized way. This method outputs an empty pandas dataframe that we will fill with the forecast using the .predict(ts)method. 

To install Prophet library -> !pip install prophet

we can plot the graphs using Prophet's inbuilt library named (plot_plotly)
using "Fore_plot = m.plot(forecast, xlabel='year', ylabel='Daily Sales')" we can see the daily sales throughtout the year and the prediction for the next 365 days with its upper bound and lower bound.
