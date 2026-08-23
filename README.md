# 🎬 OTLS — Over The Local Storage

<div align="center">

![OTLS Banner](https://img.shields.io/badge/OTLS-Streaming%20Platform-ff4b4b?style=for-the-badge&logo=film&logoColor=white)
![Version](https://img.shields.io/badge/version-0.0.1-brightgreen?style=for-the-badge)
![License](https://img.shields.io/badge/license-MIT-blue?style=for-the-badge)
![HTML](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)

**Your personal media. Your local machine. Zero cloud needed.**

[Features](#-features) · [Demo](#-demo) · [Getting Started](#-getting-started) · [Usage](#-usage) · [Contributing](#-contributing)

</div>

---

## 📖 About

**OTLS** — Over The Local Storage is a browser-based streaming platform that lets you organize, browse, and play your locally stored video files — no server, no account, no subscription. Built with vanilla HTML, CSS, and JavaScript, it runs entirely in your browser using the File System Access API and IndexedDB.

> Stream your local movie collection with a polished, cinema-grade interface. Everything stays on your device.

---

## ✨ Features

- 🗂️ **Folder Scanning** — Pick a directory containing your video files using the File System Access API
- 📁 **Hierarchical Library** — Organizes movies by primary and secondary folder categories
- 🎥 **Video Streaming** — Smooth playback for `.mp4`, `.mkv`, `.webm`, `.avi`, `.mov`, `.m4v`
- 🖼️ **Smart Thumbnails** — Auto-generated video frame previews with fallback to OMDB/TMDB posters
- 🔍 **Search & Filter** — Instantly find files by name, or filter by category/genre pills
- 📌 **Continue Watching** — Saves playback progress via `localStorage` — pick up where you left off
- 🌙 **Dark / Light Mode** — Smooth theme toggle with Dark, Light, and System preferences saved locally
- 📱 **Responsive Design** — Works on desktop, tablet, and mobile browsers
- 🎬 **Hero Billboard** — Featured movie showcase with backdrop imagery
- 🎮 **Custom Video Player** — Full custom controls with play/pause, seek, volume, speed, fullscreen, and PiP
- 📦 **Mini Player** — Picture-in-picture style overlay for browsing while watching
- ⏩ **Playback Speed** — 0.25× to 2× speed presets
- ⌨️ **Keyboard Shortcuts** — Full keyboard control when player is active
- 📱 **Touch Gestures** — Swipe to seek and swipe down to close on mobile
- 💾 **Persistence** — IndexedDB stores directory handles; `localStorage` stores watch history and movie list
- ✏️ **Manual List Editing** — Edit your movie list directly via a text modal
- 🚫 **Zero Dependencies** — Pure HTML, CSS, and JS. No frameworks, no npm, no build step

---

## 🖥️ Demo

> **No live demo needed — just open `index.html` in your browser.**

```
git clone https://github.com/yosoyjayakumar/otls.git
cd otls
open index.html   # or double-click the file
```

---

## 🚀 Getting Started

### Prerequisites

- A modern browser with File System Access API support:
  - Chrome / Edge 86+ ✅ Full support
  - Opera ✅ Supported
  - Firefox ⚠️ Limited (no folder picker support)
  - Safari ⚠️ Partial support
- Local video files you want to stream

### Installation

1. **Clone the repository**
    ```bash
    git clone https://github.com/yosoyjayakumar/otls.git
    ```

2. **Navigate to the project folder**
    ```bash
    cd otls
    ```

3. **Open in browser**
    ```bash
    # Simply open the file directly
    open index.html

    # OR serve locally with Python (optional)
    python -m http.server 8080
    # Then visit: http://localhost:8080
    ```

4. **Load your media**
    - Click **"Choose Movies Folder"** on the welcome screen to scan a directory
    - Or use **"Choose Video Files"** to select individual files
    - Your library appears instantly — no upload, no processing

---

## 📁 Project Structure

```
otls/
├── index.html              # Entry point, Core layout, Player UI, All app logic
├── style.css               # All styles, themes, animations, responsive design
├── config.js               # OMDB & TMDB API configuration
├── movies.json             # Initial movie list (optional)
├── .gitignore
└── README.md
```

**Expected folder structure for scanned media:**

```
YourRootFolder/
├── Action/              (Primary Category)
│   ├── 2020/           (Secondary Category)
│   │   ├── Movie1.mp4
│   │   ├── Movie2.mkv
│   ├── 2021/
│   │   ├── Movie3.mp4
├── Comedy/
│   ├── 2020/
│   │   ├── Movie4.mp4
│   └── Classics/
│       ├── Movie5.avi
```

---

## 🎮 Usage

### Adding Media

On first load, use the welcome screen to either:
- **Choose Movies Folder** — scans a directory recursively for `.mp4`, `.mkv`, `.avi`, `.webm`, `.mov`, `.m4v` files and organizes them by folder hierarchy
- **Choose Video Files** — select individual video files directly

After the initial scan, use the top bar buttons:
- **Scan Folder** — re-scan or select a new folder
- **Add Files** — add individual files to the current library
- **Edit List** — manually edit the movie list via a text modal
- **Save** — persist the current library to `localStorage`
- **Reset** — clear all data and return to the welcome screen

### Playback

Click any card to open the full player. Use the custom controls or keyboard shortcuts for play/pause, seek, volume, fullscreen, playback speed, and picture-in-picture.

### Continue Watching

Playback positions are saved automatically in `localStorage`. A progress bar appears on thumbnails, and a **Continue Watching** row populates on the homepage.

### Themes

Toggle between dark, light, and system themes using the 🌙 icon in the header. Your preference is remembered across sessions.

### Keyboard Shortcuts

| Key | Action |
|-----|--------|
| `Space` | Play / Pause |
| `←` / `→` | Seek ±10 seconds |
| `↑` / `↓` | Volume up / down |
| `F` | Toggle fullscreen |
| `M` | Toggle mute |
| `Esc` | Close player |

### Mobile Gestures

- Swipe left/right on the player to seek ±10 seconds
- Swipe down to close the player

---

## 🛠️ Tech Stack

| Technology | Purpose |
|------------|---------|
| **HTML5** | Semantic structure, `<video>` element |
| **CSS3** | Custom properties, Grid, Flexbox, animations, glassmorphism |
| **Vanilla JavaScript (ES6+)** | App logic, File System Access API, IndexedDB, localStorage |
| **File System Access API** | Loading local folders and files without a server |
| **IndexedDB** | Persisting directory handles across sessions |
| **localStorage** | Persisting watch history, movie list, theme preferences |
| **OMDB / TMDB APIs** | Fetching movie posters when local thumbnails aren't available |

---

## 🌐 Browser Compatibility

| Browser | Support |
|---------|---------|
| Chrome / Edge 86+ | ✅ Full support |
| Opera | ✅ Supported |
| Firefox 82+ | ⚠️ Limited (no folder picker) |
| Safari 15.2+ | ⚠️ Partial (no folder picker) |
| Mobile Chrome | ✅ Supported |
| Mobile Safari | ⚠️ Limited file access |

> **Note:** Folder scanning requires the [File System Access API](https://developer.mozilla.org/en-US/docs/Web/API/File_System_Access_API), which is currently only supported in Chromium-based browsers.

---

## 🗺️ Roadmap

- [ ] Audio file support (`.mp3`, `.flac`, `.ogg`, `.wav`)
- [ ] Favourites / bookmarks
- [ ] Subtitle / SRT file support
- [ ] Playlist creation and queue management
- [ ] Metadata editor (title, genre, poster art)
- [ ] Grid / list view toggle
- [ ] Sort by date added, duration, name
- [ ] Drag & drop file/folder support
- [ ] PWA support for installable offline app
- [ ] Custom themes / accent colors

---

## 🤝 Contributing

Contributions are welcome! This project is intentionally dependency-free, so keep PRs in plain HTML, CSS, and JS.

1. Fork the repository
2. Create your feature branch: `git checkout -b feature/your-feature-name`
3. Commit your changes: `git commit -m 'Add some feature'`
4. Push to the branch: `git push origin feature/your-feature-name`
5. Open a Pull Request

Please read [CONTRIBUTING.md](CONTRIBUTING.md) before submitting.

---

## 🐛 Known Issues

- Large folders (1000+ files) may cause initial load delay due to browser FileReader limits
- `.mkv` playback depends on browser codec support — Chrome handles most formats; Firefox may need codec packs
- Firefox and Safari restrict folder selection via the File System Access API
- OMDB/TMDB thumbnail fetching requires valid API keys configured in `config.js`

---

## 📄 License

Distributed under the **MIT License**. See [`LICENSE`](LICENSE) for details.

---

## 🙏 Acknowledgements

- Inspired by [Jellyfin](https://jellyfin.org/), [Plex](https://www.plex.tv/), and the spirit of local-first software
- Icons from [Heroicons](https://heroicons.com/)
- Built with love for people who believe your media should belong to you

---

<div align="center">

Made with ☕ and a deep distrust of monthly subscriptions.

**⭐ Star this repo if OTLS saved your media from the cloud!**

</div>
