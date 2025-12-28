# Notion Database Manager Plugin for TypingMind

Manage your Notion databases and pages directly from TypingMind.

## Features

### 1. View Structure

- View the structure of a Notion database
- List all properties and their types

### 2. Create Page

- Create a new page in a database
- Supports all Notion property types

### 3. Update Page

- Update properties of an existing page

### 4. Archive Page

- Archive (delete) a page

### 5. Query Database

- Search and filter pages in a database
- Supports sorting and pagination

### 6. Create Database

- Create a new Notion database

## Setup

1. Go to https://www.notion.so/profile/integrations
2. Create a new integration
3. Copy the "Internal Integration Token"
4. Add your database to the integration (click "..." → "Add connections")
5. Enter the API key in the plugin settings

## Usage Example

> "Show me the structure of my Notion database with ID abc123"

## Import URL

```
https://github.com/witschas/tm-plugins-server/tree/main/notion-database-plugin
```

## Requirements

- A plugin server must be set up
- Notion API key from https://www.notion.so/profile/integrations
- The integration must have access to the relevant databases
