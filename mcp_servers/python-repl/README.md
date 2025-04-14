# Python REPL MCP Server

> **EXPERIMENTAL: This MCP server is experimental and carries significant risks since it executes Python code locally on your machine. Use with extreme caution in controlled environments only.**

This Model Context Protocol (MCP) server provides a Python REPL (Read-Eval-Print Loop) interface, allowing AI agents to execute Python code, install packages, and maintain state across multiple executions.

## Features

- **Execute Python Code**: Run arbitrary Python code and get the output
- **Persistent Session**: Variables and imports persist between executions in the same session
- **Package Installation**: Install Python packages using `uv` (a faster alternative to pip)
- **Session Management**: List variables, reset the session when needed

## Security Warning

This MCP server executes Python code directly on your local system with the same permissions as the user running the server. This presents significant security risks:

1. It can access, modify, or delete any files that the running user has access to
2. It can make network connections, access APIs, or interact with other services
3. Malicious code could potentially harm your system or compromise security

**Only use this MCP in controlled environments with code you trust.**

## Setup

1. Activate virtual environment from project's root directory.

   ```bash
   # On macOS and Linux.
   source .venv/bin/activate
   ```

   ```bash
   # On Windows.
   .venv\Scripts\activate
   ```

2. Run the example.
   ```
   python main.py
   ```

## Available Tools

### execute_python

Executes Python code in a persistent environment.

**Parameters:**

- `code` (string, required): Python code to execute
- `reset` (boolean, optional): If true, resets the session and clears all variables

**Response:**

- Output from the code execution
- Error messages if the code fails
- Result of the last expression if there's no output

### list_variables

Lists all variables currently defined in the session.

**Parameters:**

- None

**Response:**

- List of variable names and their string representations

### install_package

Installs a Python package using uv.

**Parameters:**

- `package` (string, required): Package name to install (e.g., 'pandas')

**Response:**

- Success or error message

## Example Queries

- "Show me an example of using pandas to process the data in Python dictionary."
- "Create a sample code that executes binary search and list of all variable names."
- "Can you create an ARIMA model and forecast on synthetic financial data?"
- "How can I get started with scikit-learn for training classification model?"
