# Insurance Rate Filing Comparison Agent

This agent analyzes and compares insurance rate filings by leveraging Amazon Bedrock Knowledge Bases and file system operations. It produces detailed markdown reports comparing different rate filings based on user queries.

## Features

- Searches knowledge bases containing insurance rate filings
- Analyzes and compares rate filings from different insurers
- Identifies key differences in premium changes, coverage modifications, and more
- Generates comprehensive markdown reports with detailed analysis

## Prerequisites

- Python 3.9+
- AWS credentials with access to Amazon Bedrock
- Amazon Bedrock Knowledge Base(s) containing insurance rate filing documents

## Setup

1. Install dependencies:
```bash
pip install -r requirements.txt
```

2. Set up environment variables in a `.env` file:
```
AWS_REGION=us-east-1
AWS_PROFILE=your-profile
```

## Usage

Run the agent with:

```bash
python main.py
```

The agent will:
1. Start the Bedrock KB Search and Filesystem MCPs
2. Create a unique session ID
3. Connect to your Amazon Bedrock Knowledge Bases
4. Allow you to query for specific rate filing comparisons
5. Save the resulting analysis as a markdown file in the `output/{session_uuid}/` directory

## Technical Implementation

This agent uses multiple Model Context Providers (MCPs):

1. **Bedrock KB Search MCP** - Connects to Amazon Bedrock Knowledge Bases to search and retrieve relevant rate filing documents
2. **Filesystem MCP** - Provides file operations to save the generated comparison report

The agent runs with the Claude 3.5 Sonnet model and is prompted to act as an insurance analyst specializing in rate filing analysis.

## Sample Queries

- "Compare auto insurance rate filings from State Farm and Allstate for personal auto coverage in California from the last year."
- "Analyze the differences between GEICO and Progressive's homeowners insurance rate filings in Texas from the last 6 months."

## Output

The agent generates a markdown file with the following sections:
- Executive summary
- Detailed comparison of the rate filings
- Analysis of potential market impacts
- Regulatory compliance considerations
- Recommendations for stakeholders

Output files are saved to: `output/{session_uuid}/rate_filing_comparison.md` 