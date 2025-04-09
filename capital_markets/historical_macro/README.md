# Historical Macro Comparison Agent

This agent analyzes current macroeconomic conditions and identifies historical time periods with similar characteristics. It uses FRED API data and Perplexity Search to gather information and perform comparative analysis.

## Overview

The Historical Macro Comparison Agent helps answer questions like:
- What historical time periods are most similar to current macroeconomic conditions?
- What can we learn from these historical parallels?
- What might these historical similarities suggest about future economic developments?

## Features

- Retrieves and analyzes macroeconomic data from FRED API
- Gathers context and additional information using Perplexity Search
- Provides narrative analysis of similarities between current and historical economic conditions

## Prerequisites

Before running this agent, you need:

1. A FRED API key (register at https://fred.stlouisfed.org/docs/api/api_key.html)
2. A Perplexity API key
3. Python environment with UV installed for the FRED API MCP
4. Docker installed for the Perplexity Search MCP

## Setup

1. Create a `.env` file in this directory with the following variables:
   ```
   FRED_API_KEY=your_fred_api_key
   PERPLEXITY_API_KEY=your_perplexity_api_key
   ```

2. Ensure that the path to the MCP servers is correct in the `config.py` file.

## Usage

To run the agent:

```bash
cd capital_markets/historical_macro
python main.py
```

The agent will:
1. Retrieve macroeconomic data using the FRED API
2. Gather contextual information using Perplexity Search
3. Analyze the data to identify historical parallels
4. Provide insights on similarities between current economic conditions and historical periods

## Customization

You can modify the agent's behavior by editing:
- `main.py`: To change the agent's instructions or the model used
- `config.py`: To adjust configuration settings for the MCPs 