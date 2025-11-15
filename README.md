# BrSE Toolkit 🚀

> A curated collection of productivity tools, automation scripts, and AI-powered workflows for Bridge System Engineers working across Japanese and Vietnamese tech environments.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

---

## 🎯 About This Project

As a Bridge System Engineer (BrSE) working between Japanese clients and Vietnamese development teams, I've built various tools and workflows to streamline communication, automate repetitive tasks, and improve productivity. This repository shares those battle-tested solutions with the community.

**Focus Areas:**
- 🌐 Japanese ⟷ Vietnamese translation automation
- 🤖 RPA & low-code platform integrations (WinActor, Kintone)
- 🔧 Claude AI-powered development workflows
- 📊 Data integration tools (Snowflake, Google Sheets)
- 📝 Documentation & reporting automation

---

## 🛠️ Featured Tools

### 1️⃣ Excel Translator
> Batch translate Excel files while preserving formatting and formulas

**Features:**
- Multi-sheet support with formula preservation
- Japanese ⟷ Vietnamese ⟷ English
- Conditional formatting maintained
- Custom glossary support

📁 [View Tool](tools/excel-translator/) | 📖 [Documentation](docs/excel-translator.md)

---

### 2️⃣ PowerPoint Translator
> Automated slide translation with layout preservation

**Features:**
- Text box & shape text translation
- Notes & comments included
- Template-aware processing
- Batch processing support

📁 [View Tool](tools/pptx-translator/) | 📖 [Documentation](docs/pptx-translator.md)

---

### 3️⃣ Claude Code MCP Servers
> Model Context Protocol servers for enhanced development workflows

#### Backlog MCP Server
Integration with Nulab Backlog for project management automation
- Issue creation & updates
- Bulk operations support
- Custom field mapping

#### Google Sheets MCP Server
Advanced spreadsheet operations with Claude Code
- Data extraction & transformation
- Formula manipulation
- Multi-sheet operations

📁 [View MCP Servers](claude-code/mcp-servers/) | 📖 [Setup Guide](docs/mcp-setup-guide.md)

---

### 4️⃣ Claude Skills Library
> Pre-configured AI skills for common BrSE tasks

- **BrSE Workflow**: Project coordination templates
- **JP Business Context**: Japanese business communication patterns
- **Technical Translation**: Domain-specific terminology handling

📁 [View Skills](claude-code/skills/) | 📖 [Usage Guide](docs/claude-skills.md)

---

## 📚 Documentation

### Getting Started
- [Installation Guide](docs/installation.md)
- [Quick Start Tutorial](docs/quick-start.md)
- [Configuration](docs/configuration.md)

### Guides
- [MCP Server Setup](docs/mcp-setup-guide.md)
- [Google Sheets Integration](docs/google-sheets-guide.md)
- [Translation Best Practices](docs/translation-best-practices.md)

### Examples
- [Kintone Integration Example](examples/kintone-integration/)
- [Snowflake Data Pipeline](examples/snowflake-setup/)
- [Automated Reporting Workflow](examples/automated-reporting/)

---

## 🚀 Quick Start

### Prerequisites
- Python 3.9+
- Node.js 18+ (for MCP servers)
- Claude Code CLI (optional, for AI workflows)

### Installation

```bash
# Clone the repository
git clone https://github.com/YOUR_USERNAME/brse-toolkit.git
cd brse-toolkit

# Install Python dependencies
pip install -r requirements.txt

# Install Node dependencies (for MCP servers)
cd claude-code/mcp-servers/backlog-mcp
npm install
```

### Basic Usage

```bash
# Example: Translate an Excel file
python tools/excel-translator/translate.py input.xlsx --target-lang vi

# Example: Run Backlog MCP server
cd claude-code/mcp-servers/backlog-mcp
npm start
```

---

## 🎨 Use Cases

### For BrSEs
- Automate requirement document translation
- Sync tasks between Backlog and Google Sheets
- Generate client reports in Japanese

### For Project Managers
- Bulk update project issues
- Extract analytics from multiple data sources
- Automated status reporting

### For Developers
- Quick setup of development environments
- Integrate AI assistance into workflows
- Reusable prompt templates

---

## 🗺️ Roadmap

### Current Version: 0.1.0 (Beta)

**In Progress:**
- [ ] Excel Translator v1.0 (stable release)
- [ ] PowerPoint Translator initial version
- [ ] Backlog MCP comprehensive documentation

**Planned:**
- [ ] Video tutorials for each tool
- [ ] VS Code extension integration
- [ ] Slack bot for quick translations
- [ ] Notion integration
- [ ] Docker containerization

**Future Ideas:**
- [ ] Web UI for translation tools
- [ ] Multi-language support expansion
- [ ] AI-powered requirement analysis
- [ ] Automated test case generation

---

## 🤝 Contributing

Contributions are welcome! Whether it's:
- 🐛 Bug reports
- 💡 Feature requests
- 📝 Documentation improvements
- 🔧 Code contributions

Please see [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

### Development Setup

```bash
# Fork and clone your fork
git clone https://github.com/YOUR_USERNAME/brse-toolkit.git

# Create a feature branch
git checkout -b feature/amazing-feature

# Make changes and commit
git commit -m "Add amazing feature"

# Push and create PR
git push origin feature/amazing-feature
```

---

## 📫 Contact & Support

- **Blog**: [Your Facebook Page](#) - Tips & tutorials in Vietnamese
- **LinkedIn**: [Your Profile](#) - Professional updates
- **Issues**: [GitHub Issues](https://github.com/YOUR_USERNAME/brse-toolkit/issues) - Bug reports & feature requests

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

- Built with experience from real-world BrSE projects
- Inspired by the Vietnamese IT outsourcing community
- Powered by Anthropic's Claude AI
- Special thanks to all contributors

---

## ⭐ Show Your Support

If you find this toolkit helpful, please consider:
- ⭐ Starring this repository
- 🔗 Sharing with fellow BrSEs
- 📝 Writing about your experience
- 🤝 Contributing improvements

---

<div align="center">

**Made with ❤️ by a BrSE, for BrSEs**

[⬆ back to top](#brse-toolkit-)

</div>
