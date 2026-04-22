# ⚡ DevBoard — Real-Time Collaborative Code Editor

> A browser-based collaborative code editor with AI pair programming, live code execution, and real-time team chat. Zero backend. Zero cost.

![DevBoard](https://img.shields.io/badge/Status-Live-4dff91?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-f0ff44?style=flat-square)
![Cost](https://img.shields.io/badge/Hosting_Cost-$0-44d9ff?style=flat-square)
![Languages](https://img.shields.io/badge/Languages-10+-ff9f44?style=flat-square)

---

## 🔗 Live Demo

**[devboard.yourusername.github.io](https://yourusername.github.io/devboard)**

> Open in two browser tabs, share the Room ID — and watch real-time collaboration in action.

---

## ✨ Features

### 👥 Real-Time Collaboration
- Create or join a **shared coding room** with a unique Room ID
- Code changes sync **live across all connected tabs/users**
- **Remote cursors** with colored labels show where teammates are editing
- **Live team chat** sidebar synced in real time

### 🖊️ Code Editor
- Full-featured editor with **line numbers**, **Tab indentation**, and cursor position tracking
- **Multi-file support** — add, switch, and delete files with tabbed navigation
- Supports **10 languages**: JavaScript, Python, Java, C++, TypeScript, Go, Rust, HTML, CSS, SQL
- One-click **format**, **copy**, and **download** for any file

### ▶️ Live Code Execution
- Runs real code via the **[Piston API](https://github.com/engineer-man/piston)** (free, open source)
- Output panel shows `stdout`, `stderr`, and exit code
- Supported runtimes: JavaScript, Python, Java, C++, TypeScript, Go, Rust

### 🤖 AI Pair Programming
- Powered by **Google Gemini 1.5 Flash** (free — 1,500 requests/day)
- Context-aware: AI sees your current code automatically
- Quick actions: **Explain**, **Find Bugs**, **Optimize**, **Add Comments**, **Write Tests**, **Complexity Analysis**
- Full conversation memory within the session

---

## 🛠️ Tech Stack

| Layer | Technology | Cost |
|---|---|---|
| Frontend | Vanilla HTML / CSS / JavaScript | Free |
| Real-time Sync | localStorage + Storage Events API | Free |
| Code Execution | [Piston API](https://emkc.org/api/v2/piston) | Free |
| AI Assistant | [Gemini 1.5 Flash API](https://aistudio.google.com) | Free (1500 req/day) |
| Hosting | GitHub Pages | Free |

**No Node.js. No npm. No build step. No server. One HTML file.**

---

## 🚀 Getting Started

### Option 1 — Run locally
```bash
# Clone the repo
git clone https://github.com/yourusername/devboard.git

# Open in browser — no server needed
open index.html
```

### Option 2 — Deploy to GitHub Pages (recommended)
1. Fork this repo or upload `index.html` renamed as `index.html`
2. Go to **Settings → Pages**
3. Set source to **main branch / root**
4. Your app is live at `https://yourusername.github.io/devboard`

---

## 🔑 API Keys Setup

### Gemini API (AI Assistant) — Free
1. Visit [aistudio.google.com/app/apikey](https://aistudio.google.com/app/apikey)
2. Sign in with Google → click **Create API Key**
3. Paste it into the **AI Assistant panel** inside DevBoard
4. Free tier: **1,500 requests/day**, no credit card required

> Keys are never stored or transmitted anywhere — they live only in your browser session.

---

## 💡 How to Use

```
1. Open DevBoard in your browser
2. Enter your name → click "Create Room"
3. Share the Room ID (e.g. DEV-X4K2) with a teammate
4. Teammate opens DevBoard → enters the Room ID → clicks "Join Room"
5. Both users now share a live editor session
```

To use AI assistance, add your free Gemini API key in the AI panel on the right.

---

## 📁 Project Structure

```
devboard/
└── index.html        ← Entire application (HTML + CSS + JS)
└── README.md         ← This file
```

---

## 🏗️ Architecture

```
Browser Tab A ──┐
                ├── localStorage (Room State) ── Storage Events API ──┐
Browser Tab B ──┘                                                      │
                                                                       ▼
                                                            Real-time sync (~1.2s)

Code Execution:   Browser → Piston API (emkc.org) → Result
AI Assistant:     Browser → Gemini API (Google) → Response
```

No WebSocket server needed. Real-time sync is achieved using the browser's `localStorage` and `StorageEvent` API — which fires instantly across tabs on the same machine, and can be extended to a real WebSocket backend (e.g. Supabase Realtime, Ably) for cross-device sync.

---

## 🔮 Roadmap / Possible Extensions

- [ ] Cross-device real-time sync via Supabase Realtime (free tier)
- [ ] Syntax highlighting via CodeMirror or Monaco Editor
- [ ] GitHub Gist save/load integration
- [ ] Video/audio call via Daily.co or 100ms (free tiers)
- [ ] Persistent rooms with user authentication

---

## 🎯 Why I Built This

Pair programming and remote collaboration are central to modern software development, yet existing tools (VS Code Live Share, CodePen, Replit) either require installation, accounts, or paid plans. DevBoard proves that a powerful collaborative coding experience can be delivered in a **single HTML file** with zero infrastructure cost.

---

## 📄 License

MIT — free to use, modify, and distribute.

---

## 🙋 Author

**Your Name**
- GitHub: [@yourusername](https://github.com/yourusername)
- LinkedIn: [linkedin.com/in/yourprofile](https://linkedin.com/in/yourprofile)
- Portfolio: [yourportfolio.com](https://yourportfolio.com)

---

> ⭐ If you found this useful, please star the repo — it helps a lot!
