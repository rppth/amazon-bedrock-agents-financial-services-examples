# 🤖 Amazon Bedrock Agents FSI Examples with MCP

<div align="center">
Examples of Amazon Bedrock Agents for the Financial Services Industry (FSI)
  
  [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
  [![Python 3.9+](https://img.shields.io/badge/python-3.9+-blue.svg)](https://www.python.org/downloads/)
  [![AWS](https://img.shields.io/badge/AWS-%23FF9900.svg?style=flat&logo=amazon-aws&logoColor=white)](https://aws.amazon.com/)
</div>

## 📋 Table of Contents
- [Installation](#-installation)
- [Getting Started](#-getting-started)
- [Repository Structure](#-repository-structure)
  - [MCP Servers](#-mcp-servers)
  - [Managed Tools](#-managed-tools)
  - [Insurance Examples](#-insurance)
  - [Capital Markets Examples](#-capital-markets)


## 🔧 Installation

To install the required dependencies, navigate to the InlineAgent directory and install the package:

```bash
cd src/InlineAgent
pip install -e .
```
⚠️ This step is required before moving forward.

## 🚀 Getting Started

Before exploring the industry-specific examples, you should first explore the main.py files in the mcp_servers directories. This will help you understand what each Model Context Protocol (MCP) server does and how it can be used:

```bash
# Explore each MCP server to understand its functionality
cd mcp_servers/python-repl
# Review the main.py and README.md to learn how this MCP works

# Repeat for other MCP servers
```

> 💡 Understanding these individual MCPs will make it easier to comprehend the more complex industry-specific examples, which typically use multiple MCPs together.

## 🏗️ Repository Structure

### 🔌 MCP Servers

The `mcp_servers` directory contains various Model Context Protocol (MCP) servers:

- 🐍 [`python-repl`](./mcp_servers/python-repl): Python REPL environment for executing code in a persistent environment
- 📊 [`financial-datasets`](./mcp_servers/financial-datasets): Access to financial market data for stocks, cryptocurrencies, and other instruments
- 🔍 [`bedrock-kb-search`](./mcp_servers/bedrock-kb-search): Amazon Bedrock Knowledge Bases search functionality
- 📈 [`fredapi`](./mcp_servers/fredapi): Federal Reserve Economic Data API integration for economic indicators
- 🔎 [`perplexity-search`](./mcp_servers/perplexity-search): Perplexity Search service for web information retrieval
- 📁 [`filesystem`](./mcp_servers/filesystem): File system operations for reading and writing files

### 🛠️ Managed Tools

The `managed_tools` directory includes:

- 👨‍💻 [`code_interpreter`](./managed_tools/code_interpreter): The Managed Code Interpreter for Amazon Bedrock Agents for executing Python code and data visualization

### 🏥 Insurance

The `insurance` directory contains insurance industry specific examples:

#### 📋 [`actuarial_modelling_assistant`](./insurance/actuarial_modelling_assistant)

**What it does**: Analyzes insurance datasets to identify trends, model risks, and generate actuarial insights.

**MCPs used**:
- 🐍 **Python REPL**: For data analysis, statistical modeling, and visualization
- 📁 **Filesystem**: Mentioned in the README for file operations, though not explicitly configured in config.py

**Key features**:
- Exploratory data analysis on policy, claims, and risk data
- Statistical modeling for claim frequency and severity
- Loss ratio and reserve adequacy calculations
- Actuarial visualizations and reports

#### 📝 [`rate_filing_comparison`](./insurance/rate_filing_comparison)

**What it does**: Compares insurance rate filings from different insurers to identify differences and market trends.

**MCPs used**:
- 🔍 **Bedrock KB Search**: For retrieving rate filing documents from knowledge bases
- 📁 **Filesystem**: For saving comparison reports to output directories

**Key features**:
- Knowledge base search of insurance rate filings
- Detailed comparison of premium changes
- Coverage modification analysis
- Markdown report generation

### 💹 Capital Markets

The `capital_markets` directory includes capital markets related examples:

#### 💰 [`crypto_investment_agent`](./capital_markets/crypto_investment_agent)

**What it does**: Analyzes cryptocurrency investment opportunities and provides investment recommendations.

**MCPs used**:
- 📊 **Financial Datasets**: For cryptocurrency price data
- 📈 **FRED API**: For macroeconomic indicators
- 🔎 **Perplexity Search**: For market news and sentiment

**Managed tools used**:
- 👨‍💻 **Code Interpreter**: For investment modeling, risk analysis, and data visualization

**Key features**:
- Historical cryptocurrency price analysis
- Macroeconomic impact assessment
- Risk modeling and scenario simulation
- Investment allocation recommendations

#### 📉 [`stock_data_processing`](./capital_markets/stock_data_processing)

**What it does**: Processes stock market data to identify technical patterns and develop trading strategies.

**MCPs used**:
- 📊 **Financial Datasets**: For stock market data
- 📁 **Filesystem**: For storing results and trading signals

**Managed tools used**:
- 👨‍💻 **Code Interpreter**: For technical analysis and strategy backtesting

**Key features**:
- Technical indicator calculation
- Trading pattern identification
- Strategy backtesting and optimization
- Performance visualization

#### 📊 [`historical_macro`](./capital_markets/historical_macro)

**What it does**: Identifies historical periods with macroeconomic conditions similar to the present.

**MCPs used**:
- 📈 **FRED API**: For economic data retrieval
- 🔎 **Perplexity Search**: For historical context and market research

**Key features**:
- Economic indicator comparison
- Historical parallel identification
- Similarity scoring and ranking
- Forward-looking insights based on historical patterns

