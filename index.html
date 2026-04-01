<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>TubeAI – YouTube Channel Analyzer</title>
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=DM+Sans:wght@300;400;500;600&family=JetBrains+Mono:wght@400;600&display=swap" rel="stylesheet"/>
<script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/4.4.1/chart.umd.min.js"></script>
<style>
  :root {
    --red: #ff0000;
    --red-dim: #cc0000;
    --red-glow: rgba(255,0,0,0.18);
    --red-soft: rgba(255,0,0,0.08);
    --bg: #0a0a0a;
    --surface: #111111;
    --surface2: #181818;
    --surface3: #202020;
    --border: rgba(255,255,255,0.07);
    --text: #f0f0f0;
    --muted: #777;
    --accent: #ff4444;
    --font-display: 'Bebas Neue', sans-serif;
    --font-body: 'DM Sans', sans-serif;
    --font-mono: 'JetBrains Mono', monospace;
  }
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  html { scroll-behavior: smooth; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: var(--font-body);
    line-height: 1.6;
    overflow-x: hidden;
  }

  /* NOISE OVERLAY */
  body::before {
    content: '';
    position: fixed; inset: 0; z-index: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.04'/%3E%3C/svg%3E");
    pointer-events: none;
    opacity: 0.4;
  }

  /* NAV */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    display: flex; align-items: center; justify-content: space-between;
    padding: 0 5%;
    height: 68px;
    background: rgba(10,10,10,0.85);
    backdrop-filter: blur(20px);
    border-bottom: 1px solid var(--border);
  }
  .nav-logo {
    font-family: var(--font-display);
    font-size: 1.9rem;
    letter-spacing: 2px;
    color: var(--text);
    display: flex; align-items: center; gap: 10px;
  }
  .nav-logo span { color: var(--red); }
  .nav-logo .play-icon {
    width: 32px; height: 32px;
    background: var(--red);
    border-radius: 8px;
    display: flex; align-items: center; justify-content: center;
    position: relative;
  }
  .nav-logo .play-icon::after {
    content: '';
    border-style: solid;
    border-width: 7px 0 7px 14px;
    border-color: transparent transparent transparent white;
    margin-left: 3px;
  }
  .nav-links {
    display: flex; gap: 36px; list-style: none;
  }
  .nav-links a {
    color: var(--muted); text-decoration: none;
    font-size: 0.88rem; font-weight: 500; letter-spacing: 0.5px;
    text-transform: uppercase;
    transition: color 0.2s;
    position: relative;
  }
  .nav-links a::after {
    content: ''; position: absolute; bottom: -4px; left: 0;
    width: 0; height: 2px; background: var(--red);
    transition: width 0.3s ease;
  }
  .nav-links a:hover { color: var(--text); }
  .nav-links a:hover::after { width: 100%; }

  .hamburger {
    display: none; flex-direction: column; gap: 5px; cursor: pointer; padding: 4px;
  }
  .hamburger span {
    display: block; width: 24px; height: 2px;
    background: var(--text); border-radius: 2px;
    transition: all 0.3s;
  }

  /* SECTIONS */
  section { position: relative; z-index: 1; }

  /* ===== HOME ===== */
  #home {
    min-height: 100vh;
    display: flex; flex-direction: column; align-items: center; justify-content: center;
    padding: 100px 5% 60px;
    overflow: hidden;
  }
  .hero-bg {
    position: absolute; inset: 0; z-index: 0;
    background: radial-gradient(ellipse 80% 60% at 50% 0%, rgba(255,0,0,0.12) 0%, transparent 70%);
  }
  .hero-grid {
    position: absolute; inset: 0; z-index: 0;
    background-image:
      linear-gradient(var(--border) 1px, transparent 1px),
      linear-gradient(90deg, var(--border) 1px, transparent 1px);
    background-size: 60px 60px;
    mask-image: radial-gradient(ellipse 70% 70% at 50% 50%, black 40%, transparent 100%);
  }
  .hero-content { position: relative; z-index: 2; text-align: center; max-width: 900px; }

  .hero-badge {
    display: inline-flex; align-items: center; gap: 8px;
    background: var(--red-soft);
    border: 1px solid rgba(255,0,0,0.25);
    border-radius: 999px;
    padding: 6px 18px;
    font-size: 0.78rem; font-weight: 600; letter-spacing: 1px;
    text-transform: uppercase; color: var(--accent);
    margin-bottom: 32px;
    animation: fadeDown 0.8s ease both;
  }
  .hero-badge .dot {
    width: 6px; height: 6px; border-radius: 50%;
    background: var(--red);
    animation: pulse 1.5s infinite;
  }
  @keyframes pulse {
    0%,100% { opacity: 1; transform: scale(1); }
    50% { opacity: 0.5; transform: scale(1.3); }
  }

  h1.hero-title {
    font-family: var(--font-display);
    font-size: clamp(3.2rem, 9vw, 8rem);
    line-height: 0.95;
    letter-spacing: 2px;
    animation: fadeUp 0.9s ease 0.1s both;
  }
  h1.hero-title .red { color: var(--red); }
  h1.hero-title .outline {
    -webkit-text-stroke: 1px rgba(255,255,255,0.3);
    color: transparent;
  }

  .hero-sub {
    margin-top: 28px;
    font-size: 1.1rem; color: var(--muted); max-width: 560px; margin-inline: auto;
    animation: fadeUp 0.9s ease 0.25s both;
  }

  .hero-ctas {
    margin-top: 44px; display: flex; gap: 16px; justify-content: center; flex-wrap: wrap;
    animation: fadeUp 0.9s ease 0.4s both;
  }
  .btn {
    padding: 14px 32px; border-radius: 8px; font-family: var(--font-body);
    font-size: 0.92rem; font-weight: 600; cursor: pointer; border: none;
    text-decoration: none; display: inline-flex; align-items: center; gap: 8px;
    transition: all 0.25s ease; letter-spacing: 0.3px;
  }
  .btn-primary {
    background: var(--red); color: #fff;
    box-shadow: 0 0 30px rgba(255,0,0,0.3);
  }
  .btn-primary:hover {
    background: var(--accent);
    box-shadow: 0 0 50px rgba(255,0,0,0.5);
    transform: translateY(-2px);
  }
  .btn-ghost {
    background: transparent; color: var(--text);
    border: 1px solid var(--border);
  }
  .btn-ghost:hover {
    border-color: rgba(255,255,255,0.25);
    background: rgba(255,255,255,0.05);
    transform: translateY(-2px);
  }

  .hero-stats {
    margin-top: 70px;
    display: flex; gap: 60px; justify-content: center; flex-wrap: wrap;
    animation: fadeUp 0.9s ease 0.55s both;
  }
  .hero-stat { text-align: center; }
  .hero-stat .num {
    font-family: var(--font-display);
    font-size: 2.8rem; color: var(--red); line-height: 1;
  }
  .hero-stat .lbl { font-size: 0.78rem; color: var(--muted); text-transform: uppercase; letter-spacing: 1px; margin-top: 4px; }

  /* SCROLL INDICATOR */
  .scroll-ind {
    position: absolute; bottom: 32px; left: 50%; transform: translateX(-50%);
    display: flex; flex-direction: column; align-items: center; gap: 6px;
    color: var(--muted); font-size: 0.72rem; text-transform: uppercase; letter-spacing: 2px;
    animation: fadeUp 1s ease 1s both;
  }
  .scroll-ind .arrow {
    width: 20px; height: 20px;
    border-right: 2px solid var(--muted);
    border-bottom: 2px solid var(--muted);
    transform: rotate(45deg);
    animation: bounce 1.5s infinite;
  }
  @keyframes bounce { 0%,100% { transform: rotate(45deg) translateY(0); } 50% { transform: rotate(45deg) translateY(6px); } }

  /* ===== FEATURES ===== */
  #features {
    padding: 120px 5%;
    background: var(--surface);
  }

  .section-label {
    font-family: var(--font-mono);
    font-size: 0.75rem; color: var(--red);
    text-transform: uppercase; letter-spacing: 3px;
    margin-bottom: 16px; display: block;
  }
  .section-title {
    font-family: var(--font-display);
    font-size: clamp(2.4rem, 5vw, 4rem);
    line-height: 1.05; letter-spacing: 1px;
    margin-bottom: 16px;
  }
  .section-desc { color: var(--muted); max-width: 500px; font-size: 1rem; margin-bottom: 64px; }

  .features-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 2px;
  }
  .feature-card {
    background: var(--surface2);
    padding: 40px 36px;
    position: relative; overflow: hidden;
    transition: background 0.3s;
    cursor: default;
  }
  .feature-card::before {
    content: '';
    position: absolute; top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, transparent, var(--red), transparent);
    transform: scaleX(0);
    transition: transform 0.4s ease;
  }
  .feature-card:hover { background: var(--surface3); }
  .feature-card:hover::before { transform: scaleX(1); }

  .feat-icon {
    width: 52px; height: 52px; border-radius: 12px;
    background: var(--red-soft);
    border: 1px solid rgba(255,0,0,0.2);
    display: flex; align-items: center; justify-content: center;
    font-size: 1.5rem; margin-bottom: 24px;
    transition: all 0.3s;
  }
  .feature-card:hover .feat-icon {
    background: var(--red-glow);
    box-shadow: 0 0 20px var(--red-glow);
  }
  .feat-title {
    font-family: var(--font-display);
    font-size: 1.5rem; letter-spacing: 1px; margin-bottom: 12px;
  }
  .feat-desc { color: var(--muted); font-size: 0.92rem; line-height: 1.7; }

  .feat-tag {
    display: inline-block; margin-top: 20px;
    background: var(--red-soft); border: 1px solid rgba(255,0,0,0.15);
    color: var(--red); font-size: 0.7rem; font-weight: 600;
    padding: 3px 12px; border-radius: 999px; text-transform: uppercase; letter-spacing: 1px;
    font-family: var(--font-mono);
  }

  /* ===== ANALYZER ===== */
  #analyzer {
    padding: 120px 5%;
    background: var(--bg);
  }

  .analyzer-wrap { max-width: 1100px; margin: 0 auto; }

  .input-zone {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 40px;
    margin-bottom: 48px;
    display: flex; gap: 16px; flex-wrap: wrap; align-items: flex-end;
  }
  .input-group { flex: 1; min-width: 260px; }
  .input-group label {
    display: block; font-size: 0.78rem; font-weight: 600;
    text-transform: uppercase; letter-spacing: 1px; color: var(--muted);
    margin-bottom: 10px; font-family: var(--font-mono);
  }
  .input-group input {
    width: 100%; padding: 14px 18px;
    background: var(--surface2); border: 1px solid var(--border);
    border-radius: 8px; color: var(--text); font-family: var(--font-body); font-size: 0.95rem;
    outline: none; transition: border-color 0.25s, box-shadow 0.25s;
  }
  .input-group input:focus {
    border-color: rgba(255,0,0,0.5);
    box-shadow: 0 0 0 3px rgba(255,0,0,0.08);
  }
  .input-group input::placeholder { color: #444; }

  /* DASHBOARD */
  .dashboard { display: none; }
  .dashboard.active { display: block; animation: fadeUp 0.6s ease both; }

  .channel-header {
    display: flex; gap: 24px; align-items: center;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 16px; padding: 28px 36px;
    margin-bottom: 32px; flex-wrap: wrap;
  }
  .channel-avatar {
    width: 72px; height: 72px; border-radius: 50%;
    background: linear-gradient(135deg, var(--red), #ff6600);
    display: flex; align-items: center; justify-content: center;
    font-family: var(--font-display); font-size: 2rem; color: #fff;
    flex-shrink: 0;
    box-shadow: 0 0 30px rgba(255,0,0,0.3);
  }
  .channel-info h3 { font-family: var(--font-display); font-size: 1.8rem; letter-spacing: 1px; }
  .channel-info p { color: var(--muted); font-size: 0.9rem; margin-top: 4px; }
  .channel-badge {
    margin-left: auto;
    background: rgba(0,255,100,0.1); border: 1px solid rgba(0,255,100,0.25);
    color: #00ff66; padding: 6px 16px; border-radius: 999px;
    font-size: 0.75rem; font-weight: 600; text-transform: uppercase;
    letter-spacing: 1px; font-family: var(--font-mono);
    display: flex; align-items: center; gap: 6px;
  }
  .channel-badge::before {
    content: ''; width: 6px; height: 6px; border-radius: 50%; background: #00ff66;
    animation: pulse 1.5s infinite;
  }

  .kpi-row {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
    gap: 16px; margin-bottom: 32px;
  }
  .kpi {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px; padding: 24px 24px 20px;
    position: relative; overflow: hidden;
    transition: transform 0.25s, box-shadow 0.25s;
  }
  .kpi:hover {
    transform: translateY(-3px);
    box-shadow: 0 12px 40px rgba(0,0,0,0.4);
  }
  .kpi::after {
    content: '';
    position: absolute; bottom: 0; left: 0; right: 0; height: 2px;
    background: linear-gradient(90deg, var(--red), transparent);
  }
  .kpi-label {
    font-family: var(--font-mono); font-size: 0.7rem;
    color: var(--muted); text-transform: uppercase; letter-spacing: 1.5px;
    margin-bottom: 8px;
  }
  .kpi-value {
    font-family: var(--font-display); font-size: 2.2rem; color: var(--text); line-height: 1;
  }
  .kpi-change {
    margin-top: 8px; font-size: 0.78rem; font-weight: 600;
    display: flex; align-items: center; gap: 4px;
  }
  .kpi-change.up { color: #00cc66; }
  .kpi-change.down { color: var(--red); }

  .charts-grid {
    display: grid; grid-template-columns: 1fr 1fr; gap: 24px; margin-bottom: 24px;
  }
  .chart-box {
    background: var(--surface); border: 1px solid var(--border);
    border-radius: 16px; padding: 28px;
  }
  .chart-box h4 {
    font-family: var(--font-display); font-size: 1.2rem; letter-spacing: 0.5px;
    margin-bottom: 4px;
  }
  .chart-box p { font-size: 0.78rem; color: var(--muted); margin-bottom: 20px; }
  .chart-box canvas { max-height: 240px; }

  .chart-full { grid-column: 1 / -1; }
  .chart-full canvas { max-height: 280px; }

  /* TABLE */
  .top-videos {
    background: var(--surface); border: 1px solid var(--border);
    border-radius: 16px; padding: 28px; margin-bottom: 24px;
  }
  .top-videos h4 { font-family: var(--font-display); font-size: 1.2rem; letter-spacing: 0.5px; margin-bottom: 20px; }
  table { width: 100%; border-collapse: collapse; font-size: 0.88rem; }
  th {
    text-align: left; font-family: var(--font-mono); font-size: 0.7rem;
    color: var(--muted); text-transform: uppercase; letter-spacing: 1px;
    padding: 10px 16px; border-bottom: 1px solid var(--border);
  }
  td { padding: 13px 16px; border-bottom: 1px solid rgba(255,255,255,0.04); }
  tr:last-child td { border-bottom: none; }
  tr:hover td { background: var(--surface2); }
  .video-rank {
    font-family: var(--font-mono); color: var(--red); font-weight: 600;
    font-size: 0.8rem;
  }
  .views-bar {
    display: flex; align-items: center; gap: 10px;
  }
  .bar-bg {
    flex: 1; height: 4px; background: var(--surface3); border-radius: 2px; overflow: hidden;
  }
  .bar-fill {
    height: 100%; background: linear-gradient(90deg, var(--red), #ff6600);
    border-radius: 2px;
  }

  /* ===== ABOUT ===== */
  #about {
    padding: 120px 5%;
    background: var(--surface);
  }
  .about-grid {
    display: grid; grid-template-columns: 1fr 1fr; gap: 80px; align-items: center;
    max-width: 1100px; margin: 0 auto;
  }
  .about-text .section-desc { max-width: 100%; }

  .about-timeline { display: flex; flex-direction: column; gap: 0; }
  .tl-item {
    display: flex; gap: 20px; padding: 24px 0;
    border-bottom: 1px solid var(--border);
    position: relative;
  }
  .tl-item:last-child { border-bottom: none; }
  .tl-num {
    font-family: var(--font-display); font-size: 2.5rem; color: var(--red-dim);
    line-height: 1; flex-shrink: 0; width: 60px;
    opacity: 0.4;
    transition: opacity 0.3s;
  }
  .tl-item:hover .tl-num { opacity: 1; }
  .tl-body h5 { font-family: var(--font-display); font-size: 1.15rem; letter-spacing: 0.5px; margin-bottom: 6px; }
  .tl-body p { color: var(--muted); font-size: 0.88rem; line-height: 1.6; }

  .tech-pills {
    display: flex; flex-wrap: wrap; gap: 10px; margin-top: 36px;
  }
  .pill {
    background: var(--surface2); border: 1px solid var(--border);
    padding: 6px 16px; border-radius: 999px;
    font-family: var(--font-mono); font-size: 0.75rem; color: var(--muted);
    transition: all 0.25s;
  }
  .pill:hover {
    border-color: rgba(255,0,0,0.35);
    color: var(--red);
    background: var(--red-soft);
  }

  /* FOOTER */
  footer {
    background: var(--bg); border-top: 1px solid var(--border);
    padding: 48px 5% 36px;
    display: flex; align-items: center; justify-content: space-between;
    flex-wrap: wrap; gap: 20px; position: relative; z-index: 1;
  }
  .foot-logo { font-family: var(--font-display); font-size: 1.6rem; letter-spacing: 2px; }
  .foot-logo span { color: var(--red); }
  footer p { color: var(--muted); font-size: 0.82rem; }

  /* ANIMATIONS */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(24px); }
    to { opacity: 1; transform: translateY(0); }
  }
  @keyframes fadeDown {
    from { opacity: 0; transform: translateY(-16px); }
    to { opacity: 1; transform: translateY(0); }
  }

  .reveal {
    opacity: 0; transform: translateY(30px);
    transition: opacity 0.7s ease, transform 0.7s ease;
  }
  .reveal.visible { opacity: 1; transform: translateY(0); }

  /* Loading spinner */
  .spinner {
    display: none; width: 36px; height: 36px;
    border: 3px solid var(--border);
    border-top-color: var(--red);
    border-radius: 50%;
    animation: spin 0.7s linear infinite;
    margin: 40px auto;
  }
  .spinner.active { display: block; }
  @keyframes spin { to { transform: rotate(360deg); } }

  /* MOBILE NAV */
  .mobile-menu {
    display: none;
    position: fixed; top: 68px; left: 0; right: 0; z-index: 99;
    background: rgba(10,10,10,0.97);
    backdrop-filter: blur(20px);
    border-bottom: 1px solid var(--border);
    flex-direction: column; padding: 24px 5%;
    gap: 20px;
  }
  .mobile-menu.open { display: flex; }
  .mobile-menu a {
    color: var(--muted); text-decoration: none;
    font-size: 1.1rem; font-weight: 500;
    padding: 8px 0;
    border-bottom: 1px solid var(--border);
    transition: color 0.2s;
  }
  .mobile-menu a:hover { color: var(--text); }

  /* RESPONSIVE */
  @media (max-width: 900px) {
    .nav-links { display: none; }
    .hamburger { display: flex; }
    .charts-grid { grid-template-columns: 1fr; }
    .about-grid { grid-template-columns: 1fr; gap: 48px; }
    .chart-full { grid-column: 1; }
    .hero-stats { gap: 32px; }
    .input-zone { flex-direction: column; }
  }
  @media (max-width: 560px) {
    .kpi-row { grid-template-columns: 1fr 1fr; }
    .channel-header { flex-direction: column; align-items: flex-start; }
    .channel-badge { margin-left: 0; }
    th:last-child, td:last-child { display: none; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="nav-logo">
    <div class="play-icon"></div>
    Tube<span>AI</span>
  </div>
  <ul class="nav-links">
    <li><a href="#home">Home</a></li>
    <li><a href="#features">Features</a></li>
    <li><a href="#analyzer">Analyzer</a></li>
    <li><a href="#about">About</a></li>
  </ul>
  <div class="hamburger" onclick="toggleMenu()" id="hamburger">
    <span></span><span></span><span></span>
  </div>
</nav>
<div class="mobile-menu" id="mobileMenu">
  <a href="#home" onclick="toggleMenu()">Home</a>
  <a href="#features" onclick="toggleMenu()">Features</a>
  <a href="#analyzer" onclick="toggleMenu()">Analyzer</a>
  <a href="#about" onclick="toggleMenu()">About</a>
</div>

<!-- ===== HOME ===== -->
<section id="home">
  <div class="hero-bg"></div>
  <div class="hero-grid"></div>
  <div class="hero-content">
    <div class="hero-badge"><span class="dot"></span> AI-Powered Analytics Platform</div>
    <h1 class="hero-title">
      YOUTUBE<br>
      <span class="red">CHANNEL</span><br>
      <span class="outline">ANALYZER</span>
    </h1>
    <p class="hero-sub">Decode your channel's performance with machine learning. Predict growth, track engagement, and outpace the algorithm.</p>
    <div class="hero-ctas">
      <a href="#analyzer" class="btn btn-primary">▶ Analyze a Channel</a>
      <a href="#features" class="btn btn-ghost">Explore Features</a>
    </div>
    <div class="hero-stats">
      <div class="hero-stat">
        <div class="num">98%</div>
        <div class="lbl">Prediction Accuracy</div>
      </div>
      <div class="hero-stat">
        <div class="num">250K+</div>
        <div class="lbl">Channels Analyzed</div>
      </div>
      <div class="hero-stat">
        <div class="num">12</div>
        <div class="lbl">AI Metrics</div>
      </div>
      <div class="hero-stat">
        <div class="num">Real-time</div>
        <div class="lbl">Data Sync</div>
      </div>
    </div>
  </div>
  <div class="scroll-ind">Scroll <div class="arrow"></div></div>
</section>

<!-- ===== FEATURES ===== -->
<section id="features">
  <span class="section-label reveal">// What we offer</span>
  <h2 class="section-title reveal">Powerful AI<br>Analytics Suite</h2>
  <p class="section-desc reveal">Six precision-engineered tools that transform raw YouTube data into strategic intelligence.</p>

  <div class="features-grid">
    <div class="feature-card reveal">
      <div class="feat-icon">🤖</div>
      <div class="feat-title">AI Growth Predictor</div>
      <p class="feat-desc">Our LSTM neural network models project subscriber and view growth up to 12 months ahead, trained on 500M+ data points from YouTube's ecosystem.</p>
      <span class="feat-tag">Machine Learning</span>
    </div>
    <div class="feature-card reveal">
      <div class="feat-icon">📊</div>
      <div class="feat-title">Engagement Analytics</div>
      <p class="feat-desc">Deep-dive into likes, comments, shares, and watch-time patterns. Identify viral content fingerprints and replicate success consistently.</p>
      <span class="feat-tag">Real-time</span>
    </div>
    <div class="feature-card reveal">
      <div class="feat-icon">🎯</div>
      <div class="feat-title">Competitor Intelligence</div>
      <p class="feat-desc">Benchmark against top channels in your niche. Discover content gaps, optimal upload cadence, and audience overlap opportunities.</p>
      <span class="feat-tag">Competitive</span>
    </div>
    <div class="feature-card reveal">
      <div class="feat-icon">💡</div>
      <div class="feat-title">Content Optimization</div>
      <p class="feat-desc">AI-scored titles, thumbnails, and descriptions. Get actionable recommendations to maximize click-through rate before you publish.</p>
      <span class="feat-tag">SEO + AI</span>
    </div>
    <div class="feature-card reveal">
      <div class="feat-icon">📈</div>
      <div class="feat-title">Revenue Forecasting</div>
      <p class="feat-desc">Estimate CPM, RPM, and total revenue potential based on your niche, geography, and seasonal ad spend cycles.</p>
      <span class="feat-tag">Monetization</span>
    </div>
    <div class="feature-card reveal">
      <div class="feat-icon">🔔</div>
      <div class="feat-title">Smart Alerts</div>
      <p class="feat-desc">Set custom thresholds and receive instant notifications when your channel hits milestones or when anomalies require your attention.</p>
      <span class="feat-tag">Automation</span>
    </div>
  </div>
</section>

<!-- ===== ANALYZER ===== -->
<section id="analyzer">
  <div class="analyzer-wrap">
    <span class="section-label reveal">// Try it now</span>
    <h2 class="section-title reveal">Channel Analyzer</h2>
    <p class="section-desc reveal">Enter any YouTube channel URL to generate a full AI-powered analytics report instantly.</p>

    <div class="input-zone reveal">
      <div class="input-group">
        <label>YouTube Channel URL</label>
        <input type="text" id="channelUrl" placeholder="https://youtube.com/@mkbhd" />
      </div>
      <div class="input-group" style="max-width:200px">
        <label>Time Range</label>
        <input type="text" id="timeRange" value="Last 12 Months" readonly />
      </div>
      <button class="btn btn-primary" onclick="runAnalysis()" style="flex-shrink:0; height:48px;">
        ▶ Analyze
      </button>
    </div>

    <div class="spinner" id="spinner"></div>

    <!-- DASHBOARD -->
    <div class="dashboard" id="dashboard">

      <div class="channel-header">
        <div class="channel-avatar" id="avatarLetter">M</div>
        <div class="channel-info">
          <h3 id="channelName">MKBHD</h3>
          <p id="channelHandle">@mkbhd · Technology · United States</p>
        </div>
        <div class="channel-badge">Live Data</div>
      </div>

      <div class="kpi-row" id="kpiRow"></div>

      <div class="charts-grid">
        <div class="chart-box">
          <h4>Subscriber Growth</h4>
          <p>Monthly subscriber additions over 12 months</p>
          <canvas id="subChart"></canvas>
        </div>
        <div class="chart-box">
          <h4>Engagement Breakdown</h4>
          <p>Likes · Comments · Shares distribution</p>
          <canvas id="engChart"></canvas>
        </div>
        <div class="chart-box chart-full">
          <h4>AI Growth Prediction — Next 6 Months</h4>
          <p>Historical data + ML forecast with confidence interval</p>
          <canvas id="predChart"></canvas>
        </div>
        <div class="chart-box">
          <h4>Views Per Video</h4>
          <p>Average views per upload by month</p>
          <canvas id="viewChart"></canvas>
        </div>
        <div class="chart-box">
          <h4>Audience Demographics</h4>
          <p>Age group distribution of viewers</p>
          <canvas id="demoChart"></canvas>
        </div>
      </div>

      <div class="top-videos">
        <h4>🏆 Top Performing Videos</h4>
        <table>
          <thead>
            <tr><th>#</th><th>Title</th><th>Views</th><th>Engagement</th><th>Revenue Est.</th></tr>
          </thead>
          <tbody id="videoTable"></tbody>
        </table>
      </div>

    </div>
  </div>
</section>

<!-- ===== ABOUT ===== -->
<section id="about">
  <div class="about-grid">
    <div class="about-text">
      <span class="section-label reveal">// About the project</span>
      <h2 class="section-title reveal">Built for the<br>Creator Economy</h2>
      <p class="section-desc reveal">TubeAI was developed as a capstone AI/ML project exploring how advanced analytics can democratize data-driven decision-making for content creators of all sizes.</p>
      <div class="tech-pills reveal">
        <span class="pill">Python</span>
        <span class="pill">TensorFlow</span>
        <span class="pill">YouTube Data API v3</span>
        <span class="pill">LSTM Networks</span>
        <span class="pill">Chart.js</span>
        <span class="pill">FastAPI</span>
        <span class="pill">PostgreSQL</span>
        <span class="pill">Docker</span>
        <span class="pill">React</span>
        <span class="pill">Node.js</span>
      </div>
    </div>
    <div class="about-timeline reveal">
      <div class="tl-item">
        <div class="tl-num">01</div>
        <div class="tl-body">
          <h5>Data Ingestion</h5>
          <p>Pulls channel statistics, video metadata, and audience signals via YouTube Data API v3 with smart caching layers.</p>
        </div>
      </div>
      <div class="tl-item">
        <div class="tl-num">02</div>
        <div class="tl-body">
          <h5>ML Processing</h5>
          <p>LSTM models process time-series subscriber/view data to identify trends, seasonality, and growth velocity vectors.</p>
        </div>
      </div>
      <div class="tl-item">
        <div class="tl-num">03</div>
        <div class="tl-body">
          <h5>Insight Generation</h5>
          <p>Proprietary scoring algorithms rank content quality, SEO performance, and engagement health against niche benchmarks.</p>
        </div>
      </div>
      <div class="tl-item">
        <div class="tl-num">04</div>
        <div class="tl-body">
          <h5>Predictive Output</h5>
          <p>Delivers 6-12 month growth forecasts with confidence intervals and personalized optimization recommendations.</p>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="foot-logo">Tube<span>AI</span></div>
  <p>AI-Based YouTube Analytics & Growth Predictor · Final Year Project</p>
  <p style="color:#333">© 2025 TubeAI</p>
</footer>

<script>
/* ======= NAV MOBILE ======= */
function toggleMenu() {
  const m = document.getElementById('mobileMenu');
  m.classList.toggle('open');
}

/* ======= SCROLL REVEAL ======= */
const observer = new IntersectionObserver((entries) => {
  entries.forEach(e => { if (e.isIntersecting) { e.target.classList.add('visible'); } });
}, { threshold: 0.12 });
document.querySelectorAll('.reveal').forEach(el => observer.observe(el));

/* ======= DUMMY DATA ======= */
const months = ['Jan','Feb','Mar','Apr','May','Jun','Jul','Aug','Sep','Oct','Nov','Dec'];

function randArr(len, min, max, smooth=false) {
  let arr = [];
  let cur = min + Math.random()*(max-min);
  for(let i=0;i<len;i++){
    if(smooth){ cur += (Math.random()-0.3)*(max-min)*0.15; cur = Math.max(min, Math.min(max,cur)); }
    else { cur = min + Math.random()*(max-min); }
    arr.push(Math.round(cur));
  }
  return arr;
}

const DUMMY = {
  name: '',
  subs:    randArr(12, 8000, 60000, true),
  views:   randArr(12, 500000, 4000000, true),
  avgView: randArr(12, 80000, 600000, true),
  historical: randArr(12, 10, 16, true).map(v=>v*1000000),
  prediction: [null,null,null,null,null,null,null,null,null,null,null,null,16200000,17100000,18400000,19600000,20900000,22300000],
  confHigh: [null,null,null,null,null,null,null,null,null,null,null,null,16800000,18200000,19800000,21500000,23200000,25100000],
  confLow:  [null,null,null,null,null,null,null,null,null,null,null,null,15600000,16000000,17000000,17700000,18600000,19500000],
};

const months18 = [...months, 'Jan','Feb','Mar','Apr','May','Jun'];

const TOP_VIDEOS = [
  { title:'I Tested Every Flagship Phone of 2024', views:'18.4M', eng:'9.2%', rev:'$62,000' },
  { title:'Why I Switched to Linux (and came back)', views:'12.1M', eng:'11.7%', rev:'$40,500' },
  { title:'The Camera That Changed Everything', views:'9.8M', eng:'8.4%', rev:'$33,200' },
  { title:'Ultimate PC Build Guide 2025', views:'7.3M', eng:'7.9%', rev:'$24,800' },
  { title:'AirPods Pro 4 — Honest Review After 30 Days', views:'6.1M', eng:'6.5%', rev:'$20,600' },
];

let charts = {};

/* ======= KPI ======= */
function renderKPIs() {
  const kpis = [
    { label:'Total Subscribers', value:'16.2M', change:'+8.4%', dir:'up' },
    { label:'Total Views', value:'2.8B', change:'+12.1%', dir:'up' },
    { label:'Avg Views/Video', value:'4.2M', change:'+5.3%', dir:'up' },
    { label:'Upload Frequency', value:'2× /wk', change:'+1 video', dir:'up' },
    { label:'Engagement Rate', value:'8.7%', change:'+0.4%', dir:'up' },
    { label:'Est. Monthly Revenue', value:'$180K', change:'-2.1%', dir:'down' },
  ];
  const row = document.getElementById('kpiRow');
  row.innerHTML = kpis.map(k=>`
    <div class="kpi">
      <div class="kpi-label">${k.label}</div>
      <div class="kpi-value">${k.value}</div>
      <div class="kpi-change ${k.dir}">${k.dir==='up'?'↑':'↓'} ${k.change} vs last period</div>
    </div>
  `).join('');
}

/* ======= CHARTS ======= */
const CHART_DEFAULTS = {
  color: '#f0f0f0',
  plugins: { legend: { labels: { color:'#777', font:{family:'JetBrains Mono', size:11} } } },
  scales: {
    x: { ticks:{color:'#555', font:{family:'JetBrains Mono',size:10}}, grid:{color:'rgba(255,255,255,0.04)'} },
    y: { ticks:{color:'#555', font:{family:'JetBrains Mono',size:10}}, grid:{color:'rgba(255,255,255,0.04)'} },
  }
};

function destroyCharts() {
  Object.values(charts).forEach(c => c && c.destroy());
  charts = {};
}

function renderCharts() {
  destroyCharts();

  /* Subscriber Growth */
  charts.sub = new Chart(document.getElementById('subChart'), {
    type:'bar',
    data:{
      labels: months,
      datasets:[{
        label:'New Subscribers',
        data: DUMMY.subs,
        backgroundColor: months.map((_,i)=> i===11?'rgba(255,0,0,0.9)':'rgba(255,0,0,0.4)'),
        borderRadius: 4,
        borderSkipped: false,
      }]
    },
    options:{ ...CHART_DEFAULTS, responsive:true }
  });

  /* Engagement Doughnut */
  charts.eng = new Chart(document.getElementById('engChart'), {
    type:'doughnut',
    data:{
      labels:['Likes','Comments','Shares','Saves'],
      datasets:[{
        data:[62,18,12,8],
        backgroundColor:['rgba(255,0,0,0.8)','rgba(255,100,0,0.7)','rgba(255,180,0,0.6)','rgba(100,100,255,0.6)'],
        borderColor:'#111', borderWidth:3,
        hoverOffset: 8
      }]
    },
    options:{
      responsive:true, cutout:'65%',
      plugins:{ legend:{ position:'bottom', labels:{color:'#777',font:{family:'JetBrains Mono',size:11},padding:16} } }
    }
  });

  /* Prediction Chart */
  charts.pred = new Chart(document.getElementById('predChart'), {
    type:'line',
    data:{
      labels: months18,
      datasets:[
        {
          label:'Historical Subscribers',
          data: DUMMY.historical,
          borderColor:'rgba(255,0,0,0.8)', backgroundColor:'rgba(255,0,0,0.06)',
          borderWidth:2.5, pointRadius:3, fill:true, tension:0.4,
        },
        {
          label:'AI Prediction',
          data: DUMMY.prediction,
          borderColor:'rgba(0,200,255,0.9)', backgroundColor:'transparent',
          borderWidth:2.5, pointRadius:3, borderDash:[6,4], tension:0.4,
        },
        {
          label:'Confidence High',
          data: DUMMY.confHigh,
          borderColor:'rgba(0,200,255,0.2)', backgroundColor:'rgba(0,200,255,0.06)',
          borderWidth:1, pointRadius:0, fill:'+1', tension:0.4,
        },
        {
          label:'Confidence Low',
          data: DUMMY.confLow,
          borderColor:'rgba(0,200,255,0.2)', backgroundColor:'rgba(0,200,255,0.06)',
          borderWidth:1, pointRadius:0, fill:false, tension:0.4,
        },
      ]
    },
    options:{
      responsive:true,
      plugins:{ legend:{ labels:{color:'#777',font:{family:'JetBrains Mono',size:11}} } },
      scales:{
        x:{ticks:{color:'#555',font:{family:'JetBrains Mono',size:10}},grid:{color:'rgba(255,255,255,0.04)'}},
        y:{ticks:{color:'#555',font:{family:'JetBrains Mono',size:10}, callback:v=>(v/1e6).toFixed(1)+'M'},grid:{color:'rgba(255,255,255,0.04)'}},
      }
    }
  });

  /* Views Per Video */
  charts.view = new Chart(document.getElementById('viewChart'), {
    type:'line',
    data:{
      labels: months,
      datasets:[{
        label:'Avg Views/Video',
        data: DUMMY.avgView,
        borderColor:'rgba(255,140,0,0.9)',
        backgroundColor:'rgba(255,140,0,0.08)',
        borderWidth:2.5, fill:true, tension:0.45, pointBackgroundColor:'rgba(255,140,0,0.9)', pointRadius:4
      }]
    },
    options:{
      responsive:true,
      plugins:{ legend:{ labels:{color:'#777',font:{family:'JetBrains Mono',size:11}} } },
      scales:{
        x:{ticks:{color:'#555',font:{family:'JetBrains Mono',size:10}},grid:{color:'rgba(255,255,255,0.04)'}},
        y:{ticks:{color:'#555',font:{family:'JetBrains Mono',size:10},callback:v=>(v/1e3).toFixed(0)+'K'},grid:{color:'rgba(255,255,255,0.04)'}},
      }
    }
  });

  /* Demographics */
  charts.demo = new Chart(document.getElementById('demoChart'), {
    type:'bar',
    data:{
      labels:['13-17','18-24','25-34','35-44','45-54','55+'],
      datasets:[{
        label:'Audience %',
        data:[5,28,38,17,8,4],
        backgroundColor:[
          'rgba(255,0,0,0.35)','rgba(255,0,0,0.55)','rgba(255,0,0,0.85)',
          'rgba(255,0,0,0.55)','rgba(255,0,0,0.35)','rgba(255,0,0,0.2)'
        ],
        borderRadius:4, borderSkipped:false,
      }]
    },
    options:{
      responsive:true, indexAxis:'y',
      plugins:{ legend:{display:false} },
      scales:{
        x:{ticks:{color:'#555',font:{family:'JetBrains Mono',size:10},callback:v=>v+'%'},grid:{color:'rgba(255,255,255,0.04)'}},
        y:{ticks:{color:'#777',font:{family:'JetBrains Mono',size:11}},grid:{color:'transparent'}},
      }
    }
  });
}

/* ======= VIDEO TABLE ======= */
function renderTable() {
  const tbody = document.getElementById('videoTable');
  tbody.innerHTML = TOP_VIDEOS.map((v,i)=>{
    const pct = Math.round((5-i)/5*100);
    return `<tr>
      <td><span class="video-rank">#${i+1}</span></td>
      <td>${v.title}</td>
      <td>
        <div class="views-bar">
          ${v.views}
          <div class="bar-bg"><div class="bar-fill" style="width:${pct}%"></div></div>
        </div>
      </td>
      <td>${v.eng}</td>
      <td>${v.rev}</td>
    </tr>`;
  }).join('');
}

/* ======= PARSE CHANNEL NAME ======= */
function parseName(url) {
  const raw = url.trim();
  if(!raw) return 'Demo Channel';
  const m = raw.match(/@([^\/\s]+)/);
  if(m) return m[1].charAt(0).toUpperCase() + m[1].slice(1).replace(/\d+/g,'');
  const parts = raw.split('/').filter(Boolean);
  const last = parts[parts.length-1];
  return last.replace(/@/,'').replace(/\b\w/g,c=>c.toUpperCase()).slice(0,16) || 'Demo Channel';
}

/* ======= MAIN ANALYSIS ======= */
function runAnalysis() {
  const url = document.getElementById('channelUrl').value;
  const name = parseName(url);
  const spinner = document.getElementById('spinner');
  const dash = document.getElementById('dashboard');

  dash.classList.remove('active');
  spinner.classList.add('active');

  setTimeout(()=>{
    spinner.classList.remove('active');

    document.getElementById('channelName').textContent = name;
    document.getElementById('avatarLetter').textContent = name.charAt(0).toUpperCase();
    document.getElementById('channelHandle').textContent = `@${name.toLowerCase()} · Technology · Global`;

    renderKPIs();
    renderTable();

    dash.classList.add('active');
    setTimeout(renderCharts, 80);

    dash.scrollIntoView({behavior:'smooth', block:'start'});
  }, 1800);
}

/* Enter key trigger */
document.getElementById('channelUrl').addEventListener('keydown', e => {
  if(e.key === 'Enter') runAnalysis();
});
</script>
</body>
</html>
