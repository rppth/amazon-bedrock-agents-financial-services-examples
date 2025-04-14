# Financial Datasets MCP Server with InlineAgent

This example demonstrates how to use a financial datasets API through an MCP server with InlineAgent to retrieve and analyze financial data for stocks and cryptocurrencies.

## Features

- Retrieve company financial statements (income, balance sheet, cash flow)
- Get current and historical stock prices
- Access company news
- Retrieve cryptocurrency pricing data
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

2. Get a financial datasets API key.

   - Visit https://www.financialdatasets.ai/
   - Create an account.
   - Create an API key.

3. Create a `.env` file with your financial datasets API key.

   - Create a `.env` file under the MCP server's directory. Refer to the `.env.example` for an example of what variables are needed.

4. Run the example.
   ```
   python main.py
   ```

## Available Tools

### Stock Market Data

- **get_income_statements(ticker, period="annual", limit=4)**

  - Retrieves income statements for a company
  - Parameters:
    - ticker: Stock symbol (e.g., AAPL, MSFT)
    - period: "annual", "quarterly", or "ttm" (trailing twelve months)
    - limit: Number of statements to return

- **get_balance_sheets(ticker, period="annual", limit=4)**

  - Retrieves balance sheets for a company
  - Same parameters as get_income_statements

- **get_cash_flow_statements(ticker, period="annual", limit=4)**

  - Retrieves cash flow statements for a company
  - Same parameters as get_income_statements

- **get_current_stock_price(ticker)**

  - Gets the current/latest price for a stock

- **get_historical_stock_prices(ticker, start_date, end_date, interval="day", interval_multiplier=1)**

  - Gets historical prices for a specified date range
  - Parameters:
    - start_date/end_date: Format YYYY-MM-DD
    - interval: "minute", "hour", "day", "week", "month"
    - interval_multiplier: Integer to multiply the interval

- **get_company_news(ticker)**
  - Retrieves recent news for a company

### Cryptocurrency Data

- **get_available_crypto_tickers()**

  - Lists all available cryptocurrency tickers

- **get_crypto_prices(ticker, start_date, end_date, interval="day", interval_multiplier=1)**

  - Gets historical cryptocurrency prices
  - Similar parameters to get_historical_stock_prices

- **get_current_crypto_price(ticker)**
  - Gets the current/latest price for a cryptocurrency

## Example Queries

### Stock Analysis

- "Analyze Apple's (AAPL) financial performance over the past 3 years"
- "Compare Microsoft (MSFT) and Google (GOOGL) income statements"
- "Show me the current stock price and recent news for Tesla (TSLA)"
- "Calculate key financial ratios for Amazon (AMZN) based on their latest balance sheet"

### Cryptocurrency Analysis

- "What cryptocurrencies are available for analysis?"
- "Show Bitcoin's (BTC) price trend over the past month"
- "Compare Ethereum (ETH) and Cardano (ADA) price performance year-to-date"
- "What is the current price of Dogecoin (DOGE)?"
