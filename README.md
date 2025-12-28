<h2 align="center">
  <img height="150" alt="Typing Mind - A better UI for ChatGPT" src="https://www.typingmind.com/banner.png" />
<br/>
Plugins Server
</h2>

[![Docker Image CI](https://github.com/TypingMind/plugins-server/actions/workflows/docker-image.yml/badge.svg?branch=main)](https://github.com/TypingMind/plugins-server/actions/workflows/docker-image.yml)
[![CodeQL](https://github.com/TypingMind/plugins-server/actions/workflows/codeql.yml/badge.svg)](https://github.com/TypingMind/plugins-server/actions/workflows/codeql.yml)
[![Build TypingMind Proxy](https://github.com/TypingMind/plugins-server/actions/workflows/test.yml/badge.svg)](https://github.com/TypingMind/plugins-server/actions/workflows/test.yml)

## 🌟 Introduction

Plugins Server provides additional features for [TypingMind's Plugins](https://docs.typingmind.com/plugins) where extra server-side processing is needed.

Plugins Server is used by some built-in plugins on Typing Mind (e.g., Web Page Reader). Other plugins can also make use of the existing endpoints of the Plugins Server if needed. New endpoints can be added via Pull Requests.

Plugins Server is open-sourced and is intended to be self-hosted by individual users for private use only.

**Note**: The Plugins Server only provides an endpoint for retrieving server-side processing results. To make the plugin work, you must also install a TypingMind's plugin configured to send requests to this server endpoint.

## 🔌 How to use (for Typing Mind users)

Two simple steps:

1. Deploy this repo on any hosting provider that supports NodeJS (e.g., Render.com, AWS, etc.). (We also provide a Dockerfile for easy deployment on Docker-supported hosting providers).

2. Install your desired TypingMind's plugin. Update the server endpoint URL in your Settings page.

Follow this guide for detailed instructions: [How to Deploy Plugins Server on Render.com](https://docs.typingmind.com/plugins/plugins-server/how-to-deploy-plugins-server-on-render)

Follow this guide for setting up a TypingMind's plugin: [Build a TypingMind Plugin](https://docs.typingmind.com/plugins/build-a-typingmind-plugin)

## List of available endpoints

After deploying, visit your Plugins Server URL to see the list of available endpoints (served in Swagger UI).

## 📦 Available Plugins

This repository includes **5 fixed plugins** for TypingMind that work correctly with self-hosted servers:

### 1. **Word Generator** (Fixed)

- Generate Word documents with sections, tables, lists, and formatting
- **Fixed**: Correctly extracts download URLs from self-hosted servers
- [→ Details](word-generator-plugin/README.md)

### 2. **Excel Generator** (Fixed)

- Create Excel spreadsheets with multiple sheets, tables, and formulas
- **Fixed**: Works with Koyeb, Render, Railway, and other providers
- [→ Details](excel-generator-plugin/README.md)

### 3. **PowerPoint Generator** (Fixed)

- Generate PowerPoint presentations with various slide types
- **Fixed**: Bypasses TypingMind Cloud Sync for direct downloads
- [→ Details](powerpoint-generator-plugin/README.md)

### 4. **YouTube Transcript**

- Fetch transcripts/subtitles from YouTube videos
- [→ Details](youtube-transcript-plugin/README.md)

### 5. **Web Page Reader**

- Extract readable text content from web pages
- [→ Details](web-page-reader-plugin/README.md)

---

## 🚀 Quick Start: Import Plugins

### Option A: Import via JSON (Recommended)

1. Go to the **[plugin-exports/](plugin-exports/)** directory
2. Open any `.json` file (e.g., `word-generator-plugin.json`)
3. In TypingMind: **Plugins** → **Import plugins** → **Import plugin from JSON**
4. Copy the entire JSON file content and paste it
5. Configure your Plugin Server URL
6. Save and enjoy!

**📖 Detailed Instructions**: See [plugin-exports/README.md](plugin-exports/README.md) or [plugin-exports/IMPORT_ANLEITUNG.md](plugin-exports/IMPORT_ANLEITUNG.md)

### Option B: Manual Configuration

Each plugin subdirectory contains:

- `plugin.json` - Plugin configuration
- `README.md` - Usage instructions

You can manually create plugins in TypingMind by copying the configuration from these files.

---

## 🔧 What Was Fixed?

The original official plugins didn't extract the `downloadUrl` correctly from server responses when using self-hosted servers (non-TypingMind Cloud).

**Our Fix**: Used Handlebars templates to extract download URLs and bypass Cloud Sync, enabling direct downloads from your own server.

---

## ⚠️ Important Notes

- **Generated files are automatically deleted after 1 hour**
- **Plugin Server URL must be configured** for each plugin
- **Works with any hosting provider** (Koyeb, Render, Railway, AWS, etc.)
- **No images in Word documents** (current limitation)

---

## 🛠️ Development (for Typing Mind plugins developers)

- **Development Mode:** To start the project in development mode, execute the following command in your terminal:

```bash
npm install
npm run dev
```

## 🤝 Contributing

We welcome your contributions! Help expand TypingMind Plugins Server's capabilities.

- **Plugin Development:** Check out our 'CONTRIBUTING.md' guide for details on creating plugins.
- **Bug Reports & Ideas:** Open issues to report bugs or suggest new features.
- **Documentation:** Help improve our documentation for other developers.
