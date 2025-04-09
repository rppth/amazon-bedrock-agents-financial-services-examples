# Local Stock Data Processing Agent

This agent combines Yahoo Finance data retrieval with advanced stock analysis and price prediction capabilities. It uses multiple Model Context Protocol (MCP) servers to fetch financial data and perform sophisticated analysis using Python.

## Features

### Data Collection
- Historical price data with customizable periods and intervals
- Quarterly and annual financial statements
- Options chain data for nearest expiration
- Institutional and mutual fund holdings
- All data saved in organized CSV format

### Technical Analysis
- Price metrics (returns, moving averages)
- Volatility indicators (standard deviation, ATR)
- Volume analysis
- Technical indicators (RSI, MACD, Bollinger Bands)
- Momentum and trend indicators

### Price Prediction Modeling
- Feature engineering for predictive modeling
- Train/test split with last 30 days as test set
- Multiple model types:
  * Linear models (Ridge, Lasso)
  * Tree-based models (Random Forest)
  * Time series models (ARIMA, SARIMA)
- Model validation and performance metrics
- Future price predictions with confidence intervals

### Visualization
- Interactive price and volume charts
- Technical indicator plots
- Model performance visualization
- Prediction vs actual comparisons
- Feature importance plots

### Reporting
- Comprehensive markdown reports
- Model performance analysis
- Trading insights and recommendations
- Risk assessment and limitations

## Directory Structure
```
output/
├── [session_uuid]/
    ├── data/          # Raw financial data
    ├── processed/     # Processed data and trained models
    ├── plots/         # Generated visualizations
    └── reports/       # Analysis reports and predictions
```

## Dependencies
- Yahoo Finance API for data retrieval
- pandas for data manipulation
- numpy for numerical computations
- matplotlib for visualization
- scikit-learn for machine learning
- statsmodels for time series analysis

## Usage
1. Run the agent with a stock ticker (e.g., NVDA)
2. Agent will:
   - Fetch 5 years of historical data
   - Calculate technical indicators
   - Build and evaluate prediction models
   - Generate visualizations
   - Create comprehensive analysis report
3. All outputs are saved in session-specific directories

## Example Command
```python
python main.py
```

## Output
- Historical price data in CSV format
- Processed features and indicators
- Trained prediction models
- Technical analysis plots
- Performance visualizations
- Comprehensive analysis report with:
  * Data analysis
  * Model performance metrics
  * Future price predictions
  * Confidence intervals
  * Risk assessment

## Notes
- Uses UUID for session management
- Automatically creates required directories
- Handles errors gracefully
- Saves all intermediate results
- Provides detailed logging

## Prerequisites

- Python 3.8+
- `uv` command-line tool installed and in PATH
- Required Python packages:
  ```
  yfinance
  pandas
  numpy
  matplotlib
  mcp
  httpx
  python-dotenv
  scikit-learn
  statsmodels
  ```

## Project Structure

```
local_stock_data_processing/
├── config.py          # MCP server configurations
├── main.py           # Main agent implementation
├── README.md         # This file
└── output/           # Generated data and visualizations
    └── {session_uuid}/ # Session-specific output directory
```

## How It Works

1. **Data Collection**
   - Uses Yahoo Finance MCP server to fetch historical stock data
   - Supports various time periods and intervals
   - Automatically saves data to CSV files

2. **Data Analysis and Modeling**
   - Uses Python REPL MCP server for analysis and modeling
   - Calculates technical indicators and features
   - Builds and validates prediction models
   - Generates future price predictions

3. **Visualization and Reporting**
   - Creates comprehensive visualizations
   - Generates performance metrics
   - Produces detailed analysis reports
   - Saves all outputs to session-specific directories

## Configuration

The agent uses two Model Context Protocol (MCP) servers:

1. **Yahoo Finance MCP Server**
   - Handles all financial data retrieval
   - Saves data in organized CSV format
   - Supports multiple data types (price, financials, options)

2. **Python REPL MCP Server**
   - Executes analysis and modeling code
   - Handles data processing and feature engineering
   - Trains and validates prediction models
   - Generates visualizations and reports

## Error Handling

- Graceful shutdown on keyboard interrupt
- Session-based data isolation
- Error logging and reporting
- Automatic cleanup of MCP clients

## Notes

- Each run creates a unique session directory
- All data and models are preserved between sessions
- Uses scikit-learn and statsmodels for predictions
- Comprehensive logging of analysis steps

## Contributing

To extend or modify this agent:
1. Update the MCP configurations in `config.py`
2. Modify analysis and modeling parameters in `main.py`
3. Add new model types or features
4. Ensure proper error handling and cleanup 