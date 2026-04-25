# filehub-desktop

**Native desktop app for Windows, macOS, and Linux**

A desktop application that brings FileHub's powerful search and preview capabilities directly to your desktop across Windows, macOS, and Linux. Runs in the background with system tray support.

## Features

- ⚡ **Instant Search** — Trie-based indexing for sub-millisecond results
- 👀 **File Preview** — PDF, images, video, Office docs, code
- 🖥️ **System Tray** — Runs silently in the background
- 🌐 **LAN Access** — Share your file index with other devices
- ⌨️ **Keyboard First** — Full keyboard navigation support
- 🎨 **Dark/Light Theme** — Comfortable in any lighting

## Download

[![GitHub Release](https://img.shields.io/github/v/release/filehub1/filehub-desktop?include_prereleases&label=release)](https://github.com/filehub1/filehub-desktop/releases/latest)
[![Downloads](https://img.shields.io/github/downloads/filehub1/filehub-desktop/total)](https://github.com/filehub1/filehub-desktop/releases/latest)

**Requirements:**
- Windows 10 / 11
- .NET 10 Runtime (or use self-contained build)
- Microsoft Edge WebView2 Runtime (usually pre-installed)

[Download from GitHub Releases →](https://github.com/filehub1/filehub-desktop/releases)

## Installation

1. Download the latest `filehub-desktop-*.zip` from Releases
2. Extract to a folder of your choice
3. Run `filehub.exe`

That's it! No installation wizard needed.

## Quick Start

1. **Configure Directories**
   
   Edit `~/.filehub`:
   ```yaml
   indexedDirectories:
     - C:\Users\YourName\Documents
     - D:\Projects
   ```

2. **Start Using**
   
   - Press `/` to focus search
   - Type to search instantly
   - Press `Enter` to open files
   - Press `o` for preview

## System Tray

FileHub minimizes to the system tray, running quietly in the background.

**Tray Menu:**
- **Open** — Show the main window
- **Rebuild Index** — Refresh the file index
- **Exit** — Quit the application

**Tray Features:**
- Double-click tray icon to open
- Shows indexing status on hover
- Right-click for menu options

## Keyboard Shortcuts

| Key | Action |
|-----|--------|
| `/` | Focus search |
| `j` / `↓` | Move down |
| `k` / `↑` | Move up |
| `Enter` / `l` | Open file |
| `o` | Toggle preview |
| `O` | Open in File Explorer |
| `!` | Open terminal at file location |
| `\` | Switch search mode |
| `r` | Rebuild index |
| `s` | Settings |
| `?` | Help |
| `q` / `Esc` | Minimize to tray |

## Configuration

FileHub reads `~/.filehub` (YAML) on startup:

```yaml
indexedDirectories:
  - C:\Users\YourName\Documents
  - D:\Projects
serviceAddress: 0.0.0.0:6543
excludePatterns:
  - node_modules
  - .git
  - dist
  - "*.log"
useAdminMode: false  # Enable for faster MFT indexing
theme: dark          # dark or light
```

## Build from Source

**Prerequisites:**
- .NET 10 SDK
- Node.js 18+ and npm 9+

**Steps:**
```powershell
git clone https://github.com/filehub1/filehub-desktop.git
cd filehub-desktop

# Build the web frontend first
cd ../filehub-server
npm install
npm run build

# Build the Windows app
cd ../filehub-desktop
dotnet build

# Output: bin/Debug/net10.0-windows/filehub.exe
```

**Build Release (Self-contained):**
```powershell
powershell -File scratch/build-release.ps1
```

## Related

- [FileHub Server](/docs/filehub-docker.md) — Docker deployment
- [Android App](https://github.com/filehub1/android) — Mobile version
- [Website](https://filehub1.github.io) — Product overview

## License

MIT
