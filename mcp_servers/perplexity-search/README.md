# Financial Services Perplexity Search with InlineAgent

This example demonstrates how to use Perplexity's internet search capability with InlineAgent to create a specialized assistant for Capital Markets and Insurance queries.

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

2. Get a financial datasets API key.

   - Visit https://www.perplexity.ai/
   - Create an account.
   - Create an API key from https://www.perplexity.ai/account/api

3. Create a `.env` file with your Perplexity API key.

   - Create a `.env` file under the MCP server's directory. Refer to the `.env.example` for an example of what variables are needed.

4. Ensure you have Docker installed and running on your system

   ```bash
   docker ps  # Should return the list of running containers
   ```

5. Pull the [required Docker image](https://hub.docker.com/r/mcp/perplexity-ask).

   ```bash
   docker pull mcp/perplexity-ask
   ```

6. Run the example.
   ```
   python main.py
   ```

## Available Tools

- **perplexity_ask**: Engages in a conversation by returning an ask completion response.

- **perplexity_reason**: Performs reasoning tasks by returning a well-reasoned response.

- **perplexity_research**: Performs deep research by returning a comprehensive research response with citations.

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
