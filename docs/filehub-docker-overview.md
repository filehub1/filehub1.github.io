# FileHub Docker Overview

**Cross-platform file search server — instant search, file preview, LAN access**

A cross-platform file search and preview server built with Node.js and React. Provides a web-based UI for instant file search, preview, and access — accessible from any browser on your local network.

## Features

- **Instant search** — String, Fuzzy, and Regex modes with sub-second results
- **File preview** — PDF, images, video, audio, Office documents (xlsx/docx), Markdown, code with syntax highlighting
- **LAN access** — Share your file index with other devices on the same network
- **QR code** — Scan to open on mobile instantly
- **Configurable indexing** — Specify directories and exclude patterns
- **Dark/Light theme**
- **REST API** — All features accessible via HTTP API

## Quick Start

```bash
docker run -d -p 6543:6543 -v /your/data:/data exiahuang/filehub-server:latest
```

Open `http://localhost:6543` in your browser.

## Resources

- [Full Docker Documentation →](/docs/filehub-docker.md)
- [Getting Started Guide →](/docs/filehub-getting-started.md)
- [Windows App →](/docs/filehub-windows.md)
- [Android App →](/docs/filehub-android.md)

## License

MIT