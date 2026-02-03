# Contributing to PDF to Obsidian

First off, thank you for considering contributing! 🎉

## How Can I Contribute?

### 🐛 Reporting Bugs

Before creating bug reports, please check existing issues. When creating a bug report, include:

- **Clear title and description**
- **Steps to reproduce** the issue
- **Expected vs actual behavior**
- **Sample PDF** (if possible and not confidential)
- **Browser and version** you're using

### 💡 Suggesting Features

Feature requests are welcome! Please include:

- **Use case**: Why would this feature be useful?
- **Proposed solution**: How do you envision it working?
- **Alternatives**: Any alternative solutions you've considered?

### 🔧 Pull Requests

1. Fork the repo and create your branch from `main`
2. Make your changes
3. Test thoroughly in multiple browsers
4. Update README.md if needed
5. Submit a pull request!

## Development Setup

This is a single-file HTML application, so setup is minimal:

```bash
# Clone your fork
git clone https://github.com/your-username/pdf-to-obsidian.git
cd pdf-to-obsidian

# Open in browser
open pdf-to-obsidian.html

# Or use a simple server
python -m http.server 8000
# Then visit http://localhost:8000
```

## Adding New Templates

Templates are defined in the `templates` object. Here's the structure:

```javascript
'template-id': {
    name: 'Display Name',
    fields: ['title', 'authors', 'year', 'custom-field'],
    structure: `## Section 1

## Section 2
- `
}
```

**Field naming conventions:**
- Use lowercase with hyphens: `custom-field`
- Common fields: `title`, `authors`, `year`, `publication`, `type`, `tags`, `read-status`
- Domain-specific fields should be prefixed: `gnn-architecture`, `ml-method`, `bio-organism`

## Code Style

- Use 4 spaces for indentation
- Use descriptive variable names
- Comment complex logic
- Keep functions focused and small
- Use modern ES6+ JavaScript

## Testing Checklist

Before submitting a PR, please test:

- [ ] File upload via click
- [ ] File upload via drag-and-drop
- [ ] Text extraction from various PDFs
- [ ] Metadata generation accuracy
- [ ] Download functionality
- [ ] Copy to clipboard
- [ ] Responsive design (mobile, tablet, desktop)
- [ ] Different browsers (Chrome, Firefox, Safari, Edge)

## Ideas for Contributions

Looking for something to work on? Here are some ideas:

### Easy (Good First Issues)
- Add more domain-specific templates
- Improve error messages
- Add keyboard shortcuts
- Improve mobile responsiveness
- Add dark mode toggle

### Medium
- Add batch processing for multiple PDFs
- Create browser extension version
- Add export to other formats (JSON, CSV)
- Implement custom field mapping UI
- Add template import/export

### Advanced
- Integration with reference managers (Zotero, Mendeley)
- OCR for scanned PDFs
- Citation extraction and formatting
- Advanced metadata validation
- Cloud storage integration

## Questions?

Feel free to open an issue with the label `question` or reach out to the maintainers.

## Code of Conduct

Be kind, be respectful, be helpful. We're all here to build something useful together!

---

Thank you for making PDF to Obsidian better! 🙏
