# FileHub Getting Started

**Find any file in seconds — across all your devices**

## Overview

FileHub is a cross-platform file search solution that lets you search and preview files across your private cloud instantly. No uploading to the cloud, no waiting for search results.

## Download & Install

Choose your platform:

### 🖥️ Windows Desktop App
The full native experience with system tray background running.

**Requirements:**
- Windows/MacOs/Linux
- WebView2 Runtime (usually pre-installed on Windows 11)

[Download from GitHub Releases →](https://github.com/filehub1/filehub-desktop/releases)

---

### 📱 Android App
Transform your Android device into a file search server.

**Requirements:**
- Android 8.0+ (API 26+)

[Download APK →](https://github.com/filehub1/android/releases)

---

### 🐳 Docker Server
Deploy on NAS, Raspberry Pi, or any server.

```bash
docker run -d -p 6543:6543 -v /your/data:/data exiahuang/filehub-server:latest
```

[Learn more →](/docs/filehub-docker.md)

---

### 📦 npm Package
Install as a global command line tool.

```bash
npm install -g @exiahuang/filehub
filehub-server
```

[Learn more →](https://www.npmjs.com/package/@exiahuang/filehub)

---

## Quick Usage Guide

### 1. Configure Index Directories

Add the folders you want to search:

```yaml
# ~/.filehub
indexedDirectories:
  - /path/to/your/documents
  - /path/to/your/projects
```

### 2. Start Searching

- Press `/` to focus the search box
- Type your query
- Results appear instantly
- Use `j`/`k` or arrow keys to navigate
- Press `Enter` to open, `o` to preview

### 3. Search Modes

| Mode | Description |
|------|-------------|
| **String** | Exact substring match (default) |
| **Fuzzy** | Match similar filenames |
| **Regex** | Regular expression search |

Press `\` to switch between modes.

### 4. Access from Other Devices

Enable LAN access in settings, then:
- Scan the QR code shown in the app
- Or enter the displayed URL in any browser on the same network

## Keyboard Shortcuts

| Key | Action |
|-----|--------|
| `/` | Focus search |
| `j` / `↓` | Move down |
| `k` / `↑` | Move up |
| `Enter` / `l` | Open file |
| `o` | Toggle preview panel |
| `O` | Open in system file explorer |
| `\` | Switch search mode |
| `r` | Rebuild search index |
| `s` | Open settings |
| `?` | Show help |

## Troubleshooting

### Files not showing in search
- Check if the directory is added to `indexedDirectories`
- Press `r` to rebuild the index
- Verify file permissions

### Can't access from other devices
- Ensure devices are on the same network
- Check if firewall allows port 6543
- Enable LAN access in settings

### Search is slow
- Use SSD for better indexing performance
- Exclude unnecessary folders (node_modules, .git)
- Consider using admin mode on Windows (faster MFT indexing)

## Next Steps

- [Configure FileHub →](/docs/filehub-config.md)
- [Use REST API →](/docs/filehub-api.md)
- [Keyboard Shortcuts Reference →](/docs/filehub-shortcuts.md)

## Support

- [Report Issues](https://github.com/filehub1/filehub-server/issues)
- [Discussions](https://github.com/filehub1/filehub-server/discussions)
