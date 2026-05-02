# 🔮 PersonaVault

**Your Secure Personal Digital Space**

A futuristic, all-in-one personal dashboard built as a single HTML file. No backend, no install, no dependencies — just open it in any browser and go.

---

## ✨ Features

### 🔐 Authentication
- **Facial Recognition Login** — Uses your device camera to capture and verify your face on every login
- **Password Fallback** — If your camera is unavailable or unsupported, set a password during registration instead
- **Multi-User Support** — Create multiple separate accounts on the same device, each with its own private vault
- **Gender-Aware Greeting** — On login, a robotic voice greets you as *"Sir"* or *"Ma'am"* by name using the Web Speech API

### ✅ To-Do List
- Add tasks with **High / Medium / Low** priority levels
- Check off completed tasks with a satisfying animated toggle
- Delete individual tasks or bulk-clear all completed ones
- Tasks are sorted by priority automatically

### 📔 Diary & Writing Sections
| Section | Purpose |
|---|---|
| **Personal Diary** | Daily thoughts, feelings, gratitude journal |
| **Script Writing** | Screenplays, TV scripts, podcasts, ad scripts, stage plays |
| **Ideas & Notes** | Brainstorming with category tags (Startup, Creative, Tech, Learning) |
| **Travel Journal** | Location-tagged travel memories and trip logs |

All sections feature a rich text editor with formatting toolbar. Entries are saved instantly and listed below the editor for quick review.

### 💰 Business Accounts
- Add **credit** (income) and **debit** (expense) transactions
- Choose from 11 built-in categories (Salary, Shopping, Food, Rent, Utilities, Healthcare, Education, Entertainment, Travel, Investment, Other)
- Live summary cards showing **Net Balance**, **Total Income**, **Total Expenses**, and **Transaction Count**
- Scrollable recent transaction feed with category icons and colour-coded amounts

### 🖼️ Photo & File Vault
- **Drag-and-drop** or click-to-browse file upload
- Supports images, PDFs, documents, spreadsheets, video, and audio
- Image thumbnails rendered inline in a responsive grid
- Click any file to preview images full-size or download non-image files
- Delete files individually

### 🖩 Calculator
- Full arithmetic: addition, subtraction, multiplication, division, percentage
- Expression display shows your full calculation before the result
- **Full keyboard support** — use number keys, operators, Enter, Backspace, Escape
- Animated buttons with haptic-style feedback

### 🎨 UI & Design
- **Dark / Light mode** toggle (top-right button, preference saved across sessions)
- Cyber-grid animated background
- Glowing accent colours with animated logo
- Futuristic fonts: **Orbitron** (headings), **Rajdhani** (body), **Space Mono** (mono/labels)
- Animated welcome overlay with sound-wave visualiser on every login
- Fully responsive — works on desktop and mobile

---

## 🚀 Getting Started

1. **Download** `personal-vault.html`
2. **Open** it in any modern browser (Chrome, Firefox, Edge, Safari)
3. Click **Create Account**
4. Enter your name and choose your gender
5. Optionally upload a profile photo
6. Click **Start Camera** to set up face recognition — or skip and set a password
7. Click **Create Vault** — your robotic greeter will welcome you in!

> **No internet connection required** after the initial page load (fonts load from Google Fonts on first open).

---

## 🔒 Privacy & Data Storage

- **All data is stored locally** in your browser's `localStorage`
- Nothing is ever sent to a server — there is no server
- Face data is stored as a base64 image string locally on your device
- Clearing your browser's site data will erase all vaults

> ⚠️ **Note:** Because data lives in `localStorage`, it is tied to the specific browser and device you use. Switching browsers or devices will start fresh.

---

## 🌐 Browser Compatibility

| Browser | Support |
|---|---|
| Chrome 90+ | ✅ Full support |
| Edge 90+ | ✅ Full support |
| Firefox 88+ | ✅ Full support (voice may vary) |
| Safari 14+ | ✅ Supported (camera requires HTTPS or localhost) |
| Mobile Chrome/Safari | ✅ Responsive layout (sidebar hidden on small screens) |

> Camera and voice features require a **secure context** (HTTPS or `localhost`). Opening the file directly via `file://` may block camera access in some browsers — serve it via a local server if needed (e.g. `npx serve .`).

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Structure | HTML5 |
| Styling | CSS3 (custom properties, grid, flexbox, animations) |
| Logic | Vanilla JavaScript (ES6+) |
| Camera | `getUserMedia` Web API |
| Voice | Web Speech API (`SpeechSynthesisUtterance`) |
| Storage | `localStorage` |
| Fonts | Google Fonts (Orbitron, Rajdhani, Space Mono) |

Zero external JS libraries. Zero build tools. Zero dependencies.

---

## 📁 File Structure

```
personal-vault.html     ← The entire app (HTML + CSS + JS in one file)
README.md               ← This file
```

---

## ⚙️ Configuration & Customisation

Everything lives in the single HTML file. To customise:

- **Accent colour** — change `--accent: #00f5c8` in the `:root` CSS block
- **Default theme** — change `data-theme="dark"` on the `<html>` tag to `"light"`
- **Voice pitch/rate** — adjust `utter.rate` and `utter.pitch` in the `playWelcomeVoice` function
- **Transaction categories** — add `<option>` elements inside `#txnCat` select
- **Diary types** — duplicate a panel block and register it in the sidebar nav

---

## 🐛 Known Limitations

- **Face recognition is simulated** — the current implementation captures a face photo and stores it, but the login verification confirms a photo was captured rather than running a true biometric match. For production use, integrate [face-api.js](https://github.com/justadudewhohacks/face-api.js) for real descriptor-based matching.
- **File storage limits** — `localStorage` is capped at ~5–10 MB depending on the browser. Uploading many large images may hit this limit.
- **No cloud sync** — data does not sync across devices or browsers by design (privacy-first approach).
- **Voice support varies** — robotic voice quality depends on the voices installed on your OS. Chrome on Windows/Mac provides the best results.

---

## 📄 License

This project is provided as-is for personal use. Feel free to modify and extend it for your own needs.

---

*Built with ❤️ and a lot of CSS variables.*
