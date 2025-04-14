# Filesystem Operations with InlineAgent

This example demonstrates how to use the MCP Filesystem server with InlineAgent to perform a wide range of file and directory operations on your local filesystem. Note that all actions are performed only in the mounted directory of `/projects` within this repository.

## Features

- Complete file management capabilities
- Secure access limited to specific mounted directories
- Advanced file editing with pattern matching
- Detailed file metadata and search functionality
- UUID-based output paths for unique file organization

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

2. Ensure you have Docker installed and running on your system

   ```bash
   docker ps  # Should return the list of running containers
   ```

3. Pull the [required Docker image](https://hub.docker.com/r/mcp/filesystem).

   ```bash
   docker pull mcp/filesystem
   ```

4. Run the example.
   ```
   python main.py
   ```

## Available Tools

### File Reading

- **read_file**: Read complete contents of a file with UTF-8 encoding
- **read_multiple_files**: Read several files simultaneously (failed reads won't stop the operation)

### File Writing and Editing

- **write_file**: Create new files or overwrite existing ones
- **edit_file**: Make selective edits with advanced pattern matching, including:
  - Line-based and multi-line content matching
  - Whitespace normalization with indentation preservation
  - Multiple simultaneous edits with correct positioning
  - Preview changes with dry run mode

### Directory Operations

- **create_directory**: Create new directories (creates parent directories if needed)
- **list_directory**: Show directory contents with file/directory indicators
- **list_allowed_directories**: View all accessible directories
- **directory_tree**: Get a recursive tree view of files and directories

### File Management

- **move_file**: Move or rename files and directories
- **search_files**: Find files/directories recursively with pattern matching
- **get_file_info**: Retrieve detailed file metadata (size, timestamps, type, permissions)

## Example Queries

- "Can you write a python script named `calculator.py` that implements functions for a simple calculator?"
- "Can you summarize what's in the `content.txt` file?"
- "Search through all files in the directory and tell me which file stores configuration."
- "Please create a backup directory and copy all .json files into it."
- "Can you analyze the size and last modified dates of all log files in the logs directory?"
