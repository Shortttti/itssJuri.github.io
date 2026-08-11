# 🌸 Juri's 30 Day — Premium Discipline Challenge Tracker

A polished, mobile-first progressive web app for 30-day personal discipline challenges. Track daily goals, build streaks, unlock achievements, and transform your habits.

**Live Demo:** Open `index.html` in a browser or deploy to GitHub Pages / Vercel.

## ✨ Features

### Core Challenge System
- **30-day countdown** with real-time progress tracking
- **XP & level system** (auto-calibrated, Level 1–50)
- **Streak tracking** with freeze mechanic (use once if you miss a day)
- **Perfect day detection** & milestone celebrations

### Daily Goals (8 customizable goals)
1. 🥗 **Calories** — Track consumed calories (target: 1200 kcal)
2. 🚫🍬 **No Sugar** — Daily rule (checkbox)
3. 🚫🍞 **No Bread** — Daily rule (checkbox)
4. 💧 **Water** — Target 4 L/day with +250ml/+500ml/+1L quick buttons
5. 👣 **Steps** — Target 20,000 steps with auto-progress bars
6. 🏋🏻 **Workout** — Start/finish timer or manual entry
7. 📸 **Progress Photo** — Upload one per day, chronological gallery
8. 😴 **Sleep** — Track bedtime, wake-up, hours (target: 7.5–9h)

### Gamification
- ⭐ **XP Rewards** — Each goal completion earns XP (configurable in constants.js)
- 🏆 **Achievements** — 16 unlockable badges (visible + 3 hidden surprises)
- 🔥 **Streaks** — Current, longest, milestones at 3/7/14/21/30 days
- 💯 **Perfect Days** — 100% completion tracked and celebrated

### Tracking & Analytics
- 📊 **Statistics Dashboard** — Completion %, perfect days, streak metrics
- 📈 **Weight Tracking** — Log weekly weights with trend line
- 📏 **Body Measurements** — Waist, hips, chest, arms, thighs
- 📸 **Progress Gallery** — Before/after photo chronology
- 😊 **Mood Tracker** — Daily emoji mood (great/good/neutral/bad/very bad)
- 📝 **Daily Journal** — Write reflections for each day
- 📅 **Calendar View** — 30-day grid (🟢 complete, 🟡 partial, 🔴 missed)

### Weekly & Advanced
- 📋 **Weekly Review** — Completion %, best/weakest habit, notes on progress
- 🎯 **Focus Mode** — Pomodoro-style timers (25/45/60/90 min) for deep work
- 💭 **AI Coach** — Contextual nudges ("You still have 1.2L water left")
- 🆘 **Struggling Button** — Surfaces the easiest next action for today

### Personalization
- 🎨 **5 Themes** — Sakura (default), Minimal, Latte, Midnight, Lavender
- 🌙 **Dark Mode** — Light, Dark, System preference
- 🌍 **Languages** — English, Arabic (with RTL support)
- 🔊 **Sound Effects** — Optional completion/achievement sounds
- ⚙️ **Notifications** — Reminder time customization (optional)

### Data & Export
- 💾 **Local Persistence** — All data saved to browser (localStorage)
- 📥 **Export** — JSON, CSV formats for backup
- 🔄 **Challenge Reset** — Start fresh anytime
- 📱 **PWA Ready** — Install on home screen (iOS/Android)

### Offline
- 📡 **Fully Offline** — App works without internet, syncs data on return
- 💾 **Service Worker** — Automatic asset caching
- ⚡ **No Build Step** — Deploy as-is (static files only)

## 🚀 Quick Start

### Option 1: Local Development (Recommended)
```bash
# Clone repo
git clone https://github.com/YOUR-USERNAME/juris-30-day.git
cd juris-30-day

# Open in browser (no build needed!)
open index.html
# OR
python -m http.server 8000  # and visit http://localhost:8000
```

### Option 2: Deploy to GitHub Pages (Free)

1. **Create GitHub repo** (name it anything, e.g. `juris-30-day`)
2. **Upload all files** from this folder
3. **Enable GitHub Pages** in repo Settings → Pages → Source → Main branch
4. **Visit** `https://YOUR-USERNAME.github.io/juris-30-day`

### Option 3: Deploy to Vercel (Free, Recommended)

1. **Fork or clone repo** to GitHub
2. **Visit** https://vercel.com and click "Import Project"
3. **Select your GitHub repo** and click Import
4. **Done!** Vercel auto-deploys on every push

### Option 4: Deploy to Netlify (Free)

1. **Create Netlify account** (netlify.com)
2. **Drag & drop** this folder onto Netlify's deploy zone
3. **Instant URL** generated, or **connect GitHub** for auto-deploy

## 📱 Install as PWA

### On iPhone / iPad
1. Open app in **Safari**
2. Tap **Share** → **Add to Home Screen**
3. Name it & tap **Add**
4. Icon appears on home screen; opens full-screen app

### On Android
1. Open app in **Chrome**
2. Tap **⋮ (menu)** → **Install app**
3. Confirm
4. Opens like native app

### On Desktop
1. Chrome: Click **install icon** in address bar (or ⋮ → **Install**)
2. Edge: Similar process
3. Firefox: Not yet supported

## 🔧 Configuration

All game settings live in **`js/constants.js`**. No rebuild needed — just edit and reload:

