# Getting Started with BrSE Toolkit

Welcome to BrSE Toolkit! This guide will help you get up and running quickly.

## Table of Contents

- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Project Structure](#project-structure)
- [Quick Start](#quick-start)
- [Next Steps](#next-steps)

## Prerequisites

Before you begin, ensure you have the following installed:

### Required
- **Python 3.9+**: For translation tools and automation scripts
  ```bash
  python --version  # Should show 3.9 or higher
  ```

- **Node.js 18+**: For MCP servers and JavaScript tools
  ```bash
  node --version    # Should show 18.0 or higher
  npm --version
  ```

### Optional
- **Claude Code CLI**: For AI-powered development workflows
  - Installation: [Claude Code Documentation](https://code.claude.com)

- **Git**: For version control
  ```bash
  git --version
  ```

## Installation

### 1. Clone the Repository

```bash
# Using HTTPS
git clone https://github.com/YOUR_USERNAME/brse-toolkit.git
cd brse-toolkit

# Or using SSH
git clone git@github.com:YOUR_USERNAME/brse-toolkit.git
cd brse-toolkit
```

### 2. Install Python Dependencies

```bash
# Create a virtual environment (recommended)
python -m venv venv

# Activate the virtual environment
# On Windows:
venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt
```

### 3. Install Node.js Dependencies (for MCP servers)

```bash
# Navigate to the MCP server directory
cd claude-code/mcp-servers/backlog-mcp

# Install dependencies
npm install

# Return to project root
cd ../../..
```

## Project Structure

```
brse-toolkit/
├── README.md                  # Project overview
├── LICENSE                    # MIT License
├── CONTRIBUTING.md            # Contribution guidelines
│
├── tools/                     # Ready-to-use tools
│   ├── excel-translator/      # Excel translation tool
│   └── pptx-translator/       # PowerPoint translation tool
│
├── claude-code/               # Claude Code integrations
│   ├── skills/                # Reusable AI skills
│   │   ├── brse-workflow/     # BrSE workflow templates
│   │   └── jp-business-context/  # Japanese business context
│   │
│   └── mcp-servers/           # MCP server implementations
│       ├── backlog-mcp/       # Backlog integration
│       └── google-sheets-mcp/ # Google Sheets integration
│
├── docs/                      # Documentation
│   ├── getting-started.md     # This file
│   ├── mcp-setup-guide.md     # MCP setup instructions
│   └── best-practices/        # Best practices guides
│
└── examples/                  # Example projects
    ├── kintone-integration/   # Kintone examples
    └── snowflake-setup/       # Snowflake examples
```

## Quick Start

### Using the Excel Translator

```bash
# Navigate to the tool directory
cd tools/excel-translator

# Run the translator
python translate.py input.xlsx --target-lang vi --source-lang ja

# Options:
# --target-lang: Target language (vi, ja, en)
# --source-lang: Source language (auto-detect if not specified)
# --output: Output file path (default: input_translated.xlsx)
```

### Using the Backlog MCP Server

```bash
# Navigate to the server directory
cd claude-code/mcp-servers/backlog-mcp

# Configure your API credentials
cp .env.example .env
# Edit .env with your Backlog API key

# Start the server
npm start

# The server will be available for Claude Code
```

### Using Claude Code Skills

```bash
# With Claude Code CLI installed
claude-code --skill brse-workflow

# Or add skills to your Claude Code configuration
# See: docs/mcp-setup-guide.md
```

## Configuration

### Environment Variables

Create a `.env` file in the project root:

```env
# Translation API (if using external service)
TRANSLATION_API_KEY=your_api_key_here

# Backlog Configuration
BACKLOG_SPACE_ID=your_space_id
BACKLOG_API_KEY=your_api_key

# Google Sheets (if needed)
GOOGLE_SHEETS_CREDENTIALS=path/to/credentials.json
```

### Tool-Specific Configuration

Each tool may have its own configuration file:

- **Excel Translator**: `tools/excel-translator/config.yaml`
- **PowerPoint Translator**: `tools/pptx-translator/config.yaml`
- **Backlog MCP**: `claude-code/mcp-servers/backlog-mcp/.env`

## Verification

Test your installation:

```bash
# Test Python installation
python -c "import sys; print(f'Python {sys.version}')"

# Test Node.js installation
node -v && npm -v

# Test tool availability
python tools/excel-translator/translate.py --help
```

## Next Steps

Now that you're set up, explore:

1. **[MCP Setup Guide](mcp-setup-guide.md)**: Configure Claude Code integrations
2. **[Best Practices](best-practices/)**: Learn optimal workflows
3. **[Examples](../examples/)**: See real-world usage examples
4. **[Contributing](../CONTRIBUTING.md)**: Contribute to the project

## Troubleshooting

### Common Issues

**Issue: Python module not found**
```bash
# Ensure virtual environment is activated
# Then reinstall dependencies
pip install -r requirements.txt
```

**Issue: Node.js version too old**
```bash
# Update Node.js using nvm (recommended)
nvm install 18
nvm use 18
```

**Issue: Permission denied errors**
```bash
# On Unix systems, you may need to adjust permissions
chmod +x tools/excel-translator/translate.py
```

## Getting Help

- **Documentation**: Check the [docs/](../docs/) folder
- **Issues**: [GitHub Issues](https://github.com/YOUR_USERNAME/brse-toolkit/issues)
- **Discussions**: [GitHub Discussions](https://github.com/YOUR_USERNAME/brse-toolkit/discussions)

---

Ready to start using the tools? Head to the [tools/](../tools/) directory and explore!
