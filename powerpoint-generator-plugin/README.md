# PowerPoint Generator Plugin (Fixed for Self-Hosted Servers)

A fixed version of the official PowerPoint Generator plugin that correctly works with self-hosted plugin servers.

## What's Fixed

The original plugin didn't extract the `downloadUrl` from the server response correctly. This version uses the correct Handlebars template to extract the download URL and bypasses TypingMind's Cloud Sync feature.

## Features

- **4 Slide Types**: Title slide, Content slide, Table slide, Chart slide
- **4 Chart Types**: Pie, Bar, Line, Doughnut
- **Customizable Designs**: Font families, colors, layouts
- **Footers and Slide Numbers**: Optional
- **Table Borders**: Customizable borders and colors

## Usage Example

> "Create a presentation about climate change with 5 slides: title slide, introduction, main causes, effects, and solutions."

## Import URL

```
https://github.com/witschas/tm-plugins-server/tree/main/powerpoint-generator-plugin
```

## Requirements

- A plugin server must be set up
- Works with any hosting provider (Koyeb, Render, Railway, AWS, etc.)

## Notes

- Generated PowerPoint files are automatically deleted after 1 hour
