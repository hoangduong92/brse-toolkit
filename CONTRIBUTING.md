# Contributing to BrSE Toolkit

Thank you for your interest in contributing to BrSE Toolkit! This document provides guidelines and instructions for contributing to this project.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Getting Started](#getting-started)
- [How to Contribute](#how-to-contribute)
- [Development Guidelines](#development-guidelines)
- [Pull Request Process](#pull-request-process)
- [Community](#community)

## Code of Conduct

This project adheres to a code of conduct that all contributors are expected to follow:

- Be respectful and inclusive
- Welcome newcomers and help them get started
- Focus on constructive feedback
- Respect differing viewpoints and experiences

## Getting Started

1. **Fork the repository** on GitHub
2. **Clone your fork** locally:
   ```bash
   git clone https://github.com/your-username/brse-toolkit.git
   cd brse-toolkit
   ```
3. **Create a branch** for your changes:
   ```bash
   git checkout -b feature/your-feature-name
   ```

## How to Contribute

### Reporting Bugs

- Use the GitHub issue tracker
- Check if the issue already exists
- Provide detailed information:
  - Steps to reproduce
  - Expected vs actual behavior
  - Environment details (OS, versions, etc.)

### Suggesting Enhancements

- Open an issue with the "enhancement" label
- Clearly describe the proposed feature
- Explain the use case and benefits
- Consider backwards compatibility

### Contributing Code

1. **Tools**: Add ready-to-use tools in the `tools/` directory
2. **Claude Code Skills**: Add reusable skills in `claude-code/skills/`
3. **MCP Servers**: Add MCP server implementations in `claude-code/mcp-servers/`
4. **Documentation**: Improve or add docs in the `docs/` directory
5. **Examples**: Add working examples in the `examples/` directory

## Development Guidelines

### File Structure

```
tools/
├── your-tool/
│   ├── README.md          # Tool documentation
│   ├── package.json       # Dependencies (if applicable)
│   └── src/               # Source code

claude-code/
├── skills/
│   └── your-skill/
│       └── skill.md       # Skill definition
│
└── mcp-servers/
    └── your-server/
        ├── README.md      # Setup instructions
        └── src/           # Server implementation
```

### Code Quality

- Write clear, self-documenting code
- Include comprehensive README files
- Add examples and usage instructions
- Test your code thoroughly
- Follow existing code style in the project

### Documentation

- Update relevant README files
- Add inline comments for complex logic
- Include usage examples
- Document prerequisites and dependencies

## Pull Request Process

1. **Ensure your code works**:
   - Test thoroughly
   - Update documentation
   - Add examples if applicable

2. **Commit your changes**:
   ```bash
   git add .
   git commit -m "feat: add your feature description"
   ```

   Use conventional commit messages:
   - `feat:` for new features
   - `fix:` for bug fixes
   - `docs:` for documentation changes
   - `refactor:` for code refactoring
   - `test:` for test additions

3. **Push to your fork**:
   ```bash
   git push origin feature/your-feature-name
   ```

4. **Open a Pull Request**:
   - Provide a clear title and description
   - Reference any related issues
   - Explain what changed and why
   - Include screenshots/examples if applicable

5. **Review process**:
   - Address reviewer feedback
   - Keep the conversation constructive
   - Update your PR as needed

## Community

### Questions and Support

- Open a GitHub Discussion for general questions
- Use Issues for bugs and feature requests
- Check existing documentation first

### Recognition

Contributors will be recognized in:
- README.md contributor section
- Release notes
- Project documentation

## License

By contributing to BrSE Toolkit, you agree that your contributions will be licensed under the MIT License.

---

Thank you for contributing to BrSE Toolkit! Your efforts help make this project better for the entire BrSE community.
