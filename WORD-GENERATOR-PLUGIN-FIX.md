# Word Generator Plugin - Fixed for Self-Hosted Servers

This is a **fixed version** of the official TypingMind Word Generator plugin that correctly works with self-hosted plugin servers (Koyeb, Render, Railway, etc.).

## 🐛 What Was Fixed

The original official plugin had a bug where it didn't extract the `downloadUrl` from the server response. This caused the plugin to fail with self-hosted servers, showing errors like:

```
<Error>
<Code>NoSuchBucket</Code>
<Message>The specified bucket does not exist</Message>
</Error>
```

**The Fix:** Added the correct JMESPath expression to extract the download URL:

```json
"resultTransform": {
    "engine": "jmes",
    "expression": "responseObject.downloadUrl"
},
"hasResultTransform": true
```

## 📦 File Location

The fixed plugin is located at:

```
word-generator-plugin-fixed.json
```

## 🚀 How to Import into TypingMind

### Step 1: Open TypingMind Settings

1. Open TypingMind
2. Click on **Settings** (gear icon)
3. Navigate to **Plugins**

### Step 2: Deactivate the Original Plugin

1. Find **"Word Generator"** (the official one)
2. **Toggle it OFF** to disable it

### Step 3: Import the Fixed Plugin

1. Click the **"+"** button or **"Import Plugin"**
2. Select **"Import from JSON"**
3. Choose the file: `word-generator-plugin-fixed.json`
4. Click **"Import"**

### Step 4: Configure the Plugin

1. Find **"Word Generator (Fixed for Self-Hosted)"** in the plugin list
2. Click on it to open settings
3. Under **"Plugin Server"**, enter your server URL:
   ```
   https://normal-angela-rwits-183be028.koyeb.app
   ```
4. Configure other settings as desired (font size, margins, etc.)
5. Click **"Save"**

### Step 5: Test the Plugin

1. Start a new chat in TypingMind
2. Type a prompt like:
   > "Create a Word document with a title 'Test Document' and one paragraph saying 'This is a test.'"
3. Wait for the response
4. Click on the download link
5. ✅ The Word file should download successfully!

## 🔧 Technical Details

### Original Plugin (Broken)

```json
"resultTransform": {
    "engine": "jmes",
    "expression": ""  // ⚠️ EMPTY - doesn't extract downloadUrl
},
"hasResultTransform": false
```

### Fixed Plugin

```json
"resultTransform": {
    "engine": "jmes",
    "expression": "responseObject.downloadUrl"  // ✅ Correctly extracts URL
},
"hasResultTransform": true
```

### Server Response Format

The plugin server responds with:

```json
{
  "success": true,
  "message": "File generated successfully",
  "responseObject": {
    "downloadUrl": "https://your-server.com/word-generator/downloads/file.docx"
  }
}
```

The JMESPath expression `responseObject.downloadUrl` extracts:

```
https://your-server.com/word-generator/downloads/file.docx
```

## ✅ Compatibility

This fixed plugin works with:

- ✅ **Koyeb** (tested)
- ✅ **Render** (should work)
- ✅ **Railway** (should work)
- ✅ **AWS** (should work)
- ✅ **Any self-hosted server** following the TypingMind plugins-server API

## 📝 Notes

- This is a **modified version** of the official plugin from:
  https://github.com/TypingMind/plugin-word-generator
- The fix only changes the `resultTransform` logic
- All other functionality remains the same
- Generated files are automatically deleted after 1 hour

## 🤝 Credits

Based on the official Word Generator plugin by TypingMind.
Fixed for self-hosted server compatibility.

## 📄 License

Same as the original plugin (MIT License)
