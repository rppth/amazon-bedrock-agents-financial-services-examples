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

1. Make sure you have `uv` installed on your system (used for running the server and package installation)
2. No environment variables or API keys are required

## Tools

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

## Usage Examples

### Basic Calculation
```python
execute_python(code="2 + 2")
```

### Variable Assignment and Persistence
```python
execute_python(code="x = 42")
execute_python(code="print(x)")  # Will output: 42
```

### Installing and Using Packages
```python
install_package(package="pandas")
execute_python(code="import pandas as pd\ndf = pd.DataFrame({'A': [1, 2, 3]})\nprint(df)")
```

### Data Visualization
```python
install_package(package="matplotlib")
execute_python(code="""
import matplotlib.pyplot as plt
import numpy as np

x = np.linspace(0, 10, 100)
y = np.sin(x)

plt.figure(figsize=(8, 4))
plt.plot(x, y)
plt.title('Sine Wave')
plt.savefig('sine_wave.png')
""")
```

### Resetting Session
```python
execute_python(code="", reset=True)
```

## Implementation Details

The server maintains a global namespace dictionary that preserves variables between executions. It uses Python's `exec()` and `eval()` functions to execute code and capture the output.

Package installation is handled by spawning a subprocess to run `uv pip install` commands. Imported packages become available immediately in the current session.

## Security Considerations

This server executes arbitrary Python code, which presents security risks. It is recommended to:

1. Run this server in a sandboxed environment
2. Limit access to the server
3. Be cautious when executing untrusted code
4. Consider using container isolation or virtualization for added protection

## Dependencies

- Python 3.10+ 
- uv
- MCP library 