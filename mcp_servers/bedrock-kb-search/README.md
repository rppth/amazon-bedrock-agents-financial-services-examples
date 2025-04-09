# Amazon Bedrock Knowledge Base Search with InlineAgent

This example demonstrates how to use Amazon Bedrock Knowledge Bases through an MCP server with InlineAgent to retrieve information from your company's data sources.

## Features

- Discover available knowledge bases and their data sources
- Query knowledge bases using natural language
- Rerank results for improved relevance
- Filter queries by specific data sources
- Retrieve information from documents, websites, and databases

## Setup Instructions

1. Ensure you have the necessary dependencies installed:
   ```
   pip install boto3 mcp
   ```

2. Make sure the `uv` command is installed and available in your PATH.
   This is required to run the server.

3. Configure your AWS credentials:
   - Set up your AWS credentials in `~/.aws/credentials` or environment variables
   - Make sure the profile has permissions to access Amazon Bedrock Knowledge Bases
   - Create a `.env` file with your AWS region and profile:
     ```
     AWS_REGION=us-east-1
     AWS_PROFILE=default
     ```

4. Run the example:
   ```
   python main.py
   ```

## Project Architecture

- **config.py** - Contains all MCP server configuration and environment variable handling
- **main.py** - InlineAgent setup and execution
- **server.py** - The MCP server that interfaces with Amazon Bedrock Knowledge Bases
- **knowledgebases/** - Directory containing the client, discovery, and runtime modules

## Server Configuration

The Bedrock Knowledge Base MCP server uses the `uv` command to run server.py:

```
uv --directory /path/to/bedrock-kb-search run server.py
```

This is configured in the `_setup_server_config` method in config.py.

## Available Tools

### Knowledge Base Discovery
- **resource://knowledgebases**
  - Returns a list of available knowledge bases and their data sources
  - MUST be called before querying any knowledge base
  - Provides knowledge base IDs and data source IDs needed for queries

### Knowledge Base Querying
- **QueryKnowledgeBases(query, knowledge_base_id, reranking=True, reranking_model_name="AMAZON", data_source_ids=None)**
  - Parameters:
    - query: A natural language query to search the knowledge base
    - knowledge_base_id: The ID of the knowledge base to query
    - reranking: Whether to rerank results for better relevance
    - reranking_model_name: The reranking model to use ("AMAZON" or "COHERE")
    - data_source_ids: Optional list of data source IDs to filter by
  - Returns documents with content, location, and relevance score

## Example Queries

- "What knowledge bases are available?"
- "Find information about AWS Lambda functions in the documentation knowledge base"
- "Search for pricing details in the product information knowledge base"
- "Look up best practices for building serverless applications"
- "Find examples of integrating Amazon Bedrock with other AWS services"

## Best Practices for Knowledge Base Searching

- Start by discovering available knowledge bases using resource://knowledgebases
- Use clear, specific queries for best results
- Make multiple focused queries instead of one complex query
- Extract and combine information from multiple results
- Consider source reliability and relevance scores
- Try different queries if results aren't relevant

## Customization

To modify the server configuration, edit the `_setup_server_config` method in `config.py`. You can change:
- The command to run the server (currently defaults to "uv")
- The directory where the server.py file is located
- Additional environment variables needed by the server 