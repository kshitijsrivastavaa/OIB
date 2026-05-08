# ⚡ SparkChat

> **Random 5-minute sparks with strangers worldwide.**
> Text · Video · Voice · 5 Fun Modes · Real-time Matching

[![Live Demo](https://img.shields.io/badge/🚀_Live_Demo-sparkchat--app.vercel.app-orange?style=for-the-badge)](https://sparkchat-app.vercel.app)
[![Backend](https://img.shields.io/badge/⚙️_Backend-sparkchat--app.onrender.com-blueviolet?style=for-the-badge)](https://sparkchat-app.onrender.com/health)
[![Next.js](https://img.shields.io/badge/Next.js-14.2-black?style=for-the-badge&logo=next.js)](https://nextjs.org)
[![Socket.io](https://img.shields.io/badge/Socket.io-4.7-white?style=for-the-badge&logo=socket.io)](https://socket.io)
[![Supabase](https://img.shields.io/badge/Supabase-Database-3ECF8E?style=for-the-badge&logo=supabase)](https://supabase.com)

---

<!-- Add your hero screenshot/demo GIF here -->
<!-- ![SparkChat Demo](./demo.gif) -->

---

## 🔥 What is SparkChat?

SparkChat connects you with a random stranger for exactly **5 minutes** — no followers, no algorithms, no pressure. Just real, spontaneous conversation.

Pick your vibe, get matched instantly, and spark something new.

---

## ✨ Features

| Feature | Description |
|---|---|
| ⚡ **Instant Matching** | Real-time socket-based matchmaking |
| 💬 **Text Chat** | Live messaging with typing indicators |
| 📹 **Video Chat** | Peer-to-peer WebRTC video calls |
| 🎙️ **Voice Chat** | Crystal-clear audio calls |
| 🎭 **5 Fun Modes** | Debate · Roast · Quiz · Opinion · Random |
| ⏱️ **5-Min Timer** | Countdown keeps convos sharp |
| 😂 **Emoji Reactions** | React in real time |
| 🌍 **180+ Countries** | Match by country & language |
| ⭐ **Star Ratings** | Rate your spark after each chat |
| 🚩 **Report System** | Safe, moderated platform |
| 👤 **Guest Mode** | No signup needed to try |
| 💎 **Premium Tier** | Razorpay-powered subscription |

---

## 🛠️ Tech Stack

```
Frontend    →  Next.js 14 · React 18 · Socket.io Client · WebRTC
Backend     →  Node.js · Express · Socket.io · JWT
Database    →  Supabase (PostgreSQL) · Row Level Security
Auth        →  Custom JWT + Supabase Auth
Payments    →  Razorpay
Deploy      →  Vercel (Frontend) · Render (Backend)
```

---

## 📁 Project Structure

```
sparkchat/
├── app/
│   ├── api/
│   │   ├── payment/
│   │   │   ├── create-order/     ← Razorpay order creation
│   │   │   └── verify/           ← Payment verification
│   │   └── online-count/         ← Live user counter
│   ├── components/
│   │   ├── Landing.js            ← Home screen
│   │   ├── Auth.js               ← Login + Signup
│   │   ├── Setup.js              ← Chat preferences
│   │   ├── Waiting.js            ← Real-time matchmaking
│   │   ├── Chat.js               ← Text + Video + Voice
│   │   ├── EndScreen.js          ← Rating + Payment
│   │   └── Profile.js            ← User stats
│   ├── page.js                   ← App router
│   ├── layout.js                 ← Root layout
│   └── globals.css               ← Dark theme
├── hooks/
│   ├── useSocket.js              ← Socket.io client
│   └── useWebRTC.js              ← WebRTC peer connections
├── lib/
│   ├── supabase.js               ← DB client + helpers
│   └── AuthContext.js            ← Auth provider
├── server/
│   └── index.js                  ← Express + Socket.io backend
├── database.sql                  ← Full DB schema
└── .env.example                  ← Environment template
```

---

## 🚀 Run Locally

### Prerequisites
- Node.js 18+
- A [Supabase](https://supabase.com) account (free)

### 1. Clone & Install

```bash
git clone https://github.com/kshitijsrivastavaa/sparkchat-app.git
cd sparkchat-app
npm install
```

### 2. Set Up Supabase

1. Create a new project at [supabase.com](https://supabase.com)
2. Go to **SQL Editor** → paste contents of `database.sql` → **Run**
3. Go to **Settings → API** → copy your keys

### 3. Configure Environment

```bash
cp .env.example .env.local
```

Fill in `.env.local`:

```env
NEXT_PUBLIC_SUPABASE_URL=https://xxxx.supabase.co
NEXT_PUBLIC_SUPABASE_ANON_KEY=eyJ...
SUPABASE_SERVICE_ROLE_KEY=eyJ...
JWT_SECRET=your_32_char_secret_here
RAZORPAY_KEY_ID=rzp_test_xxx         # optional
RAZORPAY_KEY_SECRET=xxx              # optional
NEXT_PUBLIC_RAZORPAY_KEY_ID=rzp_test_xxx
SOCKET_PORT=3001
NEXT_PUBLIC_SOCKET_URL=http://localhost:3001
NEXT_PUBLIC_APP_URL=http://localhost:3000
```

### 4. Run

Open **two terminals:**

```bash
# Terminal 1 — Backend
node server/index.js
# → SparkChat server running on port 3001

# Terminal 2 — Frontend
npm run dev
# → http://localhost:3000
```

Open [http://localhost:3000](http://localhost:3000) — you're live! 🎉

---

## ☁️ Deploy

### Frontend → Vercel

```bash
npm install -g vercel
vercel
```

Add all `.env.local` variables in Vercel → **Settings → Environment Variables**.

### Backend → Render

1. Go to [render.com](https://render.com) → **New Web Service**
2. Connect your GitHub repo
3. Set:
   - **Start Command:** `node server/index.js`
4. Add environment variables
5. Deploy!

After deploying, update in Vercel:
```
NEXT_PUBLIC_SOCKET_URL=https://your-app.onrender.com
```

---

## 💰 Razorpay Setup

1. Create account at [razorpay.com](https://razorpay.com)
2. Complete KYC (PAN + bank account)
3. Go to **Settings → API Keys**
4. Copy keys into `.env.local`

---

## 🗄️ Database Schema

| Table | Purpose |
|---|---|
| `users` | Profiles, stats, premium status |
| `chat_sessions` | Match history & metadata |
| `messages` | Chat message logs |
| `ratings` | Post-chat star ratings |
| `reports` | User report system |
| `payments` | Razorpay transaction records |
| `online_users` | Real-time presence tracking |

---

## 🔮 Roadmap

- [ ] Mobile app (React Native)
- [ ] Interest-based matching
- [ ] Language translation in chat
- [ ] Group spark rooms (3-5 people)
- [ ] Spark history & favourites
- [ ] AI-powered conversation starters
- [ ] Verified student mode

---

## 🤝 Contributing

Pull requests are welcome! For major changes, open an issue first.

---

## 📄 License

MIT © [Kshitij Srivastava](https://github.com/kshitijsrivastavaa)

---

<div align="center">

Built with ⚡ in India 🇮🇳

**[sparkchat-app.vercel.app](https://sparkchat-app.vercel.app)**

</div>
