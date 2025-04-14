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

1. Activate virtual environment from project's root directory.

   ```bash
   # On macOS and Linux.
   source .venv/bin/activate
   ```

   ```bash
   # On Windows.
   .venv\Scripts\activate
   ```

2. Get a free FRED API key:

   - Visit https://fred.stlouisfed.org/docs/api/api_key.html
   - Create an account.
   - Request an API key.

3. Create a `.env` file with your FRED API key.

   - Create a `.env` file under the MCP server's directory. Refer to the `.env.example` for an example of what variables are needed.

4. Run the example.
   ```
   python main.py
   ```

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
