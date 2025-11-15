# Claude Code Integration

This directory contains production-ready integrations for Claude Code, including MCP servers and reusable skills.

## Directory Structure

```
claude-code/
├── skills/              # Reusable AI skills and prompts
│   ├── brse-workflow/   # BrSE-specific workflow templates
│   └── jp-business-context/  # Japanese business communication
│
└── mcp-servers/         # Model Context Protocol servers
    ├── backlog-mcp/     # Backlog project management integration
    └── google-sheets-mcp/  # Google Sheets data operations
```

## What is Claude Code?

Claude Code is Anthropic's official CLI tool that brings Claude AI directly into your development workflow. It enables:

- AI-assisted development and debugging
- Context-aware code suggestions
- Integration with external tools and data sources via MCP

## MCP Servers

Model Context Protocol (MCP) servers provide Claude Code with access to external services and data.

### Available Servers

#### Backlog MCP Server
**Location**: `mcp-servers/backlog-mcp/`

Integrates Claude Code with Nulab Backlog for project management automation.

**Capabilities**:
- Create and update issues
- Query project information
- Manage comments and custom fields
- Bulk operations support

**Setup**: See [MCP Setup Guide](../docs/mcp-setup-guide.md#backlog-mcp-server)

---

#### Google Sheets MCP Server
**Location**: `mcp-servers/google-sheets-mcp/`

Enables Claude Code to interact with Google Sheets.

**Capabilities**:
- Read and write spreadsheet data
- Create and manage sheets
- Execute formulas
- Apply formatting

**Setup**: See [MCP Setup Guide](../docs/mcp-setup-guide.md#google-sheets-mcp-server)

---

## Skills

Skills are reusable prompt templates and workflows that enhance Claude Code's capabilities for specific tasks.

### Available Skills

#### BrSE Workflow
**Location**: `skills/brse-workflow/`

Templates and patterns for common BrSE tasks:
- Requirement document analysis
- Project coordination workflows
- Status report generation
- Cross-cultural communication templates

---

#### JP Business Context
**Location**: `skills/jp-business-context/`

Japanese business communication patterns:
- Formal email templates
- Business meeting protocols
- Document formatting standards
- Cultural context awareness

---

## Quick Start

### 1. Install Claude Code

```bash
# Install Claude Code CLI
npm install -g @anthropic-ai/claude-code

# Or follow official installation guide
# https://code.claude.com
```

### 2. Configure MCP Servers

```bash
# Navigate to server directory
cd mcp-servers/backlog-mcp

# Install dependencies
npm install

# Configure credentials
cp .env.example .env
# Edit .env with your API keys

# Build the server
npm run build
```

### 3. Add to Claude Code Config

Edit `~/.config/claude-code/config.json`:

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
    }
  }
}
```

### 4. Use Skills

```bash
# Load a skill in Claude Code
claude-code --skill brse-workflow

# Or reference in your prompts
# "Use the BrSE workflow skill to analyze this requirement document"
```

## Development

### Creating New MCP Servers

1. Create a new directory in `mcp-servers/`
2. Initialize with the MCP SDK:
   ```bash
   npm init -y
   npm install @anthropic-ai/sdk
   ```
3. Implement server following MCP specification
4. Add comprehensive README and tests
5. Submit a pull request

### Creating New Skills

1. Create a new directory in `skills/`
2. Add a `skill.md` file with:
   - Skill description
   - Usage instructions
   - Example prompts
   - Expected outputs
3. Test thoroughly with Claude Code
4. Document any dependencies or setup requirements

## Best Practices

### Security
- Never commit API keys or credentials
- Use environment variables for sensitive data
- Implement proper error handling
- Follow principle of least privilege

### Performance
- Cache frequently accessed data
- Implement rate limiting
- Optimize API calls
- Handle timeouts gracefully

### Documentation
- Include setup instructions
- Provide usage examples
- Document all configuration options
- Explain error messages

## Resources

- **Official Docs**: [Claude Code Documentation](https://code.claude.com)
- **MCP Specification**: [Model Context Protocol](https://spec.modelcontextprotocol.io/)
- **Setup Guide**: [docs/mcp-setup-guide.md](../docs/mcp-setup-guide.md)
- **Examples**: [examples/](../examples/)

## Contributing

We welcome contributions! See [CONTRIBUTING.md](../CONTRIBUTING.md) for guidelines.

**Ideas for new integrations**:
- Slack MCP server
- Notion MCP server
- Jira MCP server
- GitHub Actions workflows
- Custom internal tools

---

Need help? [Open an issue](https://github.com/YOUR_USERNAME/brse-toolkit/issues) or [start a discussion](https://github.com/YOUR_USERNAME/brse-toolkit/discussions).
