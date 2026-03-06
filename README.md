# ✝ Sacred Canvas — Bible Creative App

An AI-powered Bible app with three experiences:
- **Verse Art Generator** — Beautiful scripture cards with custom fonts & themes
- **Story Animator** — AI-generated animated scenes for any Bible story
- **Psalm Composer** — AI-written psalms in biblical style

Built with **React + Vite**, deployed on **Vercel** with a secure serverless API proxy.

---

## 🚀 Deploy to Vercel (5 minutes)

### Step 1 — Get your Anthropic API Key
1. Go to [console.anthropic.com](https://console.anthropic.com)
2. Sign up / log in → click **API Keys** → **Create Key**
3. Copy the key (starts with `sk-ant-...`) — save it somewhere safe

### Step 2 — Put the project on GitHub
1. Create a new repo at [github.com/new](https://github.com/new) (name it `bible-canvas`)
2. Upload all these project files, or run:
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git remote add origin https://github.com/YOUR_USERNAME/bible-canvas.git
   git push -u origin main
   ```

### Step 3 — Deploy on Vercel
1. Go to [vercel.com](https://vercel.com) and sign in with GitHub
2. Click **Add New Project** → select your `bible-canvas` repo
3. Vercel auto-detects Vite — no build settings needed
4. Before clicking Deploy, click **Environment Variables** and add:
   - **Name:** `ANTHROPIC_API_KEY`
   - **Value:** `sk-ant-...` (your key from Step 1)
5. Click **Deploy** — your app will be live in ~60 seconds!

You'll get a URL like: `https://bible-canvas.vercel.app` 🎉

---

## 💻 Run Locally

```bash
# 1. Install dependencies
npm install

# 2. Set up your API key
cp .env.example .env.local
# Edit .env.local and add your ANTHROPIC_API_KEY

# 3. Start the dev server
npm run dev
```

Open [http://localhost:5173](http://localhost:5173)

> **Note:** The Vercel serverless function (`/api/claude.js`) runs automatically
> in both local dev (via `vite.config.js` proxy) and production.

---

## 📁 Project Structure

```
bible-canvas/
├── api/
│   └── claude.js          # Vercel serverless function (secure API proxy)
├── public/
│   └── cross.svg          # Favicon
├── src/
│   ├── main.jsx           # React entry point
│   └── App.jsx            # Main app component
├── .env.example           # Environment variable template
├── .gitignore
├── index.html
├── package.json
├── vercel.json            # Vercel deployment config
└── vite.config.js         # Vite + dev proxy config
```

---

## 🔒 Security Notes

- Your `ANTHROPIC_API_KEY` lives only in Vercel's environment — never in the frontend
- All AI calls go through `/api/claude` (your own serverless function), not directly to Anthropic
- The key is never exposed in the browser or your source code

---

## 🛠 Tech Stack

| Layer      | Technology                  |
|------------|-----------------------------|
| Frontend   | React 18 + Vite             |
| API Proxy  | Vercel Serverless Functions |
| AI Model   | Claude Sonnet (Anthropic)   |
| Fonts      | Google Fonts                |
| Hosting    | Vercel (free tier works!)   |
