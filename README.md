# PDF to Obsidian Note Generator 📄→📝

A beautiful, single-file web app that extracts metadata from academic PDFs and generates ready-to-use Obsidian notes. Perfect for researchers, students, and anyone building a knowledge base.

![PDF to Obsidian](https://img.shields.io/badge/built%20with-Claude%20AI-orange)
![License](https://img.shields.io/badge/license-MIT-blue)

## ✨ Features

- **🎯 One-Click Extraction**: Drop a PDF and get structured Obsidian notes instantly
- **🤖 AI-Powered Metadata**: Uses Claude AI to intelligently extract authors, year, methods, findings, and more
- **🚀 Offline/Regex Mode**: NEW! Extract basic metadata without API calls - works completely offline
- **📋 Multiple Templates**: Pre-built templates for GNN/Medical AI, Machine Learning, Biology, and more
- **🎨 Beautiful UI**: Clean, modern interface with smooth animations
- **📦 Zero Setup**: Single HTML file - no build process, no dependencies to install
- **🔒 Privacy-Focused**: All processing happens client-side (except optional AI API calls)

## 🔄 Extraction Modes

### AI Mode (Claude API)
- **Most accurate** - AI understands context and nuance
- Extracts comprehensive metadata across all template fields
- Requires Anthropic API key
- Uses API tokens (small cost per paper)
- Best for: Building comprehensive literature databases

### Offline/Regex Mode ⚡ NEW!
- **Completely free** - no API calls, no tokens used
- Works 100% offline after page load
- Pattern-based extraction using regex
- Extracts: title, authors, year, journal, keywords, domain-specific terms
- Best for: Quick metadata extraction, batch processing, privacy-sensitive documents

**Toggle anytime** with the checkbox in the configuration panel!

### Which Mode Should I Use?

| Feature | AI Mode | Offline Mode |
|---------|---------|--------------|
| **Cost** | ~$0.01-0.02 per paper | Free |
| **Internet Required** | Yes (for API call) | No (after page load) |
| **Accuracy** | Excellent - understands context | Good - pattern matching |
| **Speed** | 2-5 seconds | Instant (<1 second) |
| **Fields Extracted** | All template fields | Basic fields + domain terms |
| **Privacy** | Sends text to Anthropic API | 100% local processing |
| **Best For** | Comprehensive metadata | Quick extraction, batch work |

**Pro Tip**: Use offline mode for initial extraction, then manually add details in Obsidian. Or use AI mode for important papers where accuracy matters!

## 🚀 Quick Start

### Prerequisites

**For AI Mode**: You'll need an Anthropic API key from [console.anthropic.com](https://console.anthropic.com/)

**For Offline Mode**: No prerequisites! Just open the file and go.

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

1. **Configure**: Either enter your API key OR check "Use Offline Mode"
2. **Upload**: Drag and drop a PDF or click to browse
3. **Extract**: PDF.js extracts text from the first 10 pages
4. **Analyze**: 
   - **AI Mode**: Claude analyzes content and extracts structured metadata
   - **Offline Mode**: Regex patterns extract basic metadata (title, authors, year, keywords)
5. **Generate**: Your Obsidian note is created with YAML frontmatter and template sections
6. **Download**: Save the `.md` file directly to your Obsidian vault

## 🔑 API Key Configuration

You have two options for configuring your Anthropic API key:

### Option A: Browser Storage (Recommended for most users)

1. Get an API key from [console.anthropic.com](https://console.anthropic.com/)
2. Open `pdf-to-obsidian.html` in your browser
3. Enter your API key in the configuration panel at the top
4. Click "Save Key"
5. Your key is stored in browser localStorage and persists across sessions

**Security**: Your key stays in your browser and is never sent anywhere except to Anthropic's API.

### Option B: Hardcode in HTML (For personal/offline use)

If you want to embed your API key directly in the HTML file:

1. Open `pdf-to-obsidian.html` in a text editor
2. Find this line (around line 570):
   ```javascript
   const HARDCODED_API_KEY = null;
   ```
3. Replace `null` with your API key:
   ```javascript
   const HARDCODED_API_KEY = 'sk-ant-api03-YOUR-KEY-HERE';
   ```
4. Save the file

**⚠️ Security Warning**: Only do this for personal use! Never commit or share a file with your API key hardcoded. See [SECURITY.md](SECURITY.md) for detailed security guidelines.

**When to use hardcoding**:
- ✅ Personal use only
- ✅ Offline/air-gapped environments
- ✅ Don't want to re-enter key each session
- ❌ Sharing the file with others
- ❌ Committing to GitHub
- ❌ Using on shared computers

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

## 🔧 Troubleshooting

### API Key Issues

**"No API key configured"**
- Make sure you've entered your API key in the configuration panel
- Or hardcode it following the instructions above
- Check that your key starts with `sk-ant-`

**"API request failed: 401"**
- Your API key is invalid or expired
- Get a new key from [console.anthropic.com](https://console.anthropic.com/)
- Make sure you copied the entire key

**"API request failed: 429"**
- You've hit rate limits
- Wait a few minutes and try again
- Check your API usage at [console.anthropic.com](https://console.anthropic.com/)

### PDF Issues

**"Error extracting PDF"**
- Make sure it's a valid PDF file
- Try a different PDF to verify the app works
- Some PDFs have security restrictions that prevent text extraction

### Other Issues

**"Metadata looks wrong"**
- The AI makes its best guess from available text
- You can manually edit the YAML frontmatter after downloading
- Consider adding more context in the PDF (clear title page helps)

**Download doesn't work**
- Try the "Copy to Clipboard" button instead
- Paste into a new file in your Obsidian vault
- Save as `.md` extension

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
