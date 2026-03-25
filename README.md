<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Shahid Afrid Khan — GitHub Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&family=Rajdhani:wght@300;400;500;600;700&family=JetBrains+Mono:wght@300;400;700&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #020409;
    --surface: #0d1117;
    --surface2: #161b22;
    --border: #21262d;
    --cyan: #00f5ff;
    --cyan2: #00bcd4;
    --purple: #b347ea;
    --purple2: #7c3aed;
    --green: #39d353;
    --orange: #ff6b35;
    --yellow: #ffd700;
    --text: #e6edf3;
    --muted: #7d8590;
    --glow-cyan: 0 0 20px #00f5ff55, 0 0 60px #00f5ff22;
    --glow-purple: 0 0 20px #b347ea55, 0 0 60px #b347ea22;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Rajdhani', sans-serif;
    overflow-x: hidden;
    min-height: 100vh;
  }

  /* ─── CANVAS BACKGROUND ─── */
  #bg-canvas {
    position: fixed;
    top: 0; left: 0;
    width: 100%; height: 100%;
    z-index: 0;
    pointer-events: none;
  }

  /* ─── MAIN WRAPPER ─── */
  .wrapper {
    position: relative;
    z-index: 1;
    max-width: 960px;
    margin: 0 auto;
    padding: 40px 24px 80px;
  }

  /* ─── HERO ─── */
  .hero {
    display: grid;
    grid-template-columns: 220px 1fr;
    gap: 40px;
    align-items: center;
    margin-bottom: 60px;
    animation: fadeSlideDown 1s ease both;
  }

  @keyframes fadeSlideDown {
    from { opacity: 0; transform: translateY(-30px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  /* avatar ring */
  .avatar-wrap {
    position: relative;
    width: 200px;
    height: 200px;
  }

  .avatar-ring {
    position: absolute;
    inset: -8px;
    border-radius: 50%;
    background: conic-gradient(
      var(--cyan) 0deg,
      var(--purple) 120deg,
      var(--orange) 240deg,
      var(--cyan) 360deg
    );
    animation: spin 4s linear infinite;
  }

  @keyframes spin {
    to { transform: rotate(360deg); }
  }

  .avatar-ring::after {
    content: '';
    position: absolute;
    inset: 4px;
    border-radius: 50%;
    background: var(--bg);
  }

  .avatar-img {
    position: absolute;
    inset: 0;
    border-radius: 50%;
    width: 100%;
    height: 100%;
    object-fit: cover;
    z-index: 2;
    border: 3px solid var(--surface2);
  }

  /* Pulse ring */
  .avatar-pulse {
    position: absolute;
    inset: -20px;
    border-radius: 50%;
    border: 2px solid var(--cyan);
    opacity: 0;
    animation: pulse-ring 2.5s ease-out infinite;
  }
  .avatar-pulse:nth-child(3) { animation-delay: 0.8s; }
  .avatar-pulse:nth-child(4) { animation-delay: 1.6s; }

  @keyframes pulse-ring {
    0%   { transform: scale(0.9); opacity: 0.6; }
    100% { transform: scale(1.4); opacity: 0; }
  }

  /* Status dot */
  .status-dot {
    position: absolute;
    bottom: 10px; right: 10px;
    width: 18px; height: 18px;
    border-radius: 50%;
    background: var(--green);
    border: 3px solid var(--bg);
    z-index: 3;
    box-shadow: 0 0 10px var(--green);
    animation: blink 2s ease-in-out infinite;
  }

  @keyframes blink {
    0%, 100% { box-shadow: 0 0 10px var(--green); }
    50%       { box-shadow: 0 0 20px var(--green), 0 0 40px var(--green); }
  }

  /* Hero text */
  .hero-text { animation: fadeSlideLeft 1s 0.2s ease both; }

  @keyframes fadeSlideLeft {
    from { opacity: 0; transform: translateX(30px); }
    to   { opacity: 1; transform: translateX(0); }
  }

  .greeting {
    font-family: 'JetBrains Mono', monospace;
    font-size: 13px;
    color: var(--cyan);
    letter-spacing: 4px;
    text-transform: uppercase;
    margin-bottom: 8px;
    opacity: 0.8;
  }

  .hero-name {
    font-family: 'Orbitron', sans-serif;
    font-size: 42px;
    font-weight: 900;
    line-height: 1.1;
    background: linear-gradient(135deg, var(--cyan), var(--purple), var(--orange));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: 12px;
    letter-spacing: -1px;
  }

  .hero-tagline {
    font-size: 18px;
    color: var(--muted);
    margin-bottom: 20px;
    font-weight: 500;
    letter-spacing: 0.5px;
  }

  .hero-tagline span { color: var(--cyan); }

  .hero-badges {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    margin-bottom: 24px;
  }

  .badge {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 6px 14px;
    border-radius: 20px;
    font-size: 13px;
    font-family: 'JetBrains Mono', monospace;
    font-weight: 600;
    letter-spacing: 0.5px;
    border: 1px solid;
    transition: all 0.3s;
  }

  .badge:hover { transform: translateY(-2px); }

  .badge-cyan  { border-color: var(--cyan);   color: var(--cyan);   background: #00f5ff15; }
  .badge-cyan:hover  { box-shadow: var(--glow-cyan);  background: #00f5ff25; }
  .badge-purple{ border-color: var(--purple); color: var(--purple); background: #b347ea15; }
  .badge-purple:hover{ box-shadow: var(--glow-purple); background: #b347ea25; }
  .badge-green { border-color: var(--green);  color: var(--green);  background: #39d35315; }
  .badge-orange{ border-color: var(--orange); color: var(--orange); background: #ff6b3515; }

  .social-links { display: flex; gap: 12px; flex-wrap: wrap; }

  .social-btn {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 9px 20px;
    border-radius: 8px;
    font-size: 13px;
    font-family: 'JetBrains Mono', monospace;
    font-weight: 600;
    cursor: pointer;
    text-decoration: none;
    transition: all 0.3s;
    border: 1px solid var(--border);
    color: var(--text);
    background: var(--surface2);
  }

  .social-btn:hover {
    border-color: var(--cyan);
    color: var(--cyan);
    box-shadow: var(--glow-cyan);
    transform: translateY(-2px);
  }

  /* ─── TYPING ANIMATION ─── */
  .typing-wrap {
    font-family: 'JetBrains Mono', monospace;
    font-size: 15px;
    color: var(--green);
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 16px 20px;
    margin-bottom: 50px;
    display: flex;
    align-items: center;
    gap: 12px;
    animation: fadeUp 0.8s 0.4s ease both;
  }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(20px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  .prompt-symbol { color: var(--cyan); font-size: 18px; }

  #typed-text::after {
    content: '▋';
    animation: cursor 0.8s step-end infinite;
  }

  @keyframes cursor {
    0%, 100% { opacity: 1; }
    50%       { opacity: 0; }
  }

  /* ─── SECTION TITLE ─── */
  .section-title {
    font-family: 'Orbitron', sans-serif;
    font-size: 13px;
    letter-spacing: 5px;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 20px;
    display: flex;
    align-items: center;
    gap: 12px;
  }

  .section-title::before {
    content: '';
    width: 30px; height: 1px;
    background: linear-gradient(to right, var(--cyan), transparent);
  }

  .section-title::after {
    content: '';
    flex: 1; height: 1px;
    background: linear-gradient(to right, var(--border), transparent);
  }

  /* ─── TECH STACK ─── */
  .tech-section { margin-bottom: 50px; animation: fadeUp 0.8s 0.5s ease both; }

  .tech-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(120px, 1fr));
    gap: 12px;
  }

  .tech-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 18px 12px;
    text-align: center;
    transition: all 0.3s;
    cursor: default;
    position: relative;
    overflow: hidden;
  }

  .tech-card::before {
    content: '';
    position: absolute;
    inset: 0;
    background: linear-gradient(135deg, var(--glow-color, transparent), transparent);
    opacity: 0;
    transition: opacity 0.3s;
  }

  .tech-card:hover {
    transform: translateY(-4px) scale(1.03);
    border-color: var(--card-accent, var(--cyan));
    box-shadow: 0 8px 30px var(--card-shadow, #00f5ff22);
  }

  .tech-card:hover::before { opacity: 1; }

  .tech-icon { font-size: 28px; margin-bottom: 8px; display: block; }
  .tech-name {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    font-weight: 700;
    letter-spacing: 1px;
    color: var(--card-accent, var(--text));
  }

  /* ─── STATS GRID ─── */
  .stats-section { margin-bottom: 50px; animation: fadeUp 0.8s 0.6s ease both; }

  .stats-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
  }

  .stat-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 24px;
    position: relative;
    overflow: hidden;
    transition: all 0.3s;
  }

  .stat-card::after {
    content: '';
    position: absolute;
    top: -50%; right: -50%;
    width: 200%; height: 200%;
    background: radial-gradient(circle, var(--accent-color, #00f5ff) 0%, transparent 60%);
    opacity: 0.03;
    pointer-events: none;
  }

  .stat-card:hover {
    border-color: var(--accent-color, var(--cyan));
    box-shadow: 0 0 30px var(--accent-shadow, #00f5ff15);
    transform: translateY(-3px);
  }

  .stat-label {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 8px;
  }

  .stat-value {
    font-family: 'Orbitron', sans-serif;
    font-size: 36px;
    font-weight: 900;
    color: var(--accent-color, var(--cyan));
    line-height: 1;
    margin-bottom: 4px;
  }

  .stat-sub {
    font-size: 13px;
    color: var(--muted);
    font-weight: 500;
  }

  .stat-icon {
    position: absolute;
    top: 20px; right: 20px;
    font-size: 28px;
    opacity: 0.4;
  }

  /* ─── STREAK BAR ─── */
  .streak-section { margin-bottom: 50px; animation: fadeUp 0.8s 0.7s ease both; }

  .streak-bar-wrap {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 28px;
    position: relative;
    overflow: hidden;
  }

  .streak-numbers {
    display: flex;
    justify-content: space-around;
    margin-bottom: 28px;
  }

  .streak-item { text-align: center; }

  .streak-num {
    font-family: 'Orbitron', sans-serif;
    font-size: 40px;
    font-weight: 900;
    background: linear-gradient(135deg, var(--cyan), var(--purple));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    display: block;
    line-height: 1;
  }

  .streak-label {
    font-size: 12px;
    font-family: 'JetBrains Mono', monospace;
    color: var(--muted);
    letter-spacing: 2px;
    text-transform: uppercase;
    margin-top: 4px;
  }

  /* Contribution graph */
  .contrib-graph { display: flex; gap: 3px; overflow: hidden; border-radius: 6px; }

  .contrib-col {
    display: flex;
    flex-direction: column;
    gap: 3px;
  }

  .contrib-cell {
    width: 12px;
    height: 12px;
    border-radius: 2px;
    background: var(--cell-color, #161b22);
    transition: all 0.2s;
  }

  .contrib-cell:hover {
    transform: scale(1.3);
    box-shadow: 0 0 8px var(--cell-color, transparent);
  }

  /* ─── PROJECTS ─── */
  .projects-section { margin-bottom: 50px; animation: fadeUp 0.8s 0.8s ease both; }

  .projects-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
  }

  .project-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 24px;
    transition: all 0.3s;
    cursor: pointer;
    position: relative;
    overflow: hidden;
  }

  .project-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0;
    width: 4px; height: 100%;
    background: linear-gradient(to bottom, var(--proj-color, var(--cyan)), transparent);
    opacity: 0;
    transition: opacity 0.3s;
  }

  .project-card:hover {
    border-color: var(--proj-color, var(--cyan));
    transform: translateY(-4px);
    box-shadow: 0 10px 40px #0009;
  }

  .project-card:hover::before { opacity: 1; }

  .proj-emoji { font-size: 24px; margin-bottom: 12px; display: block; }

  .proj-name {
    font-family: 'Orbitron', sans-serif;
    font-size: 14px;
    font-weight: 700;
    color: var(--proj-color, var(--cyan));
    margin-bottom: 8px;
    letter-spacing: 0.5px;
  }

  .proj-desc {
    font-size: 13px;
    color: var(--muted);
    line-height: 1.5;
    margin-bottom: 14px;
    font-weight: 400;
  }

  .proj-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
  }

  .proj-tag {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    padding: 3px 8px;
    border-radius: 4px;
    background: var(--surface2);
    border: 1px solid var(--border);
    color: var(--muted);
    font-weight: 600;
    letter-spacing: 0.5px;
  }

  /* ─── SKILLS BAR ─── */
  .skills-section { margin-bottom: 50px; animation: fadeUp 0.8s 0.9s ease both; }

  .skill-row {
    display: flex;
    align-items: center;
    gap: 16px;
    margin-bottom: 14px;
  }

  .skill-name {
    font-family: 'JetBrains Mono', monospace;
    font-size: 12px;
    font-weight: 700;
    color: var(--text);
    letter-spacing: 1px;
    min-width: 100px;
  }

  .skill-bar-bg {
    flex: 1;
    height: 8px;
    background: var(--surface2);
    border-radius: 4px;
    overflow: hidden;
    border: 1px solid var(--border);
  }

  .skill-bar-fill {
    height: 100%;
    border-radius: 4px;
    background: linear-gradient(to right, var(--fill-a), var(--fill-b));
    width: 0%;
    transition: width 1.4s cubic-bezier(0.25, 1, 0.5, 1);
    box-shadow: 0 0 8px var(--fill-b);
  }

  .skill-pct {
    font-family: 'Orbitron', monospace;
    font-size: 11px;
    font-weight: 700;
    min-width: 38px;
    text-align: right;
    color: var(--muted);
  }

  /* ─── FOOTER ─── */
  .footer {
    text-align: center;
    padding-top: 40px;
    border-top: 1px solid var(--border);
    animation: fadeUp 0.8s 1s ease both;
  }

  .footer-text {
    font-family: 'JetBrains Mono', monospace;
    font-size: 12px;
    color: var(--muted);
    letter-spacing: 2px;
  }

  .footer-text span {
    background: linear-gradient(135deg, var(--cyan), var(--purple));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    font-weight: 700;
  }

  /* ─── FLOATING PARTICLES ─── */
  .particles-overlay {
    position: fixed;
    inset: 0;
    z-index: 0;
    pointer-events: none;
    overflow: hidden;
  }

  .particle {
    position: absolute;
    border-radius: 50%;
    animation: float-particle linear infinite;
    opacity: 0;
  }

  @keyframes float-particle {
    0%   { transform: translateY(100vh) translateX(0); opacity: 0; }
    10%  { opacity: var(--max-opacity, 0.6); }
    90%  { opacity: var(--max-opacity, 0.6); }
    100% { transform: translateY(-20px) translateX(var(--drift, 20px)); opacity: 0; }
  }

  /* ─── SCANLINE EFFECT ─── */
  .scanlines {
    position: fixed;
    inset: 0;
    z-index: 0;
    pointer-events: none;
    background: repeating-linear-gradient(
      0deg,
      transparent,
      transparent 2px,
      rgba(0,0,0,0.03) 2px,
      rgba(0,0,0,0.03) 4px
    );
  }

  /* ─── SECTION DIVIDERS ─── */
  .divider {
    width: 100%;
    height: 1px;
    background: linear-gradient(to right, transparent, var(--cyan), transparent);
    margin: 50px 0;
    opacity: 0.3;
  }

  /* ─── RESPONSIVE ─── */
  @media (max-width: 700px) {
    .hero { grid-template-columns: 1fr; text-align: center; }
    .hero-badges, .social-links { justify-content: center; }
    .avatar-wrap { margin: 0 auto; }
    .stats-grid, .projects-grid { grid-template-columns: 1fr; }
    .hero-name { font-size: 28px; }
  }

  /* GLOW pulse on load */
  @keyframes glowIn {
    from { opacity: 0; }
    to   { opacity: 1; }
  }
</style>
</head>
<body>

<!-- Animated canvas background -->
<canvas id="bg-canvas"></canvas>

<!-- Scanlines texture -->
<div class="scanlines"></div>

<!-- Floating particles -->
<div class="particles-overlay" id="particles"></div>

<div class="wrapper">

  <!-- ─── HERO ─── -->
  <div class="hero">
    <div class="avatar-wrap">
      <div class="avatar-ring"></div>
      <div class="avatar-pulse"></div>
      <div class="avatar-pulse"></div>
      <!-- Replace src with your actual GitHub avatar URL -->
      <img
        class="avatar-img"
        src="https://avatars.githubusercontent.com/ShahidAfridKhan"
        onerror="this.src='data:image/svg+xml,<svg xmlns=%22http://www.w3.org/2000/svg%22 width=%22200%22 height=%22200%22><circle cx=%22100%22 cy=%22100%22 r=%22100%22 fill=%22%230d1117%22/><text x=%22100%22 y=%22115%22 text-anchor=%22middle%22 font-size=%2280%22 fill=%22%2300f5ff%22>S</text></svg>'"
        alt="Shahid Afrid Khan"
      />
      <div class="status-dot"></div>
    </div>

    <div class="hero-text">
      <div class="greeting">// Hello, World</div>
      <h1 class="hero-name">Shahid Afrid<br>Khan</h1>
      <p class="hero-tagline">
        B.Tech CSE (DS) · LPU · <span>AI/ML Engineer</span>
      </p>
      <div class="hero-badges">
        <span class="badge badge-cyan">🎓 LPU · 3rd Year</span>
        <span class="badge badge-purple">🤖 ML / AI</span>
        <span class="badge badge-green">☕ Java · DSA</span>
        <span class="badge badge-orange">🏏 Cricket</span>
      </div>
      <div class="social-links">
        <a href="https://linkedin.com/in/shahid-afrid-khan" class="social-btn" target="_blank">
          <svg width="14" height="14" viewBox="0 0 24 24" fill="currentColor"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
          LinkedIn
        </a>
        <a href="https://leetcode.com/u/shahidafrid_037/" class="social-btn" target="_blank">
          <svg width="14" height="14" viewBox="0 0 24 24" fill="currentColor"><path d="M16.102 17.93l-2.697 2.607c-.466.467-1.111.662-1.823.662s-1.357-.195-1.823-.662l-4.124-4.141c-.437-.436-.658-1.009-.658-1.636s.221-1.2.658-1.636l1.607-1.608c.367-.367.844-.562 1.39-.562.604 0 1.177.195 1.6.612l3.003-3.03c-.57-.615-.949-1.423-.949-2.299 0-.877.379-1.685.949-2.3l1.607-1.607c.439-.437 1.011-.658 1.638-.658s1.199.221 1.636.658l3.097 3.097c.436.436.658 1.011.658 1.636s-.222 1.199-.658 1.636l-1.607 1.608c-.372.371-.85.556-1.39.556-.604 0-1.177-.185-1.6-.556L14.07 13.77l-3.004 3.003c.57.615.95 1.424.95 2.299 0 .877-.38 1.686-.95 2.301l-1.606 1.608c-.437.436-1.01.657-1.637.657s-1.2-.221-1.636-.657l-3.097-3.097c-.437-.437-.657-1.011-.657-1.637s.22-1.2.657-1.637l1.607-1.608c.438-.437 1.011-.657 1.638-.657.604 0 1.177.22 1.6.657L9 17.44c.568-.614.946-1.423.946-2.298s-.378-1.684-.946-2.299L11.947 9.84c.57-.614.948-1.423.948-2.299 0-.877-.378-1.685-.948-2.299l-1.607-1.607c-.438-.437-1.011-.658-1.638-.658s-1.2.221-1.636.658L3.969 6.731c-.436.436-.658 1.011-.658 1.636s.222 1.2.658 1.636l1.607 1.608c.438.436 1.011.657 1.638.657.604 0 1.177-.221 1.6-.657l2.697-2.608c.466-.466 1.111-.661 1.823-.661s1.357.195 1.823.661l4.124 4.142c.437.436.658 1.009.658 1.636s-.221 1.2-.658 1.636l-1.607 1.608z"/></svg>
          LeetCode
        </a>
        <a href="https://github.com/ShahidAfridKhan" class="social-btn" target="_blank">
          <svg width="14" height="14" viewBox="0 0 24 24" fill="currentColor"><path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/></svg>
          GitHub
        </a>
      </div>
    </div>
  </div>

  <!-- ─── TYPING TERMINAL ─── -->
  <div class="typing-wrap">
    <span class="prompt-symbol">❯</span>
    <span id="typed-text"></span>
  </div>

  <!-- ─── TECH STACK ─── -->
  <div class="tech-section">
    <div class="section-title">Tech Stack</div>
    <div class="tech-grid">
      <div class="tech-card" style="--card-accent:#f89820;--card-shadow:#f8982222;">
        <span class="tech-icon">☕</span>
        <div class="tech-name" style="color:#f89820;">JAVA</div>
      </div>
      <div class="tech-card" style="--card-accent:#3572A5;--card-shadow:#3572A522;">
        <span class="tech-icon">🐍</span>
        <div class="tech-name" style="color:#3572A5;">PYTHON</div>
      </div>
      <div class="tech-card" style="--card-accent:#00f5ff;--card-shadow:#00f5ff22;">
        <span class="tech-icon">🧠</span>
        <div class="tech-name" style="color:#00f5ff;">TF/KERAS</div>
      </div>
      <div class="tech-card" style="--card-accent:#FF6B6B;--card-shadow:#FF6B6B22;">
        <span class="tech-icon">📷</span>
        <div class="tech-name" style="color:#FF6B6B;">OPENCV</div>
      </div>
      <div class="tech-card" style="--card-accent:#b347ea;--card-shadow:#b347ea22;">
        <span class="tech-icon">🐼</span>
        <div class="tech-name" style="color:#b347ea;">PANDAS</div>
      </div>
      <div class="tech-card" style="--card-accent:#E97627;--card-shadow:#E9762722;">
        <span class="tech-icon">📊</span>
        <div class="tech-name" style="color:#E97627;">POWER BI</div>
      </div>
      <div class="tech-card" style="--card-accent:#4479A1;--card-shadow:#4479A122;">
        <span class="tech-icon">🗄️</span>
        <div class="tech-name" style="color:#4479A1;">MySQL</div>
      </div>
      <div class="tech-card" style="--card-accent:#F05032;--card-shadow:#F0503222;">
        <span class="tech-icon">🌿</span>
        <div class="tech-name" style="color:#F05032;">GIT</div>
      </div>
    </div>
  </div>

  <!-- ─── GITHUB STATS ─── -->
  <div class="stats-section">
    <div class="section-title">GitHub Stats</div>
    <div class="stats-grid">
      <div class="stat-card" style="--accent-color:#00f5ff;--accent-shadow:#00f5ff15;">
        <div class="stat-label">Total Commits</div>
        <div class="stat-value" id="counter-commits">0</div>
        <div class="stat-sub">Past 12 months</div>
        <span class="stat-icon">⚡</span>
      </div>
      <div class="stat-card" style="--accent-color:#39d353;--accent-shadow:#39d35315;">
        <div class="stat-label">LeetCode Problems</div>
        <div class="stat-value" id="counter-leet">0</div>
        <div class="stat-sub">Solved &amp; counting</div>
        <span class="stat-icon">🧩</span>
      </div>
      <div class="stat-card" style="--accent-color:#b347ea;--accent-shadow:#b347ea15;">
        <div class="stat-label">Projects Built</div>
        <div class="stat-value" id="counter-projects">0</div>
        <div class="stat-sub">Deployed &amp; active</div>
        <span class="stat-icon">🚀</span>
      </div>
      <div class="stat-card" style="--accent-color:#ffd700;--accent-shadow:#ffd70015;">
        <div class="stat-label">DSA Streak</div>
        <div class="stat-value" id="counter-streak">0</div>
        <div class="stat-sub">Days of practice</div>
        <span class="stat-icon">🔥</span>
      </div>
    </div>
  </div>

  <!-- ─── CONTRIBUTION GRAPH ─── -->
  <div class="streak-section">
    <div class="section-title">Contribution Graph</div>
    <div class="streak-bar-wrap">
      <div class="streak-numbers">
        <div class="streak-item">
          <span class="streak-num">25</span>
          <span class="streak-label">Total Commits</span>
        </div>
        <div class="streak-item">
          <span class="streak-num">50</span>
          <span class="streak-label">DSA Days</span>
        </div>
        <div class="streak-item">
          <span class="streak-num">5</span>
          <span class="streak-label">Automations</span>
        </div>
      </div>
      <div class="contrib-graph" id="contrib-graph"></div>
    </div>
  </div>

  <!-- ─── PROJECTS ─── -->
  <div class="projects-section">
    <div class="section-title">Featured Projects</div>
    <div class="projects-grid">
      <div class="project-card" style="--proj-color:#00f5ff;">
        <span class="proj-emoji">😊</span>
        <div class="proj-name">FaceGuard AI</div>
        <p class="proj-desc">Real-time facial expression detection system. CNN model trained on FER2013 with live dashboard showing mental stress analytics.</p>
        <div class="proj-tags">
          <span class="proj-tag">Python</span>
          <span class="proj-tag">TensorFlow</span>
          <span class="proj-tag">OpenCV</span>
          <span class="proj-tag">Streamlit</span>
          <span class="proj-tag">Keras</span>
        </div>
      </div>
      <div class="project-card" style="--proj-color:#ff6b35;">
        <span class="proj-emoji">🍽️</span>
        <div class="proj-name">CraveAI</div>
        <p class="proj-desc">AI-powered food recommendation engine. Suggests meals based on user mood, dietary preferences, and time of day.</p>
        <div class="proj-tags">
          <span class="proj-tag">Next.js</span>
          <span class="proj-tag">AI/ML</span>
          <span class="proj-tag">React</span>
        </div>
      </div>
      <div class="project-card" style="--proj-color:#b347ea;">
        <span class="proj-emoji">📖</span>
        <div class="proj-name">WhisperDiary</div>
        <p class="proj-desc">AI-enhanced personal diary Android app with voice-based unlock and intelligent note modification features.</p>
        <div class="proj-tags">
          <span class="proj-tag">Kotlin</span>
          <span class="proj-tag">Android</span>
          <span class="proj-tag">Voice AI</span>
        </div>
      </div>
      <div class="project-card" style="--proj-color:#39d353;">
        <span class="proj-emoji">🚗</span>
        <div class="proj-name">TheRide</div>
        <p class="proj-desc">Comprehensive ride analytics dashboard built in Power BI with interactive visualizations and KPI tracking.</p>
        <div class="proj-tags">
          <span class="proj-tag">Power BI</span>
          <span class="proj-tag">DAX</span>
          <span class="proj-tag">Analytics</span>
        </div>
      </div>
    </div>
  </div>

  <!-- ─── SKILLS ─── -->
  <div class="skills-section">
    <div class="section-title">Proficiency</div>
    <div class="skills-list" id="skills-list">
      <div class="skill-row">
        <span class="skill-name">Java · DSA</span>
        <div class="skill-bar-bg">
          <div class="skill-bar-fill" data-width="82" style="--fill-a:#f89820;--fill-b:#ff6b35;"></div>
        </div>
        <span class="skill-pct">82%</span>
      </div>
      <div class="skill-row">
        <span class="skill-name">Python · ML</span>
        <div class="skill-bar-bg">
          <div class="skill-bar-fill" data-width="78" style="--fill-a:#3572A5;--fill-b:#00f5ff;"></div>
        </div>
        <span class="skill-pct">78%</span>
      </div>
      <div class="skill-row">
        <span class="skill-name">TF / Keras</span>
        <div class="skill-bar-bg">
          <div class="skill-bar-fill" data-width="72" style="--fill-a:#b347ea;--fill-b:#7c3aed;"></div>
        </div>
        <span class="skill-pct">72%</span>
      </div>
      <div class="skill-row">
        <span class="skill-name">Power BI</span>
        <div class="skill-bar-bg">
          <div class="skill-bar-fill" data-width="75" style="--fill-a:#E97627;--fill-b:#ffd700;"></div>
        </div>
        <span class="skill-pct">75%</span>
      </div>
      <div class="skill-row">
        <span class="skill-name">MySQL</span>
        <div class="skill-bar-bg">
          <div class="skill-bar-fill" data-width="68" style="--fill-a:#4479A1;--fill-b:#00f5ff;"></div>
        </div>
        <span class="skill-pct">68%</span>
      </div>
    </div>
  </div>

  <!-- ─── FOOTER ─── -->
  <div class="footer">
    <p class="footer-text">
      Crafted with <span>💙 code</span> by <span>Shahid Afrid Khan</span> · LPU, Punjab
    </p>
    <p class="footer-text" style="margin-top:8px;opacity:0.5;">
      B.Tech CSE (Data Science) · 2023–2027
    </p>
  </div>

</div>

<script>
// ─── CANVAS STARFIELD ───
const canvas = document.getElementById('bg-canvas');
const ctx = canvas.getContext('2d');
let W, H, stars = [], meteors = [];

function resize() {
  W = canvas.width  = window.innerWidth;
  H = canvas.height = window.innerHeight;
}
resize();
window.addEventListener('resize', resize);

for (let i = 0; i < 180; i++) {
  stars.push({
    x: Math.random() * 9999,
    y: Math.random() * 9999,
    r: Math.random() * 1.2 + 0.2,
    a: Math.random(),
    da: (Math.random() - 0.5) * 0.01
  });
}

function spawnMeteor() {
  meteors.push({
    x: Math.random() * W * 1.5,
    y: -10,
    len: Math.random() * 120 + 60,
    speed: Math.random() * 4 + 3,
    a: 1,
    angle: Math.PI / 5
  });
}

setInterval(spawnMeteor, 3000);

function draw() {
  ctx.clearRect(0, 0, W, H);

  // Stars
  stars.forEach(s => {
    s.a += s.da;
    if (s.a <= 0 || s.a >= 1) s.da *= -1;
    ctx.beginPath();
    ctx.arc(s.x % W, s.y % H, s.r, 0, Math.PI * 2);
    ctx.fillStyle = `rgba(180, 210, 255, ${s.a * 0.7})`;
    ctx.fill();
  });

  // Meteors
  meteors.forEach((m, i) => {
    ctx.save();
    ctx.translate(m.x, m.y);
    ctx.rotate(m.angle);
    const grad = ctx.createLinearGradient(0, 0, -m.len, 0);
    grad.addColorStop(0, `rgba(0,245,255,${m.a})`);
    grad.addColorStop(1, 'transparent');
    ctx.strokeStyle = grad;
    ctx.lineWidth = 1.5;
    ctx.beginPath();
    ctx.moveTo(0, 0);
    ctx.lineTo(-m.len, 0);
    ctx.stroke();
    ctx.restore();
    m.x += m.speed * Math.cos(m.angle);
    m.y += m.speed * Math.sin(m.angle);
    m.a -= 0.015;
    if (m.a <= 0) meteors.splice(i, 1);
  });

  requestAnimationFrame(draw);
}
draw();

// ─── FLOATING PARTICLES ───
const pContainer = document.getElementById('particles');
const colors = ['#00f5ff','#b347ea','#39d353','#ffd700','#ff6b35'];
for (let i = 0; i < 30; i++) {
  const p = document.createElement('div');
  p.className = 'particle';
  const c = colors[Math.floor(Math.random() * colors.length)];
  const size = Math.random() * 4 + 1;
  p.style.cssText = `
    width:${size}px;height:${size}px;
    background:${c};
    left:${Math.random()*100}%;
    --drift:${(Math.random()-0.5)*100}px;
    --max-opacity:${Math.random()*0.4+0.1};
    animation-duration:${Math.random()*12+8}s;
    animation-delay:${Math.random()*10}s;
    box-shadow:0 0 ${size*3}px ${c};
  `;
  pContainer.appendChild(p);
}

// ─── TYPING EFFECT ───
const messages = [
  'Building AI systems that actually understand humans...',
  'Practicing DSA · Sliding Window Pattern today 🪟',
  'Facial Expression Detection → stress analytics ✅',
  'Next.js portfolio · cosmic theme · live now 🚀',
  'Grinding LeetCode · shahidafrid_037 🧩'
];
let msgIdx = 0, charIdx = 0, deleting = false;
const typedEl = document.getElementById('typed-text');

function type() {
  const msg = messages[msgIdx];
  if (!deleting) {
    typedEl.textContent = msg.slice(0, ++charIdx);
    if (charIdx === msg.length) { deleting = true; setTimeout(type, 2200); return; }
    setTimeout(type, 38);
  } else {
    typedEl.textContent = msg.slice(0, --charIdx);
    if (charIdx === 0) { deleting = false; msgIdx = (msgIdx + 1) % messages.length; setTimeout(type, 400); return; }
    setTimeout(type, 18);
  }
}
setTimeout(type, 800);

// ─── COUNTER ANIMATION ───
function animateCounter(el, target, duration = 1600) {
  let start = null;
  function step(ts) {
    if (!start) start = ts;
    const progress = Math.min((ts - start) / duration, 1);
    const ease = 1 - Math.pow(1 - progress, 3);
    el.textContent = Math.floor(ease * target);
    if (progress < 1) requestAnimationFrame(step);
    else el.textContent = target;
  }
  requestAnimationFrame(step);
}

const counters = [
  { id: 'counter-commits',  val: 25  },
  { id: 'counter-leet',     val: 50  },
  { id: 'counter-projects', val: 8   },
  { id: 'counter-streak',   val: 50  }
];

// ─── INTERSECTION OBSERVER ───
const observer = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (!entry.isIntersecting) return;

    // Skill bars
    entry.target.querySelectorAll('.skill-bar-fill').forEach(bar => {
      bar.style.width = bar.dataset.width + '%';
    });

    // Counters
    counters.forEach(c => {
      const el = document.getElementById(c.id);
      if (el) animateCounter(el, c.val);
    });

    observer.unobserve(entry.target);
  });
}, { threshold: 0.3 });

document.querySelectorAll('.stats-section, .skills-section').forEach(s => observer.observe(s));

// ─── CONTRIBUTION GRAPH ───
const graph = document.getElementById('contrib-graph');
const weeks = 28;
const days = 7;
const levels = [
  '#161b22',
  '#0e4429',
  '#006d32',
  '#26a641',
  '#39d353'
];
// Weighted random: mostly empty, some activity
function randomLevel() {
  const r = Math.random();
  if (r < 0.55) return 0;
  if (r < 0.75) return 1;
  if (r < 0.87) return 2;
  if (r < 0.95) return 3;
  return 4;
}

for (let w = 0; w < weeks; w++) {
  const col = document.createElement('div');
  col.className = 'contrib-col';
  for (let d = 0; d < days; d++) {
    const cell = document.createElement('div');
    cell.className = 'contrib-cell';
    const lvl = randomLevel();
    cell.style.setProperty('--cell-color', levels[lvl]);
    cell.style.background = levels[lvl];
    cell.title = `${lvl} contribution${lvl !== 1 ? 's' : ''}`;
    col.appendChild(cell);
  }
  graph.appendChild(col);
}
</script>
</body>
</html>
