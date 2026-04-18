# ⚡ TempMail — Instant Disposable Email

A beautiful, zero-dependency temporary email web app powered by the **Guerrilla Mail free API**. No API keys, no backend, no build step — just a single HTML file.

![TempMail Preview](https://img.shields.io/badge/Status-Live-brightgreen?style=flat-square)
![No Dependencies](https://img.shields.io/badge/Dependencies-Zero-blue?style=flat-square)
![API](https://img.shields.io/badge/API-Guerrilla%20Mail-purple?style=flat-square)

---

## ✨ Features

- 🎲 **Auto-generate** a disposable email address on load
- 📋 **One-click copy** to clipboard
- 🔄 **Auto-refresh inbox** every 10 seconds with countdown timer
- 📬 **Email list view** with sender, subject & smart timestamps
- 📖 **Full email reader** — supports HTML and plain text emails
- 🆕 **Get New Address** button to swap to a fresh email instantly
- 💫 **Beautiful dark UI** with glassmorphism and micro-animations
- 📱 **Fully responsive** — works on mobile, tablet, desktop
- ⚡ **Zero dependencies** — no npm, no build step, no frameworks

---

## 🚀 Deploy to Vercel (Recommended)

### Option 1: Deploy via Vercel CLI

```bash
# Install Vercel CLI globally
npm install -g vercel

# Navigate to the project folder
cd "Project Temp Mail"

# Deploy (follow the prompts)
vercel

# Deploy to production
vercel --prod
```

### Option 2: One-Click Deploy via GitHub

1. **Push to GitHub:**
   ```bash
   git init
   git add .
   git commit -m "🚀 Initial commit — TempMail"
   git remote add origin https://github.com/YOUR_USERNAME/tempmail.git
   git push -u origin main
   ```

2. **Connect to Vercel:**
   - Go to [vercel.com](https://vercel.com) and sign in
   - Click **"Add New Project"**
   - Import your GitHub repository
   - Leave all settings as default — Vercel auto-detects static sites
   - Click **Deploy** ✅

3. **Done!** Your site is live at `https://tempmail-xxx.vercel.app`

### Option 3: Drag & Drop Deploy

- Go to [vercel.com/new](https://vercel.com/new)
- Drag and drop the entire `Project Temp Mail` folder
- It deploys instantly — no configuration needed

---

## 📂 File Structure

```
Project Temp Mail/
├── index.html      # Complete app — HTML + CSS + JS all inline
├── vercel.json     # Vercel routing & security headers config
└── README.md       # This file
```

---

## 🌐 API Used

**Guerrilla Mail API** — `https://api.guerrillamail.com/ajax.php`

| Endpoint | Action |
|----------|--------|
| `get_email_address` | Generate a new disposable email |
| `get_email_list` | Fetch inbox messages |
| `fetch_email` | Read full email content |

No API key required. Free and unlimited for personal use.

---

## ⚙️ How It Works

1. On page load, the app calls `get_email_address` to generate a temporary inbox
2. A session token (`sid_token`) is returned and stored in memory
3. Every 10 seconds, `get_email_list` is polled using the token
4. Clicking an email calls `fetch_email` to retrieve the full message
5. HTML emails are rendered in a sandboxed `<iframe>` for safety
6. "Get New Address" clears the token and generates a fresh inbox

> **CORS Note:** The Guerrilla Mail API supports CORS from browsers directly. A `corsproxy.io` fallback is included in case of network restrictions.

---

## 🛠️ Local Development

No build step needed! Just open the file:

```bash
# Option 1: Python simple server
python -m http.server 3000
# Then open http://localhost:3000

# Option 2: Node.js serve
npx serve .
# Then open http://localhost:3000

# Option 3: VS Code Live Server extension
# Right-click index.html → "Open with Live Server"
```

---

## 📄 License

MIT License — free to use, modify, and deploy.

---

<p align="center">Built with ❤️ using plain HTML, CSS & JS — no frameworks, no fuss.</p>
