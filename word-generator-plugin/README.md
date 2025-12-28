# Word Generator Plugin (Fixed for Self-Hosted Servers)

A fixed version of the official Word Generator plugin that correctly works with self-hosted plugin servers.

## What's Fixed

The original plugin didn't extract the `downloadUrl` from the server response correctly. This version uses the correct Handlebars template to extract the download URL and bypasses TypingMind's Cloud Sync feature.

## Features

- Hierarchical sections with headings
- Tables with formatting
- Lists with bullet points
- Header, footer, page numbers
- Table of contents (optional)
- Customizable margins, fonts, line heights

## Usage Example

> "Create a business plan for a new café."

## Import URL

```
https://github.com/witschas/tm-plugins-server/tree/main/word-generator-plugin
```

## Requirements

- A plugin server must be set up
- Works with any hosting provider (Koyeb, Render, Railway, AWS, etc.)

## Notes

- Generated Word files are automatically deleted after 1 hour
- Does not support embedding images in Word documents