```javascript
// Tweak daily targets
export const TARGETS = {
  calories: 1200,  // ← Change here
  waterMl: 4000,
  steps: 20000,
  sleepMinH: 7.5,
  sleepMaxH: 9,
};

// Adjust XP rewards
export const XP_REWARDS = {
  calories: 20,    // ← Change here
  water: 10,
  // ... all 8 goals
};
```

Challenge length defaults to 30 days. To change:

```javascript
// In js/constants.js
export const CHALLENGE_LENGTH_DAYS = 21;  // 21-day challenge instead
```

## 📂 Project Structure

```
juris-30-day/
├── index.html              # App shell (nav, views mount here)
├── manifest.json           # PWA metadata
├── service-worker.js       # Offline caching
├── css/
│   └── style.css          # All styling (themes, dark mode, responsive)
├── js/
│   ├── app.js             # Main app logic, routing, initialization
│   ├── state.js           # Central store, persistence (localStorage)
│   ├── constants.js       # Configuration (editable)
│   ├── utils.js           # Helper functions
│   ├── i18n.js            # Strings (English/Arabic)
│   ├── i18n_helper.js     # i18n utilities
│   ├── achievements.js    # Achievement definitions
│   ├── coach.js           # Coaching messages & struggling logic
│   ├── sound.js           # Web Audio API effects
│   ├── celebrate.js       # Animations & celebrations
│   └── render/
│       ├── views.js       # Home, calendar, stats, progress, profile
│       └── goalcard.js    # Reusable goal card component
└── README.md              # This file
```

## 💾 Data Model

All data persists in browser `localStorage` under key `juris30day:v1`.

**State shape:**
```javascript
{
  version: 1,
  profile: { name, email, photoDataUrl, createdAt },
  onboarded: true,
  settings: { theme, appearance, language, sounds, ... },
  challenge: { startDate, length },
  days: {
    "1": { dateISO, dayIndex, calories, noSugar, noBread, water, steps, workout, photo, sleep, mood, journal, xpEarned },
    "2": { ... },
  },
  weight: [ { id, date, kg }, ... ],
  measurements: [ { id, date, waist, hips, chest, arms, thighs }, ... ],
  weeklyReviews: { "1": { completion, bestHabit, ..., savedAt }, ... },
  achievements: { unlocked: { "first_day": timestamp, ... } },
  unlockedMilestones: [ 3, 7, 14, 21, 30 ],
}
```

## 🔐 Privacy & Security

- **No backend** — 100% client-side, all data stays on your device
- **No analytics** — Zero tracking
- **No login** — No servers, no accounts (optional future: Firebase auth)
- **Exportable** — Download your data anytime (JSON/CSV)

**Future enhancement (optional):** Wire up Firebase for cross-device sync. Instructions:
1. Create Firebase project
2. Enable Firestore & Storage
3. Copy config to `js/firebase-config.js`
4. Update `js/state.js` to sync on save

## 🎨 Theming

The app includes 5 built-in themes + dark mode. Themes are pure CSS variables — add a new theme in **`css/style.css`**:

```css
:root.theme-mytheme {
  --c-primary: #your-color;
  --c-bg: #your-bg;
  --c-text: #your-text;
  /* ... other vars */
}
```

Then add to `constants.js`:
```javascript
export const THEMES = [
  { id: 'mytheme', label: 'My Theme' },
  // ...
];
```

## 🌍 Languages

Strings live in **`js/i18n.js`**. Add a new language (e.g. Spanish):

```javascript
export const STRINGS = {
  es: {
    appName: "Día 30 de Juri",
    day_of: (d, total) => `DÍA ${d} / ${total}`,
    // ... all other keys
  },
  // ...
};
```

Then add to settings:
```javascript
// In app.js renderProfile settingRow for language
select.appendChild(el('option', { value: 'es' }, 'Español'));
```

## 🐛 Troubleshooting

### **App not loading**
- Clear browser cache (Cmd+Shift+Delete)
- Hard refresh (Cmd+Shift+R on Mac, Ctrl+Shift+R on Windows)
- Check browser console for errors (F12)

### **Data not saving**
- Check localStorage is enabled
- Verify browser supports localStorage (all modern browsers do)
- Inspect `localStorage.getItem('juris30day:v1')` in console

### **PWA not installing**
- On iPhone: Ensure HTTPS (GitHub Pages/Vercel auto-HTTPS)
- On Android: Make sure Chrome is up-to-date
- Check manifest.json is served (browser console → Network tab)

### **Offline not working**
- Service Worker requires HTTPS (localhost works)
- Wait ~10 sec after first load for SW to register
- Refresh page if SW doesn't register

## 🤝 Contributing

This is a single-developer app. To customize:

1. **Edit constants** (`js/constants.js`) for targets/XP/length
2. **Edit strings** (`js/i18n.js`) for copy or translations
3. **Edit themes** (`css/style.css`) for colors
4. **Fork & deploy** your version

## 📜 License

Public domain / MIT — use freely.

## 🎯 Next Steps (Future Enhancements)

- [ ] Firebase authentication & cloud sync
- [ ] Apple Health / Google Fit integration (manual entry only for now)
- [ ] Backup to cloud (Google Drive, iCloud)
- [ ] Social sharing (post results)
- [ ] Habit library (pre-built challenges)
- [ ] Group challenges (competitive)
- [ ] Mobile app (React Native)

## 🌸 Support

Found a bug? Have feedback?
- Open an issue on GitHub
- Email: [add contact here]

---

**Built with ❤️ for humans who want to trust themselves again.**

*One honest day at a time.*
