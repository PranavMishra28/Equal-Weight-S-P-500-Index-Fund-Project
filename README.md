# Equal-Weight S&P 500 Index Fund

This project provides a Python script to construct an equal-weight version of the S&P 500 index. The script helps users create a balanced portfolio by calculating the number of shares of each S&P 500 constituent they should purchase based on their total portfolio value.

## Table of Contents
- [Introduction](#introduction)
- [Libraries Required](#libraries-required) 
- [Setup](#setup)
- [Features](#features)
- [Detailed Steps](#detailed-steps)
- [Running the Script](#running-the-script)
- [Output](#output)
- [License](#license)

## Introduction
The S&P 500 index consists of 500 major publicly traded companies in the U.S., and this project aims to help users replicate an equal-weighted version of it. An equal-weight index fund means that each stock in the portfolio has an identical dollar allocation, as opposed to being weighted by market capitalization.

The script accepts a user-defined portfolio size, calculates the required number of shares for each stock to get equal weighting, and produces a formatted Excel sheet with recommended trades.

## Libraries Required
Ensure the following Python libraries are installed before running the script:
- `numpy`: For numerical operations
- `pandas`: For handling data in DataFrames  
- `requests`: For making API requests to IEX Cloud
- `xlsxwriter`: For formatting and exporting data to Excel
- `math`: For mathematical operations

You can install them using:
```pip install numpy pandas requests xlsxwriter```

## Setup

### API Token
You need an API token from IEX Cloud to access stock data. Save your token in a secrets.py file in the project directory with the following format:

```IEX_CLOUD_API_TOKEN = "your_token_here"```

### Stock Data
Download the list of S&P 500 stocks from here and save it as sp_500_stocks.csv in the same directory as the script.

## Features
- Fetch S&P 500 stock data: Retrieve stock price and market capitalization data
- Equal-weight calculation: Calculate the number of shares for each stock to achieve equal weighting
- Excel output: Generate an Excel file with a breakdown of the portfolio structure, including stock tickers, prices, and recommended shares to buy
- Batch API calls: Improve efficiency by using batch API requests

## Detailed Steps
1. Library Imports: Import the necessary libraries for data handling, HTTP requests, and Excel export
2. Data Import: Load the list of S&P 500 stocks from sp_500_stocks.csv
3. API Token Access: Import the API token from secrets.py
4. API Calls and Parsing: Request stock data (price and market cap) for each S&P 500 company from IEX Cloud and parse the response
5. Data Storage: Organize stock data into a DataFrame
6. Equal Weight Calculation: Based on the user's total portfolio value, compute the number of shares required to equally weight each stock
7. Excel Formatting: Use XlsxWriter to export data into a formatted Excel file, customizing column widths, headers, and cell styles

## Running the Script

### Instructions
1. Define Portfolio Value: Run the script and input your portfolio size when prompted
2. Execute API Calls: The script will retrieve data from IEX Cloud for each stock and calculate the number of shares to buy
3. Excel Output: The script exports an Excel file named recommended_trades.xlsx, containing recommended trades for each S&P 500 constituent

### Code Execution
To execute the script, run each cell in sequence, ensuring that API requests complete without errors. Upon completion, recommended_trades.xlsx will be saved in the project directory.

## Output
The Excel output, recommended_trades.xlsx, includes the following columns:
- Ticker: Stock ticker symbol
- Price: Latest stock price
- Market Capitalization: The total market cap of the company
- Number of Shares to Buy: The calculated shares to purchase for equal weighting

## License
This project is open-source and available under the MIT License. Please feel free to contribute or reach out for issues or enhancements.
