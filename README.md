<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=DM+Mono:wght@400;500&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
:root{
  --o:#FF5C1A;--o2:#FF5C1A18;--o3:#FF5C1A40;
  --bg:#0A0A0A;--bg2:#111;--bg3:#161616;
  --bd:#252525;--text:#F0EDE8;--mut:#777770;
  --mono:'DM Mono',monospace;--sans:'DM Sans',sans-serif;--disp:'Syne',sans-serif;
}
html{scroll-behavior:smooth}
body{background:var(--bg);color:var(--text);font-family:var(--sans);font-size:15px;line-height:1.7;max-width:860px;margin:0 auto;padding:0 24px 100px;overflow-x:hidden}

@keyframes fadeUp{from{opacity:0;transform:translateY(24px)}to{opacity:1;transform:translateY(0)}}
@keyframes pulseRing{0%{transform:scale(1);opacity:.5}100%{transform:scale(1.7);opacity:0}}
@keyframes boltFlash{0%,100%{opacity:1}50%{opacity:.35}}
@keyframes scan{0%{transform:translateY(-100%)}100%{transform:translateY(500%)}}
@keyframes ticker{0%{transform:translateX(0)}100%{transform:translateX(-50%)}}
@keyframes dotBlink{0%,100%{opacity:1}50%{opacity:.15}}
@keyframes shimmer{from{background-position:-200% center}to{background-position:200% center}}
@keyframes float{0%,100%{transform:translateY(0)}50%{transform:translateY(-6px)}}

.fu{animation:fadeUp .65s ease both}
.d1{animation-delay:.05s}.d2{animation-delay:.12s}.d3{animation-delay:.2s}
.d4{animation-delay:.28s}.d5{animation-delay:.36s}.d6{animation-delay:.44s}

