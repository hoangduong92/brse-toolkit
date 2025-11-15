# MCP Server Setup Guide

This guide will help you set up and configure the Model Context Protocol (MCP) servers included in BrSE Toolkit.

## Table of Contents

- [What is MCP?](#what-is-mcp)
- [Prerequisites](#prerequisites)
- [Backlog MCP Server](#backlog-mcp-server)
- [Google Sheets MCP Server](#google-sheets-mcp-server)
- [Claude Code Integration](#claude-code-integration)
- [Troubleshooting](#troubleshooting)

## What is MCP?

Model Context Protocol (MCP) is a standardized way to connect AI models like Claude to external data sources and tools. MCP servers provide:

- **Contextual data**: Access to external information during conversations
- **Tool execution**: Ability to perform actions through integrated services
- **Real-time updates**: Live data from connected platforms

## Prerequisites

Before setting up MCP servers:

- Node.js 18+ installed
- Claude Code CLI installed (or Claude Desktop)
- API credentials for the services you want to integrate

## Backlog MCP Server

The Backlog MCP server enables Claude Code to interact with Nulab Backlog for project management.

### Setup

#### 1. Install Dependencies

```bash
cd claude-code/mcp-servers/backlog-mcp
npm install
```

#### 2. Configure API Credentials

Create a `.env` file:

```bash
cp .env.example .env
```

Edit `.env` with your credentials:

```env
# Your Backlog space URL (e.g., yourspace.backlog.jp or yourspace.backlog.com)
BACKLOG_SPACE_ID=yourspace

# Get your API key from:
# https://yourspace.backlog.jp/EditApiSettings.action
BACKLOG_API_KEY=your_api_key_here

# Optional: Default project key
BACKLOG_DEFAULT_PROJECT=YOURPROJECT
```

#### 3. Test the Server

```bash
npm test
# or
npm run dev  # Runs in development mode with auto-reload
```

### Features

The Backlog MCP server provides:

- **Issue Management**: Create, update, and query issues
- **Project Information**: Access project details and metadata
- **Comments**: Add and retrieve issue comments
- **Custom Fields**: Work with custom field data
- **Bulk Operations**: Perform batch updates on multiple issues

### Usage Examples

With the server running, you can ask Claude Code:

```
"Create a new issue in Backlog for implementing the login feature"
"Update issue PROJ-123 to 'In Progress' status"
"Get all open issues assigned to me"
"Add a comment to issue PROJ-456 with the test results"
```

## Google Sheets MCP Server

The Google Sheets MCP server enables Claude Code to read and write data to Google Sheets.

### Setup

#### 1. Install Dependencies

```bash
cd claude-code/mcp-servers/google-sheets-mcp
npm install
```

#### 2. Set Up Google Cloud Credentials

1. Go to [Google Cloud Console](https://console.cloud.google.com/)
2. Create a new project or select an existing one
3. Enable the Google Sheets API
4. Create credentials (Service Account or OAuth 2.0)
5. Download the credentials JSON file

#### 3. Configure Credentials

```bash
# Copy the credentials file to the server directory
cp ~/Downloads/credentials.json .

# Create .env file
cp .env.example .env
```

Edit `.env`:

```env
# Path to your Google credentials file
GOOGLE_APPLICATION_CREDENTIALS=./credentials.json

# Optional: Default spreadsheet ID
GOOGLE_SHEETS_DEFAULT_SPREADSHEET=your_spreadsheet_id_here
```

#### 4. Test the Server

```bash
npm test
# or
npm run dev
```

### Features

The Google Sheets MCP server provides:

- **Data Reading**: Fetch data from specified ranges
- **Data Writing**: Update cells and ranges
- **Sheet Management**: Create, rename, delete sheets
- **Formatting**: Apply basic formatting to cells
- **Formula Execution**: Read and write formulas

### Usage Examples

With the server running, you can ask Claude Code:

```
"Read data from Sheet1 A1:D10 in my spreadsheet"
"Write 'Completed' to cell B5 in the Tasks sheet"
"Create a new sheet called 'Q4 Results'"
"Calculate the sum of column C and put it in C11"
```

## Claude Code Integration

### Method 1: Using Claude Code CLI

Add MCP servers to your Claude Code configuration:

**Location**: `~/.config/claude-code/config.json` (Unix) or `%APPDATA%\claude-code\config.json` (Windows)

```json
{
  "mcpServers": {
    "backlog": {
      "command": "node",
      "args": ["/path/to/brse-toolkit/claude-code/mcp-servers/backlog-mcp/dist/index.js"],
      "env": {
        "BACKLOG_SPACE_ID": "yourspace",
        "BACKLOG_API_KEY": "your_api_key"
      }
    },
    "google-sheets": {
      "command": "node",
      "args": ["/path/to/brse-toolkit/claude-code/mcp-servers/google-sheets-mcp/dist/index.js"],
      "env": {
        "GOOGLE_APPLICATION_CREDENTIALS": "/path/to/credentials.json"
      }
    }
  }
}
```

### Method 2: Using Claude Desktop

Edit Claude Desktop's configuration file:

**macOS**: `~/Library/Application Support/Claude/claude_desktop_config.json`
**Windows**: `%APPDATA%\Claude\claude_desktop_config.json`

Use the same JSON structure as above.

### Verify Installation

Restart Claude Code or Claude Desktop, then try:

```bash
claude-code mcp list
# Should show your configured servers
```

## Development

### Building the Servers

```bash
# Backlog MCP
cd claude-code/mcp-servers/backlog-mcp
npm run build

# Google Sheets MCP
cd claude-code/mcp-servers/google-sheets-mcp
npm run build
```

### Running in Development Mode

```bash
# With auto-reload
npm run dev

# With debug logging
DEBUG=mcp:* npm run dev
```

### Testing

```bash
# Run tests
npm test

# Run tests with coverage
npm run test:coverage

# Integration tests
npm run test:integration
```

## Troubleshooting

### Server Not Starting

**Check Node.js version**:
```bash
node --version  # Should be 18+
```

**Check dependencies**:
```bash
npm install
npm run build
```

### Authentication Errors

**Backlog**:
- Verify API key is correct
- Check space ID matches your Backlog space
- Ensure API key has necessary permissions

**Google Sheets**:
- Verify credentials file path is correct
- Check service account has access to the spreadsheet
- Enable Google Sheets API in Google Cloud Console

### Connection Issues

**Check server logs**:
```bash
DEBUG=mcp:* npm run dev
```

**Test server independently**:
```bash
npm test
```

### Claude Code Not Detecting Servers

1. Verify config file location and syntax
2. Restart Claude Code/Claude Desktop
3. Check server paths are absolute
4. Verify environment variables are set correctly

## Advanced Configuration

### Custom Server Options

```json
{
  "mcpServers": {
    "backlog": {
      "command": "node",
      "args": ["dist/index.js"],
      "env": {
        "BACKLOG_SPACE_ID": "yourspace",
        "BACKLOG_API_KEY": "your_api_key",
        "LOG_LEVEL": "debug",
        "CACHE_TTL": "300"
      }
    }
  }
}
```

### Multiple Instances

You can run multiple instances for different workspaces:

```json
{
  "mcpServers": {
    "backlog-project-a": {
      "command": "node",
      "args": ["dist/index.js"],
      "env": {
        "BACKLOG_SPACE_ID": "project-a",
        "BACKLOG_DEFAULT_PROJECT": "PRJA"
      }
    },
    "backlog-project-b": {
      "command": "node",
      "args": ["dist/index.js"],
      "env": {
        "BACKLOG_SPACE_ID": "project-b",
        "BACKLOG_DEFAULT_PROJECT": "PRJB"
      }
    }
  }
}
```

## Security Best Practices

1. **Never commit credentials**: Use `.env` files and add them to `.gitignore`
2. **Use environment variables**: Don't hardcode API keys
3. **Limit permissions**: Grant minimal necessary permissions to API keys
4. **Rotate keys regularly**: Update API keys periodically
5. **Secure storage**: Use secure credential management for production

## Next Steps

- Explore [examples/](../examples/) for real-world usage
- Read [best-practices/](best-practices/) for optimal workflows
- Contribute improvements to [CONTRIBUTING.md](../CONTRIBUTING.md)

---

Need help? Open an issue on [GitHub](https://github.com/YOUR_USERNAME/brse-toolkit/issues).
