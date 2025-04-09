# Stock Data Processing Multi-MCP Example

This example demonstrates how to combine multiple Model Composition Platform (MCP) services to create a comprehensive workflow for financial data processing:

1. **Financial Datasets MCP**: Retrieves historical stock data for Amazon (AMZN) using a local server
2. **Filesystem MCP**: Saves the retrieved data to a CSV file using a Docker container
3. **Code Interpreter**: Analyzes the data and creates visualizations with moving averages (built-in tool)

## Features

- Retrieves 30 days of AMZN stock price data
- Saves data in a structured CSV format
- Generates visualizations with stock price trends and moving averages
- Uses a consistent UUID-based output path across all tools
- Demonstrates the power of combining multiple specialized tools

## Setup Instructions

1. Ensure you have Docker installed and running on your system (required for Filesystem MCP)
2. Make sure the InlineAgent package is installed in your environment
3. Install uv (required for Financial Datasets MCP): `pip install uv`
4. Set up your Financial Datasets API key in the `.env` file:
   ```
   FINANCIAL_DATASETS_API_KEY=your_api_key_here
   ```
5. Run the example:
   ```
   python main.py
   ```

## How It Works

1. **Session Initialization**:
   - A unique UUID is generated for the session to ensure consistent file naming
   - Date ranges are calculated for the last 30 days

2. **MCP Configuration**:
   - **Filesystem MCP**: Uses Docker container with mounted directories
   - **Financial Datasets MCP**: Runs a local server with uv
   - **Code Interpreter**: Used as a built-in tool (no additional configuration needed)

3. **Agent Instruction**:
   - The agent is given a comprehensive set of instructions to:
     - Retrieve historical stock data for AMZN
     - Save the data to a CSV file in the proper output location
     - Create visualizations with stock price and moving average

4. **Execution**:
   - The agent coordinates the workflow across all tools
   - Each tool handles its specialized part of the task
   - The code interpreter generates visual output files

## Finding Your Output

All generated files (CSV data and visualizations) are saved to:
```
/projects/output/{SESSION_UUID}/
```

This translates to this path in your local filesystem:
```
/path/to/repository/output/{SESSION_UUID}/
```

## Customization

To modify this example:
- Change the stock ticker symbol in the agent's prompt
- Adjust the date range in the date calculation
- Modify the visualization requirements or add more analysis
- Add additional MCP tools for more advanced capabilities

## Benefits of Multi-Tool Approach

1. **Separation of Concerns**:
   - Each tool handles what it does best
   - Clean architecture with specialized components

2. **Flexibility**:
   - Easy to swap out or add additional tools
   - Simple to extend functionality

3. **Efficiency**:
   - Reduced code duplication
   - Leverages purpose-built tools 