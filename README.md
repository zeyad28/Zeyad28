  <!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Zeyad Hesham Emara – DevOps Profile</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@600;700;900&family=Share+Tech+Mono&display=swap');

  :root {
    --cyan:    #00ffc8;
    --pink:    #ff00aa;
    --yellow:  #ffcc00;
    --blue:    #00aaff;
    --green:   #39ff14;
    --bg:      #050510;
    --card-bg: rgba(255,255,255,0.03);
    --border:  rgba(255,255,255,0.08);
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    background: var(--bg);
    font-family: 'Share Tech Mono', monospace;
    min-height: 100vh;
    padding: 40px 20px;
    overflow-x: hidden;
  }

  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(0,255,200,.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,255,200,.03) 1px, transparent 1px);
    background-size: 50px 50px;
    pointer-events: none;
    z-index: 0;
  }

  .page {
    position: relative;
    z-index: 1;
    max-width: 860px;
    margin: 0 auto;
    display: flex;
    flex-direction: column;
    gap: 48px;
  }

  .banner {
    position: relative;
    width: 100%;
    height: 280px;
    background: #050510;
    border: 1px solid #1a1a3e;
    overflow: hidden;
    border-radius: 6px;
    opacity: 0;
    animation: fadeIn 0.8s ease 0.1s forwards;
  }

  @keyframes fadeIn { to { opacity: 1; } }

  .banner-grid {
    position: absolute;
    inset: 0;
    background-image:
      linear-gradient(rgba(0,255,200,.04) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,255,200,.04) 1px, transparent 1px);
    background-size: 40px 40px;
    animation: gridShift 8s linear infinite;
  }

  @keyframes gridShift {
    0%   { transform: translateY(0); }
    100% { transform: translateY(40px); }
  }

  .scanlines {
    position: absolute;
    inset: 0;
    background: repeating-linear-gradient(
      to bottom,
      transparent 0px, transparent 3px,
      rgba(0,0,0,.18) 3px, rgba(0,0,0,.18) 4px
    );
    pointer-events: none;
    z-index: 10;
  }

  .corner {
    position: absolute;
    width: 18px; height: 18px;
    border-color: var(--cyan);
    border-style: solid;
    z-index: 5;
  }
  .corner.tl { top:10px; left:10px;   border-width:2px 0 0 2px; }
  .corner.tr { top:10px; right:10px;  border-width:2px 2px 0 0; }
  .corner.bl { bottom:10px; left:10px;  border-width:0 0 2px 2px; }
  .corner.br { bottom:10px; right:10px; border-width:0 2px 2px 0; }

  .blob {
    position: absolute;
    border-radius: 50%;
    filter: blur(80px);
    opacity: 0.18;
    animation: blobPulse 6s ease-in-out infinite alternate;
  }
  .blob1 { width:300px; height:300px; background:var(--pink);   top:-80px;  left:-60px; animation-delay:0s; }
  .blob2 { width:260px; height:260px; background:#00c8ff;       top:40px;   right:40px; animation-delay:2s; }
  .blob3 { width:200px; height:200px; background:var(--yellow); bottom:-60px; left:40%; animation-delay:4s; }

  @keyframes blobPulse {
    0%   { opacity:0.13; transform:scale(1); }
    100% { opacity:0.25; transform:scale(1.15); }
  }

  .banner-content {
    position: relative;
    z-index: 3;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 100%;
    gap: 10px;
    padding: 20px;
  }

  .name {
    font-family: 'Orbitron', sans-serif;
    font-size: clamp(1.6rem, 4vw, 2.6rem);
    font-weight: 900;
    color: #fff;
    letter-spacing: 0.06em;
    text-transform: uppercase;
    position: relative;
    text-shadow: 0 0 8px #fff, 0 0 20px var(--cyan), 0 0 40px var(--cyan);
    animation: glitchBase 3.5s infinite;
  }

  .name::before {
    content: attr(data-text);
    position: absolute; inset: 0;
    color: var(--cyan);
    text-shadow: none;
    clip-path: polygon(0 20%, 100% 20%, 100% 35%, 0 35%);
    animation: glitch1 3.5s infinite;
  }

  .name::after {
    content: attr(data-text);
    position: absolute; inset: 0;
    color: var(--pink);
    text-shadow: none;
    clip-path: polygon(0 60%, 100% 60%, 100% 75%, 0 75%);
    animation: glitch2 3.5s infinite;
  }

  @keyframes glitchBase {
    0%,80%,100% { transform:none; }
    81%  { transform:skewX(-1deg); }
    82%  { transform:skewX(1deg); }
    83%  { transform:none; }
  }
  @keyframes glitch1 {
    0%,79%,100% { transform:none; opacity:0; }
    80%  { transform:translate(-3px,2px);  opacity:1; }
    81%  { transform:translate(3px,-2px);  opacity:1; }
    82%  { transform:none; opacity:0; }
    85%  { transform:translate(-2px,1px);  opacity:1; }
    86%  { opacity:0; }
  }
  @keyframes glitch2 {
    0%,79%,100% { transform:none; opacity:0; }
    80%  { transform:translate(3px,-2px);  opacity:1; }
    81%  { transform:translate(-3px,2px);  opacity:1; }
    82%  { transform:none; opacity:0; }
    84%  { transform:translate(2px,-1px);  opacity:1; }
    85%  { opacity:0; }
  }

  .title-bar { display:flex; gap:16px; align-items:center; }

  .badge {
    font-family: 'Share Tech Mono', monospace;
    font-size: 0.72rem;
    letter-spacing: 0.15em;
    padding: 4px 12px;
    border-radius: 2px;
    text-transform: uppercase;
    font-weight: 700;
    animation: badgePulse 2s ease-in-out infinite alternate;
  }
  .badge.cyan   { color:var(--cyan);   border:1px solid var(--cyan);   box-shadow:0 0 8px #00ffc880; animation-delay:0s; }
  .badge.pink   { color:var(--pink);   border:1px solid var(--pink);   box-shadow:0 0 8px #ff00aa80; animation-delay:0.6s; }
  .badge.yellow { color:var(--yellow); border:1px solid var(--yellow); box-shadow:0 0 8px #ffcc0080; animation-delay:1.2s; }

  @keyframes badgePulse {
    0%   { box-shadow:0 0 4px currentColor; }
    100% { box-shadow:0 0 14px currentColor, 0 0 28px currentColor; }
  }

  .tagline {
    font-family: 'Share Tech Mono', monospace;
    font-size: 0.82rem;
    color: #8888bb;
    letter-spacing: 0.08em;
    overflow: hidden;
    white-space: nowrap;
    border-right: 2px solid var(--cyan);
    width: 0;
    animation: typing 3s steps(50,end) 0.5s forwards, blink 0.8s step-end infinite;
  }

  @keyframes typing { to { width: 44ch; } }
  @keyframes blink  { 50% { border-color: transparent; } }

  .stack { display:flex; gap:8px; flex-wrap:wrap; justify-content:center; }

  .pill {
    font-family: 'Share Tech Mono', monospace;
    font-size: 0.62rem;
    padding: 3px 9px;
    border-radius: 20px;
    background: rgba(255,255,255,0.04);
    border: 1px solid rgba(255,255,255,0.1);
    color: #aaaacc;
    letter-spacing: 0.1em;
    opacity: 0;
    animation: fadeUp 0.5s ease forwards;
  }
  .pill:nth-child(1){animation-delay:2.8s}
  .pill:nth-child(2){animation-delay:3.0s}
  .pill:nth-child(3){animation-delay:3.2s}
  .pill:nth-child(4){animation-delay:3.4s}
  .pill:nth-child(5){animation-delay:3.6s}
  .pill:nth-child(6){animation-delay:3.8s}
  .pill:nth-child(7){animation-delay:4.0s}

  @keyframes fadeUp {
    from { opacity:0; transform:translateY(6px); }
    to   { opacity:1; transform:none; }
  }

  .status {
    position: absolute;
    bottom:0; left:0; right:0;
    height: 24px;
    background: rgba(0,255,200,0.04);
    border-top: 1px solid rgba(0,255,200,0.15);
    display: flex;
    align-items: center;
    padding: 0 16px;
    gap: 20px;
    z-index: 4;
  }

  .status-dot {
    width:6px; height:6px;
    border-radius:50%;
    background:var(--cyan);
    box-shadow:0 0 6px var(--cyan);
    animation:dotBlink 1.4s ease-in-out infinite;
  }

  @keyframes dotBlink { 0%,100%{opacity:1} 50%{opacity:0.2} }

  .status-text {
    font-size:0.58rem;
    color:rgba(0,255,200,0.5);
    letter-spacing:0.15em;
    text-transform:uppercase;
  }

  .status-link {
    font-family:'Share Tech Mono',monospace;
    font-size:0.58rem;
    color:rgba(0,170,255,0.7);
    letter-spacing:0.15em;
    text-transform:uppercase;
    text-decoration:none;
    border:1px solid rgba(0,170,255,0.25);
    padding:2px 8px;
    border-radius:2px;
    transition:color 0.2s, border-color 0.2s, box-shadow 0.2s;
    display:flex;
    align-items:center;
    gap:4px;
  }
  .status-link:hover {
    color:#00aaff;
    border-color:rgba(0,170,255,0.6);
    box-shadow:0 0 8px rgba(0,170,255,0.4);
  }

  .glitch-bar {
    position:absolute; left:0; right:0; height:2px;
    background:linear-gradient(90deg,transparent,var(--cyan),var(--pink),transparent);
    opacity:0;
    animation:glitchBar 4s ease-in-out infinite;
  }
  @keyframes glitchBar {
    0%,88%,100%{opacity:0;top:30%}
    89%{opacity:0.9;top:30%}
    90%{opacity:0.9;top:60%}
    91%{opacity:0}
  }

  .skills-section { position:relative; z-index:1; }

  .section-header {
    display: flex;
    align-items: center;
    gap: 12px;
    margin-bottom: 32px;
    opacity: 0;
    animation: slideIn 0.7s ease 0.4s forwards;
  }

  .section-header::after {
    content:'';
    flex:1;
    height:1px;
    background:linear-gradient(90deg,var(--cyan),transparent);
  }

  .section-title {
    font-family:'Orbitron',sans-serif;
    font-size:0.75rem;
    color:var(--cyan);
    letter-spacing:0.25em;
    text-transform:uppercase;
    text-shadow:0 0 10px var(--cyan);
  }

  .section-icon {
    font-size:1rem;
    animation:iconSpin 4s linear infinite;
  }
  @keyframes iconSpin {
    0%,90%,100%{transform:rotate(0deg)}
    95%{transform:rotate(360deg)}
  }

  .category {
    margin-bottom:36px;
    opacity:0;
    transform:translateY(20px);
  }
  .category.visible { animation:slideIn 0.6s ease forwards; }

  @keyframes slideIn { to{opacity:1;transform:translateY(0)} }

  .cat-label {
    font-size:0.6rem;
    letter-spacing:0.3em;
    text-transform:uppercase;
    color:rgba(255,255,255,0.25);
    margin-bottom:12px;
    padding-left:4px;
  }

  .skills-grid { display:flex; flex-wrap:wrap; gap:10px; }

  .skill-card {
    position:relative;
    background:var(--card-bg);
    border:1px solid var(--border);
    border-radius:6px;
    padding:10px 16px 10px 12px;
    display:flex;
    align-items:center;
    gap:10px;
    cursor:pointer;
    overflow:hidden;
    transition:transform 0.2s ease, border-color 0.3s ease;
    opacity:0;
    animation:cardPop 0.4s cubic-bezier(0.34,1.56,0.64,1) forwards;
  }

  .skill-card:hover { transform:translateY(-3px) scale(1.03); }
  .skill-card:hover .skill-name { color:#fff; }

  .skill-card::before {
    content:''; position:absolute; inset:0;
    opacity:0; transition:opacity 0.3s ease; border-radius:6px;
  }
  .skill-card:hover::before { opacity:1; }

  .skill-card::after {
    content:''; position:absolute;
    left:0; top:20%; bottom:20%;
    width:2px; border-radius:2px;
    transition:top 0.3s ease, bottom 0.3s ease;
  }
  .skill-card:hover::after { top:5%; bottom:5%; }

  .cat-cloud  .skill-card::after  { background:var(--cyan); }
  .cat-cloud  .skill-card:hover   { border-color:rgba(0,255,200,0.4); }
  .cat-cloud  .skill-card::before { box-shadow:inset 0 0 20px rgba(0,255,200,0.07); }

  .cat-devops .skill-card::after  { background:var(--pink); }
  .cat-devops .skill-card:hover   { border-color:rgba(255,0,170,0.4); }
  .cat-devops .skill-card::before { box-shadow:inset 0 0 20px rgba(255,0,170,0.07); }

  .cat-infra  .skill-card::after  { background:var(--yellow); }
  .cat-infra  .skill-card:hover   { border-color:rgba(255,204,0,0.4); }
  .cat-infra  .skill-card::before { box-shadow:inset 0 0 20px rgba(255,204,0,0.07); }

  .cat-lang   .skill-card::after  { background:var(--blue); }
  .cat-lang   .skill-card:hover   { border-color:rgba(0,170,255,0.4); }
  .cat-lang   .skill-card::before { box-shadow:inset 0 0 20px rgba(0,170,255,0.07); }

  .cat-os     .skill-card::after  { background:var(--green); }
  .cat-os     .skill-card:hover   { border-color:rgba(57,255,20,0.4); }
  .cat-os     .skill-card::before { box-shadow:inset 0 0 20px rgba(57,255,20,0.07); }

  .skill-icon {
    font-size:1.3rem; line-height:1;
    filter:drop-shadow(0 0 4px currentColor);
    transition:transform 0.3s ease;
    flex-shrink:0;
  }
  .skill-card:hover .skill-icon { transform:scale(1.2) rotate(-5deg); }

  .skill-name {
    font-family:'Share Tech Mono',monospace;
    font-size:0.78rem;
    color:rgba(255,255,255,0.75);
    letter-spacing:0.08em;
    transition:color 0.2s ease;
    white-space:nowrap;
  }

  .skill-bar {
    position:absolute; bottom:0; left:0; right:0;
    height:2px; background:rgba(255,255,255,0.05); overflow:hidden;
  }
  .skill-bar-fill {
    height:100%; width:0;
    transition:width 1.2s cubic-bezier(0.22,1,0.36,1);
    border-radius:2px;
  }

  .cat-cloud  .skill-bar-fill { background:linear-gradient(90deg,var(--cyan),  rgba(0,255,200,0.3)); }
  .cat-devops .skill-bar-fill { background:linear-gradient(90deg,var(--pink),  rgba(255,0,170,0.3)); }
  .cat-infra  .skill-bar-fill { background:linear-gradient(90deg,var(--yellow),rgba(255,204,0,0.3)); }
  .cat-lang   .skill-bar-fill { background:linear-gradient(90deg,var(--blue),  rgba(0,170,255,0.3)); }
  .cat-os     .skill-bar-fill { background:linear-gradient(90deg,var(--green), rgba(57,255,20,0.3)); }

  .level-dot { display:flex; gap:3px; margin-left:auto; flex-shrink:0; }
  .level-dot span {
    width:4px; height:4px; border-radius:50%;
    background:rgba(255,255,255,0.15);
    transition:background 0.3s ease;
  }
  .skill-card.animated .level-dot span.active {
    background:currentColor;
    box-shadow:0 0 4px currentColor;
  }

  .cat-cloud  .level-dot { color:var(--cyan); }
  .cat-devops .level-dot { color:var(--pink); }
  .cat-infra  .level-dot { color:var(--yellow); }
  .cat-lang   .level-dot { color:var(--blue); }
  .cat-os     .level-dot { color:var(--green); }

  .particle {
    position:fixed; border-radius:50%;
    pointer-events:none; z-index:0;
    animation:float linear infinite;
  }
  @keyframes float {
    0%  {transform:translateY(100vh) translateX(0);opacity:0}
    10% {opacity:1}
    90% {opacity:1}
    100%{transform:translateY(-10vh) translateX(var(--dx));opacity:0}
  }

  @keyframes cardPop {
    from{opacity:0;transform:scale(0.85)}
    to  {opacity:1;transform:scale(1)}
  }

  .divider {
    height:1px;
    background:linear-gradient(90deg,transparent,var(--border),transparent);
    margin:8px 0 24px;
  }

  .tooltip {
    position:fixed;
    background:rgba(5,5,16,0.95);
    border:1px solid rgba(255,255,255,0.15);
    border-radius:4px;
    padding:6px 12px;
    font-size:0.65rem;
    color:rgba(255,255,255,0.6);
    letter-spacing:0.1em;
    pointer-events:none;
    z-index:100;
    opacity:0;
    transition:opacity 0.15s ease;
    text-transform:uppercase;
  }
</style>
</head>
<body>

<div class="page">

  <!-- BANNER -->
  <div class="banner">
    <div class="banner-grid"></div>
    <div class="scanlines"></div>
    <div class="glitch-bar"></div>
    <div class="blob blob1"></div>
    <div class="blob blob2"></div>
    <div class="blob blob3"></div>
    <div class="corner tl"></div>
    <div class="corner tr"></div>
    <div class="corner bl"></div>
    <div class="corner br"></div>

    <div class="banner-content">
      <div class="name" data-text="ZEYAD HESHAM EMARA">ZEYAD HESHAM EMARA</div>
      <div class="title-bar">
        <div class="badge cyan">Cloud Architect</div>
        <div class="badge pink">DevOps Engineer</div>
        <div class="badge yellow">Expert</div>
      </div>
      <div class="tagline">⚡ Automate everything. Scale anything. Engineer the future.</div>
      <div class="stack">
        <span class="pill">AWS</span>
        <span class="pill">Docker</span>
        <span class="pill">Kubernetes</span>
        <span class="pill">Terraform</span>
        <span class="pill">CI/CD</span>
        <span class="pill">Linux</span>
        <span class="pill">Automation</span>
      </div>
    </div>

    <div class="status">
      <div class="status-dot"></div>
      <span class="status-text">SYSTEM ONLINE</span>
      <span class="status-text" style="margin-left:auto">github.com/ZeyadOS</span>
      <a href="https://www.linkedin.com/in/zeyad-emara-443092395/" target="_blank" class="status-link">
        <svg width="11" height="11" viewBox="0 0 24 24" fill="currentColor"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 0 1-2.063-2.065 2.064 2.064 0 1 1 2.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
        LinkedIn
      </a>
    </div>
  </div>

  <!-- SKILLS -->
  <div class="skills-section">
    <div class="section-header">
      <span class="section-icon">⚙</span>
      <span class="section-title">Core Skills & Tech Stack</span>
    </div>

    <div class="category cat-cloud">
      <div class="cat-label">// Cloud Platforms</div>
      <div class="skills-grid">
        <div class="skill-card" data-level="95" data-tip="Expert · 4+ yrs">
          <span class="skill-icon">☁️</span><span class="skill-name">AWS</span>
          <div class="level-dot"><span></span><span></span><span></span><span></span><span></span></div>
          <div class="skill-bar"><div class="skill-bar-fill"></div></div>
        </div>
        <div class="skill-card" data-level="80" data-tip="Advanced">
          <span class="skill-icon">🔵</span><span class="skill-name">Azure</span>
          <div class="level-dot"><span></span><span></span><span></span><span></span><span></span></div>
          <div class="skill-bar"><div class="skill-bar-fill"></div></div>
        </div>
        <div class="skill-card" data-level="75" data-tip="Advanced">
          <span class="skill-icon">🟡</span><span class="skill-name">GCP</span>
          <div class="level-dot"><span></span><span></span><span></span><span></span><span></span></div>
          <div class="skill-bar"><div class="skill-bar-fill"></div></div>
        </div>
      </div>
    </div>

    <div class="divider"></div>

    <div class="category cat-devops">
      <div class="cat-label">// DevOps & CI/CD</div>
      <div class="skills-grid">
        <div class="skill-card" data-level="95" data-tip="Expert">
          <span class="skill-icon">🐳</span><span class="skill-name">Docker</span>
          <div class="level-dot"><span></span><span></span><span></span><span></span><span></span></div>
          <div class="skill-bar"><div class="skill-bar-fill"></div></div>
        </div>
        <div class="skill-card" data-level="90" data-tip="Expert">
          <span class="skill-icon">☸️</span><span class="skill-name">Kubernetes</span>
          <div class="level-dot"><span></span><span></span><span></span><span></span><span></span></div>
          <div class="skill-bar"><div class="skill-bar-fill"></div></div>
        </div>
        <div class="skill-card" data-level="88" data-tip="Expert">
          <span class="skill-icon">🔁</span><span class="skill-name">CI/CD</span>
          <div class="level-dot"><span></span><span></span><span></span><span></span><span></span></div>
          <div class="skill-bar"><div class="skill-bar-fill"></div></div>
        </div>
        <div class="skill-card" data-level="85" data-tip="Advanced">
          <span class="skill-icon">🤖</span><span class="skill-name">Automation</span>
          <div class="level-dot"><span></span><span></span><span></span><span></span><span></span></div>
          <div class="skill-bar"><div class="skill-bar-fill"></div></div>
        </div>
        <div class="skill-card" data-level="82" data-tip="Advanced">
          <span class="skill-icon">🔶</span><span class="skill-name">GitLab CI</span>
          <div class="level-dot"><span></span><span></span><span></span><span></span><span></span></div>
          <div class="skill-bar"><div class="skill-bar-fill"></div></div>
        </div>
        <div class="skill-card" data-level="80" data-tip="Advanced">
          <span class="skill-icon">🏗️</span><span class="skill-name">Jenkins</span>
          <div class="level-dot"><span></span><span></span><span></span><span></span><span></span></div>
          <div class="skill-bar"><div class="skill-bar-fill"></div></div>
        </div>
      </div>
    </div>

    <div class="divider"></div>

    <div class="category cat-infra">
      <div class="cat-label">// Infrastructure as Code</div>
      <div class="skills-grid">
        <div class="skill-card" data-level="92" data-tip="Expert">
          <span class="skill-icon">🏔️</span><span class="skill-name">Terraform</span>
          <div class="level-dot"><span></span><span></span><span></span><span></span><span></span></div>
          <div class="skill-bar"><div class="skill-bar-fill"></div></div>
        </div>
        <div class="skill-card" data-level="88" data-tip="Expert">
          <span class="skill-icon">📦</span><span class="skill-name">Ansible</span>
          <div class="level-dot"><span></span><span></span><span></span><span></span><span></span></div>
          <div class="skill-bar"><div class="skill-bar-fill"></div></div>
        </div>
        <div class="skill-card" data-level="78" data-tip="Advanced">
          <span class="skill-icon">🌊</span><span class="skill-name">Pulumi</span>
          <div class="level-dot"><span></span><span></span><span></span><span></span><span></span></div>
          <div class="skill-bar"><div class="skill-bar-fill"></div></div>
        </div>
      </div>
    </div>

    <div class="divider"></div>

    <div class="category cat-lang">
      <div class="cat-label">// Languages & Scripting</div>
      <div class="skills-grid">
        <div class="skill-card" data-level="92" data-tip="Expert">
          <span class="skill-icon">🐍</span><span class="skill-name">Python</span>
          <div class="level-dot"><span></span><span></span><span></span><span></span><span></span></div>
          <div class="skill-bar"><div class="skill-bar-fill"></div></div>
        </div>
        <div class="skill-card" data-level="88" data-tip="Expert">
          <span class="skill-icon">💲</span><span class="skill-name">Bash</span>
          <div class="level-dot"><span></span><span></span><span></span><span></span><span></span></div>
          <div class="skill-bar"><div class="skill-bar-fill"></div></div>
        </div>
        <div class="skill-card" data-level="72" data-tip="Intermediate">
          <span class="skill-icon">🟨</span><span class="skill-name">Go</span>
          <div class="level-dot"><span></span><span></span><span></span><span></span><span></span></div>
          <div class="skill-bar"><div class="skill-bar-fill"></div></div>
        </div>
        <div class="skill-card" data-level="68" data-tip="Intermediate">
          <span class="skill-icon">📜</span><span class="skill-name">YAML / JSON</span>
          <div class="level-dot"><span></span><span></span><span></span><span></span><span></span></div>
          <div class="skill-bar"><div class="skill-bar-fill"></div></div>
        </div>
      </div>
    </div>

    <div class="divider"></div>

    <div class="category cat-os">
      <div class="cat-label">// Systems & Monitoring</div>
      <div class="skills-grid">
        <div class="skill-card" data-level="97" data-tip="Expert">
          <span class="skill-icon">🐧</span><span class="skill-name">Linux</span>
          <div class="level-dot"><span></span><span></span><span></span><span></span><span></span></div>
          <div class="skill-bar"><div class="skill-bar-fill"></div></div>
        </div>
        <div class="skill-card" data-level="84" data-tip="Advanced">
          <span class="skill-icon">📊</span><span class="skill-name">Prometheus</span>
          <div class="level-dot"><span></span><span></span><span></span><span></span><span></span></div>
          <div class="skill-bar"><div class="skill-bar-fill"></div></div>
        </div>
        <div class="skill-card" data-level="82" data-tip="Advanced">
          <span class="skill-icon">📈</span><span class="skill-name">Grafana</span>
          <div class="level-dot"><span></span><span></span><span></span><span></span><span></span></div>
          <div class="skill-bar"><div class="skill-bar-fill"></div></div>
        </div>
        <div class="skill-card" data-level="78" data-tip="Advanced">
          <span class="skill-icon">🔍</span><span class="skill-name">ELK Stack</span>
          <div class="level-dot"><span></span><span></span><span></span><span></span><span></span></div>
          <div class="skill-bar"><div class="skill-bar-fill"></div></div>
        </div>
      </div>
    </div>

  </div>
</div>

<div class="tooltip" id="tooltip"></div>

<script>
  const colors = ['#00ffc8','#ff00aa','#ffcc00','#00aaff','#39ff14'];
  for (let i = 0; i < 30; i++) {
    const p = document.createElement('div');
    p.className = 'particle';
    p.style.cssText = `
      left:${Math.random()*100}vw;
      background:${colors[Math.floor(Math.random()*colors.length)]};
      opacity:${Math.random()*0.35+0.08};
      --dx:${(Math.random()-0.5)*80}px;
      animation-duration:${Math.random()*12+8}s;
      animation-delay:-${Math.random()*15}s;
      width:${Math.random()*2+1}px;
      height:${Math.random()*2+1}px;
    `;
    document.body.appendChild(p);
  }

  function animateCard(card, delay) {
    card.style.animationDelay = delay + 's';
    const level = parseInt(card.dataset.level);
    const dots  = card.querySelectorAll('.level-dot span');
    const fill  = card.querySelector('.skill-bar-fill');
    setTimeout(() => {
      card.classList.add('animated');
      fill.style.width = level + '%';
      const active = Math.round(level / 20);
      dots.forEach((dot, i) => {
        if (i < active) setTimeout(() => dot.classList.add('active'), i * 120);
      });
    }, delay * 1000 + 200);
  }

  document.querySelectorAll('.category').forEach((cat, ci) => {
    cat.style.animationDelay = (0.5 + ci * 0.15) + 's';
    cat.classList.add('visible');
    cat.querySelectorAll('.skill-card').forEach((card, i) => {
      animateCard(card, 0.6 + ci * 0.15 + i * 0.06);
    });
  });

  const tooltip = document.getElementById('tooltip');
  document.querySelectorAll('.skill-card').forEach(card => {
    card.addEventListener('mouseenter', () => { tooltip.textContent = card.dataset.tip || ''; tooltip.style.opacity = '1'; });
    card.addEventListener('mousemove',  e  => { tooltip.style.left = (e.clientX+14)+'px'; tooltip.style.top = (e.clientY-28)+'px'; });
    card.addEventListener('mouseleave', () => { tooltip.style.opacity = '0'; });
  });
</script>
</body>
</html>
