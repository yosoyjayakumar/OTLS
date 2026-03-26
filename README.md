# 🎬 OTLS — Off-The-Local-Storage

<div align="center">

![OTLS Banner](https://img.shields.io/badge/OTLS-Streaming%20Platform-ff4b4b?style=for-the-badge&logo=film&logoColor=white)
![Version](https://img.shields.io/badge/version-1.0.0-brightgreen?style=for-the-badge)
![License](https://img.shields.io/badge/license-MIT-blue?style=for-the-badge)
![HTML](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)

**Your personal media. Your local machine. Zero cloud needed.**

[Features](#-features) · [Demo](#-demo) · [Getting Started](#-getting-started) · [Usage](#-usage) · [Tech Stack](#-tech-stack) · [Contributing](#-contributing)

</div>

---

## 📖 About

**OTLS** (Off-The-Local-Storage) is a browser-based streaming platform that lets you organize, browse, and play your locally stored video and audio files — no server, no account, no subscription. Think of it as your personal Netflix, built entirely with vanilla HTML, CSS, and JavaScript, running right in your browser.

> Stream your local media collection with a polished, cinema-grade interface. Everything stays on your device.

---

## ✨ Features

- 🗂️ **Local File Browser** — Pick files or entire folders directly from your device using the File System API
- 🎥 **Video Streaming** — Smooth playback for `.mp4`, `.mkv`, `.webm`, `.avi`, and more
- 🎵 **Audio Support** — Full audio player for `.mp3`, `.flac`, `.ogg`, `.wav`
- 🖼️ **Thumbnail Grid** — Auto-generated previews displayed in a beautiful card layout
- 🔍 **Search & Filter** — Instantly find files by name, type, or recently watched
- 📌 **Continue Watching** — Saves playback progress via `localStorage` — pick up where you left off
- ❤️ **Favourites** — Bookmark your favourite titles for quick access
- 🌙 **Dark / Light Mode** — Smooth theme toggle, preference saved locally
- 📱 **Responsive Design** — Works on desktop, tablet, and mobile browsers
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

- A modern browser (Chrome 86+, Firefox 82+, Edge 86+)
- Local video/audio files you want to stream

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

   # OR serve locally with Python (optional, for broader File API support)
   python -m http.server 8080
   # Then visit: http://localhost:8080
   ```

4. **Load your media**
   - Click **"Add Media"** or drag & drop files/folders into the browser
   - Your library appears instantly — no upload, no processing

---

## 📁 Project Structure

```
otls/
├── index.html              # Entry point, Core styles & layout, Cards, modals, player UI, Dark/light theme variables
├── js/
│   ├── app.js              # App initialization & routing
│   ├── library.js          # File loading & media library logic
│   ├── player.js           # Video/audio player controls
│   ├── storage.js          # localStorage read/write helpers
│   └── ui.js               # DOM manipulation & rendering
├── assets/
│   ├── icons/              # SVG icons
│   └── fonts/              # Local font files (if any)
└── README.md
```

---

## 🎮 Usage

### Adding Media
Click the **＋ Add Media** button in the top bar, then select individual files or an entire folder. OTLS reads the file metadata and populates your library instantly.

### Playback
Click any card to open the player. Use the custom controls for play/pause, seek, volume, fullscreen, and playback speed.

### Continue Watching
Playback positions are saved automatically in `localStorage`. A progress bar appears on thumbnails, and a **Continue Watching** row populates on the homepage.

### Themes
Toggle between dark and light mode using the 🌙 icon in the header. Your preference is remembered across sessions.

### Keyboard Shortcuts

| Key | Action |
|-----|--------|
| `Space` | Play / Pause |
| `←` / `→` | Seek ±10 seconds |
| `↑` / `↓` | Volume up / down |
| `F` | Toggle fullscreen |
| `M` | Toggle mute |
| `Esc` | Close player |

---

## 🛠️ Tech Stack

| Technology | Purpose |
|------------|---------|
| **HTML5** | Semantic structure, `<video>` / `<audio>` elements |
| **CSS3** | Custom properties, Grid, Flexbox, animations |
| **Vanilla JavaScript (ES6+)** | App logic, File System API, localStorage |
| **File & FileReader API** | Loading local files without a server |
| **localStorage API** | Persisting watch history, favourites, preferences |
| **Web Storage API** | Cross-session state management |

---

## 🌐 Browser Compatibility

| Browser | Support |
|---------|---------|
| Chrome / Edge 86+ | ✅ Full support |
| Firefox 82+ | ✅ Full support |
| Safari 15.2+ | ⚠️ Partial (no folder picker) |
| Mobile Chrome | ✅ Supported |
| Mobile Safari | ⚠️ Limited file access |

---

## 🎬 New Player Features

1. Custom Controls
Play/Pause Button - Toggle video playback with visual icon change
Time Display - Shows current time / total duration (formatted MM:SS)
Speed Selector - 0.5x, 0.75x, 1x (default), 1.25x, 1.5x, 2x playback speeds
Volume Slider - Adjustable 0-100% volume control
Fullscreen Button - Enter fullscreen playback
2. Keyboard Shortcuts (when player is active)
|Key	Action|
SPACE	Play/Pause
ESC	Close player
F	Toggle fullscreen
← Arrow	Seek back 5 seconds
→ Arrow	Seek forward 5 seconds
↑ Arrow	Volume up 10%
↓ Arrow	Volume down 10%
3. Better UI/UX
Custom styled buttons with hover effects (primary color highlight)
Semi-transparent dark background for controls
On-screen keyboard hint display
Improved title display with larger font
All controls footer-positioned and responsive
Auto-update play button text (▶ Play / ⏸ Pause)
4. Smart Player Logic
Formats time display properly (e.g., "1:23" or "2:45")
Tracks metadata loading for accurate duration display
Bounds-check seek times (prevents seeking beyond video length)
Bounds-check volume (keeps between 0-1)
Prevents accidental page scrolling on arrow key use

## 🗺️ Roadmap

- [ ] Subtitle / SRT file support
- [ ] Playlist creation and queue management
- [ ] Metadata editor (title, genre, poster art)
- [ ] Grid / list view toggle
- [ ] Sort by date added, duration, name
- [ ] Mini player (picture-in-picture mode)
- [ ] IndexedDB support for larger libraries
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
- Safari restricts folder selection via `<input type="file" webkitdirectory>` in some versions

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
