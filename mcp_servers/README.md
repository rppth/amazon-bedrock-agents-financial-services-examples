## Project Architecture

This project uses an [Inline Amazon Bedrock agent](https://docs.aws.amazon.com/bedrock/latest/userguide/agents-create-inline.html) to dynamically invoke an agent to perform specific tasks without pre-defining agent capabilities each time.

Each directory of MCP server will include the following files:

- `config.py` - Contains all MCP server configuration and environment variable handling.
- `main.py` - Inline agent setup and execution.

To test each MCP server with your own query, you can navigate to `main.py` and change the `input_text` with your desired query.

Each directory of MCP server may include additional files such as:

- `server.py` - The MCP server implementation to perform specific tasks.

- `.env.example` - Example file that shows proper `.env` file setup.
