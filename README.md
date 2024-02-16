# GroupSix_Project1

# Overview

This project is aimed at helping us find features to forecast the price of a given stock by looking through historical data and creating models to project future value. Along the way, we answered some interesting questions to help would-be investors. With publicly available data from Yahoo Finance, we saw how Tesla tracked with competitors like GM, FAANG stocks, and the S&P500.

## Installation Instructions

The following Python modules are required to run our code:

- Pandas
- Datetime
- Prophet
- Seaborn
- Numpy
- YFinance
- skLearn
- MatPlotLib

*Note: GitHub README includes either examples of the application, or the results and a summary of the analysis.*

### Data Practices

A brief rundown of our Collection, Cleaning, and Exploring is as follows:

#### Data Collection

- In the first step of the program, our code fetches historical price data for Tesla (ticker symbol TSLA) using the yFinance library in Python. This library allows us to fetch Tesla’s historical price data directly from Yahoo Finance, along with another user-specified stock symbol (the user can input any two stocks to run the program).
- After feeding in the ticker symbol(s), we get back information on date, open, high, low, close, volume, and adjusted close that are then stored into dataframes.
- By using these data points, we lay the foundation for our analysis of Tesla's stock performance over time, starting from the year of its IPO in 2010 (using the exact date of June 29th). The date for the comparison stock pulls from 2010 by default, unless the user specifies a different year.

#### Data Cleaning

- One of the main benefits to using yFinance for stock data is that it had exactly the data we needed and no missing values, incorrect data types, or inconsistencies. We did, however, remove some unnecessary columns, as the “Adjusted Close” and “Date” were most relevant to us.
- In plotting the initial data, we explored the data visually and subsequently cleaned the data in the following cells by removing all noise/columns except for “Adjusted Close” and “Date”.
- Weekends are filtered out from the stock data to ensure consistent analysis as the market is only open on weekdays, and holidays were taken into account using Prophet.
- To fit Prophet’s formatting conventions, we renamed the columns “Adjusted Close” and “Date” to “y” and “ds” respectively.

#### Data Exploration

- Initial plots were a starting point to visualize the historical price trends for TSLA and GM to get an overall sense of the stock’s movement over time.
- We used average closing values analyzed by day of the week and month to identify potential trends or patterns.
- For moving averages, we chose the 50-day and 200-day to gauge general price trends and identify potential buy/sell signals, based on price being above or below the averages, along with the average itself moving up, down, or sideways.
- Utilizing moving averages in different ways, we added additional technical indicators like the MACD (Moving Average Convergence Divergence) and Bollinger Bands.
- Volatility is an important part of the market, as was graphed to visualize the degree of variation in stock prices.
- We then incorporated the Prophet library for forecasting future stock prices, utilizing external regressors such as market index data.
- We also explored what the correlation was between TSLA and FANG stocks, along with the general market.
- We looked at price moves for different time frames based on days, seasons, etc.
- Lastly, we even incorporated Machine learning techniques like Linear Regression, used for predictive modeling and forecasting.

## Questions

### 1. Is there seasonality to Tesla stock movements?

One of the reasons why we chose Tesla is because the stock is so volatile. This chart here really sets the table and illustrates the point. Just like Elon Musk, Tesla’s market cap is truly a roller coaster ride and it can be hard to figure out whether it’s headed to the Moon or crashing back down to Earth like a SpaceX rocket launch. You can see up until 2020, things were pretty calm and then something happened that caused the stock price to look something like Bart Simpson’s haircut.

So as an investor, do you simply have to hold on to your hat or are there subtle patterns or variations that can be taken advantage of?

So our first port of call was to look at the average value of Tesla stock by month. Now I am not an investment professional, but there appears to be a clear pattern of stock price decline for Tesla throughout the spring, with a strong rebound throughout the summer. Based on this historical data, it appears that late Spring / early Summer is the most opportune time to buy Tesla stock.

But is there more to the story? Our analysis pivoted from looking at seasonal stock trends from 30,000 feet and zooming in to get a bit more granular… starting with Days of Week. And I will hand things off to Ken to tell you more about what we uncovered.

### 2. What day of the week is best to Buy Tesla Stock?

Friday has historically been the best day to buy the stock due to the price increases that occur over the week.

### 3. If you could have a time machine and invest on one specific day, what day would it be?

Answer: May 9, 2013

24.4% one-day price gain.

#### What happened on May 9, 2013?

1. Tesla reported a profit during earnings for the first time.
2. CO2 levels hit an all-time high in recorded history.
   [NASA CO2 Levels](https://climate.nasa.gov/climate_resources/7/graphic-carbon-dioxide-hits-new-high)
3. Consumer Reports Ranks Model S as “Best Car Ever Tested”.
   [CNN Money](https://money.cnn.com/2013/05/09/autos/tesla-model-s-consumer-reports/index.html)

### 4. Are there any correlations between Tesla and the FAANG stocks?

5-year correlation:

10-year correlation:

## Presentation Requirements

Your presentation should cover the following:

- **The approach that your group took in achieving the project goals:**
  - In our group project, we delved into stock market dynamics, with a focus on Tesla, aiming to uncover patterns and create predictive models. Our process involved rigorous data preparation using Python libraries like Pandas, NumPy, and visualization tools. Through exploratory analysis, we identified trends and volatilities and employed financial indicators such as moving averages, MACD, and Bollinger Bands to understand stock movements better. Our predictive modeling, centered around the Prophet library, allowed us to forecast future stock prices, considering market seasonality. Despite challenges in model precision, our collaborative approach and modular approach enabled us to refine our predictions, providing valuable insights into stock market trends.

- **Any additional questions that surfaced, what your group might research next if more time was available, or share a plan for future development:**
  - Explore additional ML models to compare vs Prophet’s findings.
  - Validation of Prophet forecasting by backtesting vs actual stock performance to assess accuracy.
  - Additional stock price correlation trends outside of just dates (e.g., weather, election years, opening prices vs closing, etc.).
  - Comparing S&P volatility to the general news sentiment leading up to the large swings.
