# TypingMind Plugin Export Collection

Diese Dateien enthalten alle 5 Plugins als exportierbare JSON-Dateien für TypingMind.

## 📦 Verfügbare Plugins

1. **word-generator-plugin.json** - Word Dokument Generator (Fix für Self-Hosted)
2. **excel-generator-plugin.json** - Excel Tabellen Generator (Fix für Self-Hosted)
3. **powerpoint-generator-plugin.json** - PowerPoint Präsentation Generator (Fix für Self-Hosted)
4. **youtube-transcript-plugin.json** - YouTube Transkript Abfrage
5. **web-page-reader-plugin.json** - Webseiten Inhaltsleser

## 🚀 So importierst du die Plugins

### Methode 1: Import über TypingMind UI

1. Öffne TypingMind
2. Klicke auf **"Plugins"**
3. Klicke auf **"Import plugins"**
4. Wähle **"Import plugin from JSON"**
5. Kopiere den **kompletten Inhalt** einer der `.json` Dateien
6. Füge den JSON-Code ein
7. Klicke auf **"Import"**
8. Konfiguriere den **Plugin Server** (deine Koyeb/Render/Railway URL)
9. Speichere das Plugin

Wiederhole dies für alle 5 Plugins die du nutzen möchtest.

### Methode 2: Direkter Datei-Import

Wenn TypingMind den Import von Dateien unterstützt:

1. Öffne TypingMind
2. Klicke auf **"Plugins"** → **"Import plugins"**
3. Wähle **"Import plugin from JSON"**
4. Lade die entsprechende `.json` Datei hoch
5. Konfiguriere und speichere

## ⚙️ Plugin Server Konfiguration

Nach dem Import musst du den **Plugin Server** in den Plugin-Einstellungen konfigurieren:

- **Plugin Server URL**: Deine self-hosted Server URL (z.B. `https://your-app.koyeb.app`)
- Diese URL ist für alle 5 Plugins identisch

## 🔧 Was wurde "fixiert"?

Die 3 Generator-Plugins (Word, Excel, PowerPoint) wurden modifiziert um mit **self-hosted Plugin Servern** zu funktionieren:

- **Problem**: Das originale Plugin extrahierte die `downloadUrl` nicht korrekt
- **Lösung**: Verwendung von Handlebars-Templates zur korrekten Extraktion
- **Ergebnis**: Direkte Download-Links funktionieren jetzt mit Koyeb, Render, Railway, etc.

## 📝 Hinweise

- Alle Plugins benötigen einen **laufenden Plugin Server** (Backend)
- Der Server Code befindet sich im `/src` Verzeichnis dieses Repositories
- Generierte Dateien werden nach **1 Stunde** automatisch gelöscht
- Die Plugins funktionieren mit **jedem** Hosting-Provider

## 🌐 Repository

- **GitHub**: https://github.com/witschas/tm-plugins-server
- **Backend Server**: Siehe `/src` Verzeichnis für Server-Code

---

**Viel Erfolg! 🎉**
