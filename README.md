<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Mohamed Amine — GitHub README Preview</title>
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;600;700&family=Syne:wght@400;600;800&display=swap" rel="stylesheet"/>
<style>
  :root {
    --green: #00E5A0;
    --green-dim: #00b87e;
    --green-glow: rgba(0,229,160,0.18);
    --bg: #0a0c10;
    --bg2: #0f1117;
    --bg3: #161b22;
    --border: #21262d;
    --text: #e6edf3;
    --muted: #7d8590;
    --orange: #f97316;
  }
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
  html { scroll-behavior: smooth; }
  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'JetBrains Mono', monospace;
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* Animated particle canvas */
  #particles { position: fixed; top: 0; left: 0; width: 100%; height: 100%; pointer-events: none; z-index: 0; opacity: 0.4; }

  .page { position: relative; z-index: 1; max-width: 860px; margin: 0 auto; padding: 2rem 1.5rem 4rem; }

  /* ── HERO ── */
  .hero { text-align: center; padding: 3.5rem 0 2rem; position: relative; }
  .hero::before {
    content: '';
    position: absolute; inset: 0;
    background: radial-gradient(ellipse 70% 50% at 50% 0%, rgba(0,229,160,0.08), transparent);
    pointer-events: none;
  }

  .avatar-ring {
    width: 96px; height: 96px;
    border-radius: 50%;
    border: 2px solid var(--green);
    padding: 3px;
    margin: 0 auto 1.4rem;
    position: relative;
    animation: spin-ring 8s linear infinite;
    background: conic-gradient(from 0deg, var(--green), transparent 60%, var(--green));
  }
  @keyframes spin-ring { to { transform: rotate(360deg); } }
  .avatar-inner {
    width: 100%; height: 100%;
    border-radius: 50%;
    background: var(--bg3);
    display: flex; align-items: center; justify-content: center;
    font-size: 2.2rem;
    font-weight: 800;
    color: var(--green);
    animation: counter-spin 8s linear infinite;
    font-family: 'Syne', sans-serif;
    letter-spacing: -1px;
  }
  @keyframes counter-spin { to { transform: rotate(-360deg); } }

  .typing-wrap { min-height: 2.4rem; margin-bottom: 0.6rem; }
  .typing-name {
    font-family: 'Syne', sans-serif;
    font-size: 2rem; font-weight: 800;
    color: var(--text);
    overflow: hidden; white-space: nowrap; width: 0;
    display: inline-block;
    border-right: 2px solid var(--green);
    animation: type-in 1.2s steps(20,end) 0.3s forwards, blink 0.8s step-end infinite;
  }
  @keyframes type-in { to { width: 100%; } }
  @keyframes blink { 50% { border-color: transparent; } }

  .tagline {
    font-size: 0.78rem; letter-spacing: 0.18em; text-transform: uppercase;
    color: var(--muted); margin-bottom: 1.6rem;
  }
  .tagline span { color: var(--green); }

  /* Badges row */
  .badges { display: flex; flex-wrap: wrap; gap: 0.5rem; justify-content: center; margin-bottom: 2rem; }
  .badge {
    display: inline-flex; align-items: center; gap: 0.4rem;
    padding: 0.3rem 0.75rem;
    background: var(--bg3); border: 1px solid var(--border);
    border-radius: 6px; font-size: 0.72rem; color: var(--muted);
    text-decoration: none; transition: border-color 0.2s, color 0.2s, box-shadow 0.2s;
    position: relative; overflow: hidden;
  }
  .badge::after {
    content: ''; position: absolute; inset: 0;
    background: var(--green-glow); opacity: 0; transition: opacity 0.2s;
  }
  .badge:hover { border-color: var(--green); color: var(--green); }
  .badge:hover::after { opacity: 1; }
  .badge svg { width: 14px; height: 14px; fill: currentColor; }

  /* ── SECTION ── */
  .section { margin: 2.5rem 0; }
  .sec-label {
    font-size: 0.72rem; letter-spacing: 0.14em; color: var(--green);
    text-transform: uppercase; margin-bottom: 0.8rem;
    display: flex; align-items: center; gap: 0.5rem;
  }
  .sec-label::after { content: ''; flex: 1; height: 1px; background: var(--border); }

  .sec-title {
    font-family: 'Syne', sans-serif; font-size: 1.05rem; font-weight: 600;
    color: var(--text); margin-bottom: 1rem;
  }

  /* Terminal block */
  .terminal {
    background: var(--bg2); border: 1px solid var(--border);
    border-radius: 10px; overflow: hidden;
  }
  .term-bar {
    background: var(--bg3); padding: 0.6rem 1rem;
    display: flex; align-items: center; gap: 0.5rem;
    border-bottom: 1px solid var(--border);
  }
  .dot { width: 10px; height: 10px; border-radius: 50%; }
  .dot.r { background: #ff5f57; }
  .dot.y { background: #febc2e; }
  .dot.g { background: #28c840; }
  .term-title { font-size: 0.7rem; color: var(--muted); margin-left: auto; margin-right: auto; }
  .term-body { padding: 1.2rem 1.4rem; font-size: 0.8rem; line-height: 1.9; }
  .kw { color: var(--green); }
  .val { color: #79c0ff; }
  .str { color: #a5d6ff; }
  .cmt { color: var(--muted); }
  .prompt { color: var(--green); }
  .cmd { color: var(--text); }

  /* Focus table */
  .focus-grid { display: grid; gap: 0.7rem; }
  .focus-row {
    background: var(--bg2); border: 1px solid var(--border);
    border-radius: 8px; padding: 0.75rem 1rem;
    display: grid; grid-template-columns: 1.6rem 1fr;
    gap: 0.6rem; align-items: start;
    transition: border-color 0.2s, transform 0.2s;
    animation: fade-up 0.5s both;
  }
  .focus-row:hover { border-color: var(--green); transform: translateX(4px); }
  .focus-row:nth-child(1) { animation-delay: 0.1s; }
  .focus-row:nth-child(2) { animation-delay: 0.2s; }
  .focus-row:nth-child(3) { animation-delay: 0.3s; }
  .focus-row:nth-child(4) { animation-delay: 0.4s; }
  @keyframes fade-up { from { opacity: 0; transform: translateY(12px); } to { opacity: 1; transform: none; } }
  .focus-icon { font-size: 1rem; }
  .focus-text { font-size: 0.78rem; color: var(--muted); line-height: 1.6; }
  .focus-text strong { color: var(--text); font-weight: 600; }

  /* Stack */
  .stack-group { margin-bottom: 1.2rem; }
  .stack-group-label { font-size: 0.68rem; letter-spacing: 0.12em; color: var(--muted); text-transform: uppercase; margin-bottom: 0.5rem; }
  .icon-row { display: flex; flex-wrap: wrap; gap: 0.5rem; }
  .tech-chip {
    display: inline-flex; align-items: center; gap: 0.4rem;
    background: var(--bg3); border: 1px solid var(--border);
    border-radius: 6px; padding: 0.3rem 0.65rem;
    font-size: 0.72rem; color: var(--muted);
    transition: all 0.2s; cursor: default;
    position: relative; overflow: hidden;
  }
  .tech-chip::before {
    content: '';
    position: absolute; left: 0; top: 0; bottom: 0;
    width: 2px; background: var(--green);
    transform: scaleY(0); transition: transform 0.2s;
    transform-origin: bottom;
  }
  .tech-chip:hover { border-color: var(--green); color: var(--green); }
  .tech-chip:hover::before { transform: scaleY(1); }
  .chip-dot { width: 6px; height: 6px; border-radius: 50%; background: var(--green); flex-shrink: 0; }

  /* Stats */
  .stats-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; }
  .stat-card {
    background: var(--bg2); border: 1px solid var(--border);
    border-radius: 10px; padding: 1rem 1.2rem;
    transition: border-color 0.2s;
    position: relative; overflow: hidden;
  }
  .stat-card::before {
    content: '';
    position: absolute; top: 0; left: 0; right: 0; height: 2px;
    background: linear-gradient(90deg, transparent, var(--green), transparent);
    transform: translateX(-100%);
    transition: transform 0.6s;
  }
  .stat-card:hover { border-color: var(--green-dim); }
  .stat-card:hover::before { transform: translateX(100%); }
  .stat-label { font-size: 0.68rem; letter-spacing: 0.12em; color: var(--muted); text-transform: uppercase; margin-bottom: 0.35rem; }
  .stat-val { font-family: 'Syne', sans-serif; font-size: 1.6rem; font-weight: 800; color: var(--green); }
  .stat-sub { font-size: 0.68rem; color: var(--muted); margin-top: 0.1rem; }

  /* Glitch bar */
  .glitch-bar {
    text-align: center; margin: 2rem 0; position: relative;
    font-size: 0.68rem; letter-spacing: 0.25em; color: var(--muted);
    text-transform: uppercase;
  }
  .glitch-bar::before, .glitch-bar::after {
    content: ''; position: absolute; top: 50%; left: 0; right: 0;
    height: 1px; background: var(--border);
  }
  .glitch-bar span { background: var(--bg); padding: 0 1rem; position: relative; z-index: 1; }

  /* Footer */
  .footer { text-align: center; padding: 2rem 0 0; }
  .footer-text { font-size: 0.72rem; color: var(--muted); font-style: italic; margin-bottom: 0.8rem; }
  .visitor-badge {
    display: inline-block; background: var(--bg3); border: 1px solid var(--border);
    border-radius: 6px; padding: 0.25rem 0.75rem; font-size: 0.68rem; color: var(--muted);
  }
  .visitor-badge span { color: var(--green); font-weight: 600; }

  /* Scroll reveal */
  .reveal { opacity: 0; transform: translateY(20px); transition: opacity 0.6s, transform 0.6s; }
  .reveal.visible { opacity: 1; transform: none; }

  /* Pulse dot */
  .pulse { display: inline-block; width: 8px; height: 8px; border-radius: 50%; background: var(--green); position: relative; margin-right: 6px; }
  .pulse::after { content: ''; position: absolute; inset: -4px; border-radius: 50%; background: var(--green); animation: pulse-ring 1.4s ease-out infinite; opacity: 0.4; }
  @keyframes pulse-ring { to { transform: scale(2.2); opacity: 0; } }

  @media(max-width:600px) {
    .stats-grid { grid-template-columns: 1fr; }
    .typing-name { font-size: 1.5rem; }
  }
</style>
</head>
<body>
<canvas id="particles"></canvas>
<div class="page">

  <!-- HERO -->
  <div class="hero">
    <div class="avatar-ring">
      <div class="avatar-inner">MA</div>
    </div>
    <div class="typing-wrap">
      <span class="typing-name">Mohamed Amine Rouissi</span>
    </div>
    <p class="tagline">Full Stack Engineer · <span>Backend</span> · Systems · <span>DevOps</span></p>
    <div class="badges">
      <a href="https://linkedin.com/in/mohamed-amine-rouissi-270616254" class="badge" target="_blank">
        <svg viewBox="0 0 24 24"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
        LinkedIn
      </a>
      <a href="https://fb.com/mohamedamine.rouissi" class="badge" target="_blank">
        <svg viewBox="0 0 24 24"><path d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z"/></svg>
        Facebook
      </a>
      <a href="mailto:Mohamedaminerouissi26@gmail.com" class="badge">
        <svg viewBox="0 0 24 24"><path d="M24 5.457v13.909c0 .904-.732 1.636-1.636 1.636h-3.819V11.73L12 16.64l-6.545-4.91v9.273H1.636A1.636 1.636 0 010 19.366V5.457c0-.9.732-1.636 1.636-1.636h.27L12 10.09l10.094-6.27h.27C23.268 3.821 24 4.557 24 5.457z"/></svg>
        Email
      </a>
      <a href="https://en.wikipedia.org/wiki/Tunisia" class="badge" target="_blank">
        <svg viewBox="0 0 24 24"><path d="M12 2C8.13 2 5 5.13 5 9c0 5.25 7 13 7 13s7-7.75 7-13c0-3.87-3.13-7-7-7zm0 9.5c-1.38 0-2.5-1.12-2.5-2.5s1.12-2.5 2.5-2.5 2.5 1.12 2.5 2.5-1.12 2.5-2.5 2.5z"/></svg>
        Tunisia 🇹🇳
      </a>
    </div>
  </div>

  <!-- WHOAMI -->
  <div class="section reveal">
    <div class="sec-label">$ whoami</div>
    <div class="terminal">
      <div class="term-bar">
        <div class="dot r"></div><div class="dot y"></div><div class="dot g"></div>
        <span class="term-title">profile.yaml</span>
      </div>
      <div class="term-body">
        <div><span class="kw">name</span><span class="cmt">:</span>     <span class="str">Mohamed Amine Rouissi</span></div>
        <div><span class="kw">role</span><span class="cmt">:</span>     <span class="str">Full Stack Engineer</span></div>
        <div><span class="kw">focus</span><span class="cmt">:</span>    <span class="str">Backend · System Design · DevOps</span></div>
        <div><span class="kw">degree</span><span class="cmt">:</span>   <span class="str">CS Engineer — Network Engineering</span></div>
        <div><span class="kw">location</span><span class="cmt">:</span> <span class="str">Tunisia 🇹🇳</span></div>
        <div><span class="kw">status</span><span class="cmt">:</span>   <span class="pulse"></span><span class="val">Open to opportunities</span></div>
        <div><span class="kw">exploring</span><span class="cmt">:</span> <span class="val">[ C#, Flutter, Linux/Security ]</span></div>
      </div>
    </div>
  </div>

  <!-- FOCUS -->
  <div class="section reveal">
    <div class="sec-label">$ cat ./focus.md</div>
    <div class="focus-grid">
      <div class="focus-row">
        <span class="focus-icon">🧱</span>
        <span class="focus-text"><strong>Scalable backend systems</strong> — resilient, high-throughput architecture with clean separation of concerns</span>
      </div>
      <div class="focus-row">
        <span class="focus-icon">🔄</span>
        <span class="focus-text"><strong>Microservices best practices</strong> — event-driven design, service mesh, distributed tracing</span>
      </div>
      <div class="focus-row">
        <span class="focus-icon">🚀</span>
        <span class="focus-text"><strong>Tunisian SaaS platform</strong> — Vercel-like deployment infrastructure built from scratch</span>
      </div>
      <div class="focus-row">
        <span class="focus-icon">🎮</span>
        <span class="focus-text"><strong>Multiplayer web games</strong> — Three.js + Socket.io real-time experiences</span>
      </div>
    </div>
  </div>

  <!-- STACK -->
  <div class="section reveal">
    <div class="sec-label">$ ls ./stack</div>
    <div class="stack-group">
      <div class="stack-group-label">Frontend</div>
      <div class="icon-row">
        <div class="tech-chip"><div class="chip-dot"></div>React</div>
        <div class="tech-chip"><div class="chip-dot"></div>Next.js</div>
        <div class="tech-chip"><div class="chip-dot"></div>Three.js</div>
      </div>
    </div>
    <div class="stack-group">
      <div class="stack-group-label">Backend</div>
      <div class="icon-row">
        <div class="tech-chip"><div class="chip-dot"></div>Java</div>
        <div class="tech-chip"><div class="chip-dot"></div>Spring Boot</div>
        <div class="tech-chip"><div class="chip-dot"></div>Node.js</div>
      </div>
    </div>
    <div class="stack-group">
      <div class="stack-group-label">Databases</div>
      <div class="icon-row">
        <div class="tech-chip"><div class="chip-dot"></div>MySQL</div>
        <div class="tech-chip"><div class="chip-dot"></div>PostgreSQL</div>
        <div class="tech-chip"><div class="chip-dot"></div>MongoDB</div>
        <div class="tech-chip"><div class="chip-dot"></div>Redis</div>
      </div>
    </div>
    <div class="stack-group">
      <div class="stack-group-label">DevOps & Tools</div>
      <div class="icon-row">
        <div class="tech-chip"><div class="chip-dot"></div>Docker</div>
        <div class="tech-chip"><div class="chip-dot"></div>Git</div>
        <div class="tech-chip"><div class="chip-dot"></div>Linux</div>
      </div>
    </div>
  </div>

  <!-- STATS -->
  <div class="section reveal">
    <div class="sec-label">$ cat ./stats.log</div>
    <div class="stats-grid">
      <div class="stat-card">
        <div class="stat-label">GitHub Streak</div>
        <div style="margin-top:0.5rem">
          <img src="https://streak-stats.demolab.com?user=Am1n0N&theme=github-dark-blue&hide_border=true&background=0f1117&stroke=21262d&ring=00E5A0&fire=f97316&currStreakLabel=00E5A0&sideLabels=7d8590&currStreakNum=e6edf3&sideNums=e6edf3&dates=484f58" width="100%" style="border-radius:6px" alt="streak"/>
        </div>
      </div>
      <div class="stat-card">
        <div class="stat-label">Languages Used</div>
        <div style="margin-top:0.5rem">
          <img src="https://github-profile-summary-cards.vercel.app/api/cards/repos-per-language?username=Am1n0N&theme=github_dark&hide_border=true" width="100%" style="border-radius:6px" alt="langs"/>
        </div>
      </div>
    </div>
    <div style="margin-top:1rem">
      <img src="https://github-readme-activity-graph.vercel.app/graph?username=Am1n0N&theme=github-compact&bg_color=0f1117&color=00E5A0&line=00b87e&point=f97316&hide_border=true" width="100%" style="border-radius:10px;border:1px solid #21262d" alt="activity"/>
    </div>
  </div>

  <div class="glitch-bar"><span>— clean architecture · scalable systems · real-world impact —</span></div>

  <div class="footer reveal">
    <p class="footer-text">⚡ Transitioning Monolith → Microservices · Building for the future of the Arab web</p>
    <div class="visitor-badge">👁 visitors: <span id="vc">loading…</span></div>
  </div>

</div>

<script>
// Particle system
const canvas = document.getElementById('particles');
const ctx = canvas.getContext('2d');
let W, H, pts = [];
const N = 55, COLOR = '#00E5A0';
function resize() { W = canvas.width = innerWidth; H = canvas.height = innerHeight; }
function randPt() { return { x: Math.random()*W, y: Math.random()*H, vx: (Math.random()-.5)*.35, vy: (Math.random()-.5)*.35, r: Math.random()*1.2+.4 }; }
resize(); for(let i=0;i<N;i++) pts.push(randPt());
window.addEventListener('resize', resize);
function draw() {
  ctx.clearRect(0,0,W,H);
  pts.forEach(p => {
    p.x+=p.vx; p.y+=p.vy;
    if(p.x<0||p.x>W) p.vx*=-1;
    if(p.y<0||p.y>H) p.vy*=-1;
    ctx.beginPath(); ctx.arc(p.x,p.y,p.r,0,Math.PI*2);
    ctx.fillStyle = COLOR; ctx.fill();
  });
  for(let i=0;i<pts.length;i++) for(let j=i+1;j<pts.length;j++) {
    const dx=pts[i].x-pts[j].x, dy=pts[i].y-pts[j].y, d=Math.sqrt(dx*dx+dy*dy);
    if(d<120) { ctx.beginPath(); ctx.moveTo(pts[i].x,pts[i].y); ctx.lineTo(pts[j].x,pts[j].y);
      ctx.strokeStyle = `rgba(0,229,160,${(1-d/120)*0.18})`; ctx.lineWidth=.5; ctx.stroke(); }
  }
  requestAnimationFrame(draw);
}
draw();

// Scroll reveal
const obs = new IntersectionObserver(entries => entries.forEach(e => { if(e.isIntersecting) e.target.classList.add('visible'); }), { threshold: 0.1 });
document.querySelectorAll('.reveal').forEach(el => obs.observe(el));

// Fake visitor counter for demo
document.getElementById('vc').textContent = (Math.floor(Math.random()*400)+120).toLocaleString();
</script>
</body>
</html>
