# Financial Services Perplexity Search with InlineAgent

<p align="center">
  <a href="https://hub.docker.com/r/mcp/perplexity-ask"><img src="https://img.shields.io/badge/Docker-perplexity_ask-blue" /></a>
  <a href="https://github.com/jsonallen/perplexity-mcp"><img src="https://img.shields.io/badge/Github-perplexity_mcp-blue" /></a>
</p>

This example demonstrates how to use Perplexity's internet search capability with InlineAgent to create a specialized assistant for Capital Markets and Insurance queries.

## Setup Instructions

1. Ensure you have Docker installed and running on your system
2. Make sure the InlineAgent package is installed in your environment
3. Create a `.env` file using the provided `.env.example` template:
   ```
   cp .env.example .env
   ```
4. Add your Perplexity API key to the `.env` file
5. Run the example:
   ```
   python main.py
   ```

## Example Queries

### Capital Markets
- "What are the current trends in cryptocurrency market regulation?"
- "How do rising interest rates affect equity valuations?"
- "What are the key metrics for evaluating fintech companies?"
- "Explain the impact of ESG factors on investment decisions"

### Insurance
- "What are the latest developments in parametric insurance?"
- "How is AI being used in underwriting processes?"
- "What regulatory changes are affecting the health insurance industry?"
- "Explain how climate risk is changing property insurance models" 