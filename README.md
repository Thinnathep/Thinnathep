<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>G'NekoVoidGG — GitHub Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Mono:ital,wght@0,400;0,700;1,400&family=Orbitron:wght@400;700;900&family=Noto+Sans+Thai:wght@300;400;700&display=swap" rel="stylesheet">
<style>
  :root {
    --void: #050508;
    --deep: #0a0a12;
    --panel: #0f0f1a;
    --border: #1a1a2e;
    --neon-purple: #b847ff;
    --neon-cyan: #00f5ff;
    --neon-pink: #ff2d78;
    --neon-green: #39ff14;
    --text: #c8c8e8;
    --muted: #5a5a7a;
    --gold: #ffd700;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--void);
    color: var(--text);
    font-family: 'Space Mono', monospace;
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* Starfield */
  #stars {
    position: fixed; top: 0; left: 0;
    width: 100%; height: 100%;
    pointer-events: none; z-index: 0;
  }

  .star {
    position: absolute;
    background: white;
    border-radius: 50%;
    animation: twinkle var(--d) infinite alternate;
  }

  @keyframes twinkle {
    0% { opacity: 0.1; transform: scale(1); }
    100% { opacity: 1; transform: scale(1.3); }
  }

  /* Floating orbs */
  .orb {
    position: fixed;
    border-radius: 50%;
    filter: blur(80px);
    opacity: 0.15;
    pointer-events: none;
    z-index: 0;
    animation: floatOrb 8s ease-in-out infinite alternate;
  }
  .orb1 { width: 400px; height: 400px; background: var(--neon-purple); top: -100px; left: -100px; animation-delay: 0s; }
  .orb2 { width: 300px; height: 300px; background: var(--neon-cyan); bottom: -50px; right: -50px; animation-delay: -4s; }
  .orb3 { width: 200px; height: 200px; background: var(--neon-pink); top: 40%; left: 30%; animation-delay: -2s; }

  @keyframes floatOrb {
    0% { transform: translate(0, 0) scale(1); }
    100% { transform: translate(30px, -30px) scale(1.1); }
  }

  /* Main container */
  .container {
    position: relative; z-index: 1;
    max-width: 860px;
    margin: 0 auto;
    padding: 40px 24px 80px;
  }

  /* Hero Banner */
  .hero-banner {
    width: 100%;
    height: 180px;
    background: linear-gradient(135deg, #0a0a1a 0%, #1a0a2e 40%, #0a1a2e 70%, #050508 100%);
    border-radius: 16px 16px 0 0;
    position: relative;
    overflow: hidden;
    display: flex;
    align-items: center;
    justify-content: center;
    border: 1px solid var(--border);
    border-bottom: none;
  }

  .hero-banner::before {
    content: '';
    position: absolute; inset: 0;
    background: 
      radial-gradient(ellipse at 20% 50%, rgba(184,71,255,0.3) 0%, transparent 60%),
      radial-gradient(ellipse at 80% 50%, rgba(0,245,255,0.2) 0%, transparent 60%);
  }

  .banner-grid {
    position: absolute; inset: 0;
    background-image: 
      linear-gradient(rgba(0,245,255,0.05) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,245,255,0.05) 1px, transparent 1px);
    background-size: 40px 40px;
    animation: gridScroll 20s linear infinite;
  }

  @keyframes gridScroll {
    0% { transform: translateY(0); }
    100% { transform: translateY(40px); }
  }

  .banner-text {
    position: relative; z-index: 2;
    text-align: center;
  }

  .banner-title {
    font-family: 'Orbitron', monospace;
    font-size: 2.4rem;
    font-weight: 900;
    background: linear-gradient(90deg, var(--neon-purple), var(--neon-cyan), var(--neon-pink));
    background-size: 200%;
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    animation: gradientShift 3s linear infinite;
    letter-spacing: 0.05em;
    text-shadow: none;
  }

  @keyframes gradientShift {
    0% { background-position: 0%; }
    100% { background-position: 200%; }
  }

  .banner-sub {
    font-size: 0.85rem;
    color: var(--neon-cyan);
    letter-spacing: 0.3em;
    margin-top: 8px;
    opacity: 0.8;
    animation: pulse 2s ease-in-out infinite;
  }

  @keyframes pulse {
    0%, 100% { opacity: 0.5; }
    50% { opacity: 1; }
  }

  /* Profile card */
  .profile-card {
    background: var(--panel);
    border: 1px solid var(--border);
    border-top: 2px solid var(--neon-purple);
    border-radius: 0 0 16px 16px;
    padding: 32px;
    margin-bottom: 24px;
    position: relative;
    overflow: hidden;
    transform-style: preserve-3d;
    transition: transform 0.3s ease, box-shadow 0.3s ease;
  }

  .profile-card:hover {
    box-shadow: 0 20px 60px rgba(184,71,255,0.2), 0 0 0 1px rgba(184,71,255,0.3);
  }

  .profile-top {
    display: flex;
    gap: 28px;
    align-items: flex-start;
  }

  .avatar-wrap {
    position: relative;
    flex-shrink: 0;
  }

  .avatar {
    width: 100px; height: 100px;
    border-radius: 50%;
    background: linear-gradient(135deg, var(--neon-purple), var(--neon-cyan));
    display: flex; align-items: center; justify-content: center;
    font-size: 3rem;
    position: relative;
    z-index: 1;
    animation: avatarFloat 4s ease-in-out infinite;
    cursor: pointer;
    transition: transform 0.3s;
  }

  .avatar:hover {
    transform: scale(1.1) rotate(10deg);
  }

  @keyframes avatarFloat {
    0%, 100% { transform: translateY(0); }
    50% { transform: translateY(-8px); }
  }

  .avatar-ring {
    position: absolute;
    inset: -6px;
    border-radius: 50%;
    border: 2px solid transparent;
    background: linear-gradient(var(--panel), var(--panel)) padding-box,
                linear-gradient(90deg, var(--neon-purple), var(--neon-cyan), var(--neon-pink), var(--neon-purple)) border-box;
    background-size: 300% 100%;
    animation: ringRotate 3s linear infinite;
  }

  @keyframes ringRotate {
    0% { background-position: 0% 50%; }
    100% { background-position: 300% 50%; }
  }

  .status-dot {
    position: absolute;
    bottom: 4px; right: 4px;
    width: 18px; height: 18px;
    background: var(--neon-green);
    border-radius: 50%;
    border: 3px solid var(--panel);
    z-index: 2;
    animation: statusPulse 2s ease-in-out infinite;
  }

  @keyframes statusPulse {
    0%, 100% { box-shadow: 0 0 0 0 rgba(57,255,20,0.7); }
    50% { box-shadow: 0 0 0 8px rgba(57,255,20,0); }
  }

  .profile-info h1 {
    font-family: 'Orbitron', monospace;
    font-size: 1.5rem;
    font-weight: 700;
    color: white;
    margin-bottom: 4px;
  }

  .profile-info .handle {
    color: var(--neon-cyan);
    font-size: 0.85rem;
    margin-bottom: 12px;
  }

  /* Typing text */
  .typing-container {
    font-size: 0.9rem;
    color: var(--text);
    min-height: 24px;
    margin-bottom: 16px;
  }

  .typing-text {
    border-right: 2px solid var(--neon-cyan);
    animation: blink 0.75s step-end infinite;
    white-space: nowrap;
    overflow: hidden;
  }

  @keyframes blink {
    0%, 100% { border-color: var(--neon-cyan); }
    50% { border-color: transparent; }
  }

  /* Social badges */
  .badges {
    display: flex; flex-wrap: wrap; gap: 8px;
    margin-top: 8px;
  }

  .badge {
    display: inline-flex; align-items: center; gap: 6px;
    padding: 6px 14px;
    border-radius: 6px;
    font-size: 0.75rem;
    font-weight: 700;
    text-decoration: none;
    transition: transform 0.2s, box-shadow 0.2s;
    cursor: pointer;
    letter-spacing: 0.05em;
  }

  .badge:hover {
    transform: translateY(-3px) scale(1.05);
    box-shadow: 0 8px 24px rgba(0,0,0,0.4);
  }

  .badge-web { background: #DC143C; color: white; }
  .badge-li { background: #0077B5; color: white; }
  .badge-tw { background: #1DA1F2; color: white; }
  .badge-ig { background: linear-gradient(45deg, #f09433, #e6683c, #dc2743, #cc2366, #bc1888); color: white; }
  .badge-fb { background: #1877F2; color: white; }

  /* Section cards */
  .section {
    background: var(--panel);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 24px;
    margin-bottom: 20px;
    position: relative;
    transition: transform 0.3s, box-shadow 0.3s;
    transform-style: preserve-3d;
  }

  .section:hover {
    transform: translateY(-4px) rotateX(1deg);
    box-shadow: 0 16px 48px rgba(0,0,0,0.5), 0 0 0 1px rgba(0,245,255,0.15);
  }

  .section-title {
    font-family: 'Orbitron', monospace;
    font-size: 0.75rem;
    color: var(--neon-cyan);
    letter-spacing: 0.3em;
    text-transform: uppercase;
    margin-bottom: 16px;
    display: flex; align-items: center; gap: 10px;
  }

  .section-title::after {
    content: '';
    flex: 1;
    height: 1px;
    background: linear-gradient(90deg, var(--neon-cyan), transparent);
  }

  /* About items */
  .about-items { display: flex; flex-direction: column; gap: 10px; }

  .about-item {
    display: flex; align-items: flex-start; gap: 12px;
    padding: 12px 16px;
    background: rgba(255,255,255,0.02);
    border-radius: 8px;
    border: 1px solid rgba(255,255,255,0.04);
    transition: all 0.3s;
  }

  .about-item:hover {
    background: rgba(184,71,255,0.08);
    border-color: rgba(184,71,255,0.2);
    transform: translateX(4px);
  }

  .about-emoji { font-size: 1.2rem; flex-shrink: 0; margin-top: 2px; }
  .about-text { font-size: 0.85rem; line-height: 1.6; color: var(--text); }
  .about-text strong { color: var(--neon-cyan); }

  /* Skill grid */
  .skill-grid {
    display: flex; flex-wrap: wrap; gap: 8px;
  }

  .skill-chip {
    display: flex; align-items: center; gap: 6px;
    padding: 8px 14px;
    border-radius: 8px;
    font-size: 0.78rem;
    font-weight: 700;
    letter-spacing: 0.05em;
    border: 1px solid rgba(255,255,255,0.08);
    background: rgba(255,255,255,0.04);
    transition: all 0.3s;
    cursor: default;
    position: relative;
    overflow: hidden;
  }

  .skill-chip::before {
    content: '';
    position: absolute; inset: 0;
    background: linear-gradient(135deg, rgba(255,255,255,0.1), transparent);
    opacity: 0;
    transition: opacity 0.3s;
  }

  .skill-chip:hover {
    transform: translateY(-3px) scale(1.05);
    border-color: var(--neon-purple);
    box-shadow: 0 8px 24px rgba(184,71,255,0.3);
  }

  .skill-chip:hover::before { opacity: 1; }

  /* Stats grid */
  .stats-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 12px;
  }

  .stat-card {
    background: rgba(255,255,255,0.02);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 16px;
    text-align: center;
    transition: all 0.3s;
    position: relative;
    overflow: hidden;
  }

  .stat-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--neon-purple), var(--neon-cyan));
  }

  .stat-card:hover {
    transform: scale(1.03);
    box-shadow: 0 0 30px rgba(184,71,255,0.2);
  }

  .stat-num {
    font-family: 'Orbitron', monospace;
    font-size: 1.8rem;
    font-weight: 900;
    color: white;
    display: block;
    animation: countUp 2s ease-out;
  }

  @keyframes countUp {
    from { opacity: 0; transform: translateY(10px); }
    to { opacity: 1; transform: translateY(0); }
  }

  .stat-label { font-size: 0.7rem; color: var(--muted); margin-top: 4px; letter-spacing: 0.1em; }

  /* Fun section */
  .fun-box {
    background: linear-gradient(135deg, rgba(184,71,255,0.08), rgba(0,245,255,0.05));
    border: 1px solid rgba(184,71,255,0.2);
    border-radius: 12px;
    padding: 20px;
    text-align: center;
    position: relative;
    overflow: hidden;
  }

  .cat-ascii {
    font-family: 'Space Mono', monospace;
    font-size: 0.7rem;
    line-height: 1.4;
    color: var(--neon-cyan);
    margin-bottom: 12px;
    display: inline-block;
    animation: catFloat 3s ease-in-out infinite;
  }

  @keyframes catFloat {
    0%, 100% { transform: translateY(0) rotate(-1deg); }
    50% { transform: translateY(-5px) rotate(1deg); }
  }

  .fun-quote {
    font-size: 0.8rem;
    color: var(--muted);
    font-style: italic;
  }

  .fun-quote span { color: var(--neon-pink); }

  /* Snake animation */
  .snake-container {
    background: rgba(0,0,0,0.3);
    border-radius: 8px;
    padding: 16px;
    text-align: center;
    border: 1px solid var(--border);
    margin-top: 12px;
    overflow: hidden;
    position: relative;
  }

  .snake-dots {
    display: flex; flex-wrap: wrap; gap: 3px;
    justify-content: center;
  }

  .dot {
    width: 10px; height: 10px;
    border-radius: 2px;
    background: rgba(255,255,255,0.05);
    transition: background 0.3s;
  }

  .dot.active { background: var(--neon-green); box-shadow: 0 0 6px var(--neon-green); }
  .dot.trail { background: rgba(57,255,20,0.3); }
  .dot.contribution { background: rgba(184,71,255,0.4); }
  .dot.hot { background: var(--neon-purple); box-shadow: 0 0 8px var(--neon-purple); }

  /* Scroll animation */
  .fade-in {
    opacity: 0;
    transform: translateY(20px);
    transition: opacity 0.6s ease, transform 0.6s ease;
  }
  .fade-in.visible { opacity: 1; transform: translateY(0); }

  /* 3D card on mouse move */
  .card-3d {
    transform-style: preserve-3d;
    transition: transform 0.1s ease;
  }

  /* Wave footer */
  .wave-footer {
    text-align: center;
    margin-top: 40px;
    color: var(--muted);
    font-size: 0.75rem;
  }

  .wave-footer span {
    display: inline-block;
    animation: waveLetter 2s ease-in-out infinite;
  }

  .wave-footer span:nth-child(1) { animation-delay: 0s; }
  .wave-footer span:nth-child(2) { animation-delay: 0.1s; }
  .wave-footer span:nth-child(3) { animation-delay: 0.2s; }
  .wave-footer span:nth-child(4) { animation-delay: 0.3s; }
  .wave-footer span:nth-child(5) { animation-delay: 0.4s; }
  .wave-footer span:nth-child(6) { animation-delay: 0.5s; }

  @keyframes waveLetter {
    0%, 100% { transform: translateY(0); }
    50% { transform: translateY(-6px); color: var(--neon-cyan); }
  }

  /* Glitch effect */
  .glitch {
    position: relative;
  }

  .glitch::before, .glitch::after {
    content: attr(data-text);
    position: absolute;
    top: 0; left: 0;
    width: 100%;
    font-family: 'Orbitron', monospace;
    font-size: 1.5rem;
    font-weight: 700;
    opacity: 0;
  }

  .glitch::before {
    color: var(--neon-pink);
    animation: glitchA 3s infinite;
    clip-path: polygon(0 0, 100% 0, 100% 35%, 0 35%);
  }

  .glitch::after {
    color: var(--neon-cyan);
    animation: glitchB 3s infinite;
    clip-path: polygon(0 65%, 100% 65%, 100% 100%, 0 100%);
  }

  @keyframes glitchA {
    0%, 90%, 100% { opacity: 0; transform: none; }
    92% { opacity: 0.8; transform: translateX(-3px); }
    95% { opacity: 0; }
    97% { opacity: 0.8; transform: translateX(3px); }
  }

  @keyframes glitchB {
    0%, 88%, 100% { opacity: 0; transform: none; }
    90% { opacity: 0.8; transform: translateX(3px); }
    93% { opacity: 0; }
    96% { opacity: 0.8; transform: translateX(-3px); }
  }

  /* Responsive */
  @media (max-width: 600px) {
    .profile-top { flex-direction: column; }
    .stats-grid { grid-template-columns: 1fr; }
    .banner-title { font-size: 1.6rem; }
  }
</style>
</head>
<body>

<!-- Starfield -->
<canvas id="stars"></canvas>

<!-- Orbs -->
<div class="orb orb1"></div>
<div class="orb orb2"></div>
<div class="orb orb3"></div>

<div class="container">

  <!-- Hero Banner -->
  <div class="hero-banner">
    <div class="banner-grid"></div>
    <div class="banner-text">
      <div class="banner-title glitch" data-text="G'NekoVoidGG">G'NekoVoidGG</div>
      <div class="banner-sub">&lt; VOID OPERATOR • CODE CONJURER • CAT PERSON &gt;</div>
    </div>
  </div>

  <!-- Profile Card -->
  <div class="profile-card card-3d fade-in" id="profileCard">
    <div class="profile-top">
      <div class="avatar-wrap">
        <div class="avatar-ring"></div>
        <div class="avatar">🐱</div>
        <div class="status-dot" title="Online"></div>
      </div>
      <div class="profile-info">
        <h1>Thinnathep</h1>
        <div class="handle">@G-NekoVoidGG</div>
        <div class="typing-container">
          <span class="typing-text" id="typingEl"></span>
        </div>
        <div class="badges">
          <span class="badge badge-web">🌐 Website</span>
          <span class="badge badge-li">💼 LinkedIn</span>
          <span class="badge badge-tw">🐦 Twitter</span>
          <span class="badge badge-ig">📸 Instagram</span>
          <span class="badge badge-fb">📘 Facebook</span>
        </div>
      </div>
    </div>
  </div>

  <!-- About -->
  <div class="section card-3d fade-in">
    <div class="section-title">🧠 About Me</div>
    <div class="about-items">
      <div class="about-item">
        <span class="about-emoji">✌️</span>
        <div class="about-text">ชอบเขียนโค้ดและแชร์ความรู้ — เพราะ <strong>knowledge hoarding is a crime</strong> 🚔</div>
      </div>
      <div class="about-item">
        <span class="about-emoji">❤️</span>
        <div class="about-text">หลงรักการเขียน code และสิ่งใหม่ๆ — <strong>Learning Curve = Vertical</strong> 📈</div>
      </div>
      <div class="about-item">
        <span class="about-emoji">💬</span>
        <div class="about-text">ถามได้ทุกอย่าง — <strong>No stupid questions</strong>, only stupid... nah, ask away.</div>
      </div>
      <div class="about-item">
        <span class="about-emoji">⚡</span>
        <div class="about-text">Currently in my <strong>Void Arc</strong> — building things that shouldn't be possible.</div>
      </div>
      <div class="about-item">
        <span class="about-emoji">🌱</span>
        <div class="about-text">Currently learning: <strong>AI Agents, Agentic Workflows</strong> — making computers do my homework.</div>
      </div>
    </div>
  </div>

  <!-- Tech Stack -->
  <div class="section card-3d fade-in">
    <div class="section-title">⚔️ Tech Arsenal</div>
    <div class="skill-grid">
      <div class="skill-chip" style="color:#61DAFB">⚛️ React</div>
      <div class="skill-chip" style="color:#4FC08D">🟩 Vue.js</div>
      <div class="skill-chip" style="color:#FF2D20">🔴 Laravel</div>
      <div class="skill-chip" style="color:#F7DF1E">🟡 JavaScript</div>
      <div class="skill-chip" style="color:#7B5EA7">🟣 AppSheet</div>
      <div class="skill-chip" style="color:#4285F4">📊 Google Apps Script</div>
      <div class="skill-chip" style="color:#00f5ff">🤖 AI Agents</div>
      <div class="skill-chip" style="color:#39ff14">🐍 Python</div>
      <div class="skill-chip" style="color:#FF6B6B">🐳 Docker</div>
      <div class="skill-chip" style="color:#F05032">📦 Git</div>
    </div>
  </div>

  <!-- Stats -->
  <div class="section card-3d fade-in">
    <div class="section-title">📊 Void Statistics</div>
    <div class="stats-grid">
      <div class="stat-card">
        <span class="stat-num" id="c1">0</span>
        <div class="stat-label">☕ COFFEE CONSUMED</div>
      </div>
      <div class="stat-card">
        <span class="stat-num" id="c2">0</span>
        <div class="stat-label">🐛 BUGS CREATED</div>
      </div>
      <div class="stat-card">
        <span class="stat-num" id="c3">0</span>
        <div class="stat-label">🔥 BUGS BLAMED ON OTHERS</div>
      </div>
      <div class="stat-card">
        <span class="stat-num" id="c4">0</span>
        <div class="stat-label">😴 HOURS OF "THINKING"</div>
      </div>
    </div>
  </div>

  <!-- Contribution Snake -->
  <div class="section card-3d fade-in">
    <div class="section-title">🐍 Contribution Void</div>
    <div class="snake-container">
      <div class="snake-dots" id="snakeGrid"></div>
      <div style="color: var(--muted); font-size:0.7rem; margin-top:10px;">
        🐍 The snake eats my contributions... and my free time
      </div>
    </div>
  </div>

  <!-- Fun Cat -->
  <div class="section card-3d fade-in">
    <div class="section-title">😹 Cat.exe</div>
    <div class="fun-box">
      <pre class="cat-ascii">
  /\_____/\
 (  OwO  )    ← meow. I am in ur code
  > ♦ ♦  <       deleting ur semicolons
  (  ___  )
   \_____/    git commit -m "cat did it"</pre>
      <div class="fun-quote">
        "There are only 10 types of people in the world:<br>
        those who understand binary, and <span>my cat</span> who doesn't care."
      </div>
    </div>
  </div>

  <!-- Wave footer -->
  <div class="wave-footer">
    <span>T</span><span>h</span><span>a</span><span>n</span><span>k</span><span>s</span>
    &nbsp;for visiting the Void 🐾
  </div>

</div>

<script>
  // Starfield
  const canvas = document.getElementById('stars');
  const ctx = canvas.getContext('2d');

  function resizeCanvas() {
    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;
  }
  resizeCanvas();
  window.addEventListener('resize', resizeCanvas);

  const stars = Array.from({ length: 150 }, () => ({
    x: Math.random() * window.innerWidth,
    y: Math.random() * window.innerHeight,
    r: Math.random() * 1.5,
    speed: Math.random() * 0.3 + 0.1,
    opacity: Math.random(),
  }));

  function drawStars() {
    ctx.clearRect(0, 0, canvas.width, canvas.height);
    stars.forEach(s => {
      s.opacity += (Math.random() - 0.5) * 0.05;
      s.opacity = Math.max(0.1, Math.min(1, s.opacity));
      ctx.beginPath();
      ctx.arc(s.x, s.y, s.r, 0, Math.PI * 2);
      ctx.fillStyle = `rgba(255,255,255,${s.opacity})`;
      ctx.fill();
    });
    requestAnimationFrame(drawStars);
  }
  drawStars();

  // Typing effect
  const phrases = [
    "Building things from the Void...",
    "Full-Stack Dev + AI Wrangler 🤖",
    "อยู่ดีๆ bug ก็ขึ้น 🐛",
    "git push --force 💀",
    "if(coffee == 0) sleep();",
    "Turning caffeine into code ☕",
    "ไม่มี code ที่ดี มีแต่ code ที่ยัง deploy ไม่ได้",
  ];
  
  let pi = 0, ci = 0, del = false, cur = '';
  const el = document.getElementById('typingEl');

  function type() {
    const phrase = phrases[pi];
    if (!del) {
      cur = phrase.slice(0, ci + 1);
      ci++;
      if (ci === phrase.length) { del = true; setTimeout(type, 2000); return; }
    } else {
      cur = phrase.slice(0, ci - 1);
      ci--;
      if (ci === 0) { del = false; pi = (pi + 1) % phrases.length; }
    }
    el.textContent = cur;
    setTimeout(type, del ? 40 : 80);
  }
  type();

  // Count-up stats
  const stats = [
    { id: 'c1', target: 9842, suffix: '' },
    { id: 'c2', target: 4206, suffix: '' },
    { id: 'c3', target: 4205, suffix: '' },
    { id: 'c4', target: 8, suffix: 'k' },
  ];

  function countUp(el, target, suffix, duration) {
    let start = 0, step = target / (duration / 16);
    const interval = setInterval(() => {
      start = Math.min(start + step, target);
      el.textContent = Math.floor(start).toLocaleString() + suffix;
      if (start >= target) clearInterval(interval);
    }, 16);
  }

  setTimeout(() => {
    stats.forEach(s => countUp(document.getElementById(s.id), s.target, s.suffix, 2000));
  }, 500);

  // Snake grid
  const grid = document.getElementById('snakeGrid');
  const COLS = 52, ROWS = 7;
  const dots = [];

  for (let i = 0; i < COLS * ROWS; i++) {
    const d = document.createElement('div');
    d.className = 'dot';
    if (Math.random() > 0.7) d.classList.add('contribution');
    if (Math.random() > 0.9) d.classList.add('hot');
    grid.appendChild(d);
    dots.push(d);
  }

  let snakePos = 0;
  let snakeTrail = [];

  function animateSnake() {
    dots.forEach(d => { d.classList.remove('active', 'trail'); });
    snakeTrail.unshift(snakePos);
    if (snakeTrail.length > 8) snakeTrail.pop();
    
    snakeTrail.forEach((pos, i) => {
      if (dots[pos]) {
        dots[pos].classList.add(i === 0 ? 'active' : 'trail');
      }
    });

    snakePos++;
    if (snakePos >= COLS * ROWS) snakePos = 0;
    setTimeout(animateSnake, 80);
  }
  animateSnake();

  // 3D card tilt
  document.querySelectorAll('.card-3d').forEach(card => {
    card.addEventListener('mousemove', e => {
      const rect = card.getBoundingClientRect();
      const x = (e.clientX - rect.left) / rect.width - 0.5;
      const y = (e.clientY - rect.top) / rect.height - 0.5;
      card.style.transform = `perspective(1000px) rotateX(${-y * 6}deg) rotateY(${x * 6}deg) translateY(-4px)`;
    });
    card.addEventListener('mouseleave', () => {
      card.style.transform = '';
    });
  });

  // Fade-in on scroll
  const obs = new IntersectionObserver(entries => {
    entries.forEach((e, i) => {
      if (e.isIntersecting) {
        setTimeout(() => e.target.classList.add('visible'), i * 100);
        obs.unobserve(e.target);
      }
    });
  }, { threshold: 0.1 });

  document.querySelectorAll('.fade-in').forEach(el => obs.observe(el));
</script>

</body>
</html>
