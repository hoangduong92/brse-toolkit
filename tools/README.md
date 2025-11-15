# Tools Directory

This directory contains ready-to-use productivity tools for Bridge System Engineers.

## Available Tools

### Excel Translator
**Location**: `excel-translator/`

Batch translate Excel files while preserving formatting, formulas, and structure.

**Features**:
- Multi-sheet support
- Formula preservation
- Japanese ⟷ Vietnamese ⟷ English translation
- Custom glossary support
- Conditional formatting maintained

**Quick Start**:
```bash
cd excel-translator
python translate.py input.xlsx --target-lang vi
```

---

### PowerPoint Translator
**Location**: `pptx-translator/`

Automated slide translation with complete layout preservation.

**Features**:
- Text box & shape translation
- Notes & comments included
- Template-aware processing
- Batch processing support

**Quick Start**:
```bash
cd pptx-translator
python translate.py presentation.pptx --target-lang ja
```

---

## Adding New Tools

To add a new tool to this directory:

1. **Create a directory** with a descriptive name (e.g., `pdf-merger/`)

2. **Required files**:
   - `README.md`: Tool documentation
   - Main script or entry point
   - `requirements.txt` or `package.json`: Dependencies

3. **Recommended structure**:
   ```
   your-tool/
   ├── README.md
   ├── requirements.txt or package.json
   ├── config.yaml (if applicable)
   ├── src/
   │   └── main implementation files
   ├── tests/
   │   └── test files
   └── examples/
       └── example usage
   ```

4. **Documentation checklist**:
   - Clear description of what the tool does
   - Installation instructions
   - Usage examples
   - Configuration options
   - Known limitations
   - License information

See [CONTRIBUTING.md](../CONTRIBUTING.md) for detailed guidelines.

---

## Tool Guidelines

All tools should:

- ✅ Be production-ready or clearly marked as beta
- ✅ Include error handling
- ✅ Have comprehensive documentation
- ✅ Include usage examples
- ✅ Follow security best practices
- ✅ Be tested before inclusion

---

## Getting Help

- **Documentation**: Check individual tool README files
- **Issues**: [Report bugs](https://github.com/YOUR_USERNAME/brse-toolkit/issues)
- **Discussions**: [Ask questions](https://github.com/YOUR_USERNAME/brse-toolkit/discussions)