/* HERO */
.hero{text-align:center;padding:72px 0 52px;position:relative}
.bolt-wrap{display:inline-flex;align-items:center;justify-content:center;width:68px;height:68px;margin-bottom:20px;position:relative;animation:float 3s ease-in-out infinite}
.bolt-wrap::before,.bolt-wrap::after{content:'';position:absolute;inset:0;border-radius:50%;border:1.5px solid var(--o);animation:pulseRing 2.2s ease-out infinite}
.bolt-wrap::after{animation-delay:1.1s}
.bolt{font-size:34px;animation:boltFlash 2.5s ease-in-out infinite;position:relative;z-index:1}
h1{font-family:var(--disp);font-size:clamp(52px,9vw,88px);font-weight:800;letter-spacing:-3px;line-height:.95;background:linear-gradient(135deg,#FF5C1A 0%,#FF9A5C 45%,#FFCBA4 85%);-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;margin-bottom:14px}
.tagline{font-size:17px;color:var(--mut);font-weight:300;letter-spacing:.2px;margin-bottom:28px}
.tagline strong{color:var(--text);font-weight:500}

/* BADGES */
.badges{display:flex;flex-wrap:wrap;gap:7px;justify-content:center;margin-bottom:32px}
.badge{display:inline-flex;align-items:center;gap:5px;padding:5px 12px;border-radius:20px;font-family:var(--mono);font-size:11.5px;border:1px solid var(--bd);background:var(--bg2);color:var(--mut);text-decoration:none;transition:border-color .2s,color .2s}
.badge:hover{border-color:var(--o);color:var(--o)}
.bdot{width:6px;height:6px;border-radius:50%;background:var(--o);animation:dotBlink 1.6s ease-in-out infinite}

/* BUTTONS */
.ctas{display:flex;gap:10px;justify-content:center;flex-wrap:wrap}
.btn-p{display:inline-flex;align-items:center;gap:7px;padding:11px 26px;background:var(--o);color:#fff;border-radius:8px;font-family:var(--disp);font-weight:700;font-size:14px;text-decoration:none;transition:opacity .2s,transform .15s}
.btn-p:hover{opacity:.85;transform:translateY(-1px)}
.btn-o{display:inline-flex;align-items:center;gap:7px;padding:11px 26px;border:1px solid var(--bd);color:var(--text);border-radius:8px;font-family:var(--disp);font-weight:700;font-size:14px;text-decoration:none;transition:border-color .2s,transform .15s}
.btn-o:hover{border-color:var(--o);transform:translateY(-1px)}

/* SECTIONS */
.sec{margin:64px 0 0}
.sec-lbl{font-family:var(--mono);font-size:10.5px;letter-spacing:2.5px;text-transform:uppercase;color:var(--o);margin-bottom:6px}
.sec-title{font-family:var(--disp);font-size:26px;font-weight:700;letter-spacing:-.5px;margin-bottom:20px;color:var(--text)}
.divider{height:1px;background:linear-gradient(90deg,transparent,var(--bd),transparent);margin:52px 0}
p{color:var(--mut);font-size:14.5px;line-height:1.8}
strong{color:var(--text);font-weight:500}
code{font-family:var(--mono);font-size:12px;background:var(--bg3);padding:2px 7px;border-radius:4px;border:1px solid var(--bd);color:var(--o)}

/* TICKER */
.ticker-wrap{overflow:hidden;border-top:1px solid var(--bd);border-bottom:1px solid var(--bd);padding:9px 0;margin:40px 0}
.ticker-inner{display:flex;white-space:nowrap;animation:ticker 24s linear infinite}
.ti{display:inline-flex;align-items:center;gap:7px;padding:0 24px;font-family:var(--mono);font-size:11px;color:var(--mut);text-transform:uppercase;letter-spacing:1px}
.ti .d{width:4px;height:4px;border-radius:50%;background:var(--o);opacity:.5}

/* SCREENSHOT GRID */
.ss-grid{display:grid;grid-template-columns:1fr 1fr;gap:10px;margin:20px 0}
.ss-slot{border-radius:12px;border:1px solid var(--bd);background:var(--bg2);aspect-ratio:16/9;overflow:hidden;position:relative;transition:border-color .2s,transform .2s;cursor:pointer}
.ss-slot:hover{border-color:var(--o);transform:scale(1.015)}
.ss-slot img{width:100%;height:100%;object-fit:cover;display:block}
.ph{width:100%;height:100%;display:flex;flex-direction:column;align-items:center;justify-content:center;gap:9px}
.ph-icon{font-size:26px;opacity:.3}
.ph-txt{font-family:var(--mono);font-size:10px;letter-spacing:1.5px;color:var(--mut);opacity:.5}
.ph-label{font-family:var(--mono);font-size:9.5px;color:var(--o);opacity:.6;letter-spacing:1px}
.scanline{position:absolute;left:0;right:0;height:35%;background:linear-gradient(to bottom,transparent,rgba(255,92,26,.04),transparent);animation:scan 3.5s ease-in-out infinite;pointer-events:none}

/* VIDEO */
.vid-slot{border-radius:12px;border:1.5px dashed var(--bd);background:var(--bg2);aspect-ratio:16/9;display:flex;flex-direction:column;align-items:center;justify-content:center;gap:12px;position:relative;overflow:hidden;cursor:pointer;transition:border-color .2s;margin:20px 0}
.vid-slot:hover{border-color:var(--o)}
.play-btn{width:56px;height:56px;border-radius:50%;background:var(--o);display:flex;align-items:center;justify-content:center;font-size:20px;transition:transform .2s}
.vid-slot:hover .play-btn{transform:scale(1.1)}
.vid-lbl{text-align:center}
.vid-lbl strong{display:block;font-size:14px;color:var(--text);margin-bottom:3px;font-family:var(--disp)}
.vid-lbl span{font-family:var(--mono);font-size:11px;color:var(--mut)}
.hint{font-size:11px;text-align:center;margin-top:6px;opacity:.35;font-family:var(--mono);color:var(--mut)}

/* FEATURES */
.feat-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(220px,1fr));gap:10px}
.fc{background:var(--bg2);border:1px solid var(--bd);border-radius:10px;padding:16px 18px;transition:border-color .2s,transform .2s}
.fc:hover{border-color:var(--o3);transform:translateY(-2px)}
.fc-icon{font-size:20px;margin-bottom:9px}
.fc-title{font-family:var(--disp);font-weight:600;font-size:13.5px;color:var(--text);margin-bottom:4px}
.fc-desc{font-size:12.5px;color:var(--mut);line-height:1.55}

/* STACK */
.stack-row{display:flex;flex-wrap:wrap;gap:7px}
.sp{display:inline-flex;align-items:center;gap:5px;padding:5px 13px;border:1px solid var(--bd);border-radius:6px;font-family:var(--mono);font-size:12px;color:var(--mut);background:var(--bg2)}
.sp .d{width:5px;height:5px;border-radius:50%;background:var(--o)}

/* CODE */
pre{background:var(--bg3);border:1px solid var(--bd);border-radius:10px;padding:18px 20px;overflow-x:auto;font-family:var(--mono);font-size:12.5px;line-height:1.75;color:#C0BDB5;position:relative}
.ch{display:flex;align-items:center;justify-content:space-between;padding:9px 16px;background:var(--bg3);border:1px solid var(--bd);border-bottom:none;border-radius:10px 10px 0 0;font-family:var(--mono);font-size:10.5px;color:var(--mut)}
.ch+pre{border-radius:0 0 10px 10px;margin:0}
.dots{display:flex;gap:5px}
.dots span{width:10px;height:10px;border-radius:50%}
.r{background:#FF5F57}.y{background:#FEBC2E}.g{background:#28C840}
.cm{color:var(--mut)}.co{color:var(--o)}.cg{color:#5FBD60}.cy{color:#E6C84A}.cw{color:#C0BDB5}

/* STEPS */
.steps{display:flex;flex-direction:column}
.step{display:flex;gap:18px;padding:18px 0;position:relative}
.step::before{content:'';position:absolute;left:18px;top:50px;bottom:-4px;width:1px;background:var(--bd)}
.step:last-child::before{display:none}
.snum{width:38px;height:38px;border-radius:50%;border:1px solid var(--bd);background:var(--bg2);display:flex;align-items:center;justify-content:center;font-family:var(--mono);font-size:12px;color:var(--o);flex-shrink:0;position:relative;z-index:1}
.sc{flex:1;padding-top:7px}
.st{font-family:var(--disp);font-weight:600;font-size:14.5px;margin-bottom:5px}
.sd{font-size:13px;color:var(--mut)}

/* ROADMAP */
.rm{display:flex;flex-direction:column;gap:8px}
.rmi{display:flex;align-items:center;gap:11px;padding:11px 15px;border:1px solid var(--bd);border-radius:8px;background:var(--bg2);font-size:13.5px;color:var(--mut);transition:border-color .2s,color .2s}
.rmi:hover{border-color:var(--o3);color:var(--text)}
.ribox{width:15px;height:15px;border:1.5px solid var(--bd);border-radius:3px;flex-shrink:0}

/* TABLE */
table{width:100%;border-collapse:collapse;margin:14px 0}
th{text-align:left;font-family:var(--mono);font-size:10.5px;letter-spacing:1px;text-transform:uppercase;color:var(--mut);padding:9px 13px;border-bottom:1px solid var(--bd)}
td{padding:10px 13px;font-size:13px;border-bottom:1px solid var(--bd);color:var(--text)}
tr:last-child td{border-bottom:none}
tr:hover td{background:var(--bg2)}
.ck{color:var(--o);font-weight:700}

/* DB GRID */
.db-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(180px,1fr));gap:8px}
.db-card{background:var(--bg2);border:1px solid var(--bd);border-radius:8px;padding:13px 15px;transition:border-color .2s}
.db-card:hover{border-color:var(--o3)}
.db-name{font-family:var(--mono);font-size:12px;color:var(--o);margin-bottom:4px}
.db-desc{font-size:12px;color:var(--mut);line-height:1.4}

/* FOOTER */
.footer{text-align:center;padding:56px 0 0;color:var(--mut);font-size:12.5px}
.fbrand{font-family:var(--disp);font-size:20px;font-weight:800;background:linear-gradient(135deg,#FF5C1A,#FF9A5C);-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;margin-bottom:6px}
.footer a{color:var(--o);text-decoration:none}
h3{font-family:var(--disp);font-weight:600;font-size:16px;margin:20px 0 8px;color:var(--text)}
</style>
</head>
<body>

<!-- HERO -->
<div class="hero fu d1">
  <div class="bolt-wrap"><span class="bolt">⚡</span></div>
  <h1>SparkChat</h1>
  <p class="tagline">Random <strong>5-minute</strong> sparks with strangers worldwide.<br>Text · Video · Voice · 5 Fun Modes · Real-time Matching</p>
  <div class="badges fu d2">
    <a class="badge" href="https://sparkchat-app.vercel.app" target="_blank"><span class="bdot"></span>Live · sparkchat-app.vercel.app</a>
    <a class="badge" href="https://sparkchat-app.onrender.com/health" target="_blank"><span class="bdot"></span>API Health</a>
    <span class="badge">Next.js 14</span>
    <span class="badge">Socket.io</span>
    <span class="badge">WebRTC</span>
    <span class="badge">Supabase</span>
    <span class="badge">🇮🇳 Made in India</span>
  </div>
  <div class="ctas fu d3">
    <a class="btn-p" href="https://sparkchat-app.vercel.app" target="_blank">🚀 Try SparkChat</a>
    <a class="btn-o" href="https://github.com/kshitijsrivastavaa/sparkchat-app" target="_blank">⭐ Star on GitHub</a>
  </div>
</div>

<!-- TICKER -->
<div class="ticker-wrap fu d3">
  <div class="ticker-inner">
    <span class="ti"><span class="d"></span>Text Chat</span><span class="ti"><span class="d"></span>Video Chat</span><span class="ti"><span class="d"></span>Voice Chat</span><span class="ti"><span class="d"></span>Debate Mode</span><span class="ti"><span class="d"></span>Roast Mode</span><span class="ti"><span class="d"></span>Quiz Mode</span><span class="ti"><span class="d"></span>Opinion Mode</span><span class="ti"><span class="d"></span>180+ Countries</span><span class="ti"><span class="d"></span>5-Min Timer</span><span class="ti"><span class="d"></span>Razorpay</span><span class="ti"><span class="d"></span>WebRTC P2P</span><span class="ti"><span class="d"></span>Real-time Matching</span>
    <span class="ti"><span class="d"></span>Text Chat</span><span class="ti"><span class="d"></span>Video Chat</span><span class="ti"><span class="d"></span>Voice Chat</span><span class="ti"><span class="d"></span>Debate Mode</span><span class="ti"><span class="d"></span>Roast Mode</span><span class="ti"><span class="d"></span>Quiz Mode</span><span class="ti"><span class="d"></span>Opinion Mode</span><span class="ti"><span class="d"></span>180+ Countries</span><span class="ti"><span class="d"></span>5-Min Timer</span><span class="ti"><span class="d"></span>Razorpay</span><span class="ti"><span class="d"></span>WebRTC P2P</span><span class="ti"><span class="d"></span>Real-time Matching</span>
  </div>
</div>

<!-- SCREENSHOTS -->
<div class="sec fu d3">
  <div class="sec-lbl">// screenshots</div>
  <div class="sec-title">See it in action</div>
  <div class="ss-grid">
    <div class="ss-slot">
      <!-- TO ADD: replace the ph div below with <img src="./screenshots/landing.png" alt="Landing"> -->
      <div class="ph">
        <div class="ph-icon">🖼</div>
        <div class="ph-txt">ADD SCREENSHOT</div>
        <div class="ph-label">Landing Page</div>
      </div>
      <div class="scanline"></div>
    </div>
    <div class="ss-slot">
      <!-- TO ADD: replace the ph div below with <img src="./screenshots/matching.png" alt="Matching"> -->
      <div class="ph">
        <div class="ph-icon">🖼</div>
        <div class="ph-txt">ADD SCREENSHOT</div>
        <div class="ph-label">Finding Match</div>
      </div>
      <div class="scanline"></div>
    </div>
    <div class="ss-slot">
      <!-- TO ADD: replace the ph div below with <img src="./screenshots/chat.png" alt="Chat"> -->
      <div class="ph">
        <div class="ph-icon">🖼</div>
        <div class="ph-txt">ADD SCREENSHOT</div>
        <div class="ph-label">Chat Screen</div>
      </div>
      <div class="scanline"></div>
    </div>
    <div class="ss-slot">
      <!-- TO ADD: replace the ph div below with <img src="./screenshots/video.png" alt="Video"> -->
      <div class="ph">
        <div class="ph-icon">🖼</div>
        <div class="ph-txt">ADD SCREENSHOT</div>
        <div class="ph-label">Video Call</div>
      </div>
      <div class="scanline"></div>
    </div>
  </div>
  <p class="hint">→ replace placeholder divs with &lt;img src="./screenshots/..."&gt;</p>
</div>

<!-- VIDEO DEMO -->
<div class="sec fu d4">
  <div class="sec-lbl">// live demo</div>
  <div class="sec-title">Watch it work</div>
  <!-- TO ADD: replace vid-slot with <iframe width="100%" style="aspect-ratio:16/9;border-radius:12px;border:none" src="YOUR_YOUTUBE_EMBED" allowfullscreen></iframe> -->
  <div class="vid-slot">
    <div class="scanline"></div>
    <div class="play-btn">▶</div>
    <div class="vid-lbl">
      <strong>Demo Video</strong>
      <span>Paste your YouTube / Loom embed here</span>
    </div>
  </div>
  <p class="hint">→ replace vid-slot div with your &lt;iframe&gt; embed</p>
</div>

<div class="divider"></div>

<!-- FEATURES -->
<div class="sec fu d4">
  <div class="sec-lbl">// features</div>
  <div class="sec-title">Everything packed in</div>
  <div class="feat-grid">
    <div class="fc"><div class="fc-icon">⚡</div><div class="fc-title">Instant Matching</div><div class="fc-desc">Real-time socket matchmaking. No swiping, no waiting.</div></div>
    <div class="fc"><div class="fc-icon">💬</div><div class="fc-title">Text Chat</div><div class="fc-desc">Live messaging with typing indicators and emoji reactions.</div></div>
    <div class="fc"><div class="fc-icon">📹</div><div class="fc-title">Video Chat</div><div class="fc-desc">Peer-to-peer WebRTC video — no server relay.</div></div>
    <div class="fc"><div class="fc-icon">🎙️</div><div class="fc-title">Voice Chat</div><div class="fc-desc">Crystal-clear audio calls via real WebRTC audio.</div></div>
    <div class="fc"><div class="fc-icon">🎭</div><div class="fc-title">5 Fun Modes</div><div class="fc-desc">Debate · Roast · Quiz · Opinion · Random.</div></div>
    <div class="fc"><div class="fc-icon">⏱️</div><div class="fc-title">5-Min Timer</div><div class="fc-desc">Countdown keeps conversations sharp and fun.</div></div>
    <div class="fc"><div class="fc-icon">🌍</div><div class="fc-title">180+ Countries</div><div class="fc-desc">Match by country and language preference.</div></div>
    <div class="fc"><div class="fc-icon">🚩</div><div class="fc-title">Report System</div><div class="fc-desc">Safe, moderated platform with user reports.</div></div>
    <div class="fc"><div class="fc-icon">⭐</div><div class="fc-title">Star Ratings</div><div class="fc-desc">Rate your spark after each chat session.</div></div>
    <div class="fc"><div class="fc-icon">👤</div><div class="fc-title">Guest Mode</div><div class="fc-desc">No signup needed to try the app.</div></div>
    <div class="fc"><div class="fc-icon">💎</div><div class="fc-title">Premium Tier</div><div class="fc-desc">Razorpay-powered subscriptions built in.</div></div>
    <div class="fc"><div class="fc-icon">🌙</div><div class="fc-title">Dark Theme</div><div class="fc-desc">Sleek dark UI throughout the entire app.</div></div>
  </div>
</div>

<div class="divider"></div>

<!-- TECH STACK -->
<div class="sec fu d4">
  <div class="sec-lbl">// tech stack</div>
  <div class="sec-title">Built with</div>
  <div class="stack-row">
    <span class="sp"><span class="d"></span>Next.js 14</span>
    <span class="sp"><span class="d"></span>React 18</span>
    <span class="sp"><span class="d"></span>Socket.io</span>
    <span class="sp"><span class="d"></span>WebRTC</span>
    <span class="sp"><span class="d"></span>Node.js</span>
    <span class="sp"><span class="d"></span>Express</span>
    <span class="sp"><span class="d"></span>Supabase</span>
    <span class="sp"><span class="d"></span>PostgreSQL</span>
    <span class="sp"><span class="d"></span>JWT Auth</span>
    <span class="sp"><span class="d"></span>Razorpay</span>
    <span class="sp"><span class="d"></span>Vercel</span>
    <span class="sp"><span class="d"></span>Render</span>
  </div>
</div>

<div class="divider"></div>

<!-- QUICK START -->
<div class="sec fu d5">
  <div class="sec-lbl">// quick start</div>
  <div class="sec-title">Run locally in 4 steps</div>
  <div class="steps">
    <div class="step">
      <div class="snum">01</div>
      <div class="sc">
        <div class="st">Clone & install</div>
        <div style="margin-top:10px">
          <div class="ch"><div class="dots"><span class="r"></span><span class="y"></span><span class="g"></span></div><span>terminal</span></div>
          <pre><span class="cg">git clone</span> https://github.com/kshitijsrivastavaa/sparkchat-app.git
<span class="cy">cd</span> sparkchat-app && <span class="cg">npm install</span></pre>
        </div>
      </div>
    </div>
    <div class="step">
      <div class="snum">02</div>
      <div class="sc">
        <div class="st">Set up Supabase (free)</div>
        <div class="sd" style="margin-top:5px">Go to <strong>supabase.com</strong> → New Project → SQL Editor → paste <code>database.sql</code> → Run. Then copy your Project URL + keys.</div>
      </div>
    </div>
    <div class="step">
      <div class="snum">03</div>
      <div class="sc">
        <div class="st">Configure environment</div>
        <div style="margin-top:10px">
          <div class="ch"><div class="dots"><span class="r"></span><span class="y"></span><span class="g"></span></div><span>.env.local</span></div>
          <pre><span class="co">NEXT_PUBLIC_SUPABASE_URL</span>=https://xxxx.supabase.co
<span class="co">NEXT_PUBLIC_SUPABASE_ANON_KEY</span>=eyJ...
<span class="co">SUPABASE_SERVICE_ROLE_KEY</span>=eyJ...
<span class="co">JWT_SECRET</span>=your_32_char_secret_here
<span class="co">SOCKET_PORT</span>=3001
<span class="co">NEXT_PUBLIC_SOCKET_URL</span>=http://localhost:3001
<span class="co">NEXT_PUBLIC_APP_URL</span>=http://localhost:3000</pre>
        </div>
      </div>
    </div>
    <div class="step">
      <div class="snum">04</div>
      <div class="sc">
        <div class="st">Start both servers</div>
        <div style="margin-top:10px">
          <div class="ch"><div class="dots"><span class="r"></span><span class="y"></span><span class="g"></span></div><span>terminal 1 — backend</span></div>
          <pre><span class="cg">node</span> server/index.js
<span class="cm"># SparkChat server running on port 3001</span></pre>
          <div class="ch" style="margin-top:8px"><div class="dots"><span class="r"></span><span class="y"></span><span class="g"></span></div><span>terminal 2 — frontend</span></div>
          <pre><span class="cg">npm run dev</span>
<span class="cm"># → open http://localhost:3000 🎉</span></pre>
        </div>
      </div>
    </div>
  </div>
</div>

<div class="divider"></div>

<!-- DATABASE -->
<div class="sec fu d5">
  <div class="sec-lbl">// database</div>
  <div class="sec-title">Schema overview</div>
  <div class="db-grid">
    <div class="db-card"><div class="db-name">users</div><div class="db-desc">Profiles, stats, premium status, reputation</div></div>
    <div class="db-card"><div class="db-name">chat_sessions</div><div class="db-desc">Match history, type, mode, duration</div></div>
    <div class="db-card"><div class="db-name">messages</div><div class="db-desc">Chat message logs per session</div></div>
    <div class="db-card"><div class="db-name">ratings</div><div class="db-desc">Post-chat 1–5 star ratings</div></div>
    <div class="db-card"><div class="db-name">reports</div><div class="db-desc">User report + moderation system</div></div>
    <div class="db-card"><div class="db-name">payments</div><div class="db-desc">Razorpay transaction records</div></div>
    <div class="db-card"><div class="db-name">online_users</div><div class="db-desc">Real-time presence & socket tracking</div></div>
  </div>
</div>

<div class="divider"></div>

<!-- DEPLOY -->
<div class="sec fu d5">
  <div class="sec-lbl">// deploy</div>
  <div class="sec-title">Go live</div>
  <h3>Frontend → Vercel</h3>
  <div class="ch"><div class="dots"><span class="r"></span><span class="y"></span><span class="g"></span></div><span>terminal</span></div>
  <pre><span class="cg">npm install -g vercel</span>
<span class="cg">vercel</span>
<span class="cm"># Add all .env.local vars in Vercel → Settings → Environment Variables</span></pre>
  <h3>Backend → Render</h3>
  <p>New Web Service → connect repo → Start Command: <code>node server/index.js</code> → add env vars → Deploy</p>
  <div style="margin-top:12px">
  <div class="ch"><div class="dots"><span class="r"></span><span class="y"></span><span class="g"></span></div><span>after backend deploy, update in vercel</span></div>
  <pre><span class="co">NEXT_PUBLIC_SOCKET_URL</span>=https://your-app.onrender.com</pre>
  </div>
</div>

<div class="divider"></div>

<!-- ROADMAP -->
<div class="sec fu d5">
  <div class="sec-lbl">// roadmap</div>
  <div class="sec-title">What's coming</div>
  <div class="rm">
    <div class="rmi"><div class="ribox"></div>Mobile app (React Native)</div>
    <div class="rmi"><div class="ribox"></div>Interest-based matching</div>
    <div class="rmi"><div class="ribox"></div>In-chat language translation</div>
    <div class="rmi"><div class="ribox"></div>Group spark rooms (3–5 people)</div>
    <div class="rmi"><div class="ribox"></div>Spark history & favourites</div>
    <div class="rmi"><div class="ribox"></div>AI-powered conversation starters</div>
    <div class="rmi"><div class="ribox"></div>Verified student / college mode</div>
  </div>
</div>

<div class="divider"></div>

<!-- FOOTER -->
<div class="footer fu d6">
  <div class="fbrand">⚡ SparkChat</div>
  <p style="margin-bottom:6px">Built with passion in India 🇮🇳 · MIT License</p>
  <p><a href="https://sparkchat-app.vercel.app">Live App</a> · <a href="https://github.com/kshitijsrivastavaa/sparkchat-app">GitHub</a> · <a href="https://sparkchat-app.onrender.com/health">API Health</a></p>
</div>

</body>
</html>
