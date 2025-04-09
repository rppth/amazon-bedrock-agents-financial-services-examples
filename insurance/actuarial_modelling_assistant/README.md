# Actuarial Modeling Assistant

This agent uses advanced Python-based data analysis and statistical modeling to perform actuarial analysis on insurance datasets. It leverages the Python REPL MCP server to execute code directly and generate insights.

## Features

- **Data Analysis**: Exploratory data analysis on insurance policies, claims, risk factors, payments, and reserve adjustments
- **Statistical Modeling**: Predictive models for claim frequency, severity, and risk assessment
- **Actuarial Metrics**: Calculation of key metrics like loss ratios and reserve adequacy
- **Visualization**: Generation of charts and graphs to communicate findings
- **Reporting**: Creation of comprehensive actuarial reports and recommendations
- **File Management**: Ability to navigate, read, and write files with the filesystem MCP

## Sample Datasets

The agent works with the following datasets located in the `sample-actuarial-data` directory:

1. **insurance_policies.csv**: Policy information including type, region, client age, risk score, etc.
2. **insurance_claims.csv**: Claims data with amounts, types, status, and settlement details
3. **insurance_risk_factors.csv**: Risk factors specific to each policy type
4. **insurance_payments.csv**: Payment history and status information
5. **insurance_reserve_adjustments.csv**: Adjustments made to claim reserves with reasons

## How It Works

The agent:
1. Connects to the Python REPL and filesystem MCP servers
2. Loads and processes the insurance datasets
3. Performs analysis and modeling as directed by the user
4. Generates visualizations and reports
5. Saves all outputs to the specified output directory

## Usage

Run the agent with:

```bash
python main.py
```

This will:
1. Generate a unique session ID
2. Create an output directory
3. Start the agent with the Python REPL and filesystem capabilities
4. Execute the actuarial analysis
5. Save results to the output directory

## Technical Implementation

This agent uses:
- **Python REPL MCP**: For executing Python code in a persistent environment
- **Filesystem MCP**: For file operations, including listing directories, reading/writing files
- **InlineAgent Framework**: For agent orchestration and tool integration
- **Statistical Libraries**: For modeling (installed dynamically during execution)

## Output

All generated files (visualizations, reports, model outputs) are saved to:
`output/{session_uuid}/`

The comprehensive actuarial report includes:
- Data exploration findings
- Claim frequency and severity analysis
- Loss ratio calculations
- Reserve adequacy assessment
- Payment pattern analysis
- Predictive modeling results
- Recommendations based on the analysis 