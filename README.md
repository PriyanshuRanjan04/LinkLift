# ⛓️ LinkLift — Job Link Cleaner

> **From messy links to clean applications — instantly.**

LinkLift is a powerful, zero-dependency, single-file web app that cleans LinkedIn redirect links, resolves `lnkd.in` short links, and intelligently extracts job URLs from bulk email text. No install. No backend. No tracking. Just open and paste.

---

## ✨ Features

| Feature | Description |
|---|---|
| 🔗 Link Cleaning | Decodes `linkedin.com/safety/go` redirects, `lnkd.in` short links, and direct URLs |
| 📨 Bulk Email Parsing | Paste an entire job email — all links are extracted automatically |
| 🏢 Company Context | Detects company name & role from surrounding email text for each link |
| 🌙 Dark Mode | System-aware, toggle with one click |
| 📋 Session History | Last 10 parses saved locally, click any to reload |
| 📊 Stats Row | Shows Total / Cleaned / Direct / Broken link counts at a glance |
| 🔍 Filter Bar | Filter cards by Applied status and link type (multi-select) |
| ↕️ Sort | Sort by Default, Applied Last, Broken First, or Alphabetical |
| ✅ Mark as Applied | Track which jobs you've applied to, persisted across sessions |
| 📝 Notes per Link | Add private notes under each link with auto-save and character counter |
| 📤 CSV Export | Download all results as a `.csv` file |
| 📋 Copy All | Copy all clean, non-duplicate links to clipboard in one click |
| 🔔 Toast Notifications | Feedback toasts for empty actions, copied states, etc. |

---

## 🖼️ Tech Stack

- **HTML5** — Semantic, single-file structure
- **CSS3 (Vanilla)** — CSS variables, dark mode, animations, responsive design
- **JavaScript (Vanilla ES6+)** — No frameworks, no npm, no build step
- **localStorage** — All state (history, applied, notes) stored locally on your device
- **Google Fonts** — Inter typeface

> 🚫 No React. No Vue. No Tailwind. No backend. No install. Open `index.html` and it just works.

---

## 🚀 Getting Started

### Option 1 — Open Directly
Just double-click `index.html`. Done.

### Option 2 — Local Server
```bash
cd LinkLift
npx -y serve .
```
Then open `http://localhost:3000`

---

## 📦 Project Structure

```
LinkLift/
├── index.html          # Entire app — HTML, CSS, and JS in one file
├── README.md           # You are here
└── .gitignore
```

---

## 🧠 How It Works

### Link Cleaning Logic

| Input Type | What Happens |
|---|---|
| `linkedin.com/safety/go?url=...` | URL param is decoded and extracted |
| `lnkd.in/xxxxxxx` | Flagged as Short Link (opens directly) |
| Any `https://` URL | Flagged as Direct |
| Malformed redirect | Flagged as Broken |
| Non-URL text | Skipped |

### Bulk Email Mode
When multiline text is pasted, the app switches to **Bulk Mode** automatically. It scans every line for URLs and also reads the lines **above each link** to capture the company name and job role — displayed on every result card.

### Example
```
1. Workato — SDE Intern | Stipend: 75k/month
Apply: https://www.linkedin.com/safety/go/?url=https%3A%2F%2Fcareers.workato.com...

2. Razorpay — Product Intern
Apply: https://lnkd.in/gRazorpay1
```
**Result cards show:**
- 🏢 **Workato** · SDE Intern | Stipend: 75k/month → cleaned direct link
- 🏢 **Razorpay** · Product Intern → short link flagged

---

## 🗓️ Development Phases

### ✅ Phase 1 — Core Engine & UI
- Link cleaning regex engine
- Dark mode with system detection
- Animated result cards, empty state + example chips
- Deduplication logic

### ✅ Phase 2 — Session & Data
- 10-item session history with time-ago labels
- Stats row (Total / Cleaned / Direct / Broken)
- CSV Export

### ✅ Phase 3 — Application Tracking
- Mark as Applied (green badge, left border, card sort)
- Per-link notes with debounced auto-save and char counter

### ✅ Phase 4 — Polish & Power Features
- Filter bar (status + type multi-select pills)
- Sort dropdown (4 modes)
- Auto-resizing textarea, clear button
- "Nothing to copy" toast
- Company/role context extraction from email text
- Inline SVG favicon, scroll-to-results

---

## 💡 Future Ideas

- 🔌 **Chrome Extension** — Parse links without leaving LinkedIn or Gmail
- 📈 **Application Dashboard** — Visualise your application history over time
- 📥 **CSV Import** — Restore previous sessions from a downloaded CSV
- 🤖 **AI Extraction** — Use an LLM API key to parse messier email formats
- 🔗 **Notion / Sheets Export** — Push applied jobs directly to your tracker

---

## 🌐 Deployment

Hosted on **Vercel** (free static hosting):
1. Push repo to GitHub
2. Import at [vercel.com](https://vercel.com)
3. Deploy — no configuration needed

Every `git push` auto-deploys via Vercel.

---

## 👤 Author

Built by **Priyanshu Ranjan** — [github.com/PriyanshuRanjan04](https://github.com/PriyanshuRanjan04)

---

## 📄 License

MIT — free to use, fork, and extend.
