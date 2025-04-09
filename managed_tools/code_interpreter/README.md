# Amazon Bedrock Managed Code Interpreter Example

This example demonstrates how to use Amazon Bedrock's managed Code Interpreter tool with InlineAgent. The Code Interpreter allows an agent to write and execute Python code, create visualizations, perform data analysis, and more.

## Features

- Write and execute Python code
- Create data visualizations
- Perform data analysis and mathematical calculations
- Test algorithms and generate example code
- Process and transform data

## Setup Instructions

1. Ensure you have the necessary dependencies installed:
   ```
   pip install -r requirements.txt
   ```

2. Configure your AWS credentials:
   - Set up your AWS credentials in `~/.aws/credentials` or environment variables
   - Make sure the profile has permissions to access Amazon Bedrock

3. Run the example:
   ```
   python main.py
   ```

## How It Works

The example in `main.py` creates an InlineAgent with only the managed Code Interpreter tool:

```python
InlineAgent(
    foundation_model="us.anthropic.claude-3-5-sonnet-20241022-v2:0",
    instruction="You are a helpful coding assistant...",
    agent_name="code_interpreter_assistant",
    action_groups=[
        {
            "name": "CodeInterpreter",
            "builtin_tools": {
                "parentActionGroupSignature": "AMAZON.CodeInterpreter"
            },
        },
    ],
)
```

The agent is then invoked with a prompt to create a visualization of the Fibonacci sequence.

## Customization

You can modify the example to:
- Change the foundation model
- Update the instructions to the agent
- Modify the input prompt to solve different problems
- Add additional managed tools or MCP clients

## Additional Information

For more details on using the Code Interpreter with Amazon Bedrock Agents, refer to the [official documentation](https://docs.aws.amazon.com/bedrock/latest/userguide/agents-tools.html).

## Requirements

- Python 3.8+
- AWS account with access to Amazon Bedrock
- Proper IAM permissions for Bedrock and the Code Interpreter 