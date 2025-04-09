# Crypto Investment Analysis Agent

This agent analyzes cryptocurrency investment opportunities, assesses risks, and builds investment models. It combines cryptocurrency market data, macroeconomic indicators, market research, and quantitative modeling to provide comprehensive investment analysis.

## Overview

The Crypto Investment Analysis Agent helps answer questions like:
- How to allocate investment between different cryptocurrencies
- What risks and potential returns to expect from crypto investments
- How different market scenarios might affect crypto investments
- How macroeconomic factors might impact cryptocurrency performance

## Features

- Retrieves historical and current cryptocurrency price data
- Analyzes macroeconomic indicators that might impact crypto markets
- Gathers news and analyst opinions about cryptocurrencies
- Creates investment models and simulates risk scenarios
- Visualizes price trends and investment performance metrics
- Calculates key risk metrics like volatility, drawdown, and risk-adjusted returns

## Prerequisites

Before running this agent, you need:

1. A Financial Datasets API key
2. A FRED API key (register at https://fred.stlouisfed.org/docs/api/api_key.html)
3. A Perplexity API key
4. Docker installed for the Perplexity Search MCP
5. Python environment with UV installed for FRED API and Financial Datasets MCPs

## Setup

1. Create a `.env` file in this directory with the following variables:
   ```
   FINANCIAL_DATASETS_API_KEY=your_financial_datasets_api_key
   FRED_API_KEY=your_fred_api_key
   PERPLEXITY_API_KEY=your_perplexity_api_key
   ```

2. Ensure that the paths to the MCP servers are correct in the `config.py` file.

## Usage

To run the agent:

```bash
cd capital_markets/crypto_investment_agent
python main.py
```

The agent is pre-configured to analyze a $100,000 investment in Bitcoin (BTC) and Ethereum (ETH) with a 2-year time horizon, but you can modify the prompt in `main.py` to analyze different cryptocurrencies or investment scenarios.

The agent will:
1. Retrieve historical cryptocurrency price data
2. Gather news and analyst opinions about the cryptocurrencies
3. Analyze macroeconomic factors that could impact the crypto market
4. Create visualizations of price trends and investment performance
5. Model the potential performance of the investment under different scenarios
6. Calculate key risk and return metrics
7. Suggest an allocation between the cryptocurrencies

## Output

All output will be saved to the `output/{session_uuid}/` directory, including:
- Visualization images created by the Code Interpreter
- Investment performance and risk metrics

## Customization

You can modify the agent's behavior by editing:
- `main.py`: To change the agent's instructions, the model used, or the default query
- `config.py`: To adjust configuration settings for the MCPs 