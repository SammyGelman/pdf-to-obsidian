# PDF to Obsidian Note Generator 📄→📝

A beautiful, single-file web app that extracts metadata from academic PDFs and generates ready-to-use Obsidian notes. Perfect for researchers, students, and anyone building a knowledge base.

![PDF to Obsidian](https://img.shields.io/badge/built%20with-Claude%20AI-orange)
![License](https://img.shields.io/badge/license-MIT-blue)

## ✨ Features

- **🎯 One-Click Extraction**: Drop a PDF and get structured Obsidian notes instantly
- **🤖 AI-Powered Metadata**: Uses Claude AI to intelligently extract authors, year, methods, findings, and more
- **📋 Multiple Templates**: Pre-built templates for GNN/Medical AI, Machine Learning, Biology, and more
- **🎨 Beautiful UI**: Clean, modern interface with smooth animations
- **📦 Zero Setup**: Single HTML file - no build process, no dependencies to install
- **🔒 Privacy-Focused**: All processing happens client-side (except AI API calls)

## 🚀 Quick Start

### Option 1: Use Online (Easiest)

1. Visit the [hosted version](#) (coming soon!)
2. Upload your PDF
3. Download your Obsidian note

### Option 2: Run Locally

1. Download `pdf-to-obsidian.html`
2. Open it in your browser
3. That's it! No server needed.

```bash
# Or clone the repo
git clone https://github.com/yourusername/pdf-to-obsidian.git
cd pdf-to-obsidian
open pdf-to-obsidian.html  # or just double-click the file
```

## 📖 How It Works

1. **Upload**: Drag and drop a PDF or click to browse
2. **Extract**: PDF.js extracts text from the first 10 pages
3. **Analyze**: Claude AI analyzes the content and extracts structured metadata
4. **Generate**: Your Obsidian note is created with YAML frontmatter and template sections
5. **Download**: Save the `.md` file directly to your Obsidian vault

## 🎯 Use Cases

### Research Literature Review
Perfect for building a structured knowledge base of papers:
```markdown
---
title: "Graph Neural Networks for EHR-based Prediction"
authors: [Smith J, Chen L, Kumar R]
year: 2023
gnn-architecture: [GCN, GAT]
dataset: [MIMIC-III, eICU]
tags: [gnn, ehr, medical-ai]
---

## Summary
[Your notes here]
```

### Academic Reading Lists
Organize papers by topic, method, or dataset using Obsidian's graph view and Dataview queries.

### Systematic Reviews
Track papers with consistent metadata for meta-analyses and systematic reviews.

## 🛠️ Templates

Currently includes:

- **GNN + Medical AI**: For graph neural network papers using EHR data
  - Fields: gnn-architecture, medical-application, ehr-data-type, dataset
  
- **Machine Learning (General)**: For ML papers across domains
  - Fields: ml-method, application-domain, metrics
  
- **Biology/Life Sciences**: For biological research papers
  - Fields: research-area, organism, methods, key-findings

Want to add your own template? It's easy - just modify the `templates` object in the code!

## 🔧 Customization

### Adding a Custom Template

Edit the `templates` object in the HTML file:

```javascript
const templates = {
    'your-domain': {
        name: 'Your Domain Name',
        fields: ['title', 'authors', 'year', 'custom-field-1', 'custom-field-2'],
        structure: `## Summary

## Your Custom Sections
- 

## Notes
- `
    }
};
```

### Styling

The app uses CSS variables for easy theming:

```css
:root {
    --bg-primary: #f8f6f1;
    --text-primary: #2a2420;
    --accent: #d4766f;
    /* Modify these to match your preferences */
}
```

## 🧰 Tech Stack

- **PDF.js**: Client-side PDF text extraction
- **Claude AI API**: Intelligent metadata extraction
- **Vanilla JavaScript**: No frameworks, no build step
- **Modern CSS**: Clean, responsive design

## 📝 Example Output

```markdown
---
title: "Attention Is All You Need"
authors: [Vaswani A, Shazeer N, Parmar N, Uszkoreit J, Jones L, Gomez AN, Kaiser L, Polosukhin I]
year: 2017
publication: "NeurIPS"
type: research-article
ml-method: [transformer, attention-mechanism]
application-domain: [natural-language-processing, machine-translation]
dataset: [WMT-2014]
tags: [transformers, attention, nlp, deep-learning]
read-status: to-read
---

## Summary

## Key Contributions
- 

## Methodology
- 

## Results
- 

## Notes
- 
```

## 🤝 Contributing

Contributions are welcome! Here are some ideas:

- [ ] Add more domain-specific templates
- [ ] Support for batch processing multiple PDFs
- [ ] Integration with Zotero/Mendeley
- [ ] Custom field mapping
- [ ] Export to other formats (Notion, Roam)
- [ ] Browser extension version

## 📄 License

MIT License - feel free to use this for personal or commercial projects!

## 🙏 Acknowledgments

- Built with [Claude AI](https://www.anthropic.com/claude) by Anthropic
- PDF parsing by [PDF.js](https://mozilla.github.io/pdf.js/)
- Inspired by the amazing [Obsidian](https://obsidian.md) community

## 💬 Feedback & Support

Found a bug? Have a feature request? Open an issue!

---

**Made with ❤️ for researchers everywhere**
