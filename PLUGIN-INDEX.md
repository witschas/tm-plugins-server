# TypingMind Plugin Server - Alle Plugins

Dieses Repository enthält **6 Plugins** für TypingMind, die alle auf einem selbst gehosteten Plugin-Server laufen.

## 🚀 Installation

### Alle Plugins auf einmal importieren:

1. **Öffne TypingMind**
2. **Gehe zu Settings → Plugins**
3. **Klicke "Import Plugin"**
4. **Gib diese GitHub Repository URL ein:**
   ```
   https://github.com/witschas/tm-plugins-server
   ```
5. **Klicke "Import"**
6. **Du siehst nun alle 6 Plugins** in der Liste
7. **Konfiguriere jedes Plugin:**
   - Setze "Plugin Server" auf deine Server URL:
     ```
     https://emotional-sarette-typemind-69b54507.koyeb.app/
     ```
   - Gib zusätzliche Einstellungen ein (falls erforderlich)
8. **Aktiviere die Plugins** die du verwenden möchtest

---

## 📦 Verfügbare Plugins

### 1. 📹 YouTube Transcript

**Datei:** `youtube-transcript-plugin.json`

**Funktion:** Ruft Transkripte (Untertitel) von YouTube-Videos ab.

**Verwendung:**

> "Kannst du das Transkript des Videos https://www.youtube.com/watch?v=XYZ abrufen?"

**Endpunkt:** `GET /youtube-transcript/get-transcript`

---

### 2. 📄 Web Page Reader

**Datei:** `web-page-reader-plugin.json`

**Funktion:** Liest den Inhalt von Webseiten aus und extrahiert den Text.

**Verwendung:**

> "Lies den Artikel unter https://example.com/article und fasse ihn zusammen."

**Endpunkt:** `GET /web-page-reader/get-content`

---

### 3. 📊 PowerPoint Generator (Fixed)

**Datei:** `powerpoint-generator-plugin-fixed.json`

**Funktion:** Erstellt PowerPoint-Präsentationen mit verschiedenen Folientypen, Diagrammen und Tabellen.

**Features:**

- 4 Folientypen: Titelfolie, Inhaltsfolie, Tabellenfolie, Diagrammfolie
- 4 Diagrammtypen: Kreis, Balken, Linie, Ring
- Anpassbare Designs: Schriftarten, Farben, Layouts
- Fußzeilen und Foliennummern optional

**Verwendung:**

> "Erstelle eine Präsentation über Klimawandel mit 5 Folien."

**Endpunkt:** `POST /powerpoint-generator/generate`

**Fix:** Verwende Handlebars-Template für Cloud Sync Bypass.

---

### 4. 📝 Word Generator (Fixed)

**Datei:** `plugin.json` (Hauptdatei im Repository)

**Funktion:** Erstellt Word-Dokumente mit Abschnitten, Tabellen, Listen, Seitenzahlen und Inhaltsverzeichnis.

**Features:**

- Hierarchische Abschnitte mit Überschriften
- Tabellen mit Formatierung
- Listen mit Aufzählungszeichen
- Header, Footer, Seitenzahlen
- Inhaltsverzeichnis optional
- Anpassbare Ränder, Schriftarten, Zeilenabstände

**Verwendung:**

> "Erstelle einen Geschäftsplan für ein neues Café."

**Endpunkt:** `POST /word-generator/generate`

**Fix:** Verwende Handlebars-Template für Cloud Sync Bypass.

---

### 5. 📈 Excel Generator (Fixed)

**Datei:** `excel-generator-plugin-fixed.json`

**Funktion:** Erstellt Excel-Tabellen mit mehreren Blättern, Tabellen und Formeln.

**Features:**

- Mehrere Tabellenblätter pro Datei
- Verschiedene Datentypen: Text, Zahl, Währung, Prozent, Datum
- Formel-Unterstützung
- Automatische Spaltenbreite und Filter
- Anpassbare Rahmen und Farben

**Verwendung:**

