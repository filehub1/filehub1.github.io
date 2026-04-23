# FileHub Android App

**Turn your Android device into a portable file search server**

An Android file manager with built-in local web server. Search and access files from any browser on the same network.

## Features

- ⚡ **Instant Search** — Native C++ indexer for fast results
- 👀 **File Preview** — PDF, images, video, Office docs, code
- 🌐 **Built-in Server** — No computer needed to serve files
- 📱 **Mobile First** — Full-featured file manager
- 🔗 **QR Code Sharing** — Scan to access from other devices
- 🎵 **Background Playback** — Continue audio/video when app is in background

## Download

[![GitHub Release](https://img.shields.io/github/v/release/filehub1/android?include_prereleases&label=release)](https://github.com/filehub1/android/releases/latest)
[![Downloads](https://img.shields.io/github/downloads/filehub1/android/total)](https://github.com/filehub1/android/releases/latest)

**Requirements:**
- Android 8.0+ (API 26+)

### Download Options

1. **Direct APK Download**
   
   [Download from GitHub Releases →](https://github.com/filehub1/android/releases)

2. **Scan QR Code**
   
   Scan this QR code to download:
   
   ![Download QR Code](/images/android/android-qr.png)

3. **Build from Source**
   
   [See Build Instructions](#build-from-source)

## Installation

1. Download the APK from the link above
2. Enable "Install unknown apps" in Android Settings
3. Open the APK file
4. Tap Install
5. Launch FileHub

## Quick Start

1. **Grant Permissions**
   
   On first launch, grant storage permission when prompted.
   
   For Android 11+, you'll be redirected to Settings to enable "All files access".

2. **Configure Directories**
   
   In Settings → Indexed Directories, select the folders to search.

3. **Start Using**
   
   - Type in the search box for instant results
   - Tap a file to preview
   - Use the menu for additional options

## Use Cases

### Access PC Files from Phone

1. Install FileHub on your Android device
2. Run FileHub Server on your PC
3. Enable LAN Access in Settings
4. Scan the QR code on your phone
5. Browse and search PC files from your phone!

### Share Files Without Internet

- Works over Wi-Fi hotspot
- No internet connection required
- Perfect for travel or offline file sharing

### Browse Server Files

- Index your NAS/media server files
- Access from any device on the network
- Preview without downloading

## Settings

| Setting | Default | Description |
|---------|---------|-------------|
| Indexed Directories | `/storage/emulated/0` | Folders to search |
| Exclude Patterns | — | Skip matching files |
| Theme | Dark | UI theme |
| LAN Access | Off | Allow external access |
| LAN Username | — | Basic auth user |
| LAN Password | — | Basic auth password |
| Background Playback | On | Keep media playing |
| File Observer | On | Auto-refresh index |

## Permissions

| Permission | Purpose |
|-----------|---------|
| `MANAGE_EXTERNAL_STORAGE` | Read all files (Android 11+) |
| `READ_EXTERNAL_STORAGE` | Read files (Android 10-) |
| `INTERNET` | Local web server |

## Build from Source

**Prerequisites:**
- Android Studio (latest)
- Android NDK
- JDK 17+

**Steps:**
```bash
git clone https://github.com/filehub1/android.git
cd android

# Build the web frontend
cd ../filehub-server
npm install
npm run build

# Copy frontend to Android
powershell -File ../android/scratch/copy-frontend.ps1

# Open in Android Studio
# File → Open → ../android
# Run on device or build APK
```

**Build Release APK:**
```bash
cd android
./gradlew assembleRelease
```

Output: `android/app/build/outputs/apk/release/app-release.apk`

## Related

- [FileHub Server](/docs/filehub-docker.md) — Docker deployment
- [Windows App](https://github.com/filehub1/filehub-windows-app) — Desktop version
- [Website](https://filehub1.github.io) — Product overview

## License

MIT