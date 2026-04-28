# FindYourUni

A free STEM university comparison tool built with HTML, CSS, and JavaScript.

## Repository structure

```
├── index.html        # The full app
├── api/
│   └── chat.js       # Serverless function — proxies Anthropic API (keeps key secret)
├── package.json
├── vercel.json
└── README.md
```

## Deploy to Vercel (step by step)

### 1. Push this repo to GitHub
Upload all these files to a new GitHub repository.

### 2. Connect to Vercel
1. Go to https://vercel.com and sign in (free account)
2. Click **Add New Project**
3. Select **Import Git Repository**
4. Choose your GitHub repo
5. Click **Deploy** — leave all settings as default

### 3. Add your Anthropic API key
1. In Vercel, go to your project → **Settings** → **Environment Variables**
2. Click **Add New**
   - **Name:** `ANTHROPIC_API_KEY`
   - **Value:** your key from https://console.anthropic.com
   - **Environments:** check Production, Preview, Development
3. Click **Save**

### 4. Redeploy
Go to **Deployments** → click the three dots on the latest → **Redeploy**

Your app is now live with a working AI advisor at your Vercel URL.

## How the AI advisor works
- The frontend calls `/api/chat` (your Vercel serverless function)
- The function calls Anthropic using your secret API key stored in Vercel
- Your key is never exposed in the browser
- If running as a standalone HTML file (outside Vercel), it falls back to calling Anthropic directly
