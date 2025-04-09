# FRED API (Federal Reserve Economic Data) with InlineAgent

This example demonstrates how to use the FRED API through an MCP server with InlineAgent to retrieve and analyze economic data from the Federal Reserve Bank of St. Louis.

## Features

- Access economic data series from the Federal Reserve
- Search for data series by keywords
- Browse categories of economic indicators
- Retrieve observation data for specific indicators
- Analyze economic trends and indicators
- Access information about data releases

## Setup Instructions

1. Ensure you have the necessary dependencies installed:
   ```
   pip install httpx mcp
   ```

2. Make sure the `uv` command is installed and available in your PATH.
   This is required to run the FRED API server.

3. Get a free FRED API key:
   - Visit https://fred.stlouisfed.org/docs/api/api_key.html
   - Create an account and request an API key
   - Your key will be emailed to you

4. Set your FRED API key as an environment variable:
   ```
   export FRED_API_KEY=your_api_key_here
   ```
   Alternatively, create a `.env` file in this directory with:
   ```
   FRED_API_KEY=your_api_key_here
   ```

5. Run the example:
   ```
   python main.py
   ```

## Project Architecture

- **config.py** - Contains all MCP server configuration and environment variable handling
- **main.py** - InlineAgent setup and execution
- **server.py** - The MCP server that interfaces with the FRED API

## Server Configuration

The FRED API MCP server uses the `uv` command to run server.py:

```
uv --directory /path/to/fredapi run server.py
```

This is configured in the `_setup_server_config` method in config.py.

## Available Tools

### FRED Data Access
- **get_series_observations(series_id, start_date=None, end_date=None)**
  - Retrieves observations (data points) for a FRED economic data series
  - Parameters:
    - series_id: The FRED series identifier (e.g., GDP, UNRATE, CPIAUCSL)
    - start_date/end_date: Optional date filters in YYYY-MM-DD format

- **search_series(query, search_type="full_text", limit=10)**
  - Searches for economic data series by keywords
  - Parameters:
    - query: Keywords to search for
    - search_type: "full_text" (default), "series_id", or "title"
    - limit: Maximum number of results to return

### FRED Categories
- **get_category_children(category_id)**
  - Gets the child categories for a specified FRED category
  - Parameters:
    - category_id: The FRED category ID (0 is the root category)

- **get_category_series(category_id)**
  - Lists all series under a specific FRED category
  - Parameters:
    - category_id: The FRED category ID

### FRED Releases
- **get_release_dates(release_id)**
  - Gets all release dates for a given FRED release ID
  - Parameters:
    - release_id: The FRED release ID

- **get_releases()**
  - Lists all economic data releases available in FRED

## Example Queries

### Economic Indicators
- "Look up the latest unemployment rate (UNRATE) and analyze the trend"
- "What is the current inflation rate? Use the CPIAUCSL series"
- "Compare GDP growth (GDP) and the S&P 500 (SP500) over the last 5 years"
- "Show me the Federal Funds Rate (FEDFUNDS) changes since 2020"

### Data Discovery
- "Search for economic series related to housing market"
- "What categories of economic data are available in FRED?"
- "List all series in the 'Money, Banking, & Finance' category"
- "When was the latest GDP data released?"

## Common Economic Series IDs

- **UNRATE** - Unemployment Rate
- **CPIAUCSL** - Consumer Price Index for All Urban Consumers: All Items
- **GDP** - Gross Domestic Product
- **FEDFUNDS** - Federal Funds Effective Rate
- **MORTGAGE30US** - 30-Year Fixed Rate Mortgage Average
- **SP500** - S&P 500
- **DJIA** - Dow Jones Industrial Average
- **M2** - M2 Money Stock
- **NPPTTL** - Total Nonfarm Payrolls
- **HOUST** - Housing Starts

## Customization

To modify the server configuration, edit the `_setup_server_config` method in `config.py`. You can change:
- The command to run the server (currently defaults to "uv")
- The directory where the server.py file is located
- Additional environment variables needed by the server 