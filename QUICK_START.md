# 🚀 Juri's 30 Day — Quick Start Guide

## Option 1: Run Locally (Fastest)

### Mac / Linux / Windows (WSL)
```bash
cd juris-30-day
python3 -m http.server 8000
```
Then open your browser to **http://localhost:8000**

### Windows (without WSL)
```bash
cd juris-30-day
python -m http.server 8000
```

### Or use any HTTP server
```bash
npm start
# or
npx http-server -p 8000 -o
# or
ruby -run -ehttpd . -p8000
```

---

## Option 2: Deploy to GitHub Pages (FREE)

### Step 1: Create GitHub Account & Repo
1. Go to https://github.com/new
2. Name: `juris-30-day` (or anything)
3. Description: `🌸 A 30-day discipline challenge tracker`
4. Public repository
5. Click **Create repository**

### Step 2: Upload Files
1. In your new repo, click **Add file** → **Upload files**
2. Drag & drop the entire contents of the `juris-30-day` folder
3. Click **Commit changes**

### Step 3: Enable GitHub Pages
1. Go to repo **Settings**
2. Left sidebar → **Pages**
3. Under "Build and deployment":
   - Source: **Deploy from a branch**
   - Branch: **main** / Root
   - Click **Save**

### Step 4: Done!
Wait 1–2 minutes. Your app is now live at:
```
https://YOUR-GITHUB-USERNAME.github.io/juris-30-day
```

---

## Option 3: Deploy to Vercel (RECOMMENDED)

### Step 1: Upload to GitHub first
Follow "Option 2" steps above.

### Step 2: Connect to Vercel
1. Go to https://vercel.com/new
2. Click **Import Git Repository**
3. Paste your GitHub repo URL
4. Click **Import**
5. Vercel auto-detects it's a static site
6. Click **Deploy**

### Step 3: Done!
Your app is live at:
```
https://juris-30-day-YOUR-NAME.vercel.app
```

Every time you push to GitHub, Vercel auto-redeploys!

---

## Option 4: Deploy to Netlify (EASIEST)

1. Go to https://app.netlify.com
2. Drag & drop the `juris-30-day` folder onto the black area
3. **Instant URL** appears

OR connect to GitHub:
1. https://app.netlify.com/start
2. **Connect to Git**
3. Select GitHub repo
4. Auto-deploys on every push

---

## 📱 Install as PWA on Your Phone

### iPhone
1. Open the deployed URL (or localhost) in **Safari**
2. Tap **Share** (arrow icon)
3. Scroll down, tap **Add to Home Screen**
4. Tap **Add**
5. Icon appears on home screen — tap to open as full-screen app

### Android
1. Open the deployed URL in **Chrome**
2. Tap **⋮** (menu, top-right)
3. Tap **Install app**
4. Confirm
5. Opens like a native app

### Desktop (Optional)
- Chrome: Icon appears in address bar
- Click to install, opens in standalone window

---

## ⚙️ Customize Before Deploying

### Change Challenge Length
Edit `js/constants.js`:
```javascript
export const CHALLENGE_LENGTH_DAYS = 21;  // 21-day challenge
```

### Change Daily Targets
```javascript
export const TARGETS = {
  calories: 1500,      // ← change
  waterMl: 3500,       // ← change
  steps: 15000,        // ← change
  // ... etc
};
```

### Change XP Rewards
```javascript
export const XP_REWARDS = {
  calories: 25,        // ← change
  water: 15,           // ← change
  // ... etc
};
```

**No build needed** — just save, reload your browser!

---

## 🎨 Themes & Languages

### Switch Theme in App
1. Open app
2. Tap **👤 Profile**
3. Find "Settings"
4. Pick: Sakura, Minimal, Latte, Midnight, or Lavender
5. Choose Light, Dark, or System

### Change Language
1. Profile → Settings
2. Select English or العربية (Arabic)
3. App updates instantly (RTL auto-applied for Arabic)

---

## 💾 Your Data

- **All saved locally** on your device (browser storage)
- **No servers**, no accounts needed
- **Export anytime**: Profile → Export JSON/CSV
- Install on multiple devices — each keeps separate data (sync coming later)

---

## ✅ Testing Checklist

Before sharing with friends:

- [ ] Open on mobile phone (iPhone & Android)
- [ ] Test "Add to Home Screen" (PWA install)
- [ ] Add a goal, complete it, see XP reward
- [ ] Switch themes and dark mode
- [ ] Switch language to Arabic
- [ ] Close browser, reopen — data still there (offline works!)
- [ ] Try on desktop browser
- [ ] Check all 5 navigation tabs work

---

## 🆘 Troubleshooting

**App won't load?**
- Hard refresh: Cmd+Shift+R (Mac) or Ctrl+Shift+R (Windows)
- Clear cache: Chrome Settings → Clear browsing data

**Data disappeared?**
- Check browser's localStorage is enabled
- Try different browser
- Use Incognito mode to test (stores data separately)

**PWA won't install?**
- Requires HTTPS (localhost works, GitHub Pages is HTTPS)
- Wait 10 sec for Service Worker to register
- Try Safari on iPhone, Chrome on Android

**Offline not working?**
- Service Worker needs ~10 sec to register on first load
- Must be HTTPS (localhost is OK)
- Refresh page after first load

---

## 🎉 You're Ready!

Your 30-day challenge app is deployed. Start Day 1 and build the discipline that changes your life.

**One honest day at a time.** 🌸
