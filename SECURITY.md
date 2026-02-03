# Security & Privacy Guide 🔒

## Your API Key

Your Anthropic API key is a sensitive credential that should be protected. This guide explains how the app handles your key and best practices for keeping it secure.

## How the App Handles Your Key

### Browser Storage Method
When you enter your API key in the configuration panel:
- It's stored in your browser's `localStorage`
- It never leaves your computer except to make API calls to Anthropic
- It persists between sessions (you don't need to re-enter it)
- It's specific to your browser and device

**What this means**:
- ✅ Your key stays private
- ✅ Convenient - no need to re-enter
- ✅ No server-side storage
- ⚠️ Anyone with access to your browser can see it
- ⚠️ Clearing browser data will delete it

### Hardcoded Method
When you hardcode your key directly in the HTML:
- It's embedded in the file itself
- The file can work completely offline
- Very convenient for personal use

**What this means**:
- ✅ Works offline
- ✅ Never need to configure
- ⚠️ Anyone with the file has your key
- ⚠️ Easy to accidentally share or commit

## Best Practices

### ✅ DO:

1. **Get your API key from the official source**
   - Only from [console.anthropic.com](https://console.anthropic.com/)
   - Never use keys from third parties

2. **Use browser storage for normal use**
   - Easiest and reasonably secure
   - Good for personal computers

3. **Hardcode only for personal, isolated use**
   - Air-gapped systems
   - Personal offline archive
   - When you're the only user

4. **Monitor your API usage**
   - Check [console.anthropic.com](https://console.anthropic.com/) regularly
   - Set up usage alerts if available
   - Rotate keys periodically

5. **Use a separate key for this tool**
   - Don't use your production API key
   - Makes it easier to revoke if needed

### ❌ DON'T:

1. **Never commit your API key to Git**
   ```bash
   # If you hardcoded your key, DON'T do this:
   git add pdf-to-obsidian.html
   git commit -m "Added my key"  # ❌ NEVER!
   ```

2. **Don't share files with hardcoded keys**
   - Don't email the HTML file with your key
   - Don't upload to file sharing services
   - Don't send via messaging apps

3. **Don't use on shared/public computers**
   - Library computers
   - Internet cafes
   - Shared workstations
   - Your key could be accessed by others

4. **Don't post screenshots with visible keys**
   - Mask your key in screenshots
   - Be careful of screen sharing

## If Your Key is Compromised

If you think your API key has been exposed:

1. **Immediately revoke it**
   - Go to [console.anthropic.com](https://console.anthropic.com/)
   - Delete the compromised key

2. **Create a new key**
   - Generate a new API key
   - Update it in the app

3. **Check your usage**
   - Review API usage for unauthorized calls
   - Contact Anthropic support if needed

## Data Privacy

### What data is sent to Anthropic:
- Extracted text from your PDFs (first 10 pages)
- Your prompts and instructions
- This is necessary for the AI to generate metadata

### What data is NOT sent:
- Your full PDF files
- Your API key (except in headers for authentication)
- Your personal information
- Your Obsidian vault contents

### PDF Processing:
- PDFs are processed entirely in your browser
- Only text is extracted and sent to the API
- Original PDFs never leave your device

## Open Source Security

This tool is open source, which means:
- ✅ You can review all the code
- ✅ You can verify what it does with your data
- ✅ Community can audit for security issues
- ✅ You can modify it for your needs

## Local Modifications for Maximum Security

If you want maximum security, you can:

1. **Run completely offline** (after hardcoding key)
   - No external connections except to Anthropic API
   - All PDF processing is local

2. **Modify the code to restrict data**
   - Reduce text sent to API
   - Add additional encryption
   - Implement logging

3. **Self-host** (advanced)
   - Put it on your own server
   - Control all aspects of deployment

## Questions?

If you have security concerns or questions:
- Open an issue on GitHub
- Review the source code yourself
- Contact Anthropic about API security

---

**Remember**: This tool is provided as-is. You are responsible for protecting your API keys and data. Always follow security best practices and use good judgment when handling sensitive information.
