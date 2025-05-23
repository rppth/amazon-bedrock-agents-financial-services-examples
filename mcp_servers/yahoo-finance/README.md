# Yahoo Finance MCP Server with InlineAgent

This example demonstrates how to use Yahoo Finance through an MCP server with InlineAgent to retrieve and analyze financial data for stocks, including price data, financial statements, and more.

## Features

- Retrieve real-time and historical stock price data
- Access company financial statements and information
- Get analyst recommendations and major holders data
- Search for ticker symbols
- Compare multiple stocks
- Access options data
- Perform financial analysis with AI assistance

## Setup Instructions

1. Activate virtual environment from project's root directory.

   ```bash
   # On macOS and Linux.
   source .venv/bin/activate
   ```

   ```bash
   # On Windows.
   .venv\Scripts\activate
   ```

2. Run the example.
   ```
   python main.py
   ```

## Available Tools

### Stock Market Data

- **get_stock_info(ticker)**

  - Get comprehensive company information for a stock ticker
  - ticker: Stock symbol (e.g., AAPL, MSFT)

- **get_stock_price(ticker)**

  - Get the latest available stock price data
  - Returns current price, open, high, low, and volume

- **get_historical_data(ticker, period="1mo", interval="1d", start_date=None, end_date=None)**

  - Get historical price data for a ticker
  - period: 1d, 5d, 1mo, 3mo, 6mo, 1y, 2y, 5y, 10y, ytd, max
  - interval: 1m, 2m, 5m, 15m, 30m, 60m, 90m, 1h, 1d, 5d, 1wk, 1mo, 3mo

- **search_tickers(query)**
  - Search for ticker symbols based on a company name or keyword

### Financial Analysis

- **get_financials(ticker, quarterly=False)**

  - Get financial statements for a company
  - quarterly: If True, returns quarterly statements instead of annual

- **get_analyst_recommendations(ticker)**

  - Get analyst recommendations for a stock

- **get_options_data(ticker, date=None)**

  - Get options chain data for a stock

- **get_major_holders(ticker)**

  - Get major holders information for a stock

- **compare_stocks(tickers, metric="price", period="1mo")**
  - Compare multiple stocks based on a specified metric

## Example Queries

### Stock Analysis

- "What's the current price and trading volume for Tesla (TSLA)?"
- "Show me Apple's (AAPL) historical stock performance over the past year"
- "Compare the performance of Microsoft (MSFT) and Google (GOOGL)"
- "Get the latest analyst recommendations for Amazon (AMZN)"
- "Who are the major holders of Netflix (NFLX) stock?"

### Financial Analysis

- "Analyze Microsoft's (MSFT) quarterly financial statements"
- "Show me the options chain for Apple (AAPL)"
- "Search for companies in the electric vehicle industry"
- "Compare the market cap of major tech companies"
- "Get detailed company information for Tesla (TSLA)"