> "Erstelle eine Excel-Tabelle mit Umsatzdaten für Q1-Q4."

**Endpunkt:** `POST /excel-generator/generate`

**Fix:** Verwende Handlebars-Template für Cloud Sync Bypass.

---

### 6. 📊 Notion Database Manager

**Datei:** `notion-database-plugin.json`

**Funktion:** Verwaltet Notion-Datenbanken und -Seiten direkt aus TypingMind.

**Features:**

- Struktur von Datenbanken anzeigen
- Seiten erstellen, aktualisieren, archivieren
- Datenbanken abfragen (mit Filter und Sortierung)
- Neue Datenbanken erstellen

**Vorbereitung:**

1. Gehe zu https://www.notion.so/profile/integrations
2. Erstelle eine neue Integration
3. Kopiere den API-Schlüssel
4. Füge deine Datenbank zur Integration hinzu

**Verwendung:**

> "Zeige mir die Struktur meiner Notion-Datenbank mit der ID abc123"

**Endpunkte:**

- `POST /notion-database/view-structure`
- `POST /notion-database/create-page`
- `PATCH /notion-database/update-page`
- `PATCH /notion-database/archive-page`
- `POST /notion-database/query-pages`
- `POST /notion-database/create-database`

---

## 🔧 Server-Konfiguration

### Erforderliche Umgebungsvariable:

```bash
SERVER_URL=https://emotional-sarette-typemind-69b54507.koyeb.app/
```

Diese Umgebungsvariable muss auf deinem Plugin-Server gesetzt sein, damit die Download-URLs korrekt generiert werden.

### Für verschiedene Hosting-Plattformen:

- **Koyeb:** Setze `SERVER_URL` manuell in den Umgebungsvariablen
- **Render:** Wird automatisch als `RENDER_EXTERNAL_URL` gesetzt
- **Railway:** Setze `SERVER_URL` manuell
- **AWS/Andere:** Setze `SERVER_URL` manuell

---

## ⚠️ Wichtige Hinweise

### Cloud Sync Bypass

Die Generator-Plugins (Word, PowerPoint, Excel) verwenden ein spezielles **Handlebars-Template** als `resultTransform`, um TypingMinds Cloud Sync Funktion zu umgehen:

```json
"resultTransform": {
  "engine": "handlebars",
  "templateString": "[Download Word Document]({{responseObject.downloadUrl}})"
}
```

Dies stellt sicher, dass die Download-Links korrekt angezeigt werden und nicht durch Cloud Sync abgefangen werden.

### Datei-Aufbewahrung

Alle generierten Dateien werden **automatisch nach 1 Stunde gelöscht**.

### API-Endpunkte

Der Plugin-Server stellt folgende Endpunkte bereit:

- `GET /health-check` - Gesundheitscheck
- `GET /youtube-transcript/get-transcript` - YouTube Transkript
- `GET /web-page-reader/get-content` - Webseiten-Content
- `POST /powerpoint-generator/generate` - PowerPoint erstellen
- `POST /word-generator/generate` - Word erstellen
- `POST /excel-generator/generate` - Excel erstellen
- `POST /notion-database/view-structure` - Notion DB Struktur
- `POST /notion-database/create-page` - Notion Seite erstellen
- `PATCH /notion-database/update-page` - Notion Seite aktualisieren
- `PATCH /notion-database/archive-page` - Notion Seite archivieren
- `POST /notion-database/query-pages` - Notion DB abfragen
- `POST /notion-database/create-database` - Notion DB erstellen

---

## 🤝 Credits

Dieses Repository ist ein Fork von TypingMinds offiziellem `plugins-server` Repository.

**Original:** https://github.com/travis-thuanle/typingmind-proxy

**Modifikationen:**

- Cloud Sync Bypass für Generator-Plugins
- Alle Plugins als separate plugin.json Dateien
- Deutsche Beschreibungen und Dokumentation
- PLUGIN-INDEX.md für schnelle Übersicht

---

## 📄 Lizenz

Gleich wie das Original-Repository (MIT License).
