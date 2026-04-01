# 🤖 BrokeBuddy — AI Financial Survival Guide for Students

> *Your AI-powered money coach, always in your pocket.*

Built for Hackathon 2025 · Fintech AI Track · Team Algoholics

---

## 📌 Overview

BrokeBuddy is a **fully-featured, AI-powered personal finance app** designed specifically for college students aged 17–25 managing limited monthly budgets. Unlike generic expense trackers, BrokeBuddy combines intelligent spending analysis, balance forecasting, and a real AI chat assistant to help students make smarter financial decisions before it's too late.

**The problem:** 73% of students overspend every month, with zero visibility into their patterns, no personalized guidance, and no early warnings.

**The solution:** BrokeBuddy doesn't just log expenses — it thinks, predicts, and coaches.

---

## ✨ Core Features

| Feature | Description |
|--------|-------------|
| 📊 **Smart Dashboard** | Real-time financial health score (0–100), balance overview, 7-day spending chart |
| 🏷️ **Auto-Categorization** | Expenses auto-tagged: Food, Transport, Subscriptions, Shopping, etc. |
| 🤖 **AI Chat Assistant** | Ask "Can I afford this?", "Where am I overspending?" — powered by Claude AI |
| ⚡ **Balance Forecasting** | Predicts when your balance will hit zero based on last 30 days of spending |
| 🎯 **Savings Goals** | Create goals, track progress, contribute incrementally |
| 🎮 **Gamified Streaks** | Daily tracking streaks, 30-day activity grid, achievement badges |
| 📈 **Analytics** | Monthly trend charts, category breakdown, spending stats, prediction timeline |
| 💡 **Smart Budgets** | Set per-category budgets with 50-30-20 rule auto-suggestion |
| 💜 **Mood Tracker** | Log emotional states and discover correlation with spending behavior |
| 🔐 **Auth System** | Secure login/signup with localStorage persistence |

---

## 🚀 Unique Innovations (Not in Competing Apps)

### 1. 🧠 Emotion-Spending Correlation Engine
Track your mood daily and BrokeBuddy surfaces patterns like "You spend ₹420 more when stressed." Helps identify emotional spending triggers.

### 2. ⚡ AI Balance Runway Prediction
Not just current balance — the app calculates exactly how many days until you run out, based on your rolling 30-day average daily spend. Shows a visual timeline.

### 3. 💡 50-30-20 Auto-Budget Applier
One click applies the optimal budget rule across all categories based on your actual income. No manual calculation needed.

### 4. 🎯 AI Insights Engine
Automatic detection of: weekend splurge patterns, subscription overload, top overspending categories — shown as actionable insight cards on every dashboard load.

### 5. 🔥 Gamified Achievement System
6 unlockable badges tied to real financial milestones (100 transactions, 7-day streak, health score 80+, etc.) to build long-term habit formation.

### 6. 📱 Recurring Expense Tagging
Flag expenses as recurring to separate fixed costs from discretionary spending for more accurate predictions.

---

## 🛠️ Tech Stack

```
Frontend:     React 18 (CDN), Vanilla CSS with CSS Variables
AI Engine:    Claude Sonnet (Anthropic API) via /v1/messages
Storage:      localStorage (key-value DB layer)
Fonts:        Orbitron, Share Tech Mono, Rajdhani (Google Fonts)
Deployment:   Any static host (no build step required)
```

