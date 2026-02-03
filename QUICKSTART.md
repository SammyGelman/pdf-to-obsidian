# Quick Start Guide 🚀

## Two Ways to Use This Tool

### 🤖 AI Mode (Most Accurate)
Best for comprehensive metadata extraction with high accuracy.

### 🚀 Offline Mode (Fast & Free)
Best for quick extraction without API costs. Works completely offline!

---

## Getting Started - AI Mode

### Step 0: Get Your API Key
1. Go to [console.anthropic.com](https://console.anthropic.com/)
2. Sign up or log in
3. Navigate to API Keys
4. Create a new key
5. Copy it (starts with `sk-ant-`)

### Step 1: Open the App & Configure
1. Open `pdf-to-obsidian.html` in your web browser
2. Enter your API key in the configuration panel
3. Click "Save Key"

### Step 2: Upload Your PDF
- Click the drop zone or drag and drop your research paper PDF
- The app will extract text from the first 10 pages

### Step 3: Generate & Download
- Click "Generate Obsidian Note"
- Wait a few seconds while Claude AI extracts metadata
- Download the `.md` file to your Obsidian vault

That's it! 🎉

---

## Getting Started - Offline Mode

### Step 1: Open the App
Simply open `pdf-to-obsidian.html` in your web browser. No API key needed!

### Step 2: Enable Offline Mode
Check the box "🚀 Use Offline/Regex Mode" in the configuration panel.

### Step 3: Upload Your PDF
- Drag and drop your PDF or click to browse
- The app will extract text from the first 10 pages

### Step 4: Generate & Download
- Click "Generate Obsidian Note"
- Instant extraction using pattern matching
- Download the `.md` file to your Obsidian vault

That's it - completely free and offline! 🎉

---

---

## Which Mode Should I Use?

**Use AI Mode if:**
- ✅ You want the most accurate metadata extraction
- ✅ You need all template fields filled comprehensively
- ✅ You're building a serious literature database
- ✅ A few cents per paper is worth the accuracy

**Use Offline Mode if:**
- ✅ You want instant results (no waiting)
- ✅ You're processing many papers and want to save on API costs
- ✅ You need complete privacy (no data sent anywhere)
- ✅ You're offline or have unreliable internet
- ✅ You'll manually fill in details later anyway

**Pro Tip**: You can switch between modes anytime! Try offline mode first, then use AI mode for papers that need more detail.

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

### "No API key configured"
- Make sure you entered your Anthropic API key in the configuration panel
- The key should start with `sk-ant-`
- Click "Save Key" after entering it

### "API request failed"
- Your API key might be invalid - get a new one from console.anthropic.com
- You might have hit rate limits - wait a few minutes
- Check your internet connection

### Want to hardcode your key?
Click the "Want to hardcode your key?" button in the configuration panel for detailed instructions. This is great for personal use!

### Offline Mode Issues

**"Generate button is disabled"**
- Make sure you've uploaded a PDF file
- If in AI mode, you need an API key configured
- If in Offline mode, the button should enable automatically after upload

**"Metadata is incomplete in offline mode"**
- This is normal! Offline mode extracts basic fields using patterns
- You can manually add missing information in Obsidian
- Or switch to AI mode for that specific paper

**"Results are better/worse than expected"**
- Offline mode works best with well-formatted academic PDFs
- PDFs with clear title pages, author lists, and keywords sections work best
- Scanned PDFs or unusual formats may have less accurate extraction

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
