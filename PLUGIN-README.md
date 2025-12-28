# Word Generator Plugin (Fixed for Self-Hosted Servers)

## Overview

This is a **fixed version** of the official TypingMind Word Generator plugin that correctly works with self-hosted plugin servers.

## What's Fixed

The original plugin had a bug where it didn't extract the `downloadUrl` from the server response, causing download failures with self-hosted servers (Koyeb, Render, Railway, etc.).

**The Fix:** Added the correct JMESPath expression to extract the download URL.

## How to Import into TypingMind

1. **Open TypingMind**
2. **Go to Settings → Plugins**
3. **Click "Import plugins"**
4. **Paste this GitHub repository URL:**
   ```
   https://github.com/witschas/tm-plugins-server
   ```
5. **Click "Import"**
6. **Configure the plugin:**
   - Find "Word Generator (Fixed for Self-Hosted)" in the plugin list
   - Set "Plugin Server" to your server URL (e.g., `https://your-app.koyeb.app`)
   - Save and test!

## Compatibility

✅ Works with any hosting provider:

- Koyeb (tested)
- Render
- Railway
- AWS
- Self-hosted servers

## Credits

Based on the official Word Generator plugin by TypingMind.
Fixed for self-hosted server compatibility.