---

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────┐
│                    BROKEBUDDY APP                        │
├─────────────────────────────────────────────────────────┤
│  UI Layer (React Components)                             │
│  ├── AuthScreen + Onboarding                            │
│  ├── Dashboard (Health Score, Charts, Insights)         │
│  ├── Expenses (CRUD, Filter, Search)                    │
│  ├── Analytics (Trends, Forecasting, Timeline)          │
│  ├── AI Chat (Claude API Integration)                   │
│  ├── Goals & Gamification (Streaks, Achievements)       │
│  ├── Mood Tracker (Emotion-Spend Correlation)           │
│  ├── Smart Budgets (50-30-20 Rule)                      │
│  └── Settings (Profile, Data Management)               │
├─────────────────────────────────────────────────────────┤
│  State Layer (React Context API)                         │
│  ├── expenses[], goals[], income, balance               │
│  └── CRUD functions with localStorage sync             │
├─────────────────────────────────────────────────────────┤
│  Data Layer (localStorage via DB utility)                │
│  ├── bb_user, bb_expenses, bb_goals                     │
│  ├── bb_budgets, bb_moods, bb_streak                    │
│  └── bb_income, bb_balance, bb_onboarded               │
├─────────────────────────────────────────────────────────┤
│  AI Layer (Anthropic Claude API)                         │
│  └── /v1/messages with financial context injection      │
└─────────────────────────────────────────────────────────┘
```

---

## 📁 Project Structure

```
brokebuddy/
├── index.html          # Complete single-file application
└── README.md           # This file
```

> The app is intentionally a single HTML file for maximum portability and zero-setup deployment. For production, split into React components with Vite/Next.js (see Extending section).

---

## ⚙️ Setup & Running Locally

### Option A: Direct (Zero Setup)
```bash
# Just open the file in any browser
open index.html
# Or serve it:
npx serve .
# Visit http://localhost:3000
```

### Option B: Using Python
```bash
python3 -m http.server 8080
# Visit http://localhost:8080
```

### Option C: VS Code Live Server
1. Install "Live Server" extension
2. Right-click `index.html` → "Open with Live Server"

### First-Time Setup
1. Open the app
2. Click **SIGN UP** and create an account
3. Enter your name, email, and monthly income/allowance
4. Complete the 4-step onboarding tour
5. Start adding expenses!

---

## 🤖 AI Chat Setup

The AI chat uses the Anthropic Claude API. To enable it:

1. Get an API key from [console.anthropic.com](https://console.anthropic.com)
2. The app calls `https://api.anthropic.com/v1/messages` directly from the browser
3. **For production:** Route through a backend proxy to protect your API key

> Without an API key, the chat still works with fallback responses.

---

## 🗄️ Data Schema

```javascript
// User
{ id, name, email, income, tier, joinedAt }

// Expense
{ id, amount, category, note, date, isRecurring, createdAt }

// Goal
{ id, name, target, current, category, createdAt }

// Mood Entry
{ id, date, mood, note, spentToday }

// Budgets (object)
{ Food: 2000, Transport: 500, ... }
```

---

## 📊 Revenue Model

| Tier | Price | Features |
|------|-------|----------|
| Free | ₹0/mo | Basic tracking, manual categories, monthly summary |
| Pro | ₹99/mo | Full AI chat, predictive alerts, weekly reports, health score goals |
| B2B | Custom | API licensing, campus ambassador programs, fintech integrations |

---

## 🚀 Deployment

### Vercel (Recommended)
```bash
npm i -g vercel
vercel --prod
```

### Netlify
```bash
# Drag and drop the folder to netlify.com/drop
# Or:
npm i -g netlify-cli
netlify deploy --prod --dir .
```

### GitHub Pages
```bash
git init && git add . && git commit -m "BrokeBuddy"
git branch -M main
git remote add origin <your-repo>
git push -u origin main
# Enable Pages in repo Settings → Pages → Deploy from main
```

---

## 🔮 Roadmap

| Version | Feature |
|---------|---------|
| v1.5 | UPI/Bank statement import (PDF parsing) |
| v2.0 | Push notifications for budget warnings |
| v2.5 | CIBIL score tracking & improvement tips |
| v3.0 | AI auto-budget allocation |
| v4.0 | Campus peer savings groups & challenges |

---

## 🧩 Extending the App

To convert to a full React + backend app:

```bash
# Scaffold with Vite
npm create vite@latest brokebuddy -- --template react
cd brokebuddy && npm install

# Recommended additions:
npm install @supabase/supabase-js   # Database + Auth
npm install recharts                # Charts
npm install @anthropic-ai/sdk       # AI SDK
npm install react-router-dom        # Routing
npm install zustand                 # State management
```

Replace `localStorage` calls with Supabase client calls. Each `DB.set/get` maps to a Supabase table insert/select.

---

## 👥 Team

**Team Algoholics** — Hackathon 2025, Fintech AI Track

- Anushka Karwa
- Drishti Makkar  
- Rudra Chauhan

---

## 📄 License

MIT — free to use, modify, and deploy.
