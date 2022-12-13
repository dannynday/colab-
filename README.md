# Module 11 Challenge: Forecasting Net Prophet

![Decorative image.](colab/unit-11-readme-photo.png)

## Background

With over 200 million users, Mercado Libre is the most popular e-commerce site in Latin America. In this work I am analyzing the company's financial and user data in clever ways to help the company grow. 

In a bid to drive revenue, I produced a Jupyter notebook that contains data preparation, my analysis, and my visualizations for all the time series data that the company needs to understand. I used text and comments to document my findings. My notebook contain the following:

- Visual depictions of seasonality (as measured by Google Search traffic) that are of interest to the company.

- An evaluation of how the company stock price correlates to its Google Search traffic.

- A Prophet forecast model that can predict hourly user search traffic.

- Answers to the questions in Jupyter notebook.

- A plot of a forecast for the company’s future revenue.
- One jupyter notebook and Googgle colab notebook

The outcome will be:

- Identifying patterns in time series data.

- Mining for patterns in seasonality by using visualizations.

- Building sales-forecast and user-interest predictive models.

---

## Steps

First, I configure a Google Colaboratory, or Colab, workspace


### Step 1: Find Unusual Patterns in Hourly Google Search Traffic

1. Read the search data into a DataFrame, and then slice the data to just the month of May 2020. (During this month, Mercado Libre released its quarterly financial results.) I used hvPlot to visualize the results. 

2. Calculate the total search traffic for the month, and then compare the value to the monthly median across all months.

### Step 2: Mine the Search Traffic Data for Seasonality

To help Marketing, I mined the search traffic data for predictable seasonal patterns of interest in the company. 
steps I took to complete the following:

1. Group the hourly search data to plot the average traffic by the day of the week.

2. Using hvPlot, I visualized the traffic as a heatmap, referencing `index.hour` for the x-axis and `index.dayofweek` for the y-axis. 

3. Group the search data by the week of the year. This was done to check when the search traffic tend to increase 

### Step 3: Relate the Search Traffic to Stock Price Patterns

In this step I check the relationship between the search data and the company stock price 

steps I took to archieve this was:

1. To read and plot the stock price data. Concatenate the stock price data to the search data in a single DataFrame.

2. Note that market events emerged during 2020 that many companies found difficult. But after the initial shock to global financial markets, new customers and revenue increased for e-commerce platforms. 

3. I sliced the data to just the first half of 2020 (`2020-01` to `2020-06` in the DataFrame), and then use hvPlot to plot the data.

3. I create a new column in the DataFrame named “Lagged Search Trends” that offsets, or shifts, the search traffic by one hour. Create two additional columns:

   - “Stock Volatility”, which holds an exponentially weighted four-hour rolling average of the company’s stock volatility

   - “Hourly Stock Return”, which holds the percentage of change in the company stock price on an hourly basis

4. Review the time series correlation

### Step 4: Create a Time Series Model by Using Prophet

I this step, I produced a time series model that analyzes and forecasts patterns in the hourly search data. 

Steps I took:
1. Set up the Google search data for a Prophet forecasting model.

2. After estimating the model, plot the forecast.

3. I plotted the individual time series components of the model to answer the following questions:

   - What time of day exhibits the greatest popularity?

   - Which day of the week gets the most search traffic?

   - What's the lowest point for search traffic in the calendar year?

### Step 5 Forecast the Revenue by Using Time Series Models


Here I did the forecast of the total sales for the next quarter. This increase the ability to both plan budgets and help guide expectations for the company investors.

To create the forecast, I completed the following steps:

1. Read in the daily historical sales (that is, revenue) figures, and then apply a Prophet model to the data.

2. Interpret the model output to identify any seasonal patterns in the company revenue. For example, what are the peak revenue days? 

4. Produce a sales forecast for the finance group. Give a number for the expected total sales in the next quarter. I included the best- and worst-case scenarios to make better plans.


