# Filesystem Operations with InlineAgent

This example demonstrates how to use the MCP Filesystem server with InlineAgent to perform a wide range of file and directory operations on your local filesystem.

## Features

- Complete file management capabilities
- Secure access limited to specific mounted directories
- Advanced file editing with pattern matching
- Detailed file metadata and search functionality
- UUID-based output paths for unique file organization

## Setup Instructions

1. Ensure you have Docker installed and running on your system
2. Make sure the InlineAgent package is installed in your environment
3. The configuration automatically mounts:
   - The repository directory at `/projects`
4. Run the example:
   ```
   python main.py
   ```

## UUID-Based File Organization

Each time the script runs, it generates a unique UUID that's used to create a dedicated output directory. This ensures:
- Each run has its own isolated output location
- Files from different runs don't overwrite each other
- Output is organized and traceable to specific sessions

All generated files and directories are created within:
```
/projects/output/{SESSION_UUID}/
```

Which translates to this path in your local filesystem:
```
/Users/rppth/Desktop/amazon-bedrock-fsi-agents-examples/output/{SESSION_UUID}/
```

## Available Operations

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

### File Management
- **move_file**: Move or rename files and directories
- **search_files**: Find files/directories recursively with pattern matching
- **get_file_info**: Retrieve detailed file metadata (size, timestamps, type, permissions)

## Example Usage

```python
# Get the UUID for this session
session_uuid = "123e4567-e89b-12d3-a456-426614174000"  # Example UUID

# List accessible directories
list_allowed_directories()

# Create a session directory
create_directory(f"/projects/output/{session_uuid}")

# Write a new file in the session directory
write_file(f"/projects/output/{session_uuid}/example.txt", "This is example content")

# Read a file
read_file(f"/projects/output/{session_uuid}/example.txt")

# Edit a file (with dry run)
edit_file(
    path=f"/projects/output/{session_uuid}/example.txt",
    edits=[
        {
            "oldText": "This is example content",
            "newText": "This is updated content"
        }
    ],
    dryRun=True
)

# Search for files in the session directory
search_files(
    path=f"/projects/output/{session_uuid}",
    pattern="*.txt"
)

# Get file information
get_file_info(f"/projects/output/{session_uuid}/example.txt")
```

## Path Structure
When referring to paths, use the container's path structure:
- `/projects` - Your repository root
- `/projects/output/{SESSION_UUID}` - Your unique session output directory

## Finding Your Output

To find your session's output, check the UUID that was generated at the start of the run (printed in the console), then look in:
```
/Users/rppth/Desktop/amazon-bedrock-fsi-agents-examples/output/{SESSION_UUID}/
```

You can also run:
```
ls -la /Users/rppth/Desktop/amazon-bedrock-fsi-agents-examples/output/
```
to see all session directories.

## Customization

To modify the mount configuration, edit the `mount_points` list in `config.py`:

```python
self.mount_points = [
    {
        "src": "/path/on/your/machine",
        "dst": "/projects"
    }
]
```