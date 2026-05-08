<div align="center">

# ⚡ SparkChat

**Random 5-minute sparks with strangers worldwide.**

Text · Video · Voice · 5 Fun Modes · Real-time Matching

[![Live](https://img.shields.io/badge/Live-sparkchat--app.vercel.app-FF5C1A?style=flat-square&logo=vercel)](https://sparkchat-app.vercel.app)
[![API Health](https://img.shields.io/badge/API-Health-green?style=flat-square)](https://sparkchat-app.onrender.com/health)
[![Next.js](https://img.shields.io/badge/Next.js-14-black?style=flat-square&logo=next.js)](https://nextjs.org)
[![Socket.io](https://img.shields.io/badge/Socket.io-realtime-010101?style=flat-square&logo=socket.io)](https://socket.io)
[![Made in India](https://img.shields.io/badge/Made%20in-India%20🇮🇳-orange?style=flat-square)](https://github.com/kshitijsrivastavaa/sparkchat-app)

[🚀 Try SparkChat](https://sparkchat-app.vercel.app) · [⭐ Star on GitHub](https://github.com/kshitijsrivastavaa/sparkchat-app)

</div>

---

## ✨ Features

| Feature | Description |
|---|---|
| ⚡ **Instant Matching** | Real-time socket matchmaking — no swiping, no waiting |
| 💬 **Text Chat** | Live messaging with typing indicators and emoji reactions |
| 📹 **Video Chat** | Peer-to-peer WebRTC video — no server relay |
| 🎙️ **Voice Chat** | Crystal-clear audio calls via real WebRTC audio |
| 🎭 **5 Fun Modes** | Debate · Roast · Quiz · Opinion · Random |
| ⏱️ **5-Min Timer** | Countdown keeps conversations sharp and fun |
| 🌍 **180+ Countries** | Match by country and language preference |
| 🚩 **Report System** | Safe, moderated platform with user reports |
| ⭐ **Star Ratings** | Rate your spark after each chat session |
| 👤 **Guest Mode** | No signup needed to try the app |
| 💎 **Premium Tier** | Razorpay-powered subscriptions built in |
| 🌙 **Dark Theme** | Sleek dark UI throughout the entire app |

---

## 🛠️ Tech Stack

**Frontend:** Next.js 14 · React 18 · WebRTC

**Backend:** Node.js · Express · Socket.io

**Database:** Supabase · PostgreSQL

**Auth & Payments:** JWT · Razorpay

**Infra:** Vercel (frontend) · Render (backend)

---

## 🚀 Quick Start

### 1. Clone & install

```bash
git clone https://github.com/kshitijsrivastavaa/sparkchat-app.git
cd sparkchat-app && npm install
```

### 2. Set up Supabase (free)

Go to [supabase.com](https://supabase.com) → New Project → SQL Editor → paste `database.sql` → Run. Then copy your Project URL + keys.

### 3. Configure environment

Create a `.env.local` file:

```env
NEXT_PUBLIC_SUPABASE_URL=https://xxxx.supabase.co
NEXT_PUBLIC_SUPABASE_ANON_KEY=eyJ...
SUPABASE_SERVICE_ROLE_KEY=eyJ...
JWT_SECRET=your_32_char_secret_here
SOCKET_PORT=3001
NEXT_PUBLIC_SOCKET_URL=http://localhost:3001
NEXT_PUBLIC_APP_URL=http://localhost:3000
```

### 4. Start both servers

**Terminal 1 — Backend:**
```bash
node server/index.js
# SparkChat server running on port 3001
```

**Terminal 2 — Frontend:**
```bash
npm run dev
# → open http://localhost:3000 🎉
```

---

## 🗄️ Database Schema

| Table | Description |
|---|---|
| `users` | Profiles, stats, premium status, reputation |
| `chat_sessions` | Match history, type, mode, duration |
| `messages` | Chat message logs per session |
| `ratings` | Post-chat 1–5 star ratings |
| `reports` | User report + moderation system |
| `payments` | Razorpay transaction records |
| `online_users` | Real-time presence & socket tracking |

---

## 🌐 Deploy

### Frontend → Vercel

```bash
npm install -g vercel
vercel
# Add all .env.local vars in Vercel → Settings → Environment Variables
```

### Backend → Render

New Web Service → connect repo → Start Command: `node server/index.js` → add env vars → Deploy

After backend deploy, update in Vercel:
```env
NEXT_PUBLIC_SOCKET_URL=https://your-app.onrender.com
```

---

## 🗺️ Roadmap

- [ ] Mobile app (React Native)
- [ ] Interest-based matching
- [ ] In-chat language translation
- [ ] Group spark rooms (3–5 people)
- [ ] Spark history & favourites
- [ ] AI-powered conversation starters
- [ ] Verified student / college mode

---

<div align="center">

**⚡ SparkChat** · Built with passion in India 🇮🇳 · MIT License

[Live App](https://sparkchat-app.vercel.app) · [GitHub](https://github.com/kshitijsrivastavaa/sparkchat-app) · [API Health](https://sparkchat-app.onrender.com/health)

</div>
