# Excel Generator Plugin (Fixed for Self-Hosted Servers)

A fixed version of the official Excel Generator plugin that correctly works with self-hosted plugin servers.

## What's Fixed

The original plugin didn't extract the `downloadUrl` from the server response correctly. This version uses the correct Handlebars template to extract the download URL and bypasses TypingMind's Cloud Sync feature.

## Features

- Multiple sheets per Excel file
- Multiple tables per sheet
- Various data types: Text, Number, Boolean, Percent, Currency, Date
- Formula support for cells
- Auto column width and filter
- Customizable designs: fonts, colors, borders

## Data Types

- **string**: Text
- **number**: Numbers
- **boolean**: True/False
- **percent**: Percent values (e.g. 50%)
- **currency**: Currency (e.g. $1,234.56)
- **date**: Date values

## Usage Example

> "Create an Excel spreadsheet with a 'Sales' sheet that has a table with columns Month, Revenue, Cost, and Profit."

## Import URL

```
https://github.com/witschas/tm-plugins-server/tree/main/excel-generator-plugin
```

## Requirements

- A plugin server must be set up
- Works with any hosting provider (Koyeb, Render, Railway, AWS, etc.)

## Notes

- Generated Excel files are automatically deleted after 1 hour
