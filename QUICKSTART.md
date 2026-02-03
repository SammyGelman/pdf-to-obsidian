# Quick Start Guide 🚀

## Getting Started in 3 Steps

### Step 1: Open the App
Simply open `pdf-to-obsidian.html` in your web browser. No installation needed!

### Step 2: Upload Your PDF
- Click the drop zone or drag and drop your research paper PDF
- The app will extract text from the first 10 pages

### Step 3: Generate & Download
- Click "Generate Obsidian Note"
- Wait a few seconds while Claude AI extracts metadata
- Download the `.md` file to your Obsidian vault

That's it! 🎉

---

## Tips for Best Results

### 📄 PDF Quality
- Works best with text-based PDFs (not scanned images)
- The first few pages should contain title, authors, abstract
- Files under 10MB work best

### 🎯 Template Selection
Choose the template that matches your research domain:
- **GNN + Medical AI**: For machine learning papers focused on healthcare
- **Machine Learning**: For general ML/AI papers
- **Biology**: For life sciences research
- **Custom**: Build your own!

### 📝 Using in Obsidian

After downloading your note:

1. **Save to your vault**
   ```
   YourVault/Literature/paper-name.md
   ```

2. **Use Dataview to query**
   ```dataview
   TABLE authors, year, gnn-architecture
   FROM "Literature"
   WHERE type = "research-article"
   SORT year DESC
   ```

3. **Visualize in graph view**
   - Tags and links create beautiful knowledge graphs
   - Filter by metadata fields

### 🔄 Batch Processing
For multiple papers:
1. Process one paper at a time
2. Download each note
3. Organize in your vault folders

---

## Troubleshooting

### "Error extracting PDF"
- Make sure it's a valid PDF file
- Try a different PDF to verify the app works
- Some PDFs have security restrictions that prevent text extraction

### "API request failed"
- The Claude API might be temporarily unavailable
- Check your internet connection
- Try again in a few moments

### Metadata looks wrong
- The AI makes its best guess from available text
- You can manually edit the YAML frontmatter after downloading
- Consider adding more context in the PDF (clear title page helps)

### Download doesn't work
- Try the "Copy to Clipboard" button instead
- Paste into a new file in your Obsidian vault
- Save as `.md` extension

---

## Example Workflow

Here's a complete workflow for a literature review:

1. **Collect PDFs** from your searches
2. **Process each PDF** through the app
3. **Download to** `Vault/Literature/`
4. **Create an MOC** (Map of Content) note:
   ```markdown
   # GNN Medical AI Literature Review
   
   ## Papers by Year
   ```dataview
   TABLE authors, gnn-architecture, dataset
   FROM "Literature"
   WHERE contains(tags, "gnn")
   SORT year DESC
   ```
   ```

5. **Write summaries** in each note
6. **Link related papers** using `[[wiki-links]]`
7. **Explore in graph view** to find connections

---

## Need Help?

- Check the [README](README.md) for full documentation
- Open an issue on GitHub
- Read [CONTRIBUTING](CONTRIBUTING.md) to help improve the tool

Happy researching! 📚✨
