# RoyalBlue66.github.io
Dnd Website
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>The Broken World — Terra-Gaia</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@400;500;600&family=Inter:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg: #0D0F1A;
    --bg-card: #151828;
    --bg-card-hover: #1C2035;
    --text: #E8E4DC;
    --text-muted: #8A8699;
    --text-dim: #4A4760;
    --gold: #C9A84C;
    --gold-dim: #7A6430;
    --blue: #4A6FA5;
    --blue-dim: #2A3F5F;
    --border: rgba(201,168,76,0.15);
    --border-bright: rgba(201,168,76,0.4);
    --font-display: 'Cinzel', serif;
    --font-body: 'Inter', sans-serif;
  }

  html { scroll-behavior: smooth; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: var(--font-body);
    font-size: 15px;
    line-height: 1.7;
    -webkit-font-smoothing: antialiased;
  }

  /* NAV */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    background: rgba(13,15,26,0.92);
    backdrop-filter: blur(12px);
    border-bottom: 0.5px solid var(--border);
    padding: 0 2rem;
    display: flex; align-items: center; justify-content: space-between;
    height: 56px;
  }
  .nav-logo {
    font-family: var(--font-display);
    font-size: 13px;
    letter-spacing: 0.12em;
    color: var(--gold);
    text-decoration: none;
    text-transform: uppercase;
  }
  .nav-links { display: flex; gap: 2rem; list-style: none; }
  .nav-links a {
    font-size: 12px;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    color: var(--text-muted);
    text-decoration: none;
    transition: color 0.2s;
  }
  .nav-links a:hover { color: var(--gold); }

  /* HERO */
  #hero {
    position: relative;
    height: 100vh;
    display: flex; flex-direction: column;
    align-items: center; justify-content: center;
    text-align: center;
    overflow: hidden;
    padding: 2rem;
  }
  #starfield {
    position: absolute; inset: 0;
    pointer-events: none;
  }
  .hero-eyebrow {
    font-family: var(--font-display);
    font-size: 11px;
    letter-spacing: 0.25em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 1.5rem;
    position: relative;
  }
  .hero-title {
    font-family: var(--font-display);
    font-size: clamp(2.5rem, 7vw, 5.5rem);
    font-weight: 600;
    color: var(--text);
    line-height: 1.1;
    letter-spacing: 0.02em;
    position: relative;
    margin-bottom: 1.5rem;
  }
  .hero-title span { color: var(--gold); }
  .hero-sub {
    font-size: 15px;
    color: var(--text-muted);
    max-width: 520px;
    position: relative;
    margin-bottom: 2.5rem;
    line-height: 1.8;
  }
  .hero-meta {
    display: flex; gap: 2rem;
    position: relative;
  }
  .hero-stat { text-align: center; }
  .hero-stat-num {
    font-family: var(--font-display);
    font-size: 1.5rem;
    color: var(--gold);
    display: block;
  }
  .hero-stat-label {
    font-size: 11px;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--text-muted);
  }
  .scroll-hint {
    position: absolute; bottom: 2rem;
    font-size: 11px; letter-spacing: 0.15em;
    text-transform: uppercase; color: var(--text-dim);
    animation: pulse 2s ease-in-out infinite;
  }
  @keyframes pulse { 0%,100%{opacity:0.4} 50%{opacity:1} }

  /* SECTIONS */
  section { padding: 6rem 2rem; max-width: 1100px; margin: 0 auto; }
  .section-label {
    font-family: var(--font-display);
    font-size: 10px;
    letter-spacing: 0.3em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 0.75rem;
    display: block;
  }
  .section-title {
    font-family: var(--font-display);
    font-size: clamp(1.5rem, 4vw, 2.5rem);
    font-weight: 500;
    color: var(--text);
    margin-bottom: 1rem;
    line-height: 1.2;
  }
  .section-intro {
    font-size: 15px;
    color: var(--text-muted);
    max-width: 680px;
    margin-bottom: 3rem;
    line-height: 1.8;
  }
  .divider {
    width: 100%;
    height: 0.5px;
    background: var(--border);
    margin: 0;
  }

  /* WORLD OVERVIEW */
  .world-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 1px;
    border: 0.5px solid var(--border);
    border-radius: 12px;
    overflow: hidden;
    margin-bottom: 3rem;
  }
  .world-card {
    background: var(--bg-card);
    padding: 1.75rem;
    transition: background 0.2s;
  }
  .world-card:hover { background: var(--bg-card-hover); }
  .world-card-icon {
    font-size: 1.5rem;
    margin-bottom: 1rem;
    display: block;
  }
  .world-card-title {
    font-family: var(--font-display);
    font-size: 14px;
    letter-spacing: 0.05em;
    color: var(--gold);
    margin-bottom: 0.5rem;
  }
  .world-card-body {
    font-size: 13px;
    color: var(--text-muted);
    line-height: 1.7;
  }

  /* CONSTELLATIONS */
  .const-section { margin-bottom: 3rem; }
  .const-section-label {
    font-family: var(--font-display);
    font-size: 11px;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--text-muted);
    margin-bottom: 1.25rem;
    padding-bottom: 0.75rem;
    border-bottom: 0.5px solid var(--border);
  }
  .const-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
    gap: 1rem;
  }
  .const-card {
    background: var(--bg-card);
    border: 0.5px solid var(--border);
    border-radius: 10px;
    padding: 1.25rem;
    transition: border-color 0.2s, background 0.2s;
    cursor: default;
  }
  .const-card:hover {
    border-color: var(--border-bright);
    background: var(--bg-card-hover);
  }
  .const-card.major { border-left: 2px solid var(--gold); }
  .const-card.minor { border-left: 2px solid var(--blue); }
  .const-name {
    font-family: var(--font-display);
    font-size: 14px;
    color: var(--text);
    margin-bottom: 4px;
  }
  .const-concept {
    font-size: 11px;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 0.6rem;
  }
  .const-card.minor .const-concept { color: var(--blue); }
  .const-desc {
    font-size: 12.5px;
    color: var(--text-muted);
    line-height: 1.65;
  }
  .const-pair {
    font-size: 11px;
    color: var(--text-dim);
    margin-top: 8px;
    padding-top: 8px;
    border-top: 0.5px solid var(--border);
  }
  .const-pair span { color: var(--text-muted); }

  /* SOVEREIGNS & MAGICAL GIRLS */
  .person-list { display: flex; flex-direction: column; gap: 1.5rem; }
  .person-card {
    background: var(--bg-card);
    border: 0.5px solid var(--border);
    border-radius: 12px;
    padding: 1.75rem;
    display: grid;
    grid-template-columns: auto 1fr;
    gap: 1.5rem;
    transition: border-color 0.2s;
  }
  .person-card:hover { border-color: var(--border-bright); }
  .person-avatar {
    width: 56px; height: 56px;
    border-radius: 50%;
    background: var(--gold-dim);
    display: flex; align-items: center; justify-content: center;
    font-family: var(--font-display);
    font-size: 18px;
    color: var(--gold);
    flex-shrink: 0;
  }
  .person-avatar.mg { background: var(--blue-dim); color: #7BADD4; }
  .person-title {
    font-family: var(--font-display);
    font-size: 14px;
    color: var(--gold);
    margin-bottom: 2px;
    line-height: 1.3;
  }
  .person-title.mg { color: #7BADD4; }
  .person-name {
    font-size: 13px;
    color: var(--text-muted);
    margin-bottom: 0.6rem;
  }
  .person-body {
    font-size: 13px;
    color: var(--text-muted);
    line-height: 1.7;
  }
  .person-tags { display: flex; flex-wrap: wrap; gap: 6px; margin-top: 0.75rem; }
  .person-tag {
    font-size: 11px;
    padding: 2px 10px;
    border-radius: 99px;
    background: rgba(201,168,76,0.08);
    border: 0.5px solid var(--border);
    color: var(--text-muted);
  }
  .person-tag.mg {
    background: rgba(74,111,165,0.12);
    border-color: rgba(74,111,165,0.3);
  }
  .stars { color: var(--gold); font-size: 13px; margin-top: 4px; }

  /* SKILL TREES */
  .tree-tabs {
    display: flex; flex-wrap: wrap; gap: 6px;
    margin-bottom: 2rem;
  }
  .tree-tab {
    font-size: 12px;
    padding: 5px 14px;
    border-radius: 99px;
    border: 0.5px solid var(--border);
    background: transparent;
    color: var(--text-muted);
    cursor: pointer;
    font-family: var(--font-body);
    transition: all 0.15s;
    letter-spacing: 0.03em;
  }
  .tree-tab:hover { color: var(--text); border-color: rgba(201,168,76,0.4); }
  .tree-tab.active {
    background: var(--gold-dim);
    border-color: var(--gold);
    color: var(--gold);
  }
  .tree-panel { display: none; }
  .tree-panel.active { display: block; }
  .tree-header {
    margin-bottom: 2rem;
    padding-bottom: 1.5rem;
    border-bottom: 0.5px solid var(--border);
  }
  .tree-name {
    font-family: var(--font-display);
    font-size: 1.5rem;
    margin-bottom: 0.5rem;
  }
  .tree-desc { font-size: 14px; color: var(--text-muted); line-height: 1.7; max-width: 600px; }
  .tree-fantasy { font-size: 12px; color: var(--text-dim); margin-top: 6px; font-style: italic; }
  .tree-nodes { display: flex; flex-direction: column; }
  .tree-connector {
    width: 1px; height: 20px;
    background: var(--border-bright);
    margin-left: 27px;
  }
  .tree-node {
    background: var(--bg-card);
    border: 0.5px solid var(--border);
    border-radius: 10px;
    padding: 1.25rem 1.5rem;
    display: grid;
    grid-template-columns: 44px 1fr;
    gap: 1rem;
    transition: border-color 0.2s, background 0.2s;
  }
  .tree-node:hover { border-color: rgba(201,168,76,0.3); background: var(--bg-card-hover); }
  .tree-node.milestone { border-left: 2px solid var(--gold); }
  .node-badge {
    width: 36px; height: 36px;
    border-radius: 50%;
    display: flex; align-items: center; justify-content: center;
    font-size: 11px; font-weight: 500;
    flex-shrink: 0;
    margin-top: 2px;
  }
  .badge-1 { background: rgba(21,100,80,0.3); color: #5DCAA5; border: 0.5px solid rgba(29,158,117,0.4); }
  .badge-2 { background: rgba(133,79,11,0.3); color: #EF9F27; border: 0.5px solid rgba(186,117,23,0.4); }
  .badge-3 { background: rgba(163,45,45,0.3); color: #F09595; border: 0.5px solid rgba(163,45,45,0.4); }
  .node-body-inner { }
  .node-title {
    font-family: var(--font-display);
    font-size: 13px;
    color: var(--text);
    margin-bottom: 2px;
  }
  .node-cost { font-size: 11px; color: var(--text-dim); margin-bottom: 6px; }
  .node-desc { font-size: 13px; color: var(--text-muted); line-height: 1.65; }
  .node-tags-row { display: flex; flex-wrap: wrap; gap: 4px; margin-top: 8px; }
  .node-tag {
    font-size: 10px; padding: 1px 8px;
    border-radius: 99px;
    border: 0.5px solid var(--border);
    color: var(--text-dim);
  }
  .node-tag.milestone-tag { border-color: rgba(201,168,76,0.4); color: var(--gold); }
  .node-tag.ultimate-tag { border-color: rgba(163,45,45,0.5); color: #F09595; }

  /* NATIONS */
  .nations-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
    gap: 1rem;
  }
  .nation-card {
    background: var(--bg-card);
    border: 0.5px solid var(--border);
    border-radius: 10px;
    padding: 1.25rem 1.5rem;
    transition: border-color 0.2s, background 0.2s;
  }
  .nation-card:hover { border-color: var(--border-bright); background: var(--bg-card-hover); }
  .nation-name {
    font-family: var(--font-display);
    font-size: 14px;
    color: var(--text);
    margin-bottom: 4px;
  }
  .nation-insp {
    font-size: 11px;
    text-transform: uppercase;
    letter-spacing: 0.08em;
    color: var(--text-dim);
    margin-bottom: 0.75rem;
  }
  .nation-stats {
    display: flex; gap: 6px; flex-wrap: wrap;
    margin-bottom: 0.75rem;
  }
  .nation-stat {
    font-size: 10px;
    padding: 2px 8px;
    border-radius: 99px;
    border: 0.5px solid var(--border);
    color: var(--text-muted);
  }
  .nation-desc {
    font-size: 12.5px;
    color: var(--text-muted);
    line-height: 1.65;
  }

  /* FOOTER */
  footer {
    border-top: 0.5px solid var(--border);
    padding: 3rem 2rem;
    text-align: center;
  }
  .footer-title {
    font-family: var(--font-display);
    font-size: 12px;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 0.5rem;
  }
  .footer-sub { font-size: 12px; color: var(--text-dim); }

  /* RESPONSIVE */
  @media (max-width: 640px) {
    nav { padding: 0 1rem; }
    .nav-links { gap: 1rem; }
    .nav-links a { font-size: 11px; }
    section { padding: 4rem 1rem; }
    .person-card { grid-template-columns: 1fr; }
    .person-avatar { display: none; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <a class="nav-logo" href="#hero">Terra-Gaia</a>
  <ul class="nav-links">
    <li><a href="#world">World</a></li>
    <li><a href="#constellations">Constellations</a></li>
    <li><a href="#sovereigns">Sovereigns</a></li>
    <li><a href="#magical-girls">Magical Girls</a></li>
    <li><a href="#tempo">Tempo</a></li>
    <li><a href="#nations">Nations</a></li>
  </ul>
</nav>

<!-- HERO -->
<div id="hero">
  <canvas id="starfield"></canvas>
  <p class="hero-eyebrow">Year 6060 — God is dead. Humanity killed him.</p>
  <h1 class="hero-title">The <span>Broken</span> World</h1>
  <p class="hero-sub">A fragment of the old world, held together by the Foundation Engine and the music no one hears but everyone carries. Welcome to Terra-Gaia.</p>
  <div class="hero-meta">
    <div class="hero-stat">
      <span class="hero-stat-num">12</span>
      <span class="hero-stat-label">Major Constellations</span>
    </div>
    <div class="hero-stat">
      <span class="hero-stat-num">12</span>
      <span class="hero-stat-label">Minor Constellations</span>
    </div>
    <div class="hero-stat">
      <span class="hero-stat-num">12</span>
      <span class="hero-stat-label">Tempo Trees</span>
    </div>
    <div class="hero-stat">
      <span class="hero-stat-num">13</span>
      <span class="hero-stat-label">Nations</span>
    </div>
  </div>
  <p class="scroll-hint">↓ Scroll to explore</p>
</div>

<div class="divider"></div>

<!-- WORLD OVERVIEW -->
<section id="world">
  <span class="section-label">Foundations</span>
  <h2 class="section-title">How This World Works</h2>
  <p class="section-intro">Terra-Gaia runs on code. When god died and reality began to collapse, the first Genius built the Foundation Engine — rewriting existence itself as a stable system. Everything since has been built on that foundation.</p>
  <div class="world-grid">
    <div class="world-card">
      <span class="world-card-icon">⚙️</span>
      <div class="world-card-title">The Foundation Engine</div>
      <div class="world-card-body">The machine that holds the world together. It recoded reality after god's death — your hair color, your abilities, the laws of physics. All of it runs on the World Formula. Housed in Concordia Academia. Only the Genius and select council members have access.</div>
    </div>
    <div class="world-card">
      <span class="world-card-icon">🎵</span>
      <div class="world-card-title">Tempo</div>
      <div class="world-card-body">If Magic is programming reality, Tempo is 3D modeling it. Every person has a Tempo — a music they may never hear, deep inside them. Using it means playing with your own identity and existence to influence the world around you.</div>
    </div>
    <div class="world-card">
      <span class="world-card-icon">✨</span>
      <div class="world-card-title">True Names</div>
      <div class="world-card-body">Every person and object has a True Name — the folder that holds their existence. Knowing someone's True Name means access to their entire self. All Anomaly Hunters are required to know theirs. Reality in an Anomaly responds to identity.</div>
    </div>
    <div class="world-card">
      <span class="world-card-icon">🌀</span>
      <div class="world-card-title">Anomalies</div>
      <div class="world-card-body">Points where reality fractures and collapses. They occur wherever an Anti-Anomaly Tower doesn't reach. Glitch entities emerge from them and cannot be harmed by conventional weapons — only Debugs made with Orichalcum can wound them.</div>
    </div>
    <div class="world-card">
      <span class="world-card-icon">💎</span>
      <div class="world-card-title">Orichalcum</div>
      <div class="world-card-body">The rarest material in Terra-Gaia. Only found in Concordia. The only substance that can harm Glitch entities. Every nation's need for it is why Concordia holds more global power than any army could provide.</div>
    </div>
    <div class="world-card">
      <span class="world-card-icon">👁️</span>
      <div class="world-card-title">Concordia</div>
      <div class="world-card-body">Not just a nation — the world government. The Genius leads. The Luminary Council governs. The Holy Knights enforce. And the Academia identifies, trains, and absorbs the most talented people in the world. Class 0 has just been announced.</div>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- CONSTELLATIONS -->
<section id="constellations">
  <span class="section-label">The Sky</span>
  <h2 class="section-title">Constellations</h2>
  <p class="section-intro">Humanity always needs belief. Those who look up to godlike beings called Constellations can earn their favor. Each Major Constellation is paired with a Minor opposite — a shadow of what it represents.</p>

  <div class="const-section">
    <div class="const-section-label">Major Constellations — The Twelve</div>
    <div class="const-grid" id="major-consts"></div>
  </div>

  <div class="const-section">
    <div class="const-section-label">Minor Constellations</div>
    <div class="const-grid" id="minor-consts"></div>
  </div>
</section>

<div class="divider"></div>

<!-- SOVEREIGNS -->
<section id="sovereigns">
  <span class="section-label">The Chosen</span>
  <h2 class="section-title">Sovereigns</h2>
  <p class="section-intro">A Sovereign is more than a mortal with divine favor — they become an extension of the Constellation's will on earth. The bond is both a blessing and a burden. Failure can result in the withdrawal of power, death, or worse.</p>
  <div class="person-list" id="sovereigns-list"></div>
</section>

<div class="divider"></div>

<!-- MAGICAL GIRLS -->
<section id="magical-girls">
  <span class="section-label">The Devoted</span>
  <h2 class="section-title">Magical Girls</h2>
  <p class="section-intro">Magical Girls embody a Constellation's concept in their own way — not through a binding contract, but through personal expression, devotion, and connection. In return, their Constellation may gift them an outfit, weapon, or familiar. Power is measured in stars.</p>
  <div class="person-list" id="mg-list"></div>
</section>

<div class="divider"></div>

<!-- TEMPO SKILL TREES -->
<section id="tempo">
  <span class="section-label">Inner Music</span>
  <h2 class="section-title">Tempo Skill Trees</h2>
  <p class="section-intro">Tempo abilities are learned through Mentors — you cannot develop them alone. Each level-up grants one point to spend in these trees. Milestone nodes (★) and ultimates cost 2–3 points and should feel like turning points.</p>
  <div class="tree-tabs" id="tree-tabs"></div>
  <div id="tree-panels"></div>
</section>

<div class="divider"></div>

<!-- NATIONS -->
<section id="nations">
  <span class="section-label">The Map</span>
  <h2 class="section-title">Nations of Terra-Gaia</h2>
  <p class="section-intro">Thirteen nations, each with its own history, culture, and relationship to Concordia's authority. The year is 6060. The Age of Peace is holding — barely.</p>
  <div class="nations-grid" id="nations-grid"></div>
</section>

<footer>
  <div class="footer-title">The Broken World — Terra-Gaia</div>
  <div class="footer-sub">Year 6060 &nbsp;·&nbsp; This document is a living record</div>
</footer>

<script>
// STARFIELD
(function(){
  const canvas = document.getElementById('starfield');
  const ctx = canvas.getContext('2d');
  let stars = [], mouse = {x:0,y:0}, W, H;
  function resize(){ W=canvas.width=window.innerWidth; H=canvas.height=window.innerHeight; }
  resize();
  window.addEventListener('resize', resize);
  for(let i=0;i<180;i++){
    stars.push({
      x: Math.random()*W, y: Math.random()*H,
      r: Math.random()*1.2+0.2,
      o: Math.random()*0.6+0.1,
      vx: (Math.random()-0.5)*0.08,
      vy: (Math.random()-0.5)*0.08
    });
  }
  document.addEventListener('mousemove', e=>{ mouse.x=e.clientX; mouse.y=e.clientY; });
  function draw(){
    ctx.clearRect(0,0,W,H);
    stars.forEach(s=>{
      const dx = (mouse.x-W/2)*0.003, dy = (mouse.y-H/2)*0.003;
      s.x += s.vx + dx*0.015;
      s.y += s.vy + dy*0.015;
      if(s.x<0) s.x=W; if(s.x>W) s.x=0;
      if(s.y<0) s.y=H; if(s.y>H) s.y=0;
      ctx.beginPath();
      ctx.arc(s.x,s.y,s.r,0,Math.PI*2);
      ctx.fillStyle = `rgba(201,168,76,${s.o})`;
      ctx.fill();
    });
    requestAnimationFrame(draw);
  }
  draw();
})();

// CONSTELLATIONS DATA
const MAJOR_CONSTS = [
  { name:"The Hourglass", concept:"Time", opposite:"The Night Owl", desc:"Accepts that time cannot be bargained with or returned. Those who follow it understand urgency, patience, and the weight of a moment." },
  { name:"The Enigma", concept:"Mystery", opposite:"The Scholar", desc:"Its shape shifts depending on who is looking. No two people see the same pattern. Comfortable with questions over answers, and not knowing." },
  { name:"The Phoenix", concept:"Change & Rebirth", opposite:"The Hollow", desc:"Burns brightest after disaster. Those who follow it believe nothing is truly over and nothing stays the same. They walk toward transformation." },
  { name:"The Artist", concept:"Creation", opposite:"The Mimic", desc:"Said to have pulled something creative out of the world when it ascended. Those who follow it are driven to make things that did not exist before." },
  { name:"The Lovers", concept:"Love", opposite:"The Stalker", desc:"Two stars orbit without colliding or separating. Connection is not simple — it is a force with gravity. What it means depends on what love has done to you." },
  { name:"The Voyager", concept:"Adventure & Discovery", opposite:"The Legerdemain", desc:"Moves across the sky at a different rate than the others — slowly drifting, as if going somewhere. Those who follow it rarely stay in one place for long." },
  { name:"The Warrior", concept:"Courage & Conflict", opposite:"The Martyr", desc:"Not about bloodshed. It represents the willingness to stand in front of something that frightens you and not step back. Sometimes that is a quiet room." },
  { name:"The Coin", concept:"Prosperity & Reward", opposite:"The Voracity", desc:"Associated not just with wealth but with deserved outcomes — what you put in determines what you get out. Strong sense of fairness, or ambition, or both." },
  { name:"The Harvest", concept:"Growth & Abundance", opposite:"The Rot", desc:"Appears fullest in seasons of plenty. Those who follow it believe in patience, care, and the idea that what you tend to will eventually provide." },
  { name:"The Eye", concept:"Vision & Teaching", opposite:"The Watcher", desc:"Knowledge not passed on is knowledge wasted. Those who follow it are often teachers furious at ignorance who cannot stop trying to fix it." },
  { name:"The Weaver", concept:"Fate & Destiny", opposite:"The Chasm", desc:"Stars form a web the eye keeps finding new paths through. Followers believe lives are connected by invisible threads. Peace or terror — depends on the person." },
  { name:"The Equinox", concept:"Balance", opposite:"The Collective", desc:"Has no opposite — which is considered significant. Balance is not stillness. It is constant, exhausting work. The Equinox holds the center of all things." }
];

const MINOR_CONSTS = [
  { name:"The Hollow", concept:"Stagnation", opposite:"The Phoenix", desc:"Appears as a ring of stars with nothing at its center. It finds people who have stopped. Whether that stopping is rest or surrender depends on what they do next." },
  { name:"The Watcher", concept:"Ignorance & Nihility", opposite:"The Eye", desc:"Sees everything and acts on none of it. Stars are among the brightest in the sky. Believers think observation is enough — that involvement only makes things worse." },
  { name:"The Scholar", concept:"Knowledge Pursued to Its End", opposite:"The Enigma", desc:"Unlike the Eye, which shares, the Scholar collects. Hoards. Needs to know. Chases the Enigma across the sky. No one knows what happens if it catches it." },
  { name:"The Chasm", concept:"Obsession & Anxiety", opposite:"The Weaver", desc:"A fault line in the stars that goes deeper than it should. Those who carry it have fallen into something they cannot stop returning to. It is not malevolent. It simply is." },
  { name:"The Night Owl", concept:"Remembrance & Memory", opposite:"The Hourglass", desc:"Always visible but only noticed in the darkest part of the night. Those who carry it are defined by what they cannot let go of. Sometimes wisdom. Sometimes weight. Often both." },
  { name:"The Collective", concept:"Unison", opposite:"The Equinox", desc:"A dense cluster where no single star is distinct. Followers believe in the whole above the individual. The Equinox watches it warily from across the sky." },
  { name:"The Martyr", concept:"Justice & Sacrifice", opposite:"The Warrior", desc:"Those who carry it have decided something matters more than their survival. This is sometimes heroic. Sometimes self-destruction dressed in noble language. The Martyr rarely knows which." },
  { name:"The Stalker", concept:"Paranoia & Truth", opposite:"The Lovers", desc:"Hides behind other constellations. Carriers are convinced they see something others don't. Sometimes they are right. The difficulty is that the Stalker cannot tell the difference." },
  { name:"The Doctor", concept:"Decay & Medicine", opposite:"The Saint", desc:"Things fall apart. The question is what you do about it. Those who carry it either fight the rot or study it. The line between those two is thinner than either side admits." },
  { name:"The Mimic", concept:"Imitation & Surprise", opposite:"The Artist", desc:"Looks different every time you find it. Carriers are masters of becoming what the moment requires. Whether that is adaptation or deception depends entirely on the person." },
  { name:"The Voracity", concept:"Consumption", opposite:"The Coin", desc:"The largest Minor constellation in star-count. Those who carry it are defined by hunger. The Coin teaches that enough is a real thing. The Voracity has never believed it." },
  { name:"The Legerdemain", concept:"Trickery, Lies & Deceit", opposite:"The Voyager", desc:"Stars arranged to look like something else entirely at first glance. Not necessarily malicious — some are performers who understand that belief shapes reality as much as truth." }
];

function buildConsts(data, containerId, cls) {
  const el = document.getElementById(containerId);
  data.forEach(c => {
    el.innerHTML += `
      <div class="const-card ${cls}">
        <div class="const-name">${c.name}</div>
        <div class="const-concept">${c.concept}</div>
        <div class="const-desc">${c.desc}</div>
        <div class="const-pair">Opposite: <span>${c.opposite}</span></div>
      </div>`;
  });
}
buildConsts(MAJOR_CONSTS, 'major-consts', 'major');
buildConsts(MINOR_CONSTS, 'minor-consts', 'minor');

// SOVEREIGNS
const SOVEREIGNS = [
  {
    initials:"BC", title:"The Black Cat of Destined Death — The Intern of Death",
    name:"Sovereign of The Hourglass",
    tags:["The Hourglass","Death","Fated"],
    body:"Has the job of delivering fated death upon those who deserve it. Those who escaped their death will find her in front of them. She is not the full Gazed — the real Sovereign of Time is the Old Man of The Mountain, and she is his intern, dealing with souls after the people of Tribao send them to him. A massive fanbase online thanks to her looks and general reputation as a badass."
  },
  {
    initials:"W", title:"He who has seen a thousand exploding suns — Wulfrun, High Priest of The Flying Tower",
    name:"Sovereign of The Equinox",
    tags:["The Equinox","Balance","Morally Complex"],
    body:"A hero to some, a villain to others. Wulfrun will commit what most would consider villainy for the sake of the world — including the massacre of mages to strengthen the mages of today. He only lands his flying magic tower when it needs fuel. He likely does not care about his own cult."
  },
  {
    initials:"A", title:"The Maestro that got his heart locked — Amadeus, The Hero of Classical Music",
    name:"Sovereign of The Artist",
    tags:["The Artist","Music","Imprisoned"],
    body:"To create perfect art, one must pour out blood, sweat, and tears. Amadeus's powers come with the condition that he must create the perfect music. Until then he is locked in an endless cycle of composition, imprisoned in the opera house in Malum. When he creates something worthy of being called a masterpiece, his lock opens for a day. His concerts are once-in-a-lifetime experiences."
  },
  {
    initials:"BG", title:"He who plays god — Bastien Gentric, The Hero of Montpelier",
    name:"Sovereign of The Phoenix",
    tags:["The Phoenix","Hérault","War"],
    body:"The youngest son of the Gentric noble family, Bastien was a child soldier in the war against Venetus. He defeated Yvain of the Round Table, catching the attention of the Phoenix constellation. He was given the order to do whatever he deemed necessary to address Hérault's issues. He is not easy to approach."
  },
  {
    initials:"SB", title:"Hope of an Entire Nation — Saint Bertrina, The Rosé Demon",
    name:"Sovereign of The Lovers",
    tags:["The Lovers","Urgora","Purification"],
    body:"Said to be the daughter of the Obsidian Butterfly of Pietoria, summoned to lower Urgora by the wishes of the people. Her ability to purify the toxic air became the hope of every Urgora citizen — though she is called the Rosé Demon because she chooses whom she wants to save."
  },
  {
    initials:"FC", title:"Compass of Desires — Fey's Compass",
    name:"Sovereign of The Voyager",
    tags:["The Voyager","Artifact","Legendary"],
    body:"Not a mortal — the Voyager tends to bless anything associated with adventure, including tools. This compass is one of the world's approximately 100 legendary items. It is currently in the possession of Morgan le Fey."
  },
  {
    initials:"AL", title:"Mistress of The Eternal Combat — Fū Ren (Lady) Ah-Lam",
    name:"Sovereign of The Warrior",
    tags:["The Warrior","Tribao","Business"],
    body:"Not a fighter herself. Lady Ah-Lam is the biggest businesswoman on Vermillion Bird Island. Her main job is setting up fights and turning the island into a perpetual arena. She supplies everything needed to the fighters and manages everything that happens in these battles."
  }
];

const sovList = document.getElementById('sovereigns-list');
SOVEREIGNS.forEach(s => {
  const tags = s.tags.map(t=>`<span class="person-tag">${t}</span>`).join('');
  sovList.innerHTML += `
    <div class="person-card">
      <div class="person-avatar">${s.initials}</div>
      <div>
        <div class="person-title">${s.title}</div>
        <div class="person-name">${s.name}</div>
        <div class="person-body">${s.body}</div>
        <div class="person-tags">${tags}</div>
      </div>
    </div>`;
});

// MAGICAL GIRLS
const MG = [
  {
    initials:"MF", stars:"✦✦✦", title:"The Bride Who Kept Dancing — Mireille Fontaine",
    constell:"The Lovers",
    tags:["Hérault","Wedding Singer","Three Stars"],
    body:"A wedding singer in Hérault's lower arrondissements who performed at other people's celebrations her entire life while her own love story quietly fell apart. Her devotion to the Lovers was not born from happiness — it was born from the belief, held stubbornly against all evidence, that love was still worth it. Her outfit is a gown that is never quite the same color twice. Her weapon is a microphone stand wreathed in rose vines that bloom and wither in real time. She still performs at weddings. She cries at all of them."
  },
  {
    initials:"H", stars:"✦", title:"The Paper Crane Girl — Hana",
    constell:"The Night Owl",
    tags:["Shi-Tenzan","Age 12","One Star"],
    body:"Folds paper cranes for everyone she has ever lost. Her bedroom ceiling is covered in them. She doesn't think of this as devotion — she thinks of it as just something she does. The Night Owl apparently disagreed. Her power is modest: she can spend a moment with the memory of someone she has lost — not speak to them, not bring them back, just sit with them clearly for a few seconds before they fade. She uses it carefully."
  },
  {
    initials:"GH", stars:"✦✦", title:"The Loudest Woman in Any Room — Greta Halvorsen",
    constell:"The Warrior",
    tags:["Urgora","Labor Organizer","Two Stars"],
    body:"A labor organizer from Urgora's mountain cities who has been arrested eleven times and considers this a respectable average. She has never thrown a punch in her life. But the Warrior does not require that — it requires the willingness to stand in front of something that frightens you and not step back. Her outfit is a heavy worker's coat that is apparently indestructible. Her weapon is a megaphone that, when used with genuine anger on behalf of others, can be heard from three mountains away."
  },
  {
    initials:"EA", stars:"✦", title:"The Boy Who Reads Everything — Ezekiel Addo",
    constell:"The Eye",
    tags:["Galfond","Age 17","One Star"],
    body:"Reads approximately four books a week. Started a free tutoring collective in his neighborhood at age fourteen. His devotion to the Eye is entirely unconscious — he has never formally followed a Constellation, he just cannot stand it when people don't know things they could know. His outfit is subtle: reading glasses that weren't there before, a coat with pockets that always contain the book most relevant to whoever is standing near him. Columbina Acisculus has reportedly seen his star and said nothing for a very long time."
  },
  {
    initials:"YN", stars:"✦✦ / ✦", title:"The Twin Merchants — Yusra and Nadia Khalil",
    constell:"The Coin",
    tags:["Kirkbay","Sisters","Two Stars & One Star"],
    body:"Sisters who run a small import business that has no business being as successful as it is. Yusra has two stars — she understands wealth is not the point, and has built a small empire of fair wages and community investment. Nadia has one star and is still figuring out what the Coin means to her. She likes money and is not embarrassed about it. The Coin has not withdrawn its favor. Their weapon is a set of scales that can determine the exact fair value of any transaction, object, or debt."
  },
  {
    initials:"PV", stars:"✦✦", title:"The Gardener Who Grows the Wrong Things — Petra Voss",
    constell:"The Harvest",
    tags:["Concordia","Botanist","Two Stars"],
    body:"A botanist who specializes in plants most people consider useless, invasive, or dead. Her outfit is a layered green work dress perpetually dusted with soil that will not wash out. Her weapon is a trowel that can accelerate growth in anything it touches — including things that probably should not be growing. She uses her power mostly in places declared dead land, including several Anomaly-adjacent zones. The plants do not always look like normal plants afterward. She considers this a success."
  },
  {
    initials:"IB", stars:"✦✦✦", title:"The Cartographer of Nowhere — Idris Bekele",
    constell:"The Voyager",
    tags:["Kirkbay","Age 31","Three Stars"],
    body:"Makes maps of places that do not officially exist — the half-collapsed ruins between borders, the unnamed islands on no government chart, the roads that lead somewhere different depending on the season. No fixed address. Three stars for someone who has never fought anything, never saved a city. But the Voyager measures by distance covered and honesty of intention, and Idris has been genuinely, purely going somewhere his entire life. His weapon is a compass that always points toward the most interesting thing within a hundred miles rather than north."
  },
  {
    initials:"V", stars:"✦", title:"The Understudy — Vael",
    constell:"The Mimic",
    tags:["Unknown Origin","Theatre","One Star"],
    body:"No one knows Vael's full name or where they came from. Understudy for seventeen different productions across four countries, never officially taking the stage. They watch. They absorb. They can perform any role they have ever understudied with terrifying perfection but seem uninterested unless someone specifically needs them. Their outfit shifts to match whatever role they are currently inhabiting — not a disguise, more like the costume fits who they are choosing to be. Veyra Veyrinman has tried to find them three times. They have not been findable."
  },
  {
    initials:"R", stars:"✦", title:"No Title — Rook",
    constell:"The Hollow",
    tags:["Kirkbay","Whereabouts Unknown","One Star"],
    body:"Showed up in Kirkbay six years ago and has been working odd jobs since. Does not follow the Hollow in any active sense. But the Hollow found her anyway — she had stopped. Something happened before Kirkbay that she does not discuss, and she has been very still since. Her outfit is a plain dark coat with a single dull star on the back where she cannot see it. Her weapon has not appeared yet. The Hollow seems to be waiting. People who know what the star means watch her with a particular kind of attention — not pity. Recognition."
  }
];

const mgList = document.getElementById('mg-list');
MG.forEach(m => {
  const tags = m.tags.map(t=>`<span class="person-tag mg">${t}</span>`).join('');
  mgList.innerHTML += `
    <div class="person-card">
      <div class="person-avatar mg">${m.initials}</div>
      <div>
        <div class="person-title mg">${m.title}</div>
        <div class="person-name">${m.constell} &nbsp;·&nbsp; <span class="stars">${m.stars}</span></div>
        <div class="person-body">${m.body}</div>
        <div class="person-tags">${tags}</div>
      </div>
    </div>`;
});

// SKILL TREES
const TREES = [
  { id:"boundary", name:"Boundary", color:"#8B7FD4", desc:"Territory and space. You begin by claiming ground and end by replacing reality with your own version of it.", fantasy:"A general who decides where the battlefield ends.",
    nodes:[
      {title:"Field Sense",cost:1,desc:"You always know the exact dimensions of any space you inhabit. You feel when your Tempo is interfered with. Passive.",tags:["passive"]},
      {title:"Soft Boundary",cost:1,desc:"Create a small invisible boundary up to 10 feet across. Creatures inside feel mild resistance leaving. Creatures may notice something is wrong on a Wisdom save. Sustained 1 hour.",tags:["concentration","1 hour"]},
      {title:"Tempo Zone",cost:1,desc:"Your boundary becomes real. Creatures leaving must pass a Strength check (DC 12 + prof bonus) or be pushed back. Range expands to 30 feet. The edge of the zone faintly glows your color.",tags:["active","30ft"]},
      {title:"Hard Cage",cost:1,desc:"The boundary becomes physical. Creatures cannot pass through without breaking it (damage = INT/WIS mod × 5). You can now target a specific creature instead of an area.",tags:["active","targeted"]},
      {title:"Layered Field",cost:1,desc:"Maintain two boundaries simultaneously — an outer soft boundary and an inner hard cage. The outer layer can be invisible to non-Tempo users.",tags:["advanced","dual"]},
      {title:"Branded Territory ★",cost:2,desc:"Within your boundary, you choose what passes — sound, light, magic, air. Specific spells or Tempo abilities can be blocked or allowed. Lasts 8 hours. Milestone.",tags:["milestone","8 hours"],milestone:true},
      {title:"Conceptual Reality ★★",cost:3,desc:"You project your inner world outward, replacing perceived reality. Partial manifestation appears as a colored egg visible to all. Full manifestation completely separates the interior from the outside world. Once per long rest.",tags:["ultimate","1/long rest"],milestone:true}
    ]
  },
  { id:"resonance", name:"Resonance", color:"#5DCAA5", desc:"Self-mastery. Finding the specific music that is yours alone and sharpening it into something no one else can replicate.", fantasy:"A musician who spent years discovering their sound and now plays in a way no one can teach.",
    nodes:[
      {title:"Hear the Music",cost:1,desc:"You become aware of your own Tempo — a faint internal rhythm. You know when your Tempo is being disrupted. Passive.",tags:["passive"]},
      {title:"Innate Technique I",cost:1,desc:"You identify one minor innate ability tied to your Tempo — something small and personal. Work with your DM to define it. This ability is always active.",tags:["passive","personal"]},
      {title:"Tempo Sharpening",cost:1,desc:"Advantage on saving throws against abilities that would alter your identity, charm you, or overwrite your personality.",tags:["passive","defensive"]},
      {title:"Innate Technique II",cost:1,desc:"Your innate ability scales meaningfully upward. The same idea, made larger. Work with the DM.",tags:["passive","upgrade"]},
      {title:"Resonant Body",cost:1,desc:"Resistance to psychic damage. Immunity to the Charmed condition. Your Tempo is now visually detectable to other Tempo users.",tags:["passive","defensive"]},
      {title:"Signature ★",cost:2,desc:"Your Tempo becomes recognizable. A visual, auditory, or physical phenomenon accompanies your most powerful moments. Advantage on Charisma checks with those who have witnessed it. Milestone.",tags:["milestone","signature"],milestone:true},
      {title:"Innate Technique III — True Form ★★",cost:3,desc:"The full expression of your innate ability. What was once minor becomes reality-altering. The thing that is uniquely yours becomes something the world has to account for. Once per long rest.",tags:["ultimate","personal","1/long rest"],milestone:true}
    ]
  },
  { id:"deal", name:"The Deal", color:"#D85A30", desc:"Contracts, marks, and promises. Every ability here is a two-way exchange. Power always comes with a price or a promise.", fantasy:"Someone who understands that everything in the world is a negotiation — and they are very good at it.",
    nodes:[
      {title:"Read the Terms",cost:1,desc:"You sense whether a contract or promise has weight to it. You always know when someone is lying about a formally stated intention. Passive.",tags:["passive"]},
      {title:"Mark of Possession I",cost:1,desc:"Place a subtle invisible mark on a creature. You always know their general direction and if they are alive. Lasts 7 days. One mark active at a time.",tags:["active","7 days"]},
      {title:"Mark of Possession II",cost:1,desc:"Your mark carries a minor effect — disadvantage on Deception against you, or you can hear what they hear for 1 minute per day, or send one word to their mind per day.",tags:["active","upgraded"]},
      {title:"Binding Word",cost:1,desc:"A ritual establishing a promise between two parties. If either breaks it, MOTHER notices. The penalty is determined by the DM and is never trivial.",tags:["ritual","consequence"]},
      {title:"Mark of Possession III",cost:1,desc:"Your mark carries a trap. Define a trigger condition. When triggered: 4d8 psychic damage, a condition for 1 minute, or teleport to your location.",tags:["active","trap"]},
      {title:"Favorable Terms ★",cost:2,desc:"In any negotiation, spend a bonus action to read the situation. The DM must tell you one thing the other party wants more than what they are asking for. Milestone.",tags:["milestone","social"],milestone:true},
      {title:"Bargain with the DM ★★",cost:3,desc:"Pause the scene and make an offer to the DM directly. State what you want and what you will pay. The DM can refuse, counter, or accept. If accepted, the narrative bends in your favor — but the cost is real and immediate. Once per campaign arc.",tags:["ultimate","dm-facing","once/arc"],milestone:true}
    ]
  },
  { id:"sacrifice", name:"Sacrifice", color:"#E24B4A", desc:"Deletion. You give things up permanently to become something sharper. The further you go the less recognizable you are.", fantasy:"Someone who keeps throwing pieces of themselves into the fire and walking out stronger — and less.",
    nodes:[
      {title:"Cost Awareness",cost:1,desc:"You understand intuitively what something is worth — in Tempo terms, in personal terms. You know when an ability will cost you something before you commit. Passive.",tags:["passive"]},
      {title:"Restriction C.A.D. I — Minor",cost:1,desc:"Delete one minor personal quality to empower another. Examples: suppress smell for advantage on sound-based Perception; suppress dreaming for 4-hour sleep; suppress one memory for a new language proficiency. The loss is real and permanent.",tags:["permanent","minor loss"]},
      {title:"Pain Tolerance",cost:1,desc:"Take 2d6 damage to treat a failed saving throw as a success. Usable a number of times per day equal to your proficiency bonus.",tags:["active","defensive"]},
      {title:"Restriction C.A.D. II — Moderate",cost:2,desc:"A significant deletion. Examples: lose the ability to feel one emotion permanently to gain immunity to its debuffs; lose a sense entirely to triple the acuity of another. The benefit must feel proportional. The loss must feel real.",tags:["permanent","significant loss"]},
      {title:"Sharpened Edge",cost:1,desc:"For each Restriction C.A.D. node taken, gain +1 to attack rolls or spell save DC (choose once, applies to all).",tags:["passive","scales"]},
      {title:"The Empty Space ★",cost:2,desc:"Where you have deleted parts of yourself, something has grown in the gap. Once per short rest, treat one ability roll as having advantage if it relates to an area where you have made a sacrifice. Milestone.",tags:["milestone","1/short rest"],milestone:true},
      {title:"Restriction C.A.D. III — Total ★★",cost:3,desc:"Something fundamental about who you are is given up permanently — your name's meaning, your ability to be remembered by strangers, your reflection, your aging. In exchange, one ability of equivalent mythic weight. Cannot be undone.",tags:["ultimate","permanent","irreversible"],milestone:true}
    ]
  },
  { id:"physique", name:"Physique", color:"#888780", desc:"Your Tempo turned inward to reinforce your body. The music making you harder to break.", fantasy:"Someone whose inner rhythm is so steady it becomes structural — like rebar inside concrete.",
    nodes:[
      {title:"Tempo Constitution",cost:1,desc:"Gain 2 maximum HP per character level, applied retroactively and to future levels.",tags:["passive","hp"]},
      {title:"Steady Rhythm",cost:1,desc:"Advantage on Constitution saving throws to maintain concentration and against the Exhaustion condition.",tags:["passive"]},
      {title:"Reinforced Frame",cost:1,desc:"Resistance to bludgeoning damage. Your Tempo visibly ripples under your skin when you take a hit.",tags:["passive","resistance"]},
      {title:"Impact Absorption",cost:1,desc:"When a single hit would drop you below half maximum HP, use your reaction to halve that damage. Once per short rest.",tags:["reaction","1/short rest"]},
      {title:"Unbroken Tempo",cost:1,desc:"You can act normally while at 0 HP for up to 2 rounds before making death saving throws. You still make saves — you simply do not collapse immediately.",tags:["passive","dramatic"]},
      {title:"Living Fortress ★",cost:2,desc:"Maximum HP increases by 20. Immunity to the Frightened condition. Allies within 10 feet gain +2 to saving throws while you are conscious. Milestone.",tags:["milestone","aura","hp"],milestone:true},
      {title:"Absolute Body ★★",cost:3,desc:"Resistance to all damage except psychic. Once per long rest, when you would die, you instead drop to 1 HP. Your Tempo screams loud enough for everyone in the area to hear when this triggers.",tags:["ultimate","1/long rest"],milestone:true}
    ]
  },
  { id:"echo", name:"Echo", color:"#378ADD", desc:"Observation and absorption. You grow stronger by watching others. The Mentor mechanic made into a skill.", fantasy:"Someone who watches a person do something once and walks away knowing how to do it.",
    nodes:[
      {title:"Tempo Sight",cost:1,desc:"See the Tempo of other creatures as a faint colored aura. Read emotional state and whether they hold power in reserve. Passive.",tags:["passive"]},
      {title:"Trace",cost:1,desc:"After observing an ability used, make an Arcana check (DC set by DM). On success, you understand the basic mechanism — not how to replicate it yet, but enough to anticipate it.",tags:["active","observation"]},
      {title:"Echo Fragment",cost:1,desc:"After a successful Trace, attempt a simplified version of what you observed at roughly half power. Concentration required. Once per observed ability per long rest.",tags:["active","1/long rest per ability"]},
      {title:"Deeper Reading",cost:1,desc:"Your Tempo Sight deepens. You know a creature's rough Tempo tree type. You also know when someone is at or near their Tempo limit.",tags:["passive","upgraded"]},
      {title:"Learning Rhythm",cost:1,desc:"Mentor training sessions take half the time. Once per campaign, learn a single ability from a deceased mentor whose technique you witnessed firsthand.",tags:["passive","mentor"]},
      {title:"Mirror ★",cost:2,desc:"When targeted by an ability you have previously Traced, use your reaction to reflect it back at its source at half potency. Milestone.",tags:["milestone","reaction"],milestone:true},
      {title:"Resonant Copy ★★",cost:3,desc:"After witnessing a Milestone or ultimate ability used, attempt to absorb it entirely. Arcana DC 20. Success: use a stripped-down version once before it fades. Failure: Tempo disrupted for 1 hour. This should feel impossible.",tags:["ultimate","high risk"],milestone:true}
    ]
  },
  { id:"flux", name:"Flux", color:"#639922", desc:"Speed and momentum. Not about hitting hard — about being somewhere before anyone expected you.", fantasy:"The person who was already behind you before you finished deciding to look.",
    nodes:[
      {title:"Light Step",cost:1,desc:"Your footsteps make no sound unless you choose. Advantage on Dexterity (Stealth) checks involving movement. Passive.",tags:["passive"]},
      {title:"Tempo Burst",cost:1,desc:"As a bonus action, your movement speed doubles until the end of your turn. Usable a number of times equal to your proficiency bonus per short rest.",tags:["bonus action"]},
      {title:"Between Moments",cost:1,desc:"When you Disengage, you do not provoke opportunity attacks this turn or the next. Your movement leaves no visual trace — no dust, no displaced air.",tags:["active"]},
      {title:"Overclocked Reaction",cost:1,desc:"You can take two reactions per round. The second recharges at the end of your next turn rather than the start.",tags:["passive"]},
      {title:"Slipstream",cost:1,desc:"When you move through a creature's space, they make a Dexterity save or be knocked prone. Moving through their space does not count as difficult terrain.",tags:["active","movement"]},
      {title:"Afterimage ★",cost:2,desc:"When you move more than 15 feet in a turn, you leave a brief afterimage at your starting point. Until the start of your next turn, attackers have a 50% chance of targeting the afterimage. Milestone.",tags:["milestone","defensive"],milestone:true},
      {title:"Zero Interval ★★",cost:3,desc:"For one round, you act at the very start of every initiative count — before any other creature regardless of their roll. During this round you are effectively unhittable by anything requiring the attacker to track your position. Once per long rest.",tags:["ultimate","1/long rest"],milestone:true}
    ]
  },
  { id:"puppeteer", name:"Puppeteer", color:"#EF9F27", desc:"Extending your Tempo outward to move things. Where Boundary controls space, Puppeteer controls what is inside it.", fantasy:"Someone whose hands are everywhere they look.",
    nodes:[
      {title:"Reach",cost:1,desc:"Manipulate small objects within 30 feet as if you had a hand there. Cannot be used in combat for damage. Passive utility.",tags:["passive","utility"]},
      {title:"Tempo Grip",cost:1,desc:"Grab and hold a creature or object within 30 feet. Treat as a grapple using your Tempo modifier (INT or WIS) instead of STR. The grip is invisible.",tags:["active","grapple"]},
      {title:"Controlled Space",cost:1,desc:"Affect up to your proficiency bonus in objects simultaneously. Attack for 1d6 bludgeoning each (one roll per object, bonus action).",tags:["active","multi-object"]},
      {title:"Redirect",cost:1,desc:"Use your reaction to redirect a projectile or ranged spell within 60 feet, changing its target to any creature within range.",tags:["reaction"]},
      {title:"Deeper Grip",cost:1,desc:"Your Grip affects creatures larger than you without penalty. Grappled creatures take 2d6 psychic damage at the start of each of their turns.",tags:["active","upgraded"]},
      {title:"Marionette Touch ★",cost:2,desc:"An action to control a creature's physical movement — not their mind, just their body. Strength save or you control their movement and one physical action for one round. Milestone.",tags:["milestone","control"],milestone:true},
      {title:"Everything Has Strings ★★",cost:3,desc:"For one round, your Tempo reaches outward to every object and creature within 60 feet simultaneously. Creatures make Strength saves. This should look terrifying. Once per long rest.",tags:["ultimate","1/long rest"],milestone:true}
    ]
  },
  { id:"veil", name:"Veil", color:"#D4537E", desc:"Concealment and misdirection. Your Tempo turned inward to hide. You are never quite where anyone thinks you are.", fantasy:"The person in the room that no one can quite remember was there.",
    nodes:[
      {title:"Background Noise",cost:1,desc:"Other Tempo users cannot detect you passively. You do not register on Tempo Sight unless someone actively searches. Passive.",tags:["passive"]},
      {title:"Soft Vanish",cost:1,desc:"As a bonus action, creatures have disadvantage on Perception checks to notice or track you for 1 minute. You are not invisible. You are simply easy to look past.",tags:["bonus action","1 minute"]},
      {title:"False Presence",cost:1,desc:"Project a faint imprint of your Tempo to a location within 60 feet. Other Tempo users sense you as being there rather than where you actually are. Lasts until you attack or cast a spell.",tags:["active","misdirection"]},
      {title:"Veil Another",cost:1,desc:"Extend your concealment to one willing creature you touch. They gain the benefit of Soft Vanish for up to 10 minutes. Concentration required.",tags:["concentration","10 minutes"]},
      {title:"Memory Blur",cost:1,desc:"After leaving a social interaction, creatures who interacted with you must succeed on a Wisdom save (DC 12 + prof bonus) to remember specific details about your appearance or name within 24 hours.",tags:["active","social"]},
      {title:"Complete Veil ★",cost:2,desc:"Fully undetectable for up to 1 minute — invisible, soundless, undetectable by magical means of your level or lower. Attacking or casting above 2nd level ends it. Once per long rest. Milestone.",tags:["milestone","1/long rest"],milestone:true},
      {title:"The Unseen ★★",cost:3,desc:"For one round, you do not exist to anyone who has not previously seen through one of your Veil effects. Attacks cannot target you, effects cannot include you, and you leave no trace — not even to recording devices or magical sensors. Once per long rest.",tags:["ultimate","1/long rest"],milestone:true}
    ]
  },
  { id:"requiem", name:"Requiem", color:"#534AB7", desc:"The death-adjacent tree. Soul eggs, the space between living and dying. Slow to develop. The payoff is unlike anything else.", fantasy:"Someone standing calmly in the doorway between two rooms that most people never get to see both of.",
    nodes:[
      {title:"Soul Sight",cost:1,desc:"See soul eggs when they leave a body after death. Track them within 60 feet. Know when a creature nearby is close to death — a faint glow visible only to you. Passive.",tags:["passive"]},
      {title:"Gentle Send",cost:1,desc:"Perform the Sending ritual simply by being present and willing. A soul you Send gives you a brief glimpse of its last memory before departing.",tags:["ritual","utility"]},
      {title:"Hold",cost:1,desc:"Delay a creature's death for up to 1 hour. The creature stabilizes at 0 HP and does not make death saving throws during this time. Once per long rest.",tags:["active","1/long rest"]},
      {title:"Soul Reading",cost:1,desc:"By spending a minute with a recently deceased creature (within 1 hour of death), ask the DM three yes/no questions about what the creature knew or experienced. The DM answers honestly.",tags:["ritual","information"]},
      {title:"Refuse Sending",cost:2,desc:"Prevent a soul from being sent — holding it in limbo anchored to you. The soul cannot be targeted by necromantic effects while held. You can hold one soul at a time. The soul can communicate with you. The ethics of this are significant.",tags:["active","ethical weight"]},
      {title:"Echo of the Dead ★",cost:2,desc:"Temporarily call the knowledge of a held soul into your body — gaining proficiency in one skill or tool the deceased was proficient in for 24 hours. Milestone.",tags:["milestone","24 hours"],milestone:true},
      {title:"The Threshold ★★",cost:3,desc:"Cross the threshold — entering a state that is neither living nor dead. For up to 10 minutes: immune to all damage, undetectable by any means, able to observe the world as a soul does. You cannot affect anything physical. When you return, you carry back one piece of absolute knowledge. Define this with your DM. It changes your character. Once per long rest.",tags:["ultimate","1/long rest","narrative weight"],milestone:true}
    ]
  },
  { id:"forge", name:"Forge", color:"#1D9E75", desc:"Your Tempo poured into objects rather than the world directly. You fight through what you make.", fantasy:"Someone whose hands are their argument.",
    nodes:[
      {title:"Resonant Hands",cost:1,desc:"Objects you craft or repair carry a trace of your Tempo — they last twice as long, resist mundane breakage, and you always know where they are within 1 mile. Passive.",tags:["passive","crafting"]},
      {title:"Tempo Infusion I",cost:1,desc:"Spend 1 hour infusing a weapon or tool. Gains +1 to attack and damage rolls or checks made with it. One active infusion at a time.",tags:["active","1 hour","1 item"]},
      {title:"Tempo Infusion II",cost:1,desc:"Maintain up to three infusions simultaneously. Infused weapons deal +1d4 psychic damage. Infused armor grants +1 AC. Infused tools give advantage on their skill checks.",tags:["active","upgraded"]},
      {title:"Attuned Weapon",cost:1,desc:"Choose one infused weapon as your Attuned weapon. Call it to your hand as a bonus action from up to 60 feet away. It deals an extra 1d6 damage while attuned.",tags:["active","bond"]},
      {title:"Emergency Forge",cost:1,desc:"As a bonus action, infuse any object in hand — even improvised weapons. Lasts until the end of the encounter. The object counts as magical for overcoming resistances.",tags:["bonus action","combat"]},
      {title:"Signature Item ★",cost:2,desc:"Create one item of significant power over one week of crafting. Work with your DM to define it — unique to your character, carrying one property not possible through normal infusion. Cannot be permanently destroyed while you live. Milestone.",tags:["milestone","unique","crafting"],milestone:true},
      {title:"Living Construct ★★",cost:3,desc:"Spend one week constructing a small autonomous construct — no larger than a dog — that carries your Tempo independently. It has its own AC, HP, and one ability you define with the DM. If destroyed it can be rebuilt over one week. It is loyal because of what it is made of.",tags:["ultimate","construct","permanent"],milestone:true}
    ]
  },
  { id:"broadcast", name:"Broadcast", color:"#BA7517", desc:"Your Tempo expressed outward as an aura that changes the room. The leader tree. Difficult to turn off.", fantasy:"The person who walks in and the temperature of the room changes — and they are not always sure they meant it to.",
    nodes:[
      {title:"Ambient Tempo",cost:1,desc:"Advantage on Charisma (Persuasion) and Charisma (Intimidation) checks. Creatures within 10 feet are subtly aware of your emotional state whether you show it or not. Passive.",tags:["passive","aura"]},
      {title:"Rally Pulse",cost:1,desc:"Once per short rest as a bonus action, emit a pulse of your Tempo. Allies within 30 feet gain temporary HP equal to your proficiency bonus + Charisma modifier.",tags:["bonus action","ally","1/short rest"]},
      {title:"Dissonance",cost:1,desc:"One creature within 30 feet makes a Wisdom save or has disadvantage on all attack rolls and ability checks until the end of their next turn.",tags:["action","debuff"]},
      {title:"Broadcast Emotion",cost:1,desc:"Push one emotion outward through your Tempo — calm, dread, urgency, confidence. All creatures within 60 feet who fail a Wisdom save feel that emotion as their own for 1 minute. This does not control them — it colors their decision-making.",tags:["active","area","emotion"]},
      {title:"Selective Frequency",cost:1,desc:"Fine control over who your Broadcast reaches. Include or exclude any number of specific creatures from any of your Broadcast effects. Your allies are never caught in your Dissonance by accident.",tags:["passive","control"]},
      {title:"Dominant Signal ★",cost:2,desc:"Your Tempo becomes the loudest thing in the room. Concentration, up to 10 minutes. All creatures within 60 feet must beat your Tempo to cast enchantment or illusion spells — Charisma contest against you or the spell fails. Milestone.",tags:["milestone","concentration","10 minutes"],milestone:true},
      {title:"The Broadcast ★★",cost:3,desc:"For one round, every creature within 120 feet feels your inner music as if it were their own. Allies act with perfect coordination — they can take reactions on each other's turns once. Enemies must succeed a Wisdom save or spend their turn doing nothing, overwhelmed. Once per long rest.",tags:["ultimate","1/long rest","aoe"],milestone:true}
    ]
  }
];

const tabsContainer = document.getElementById('tree-tabs');
const panelsContainer = document.getElementById('tree-panels');

TREES.forEach((tree, i) => {
  const tab = document.createElement('button');
  tab.className = 'tree-tab' + (i === 0 ? ' active' : '');
  tab.textContent = tree.name;
  tab.dataset.id = tree.id;
  if (i === 0) { tab.style.borderColor = tree.color; tab.style.color = tree.color; tab.style.background = 'rgba(139,127,212,0.12)'; }
  tabsContainer.appendChild(tab);

  const nodes = tree.nodes.map((node, ni) => {
    const badgeCls = node.cost >= 3 ? 'badge-3' : node.cost === 2 ? 'badge-2' : 'badge-1';
    const milestoneStyle = node.milestone ? `border-left: 2px solid ${tree.color};` : '';
    const connector = ni > 0 ? `<div class="tree-connector"></div>` : '';
    const tags = node.tags.map(t => {
      const cls = t === 'milestone' ? 'milestone-tag' : (t === 'ultimate' ? 'ultimate-tag' : '');
      return `<span class="node-tag ${cls}">${t}</span>`;
    }).join('');
    return `${connector}<div class="tree-node" style="${milestoneStyle}"><div class="node-badge ${badgeCls}">${node.cost}pt</div><div class="node-body-inner"><div class="node-title">${ni+1}. ${node.title}</div><div class="node-cost">Cost: ${node.cost} level-up point${node.cost>1?'s':''}</div><div class="node-desc">${node.desc}</div><div class="node-tags-row">${tags}</div></div></div>`;
  }).join('');

  panelsContainer.innerHTML += `
    <div class="tree-panel${i===0?' active':''}" id="panel-${tree.id}">
      <div class="tree-header">
        <div class="tree-name" style="color:${tree.color};">${tree.name}</div>
        <div class="tree-desc">${tree.desc}</div>
        <div class="tree-fantasy">"${tree.fantasy}"</div>
      </div>
      <div class="tree-nodes">${nodes}</div>
    </div>`;
});

tabsContainer.addEventListener('click', e => {
  const tab = e.target.closest('.tree-tab');
  if (!tab) return;
  const tree = TREES.find(t => t.id === tab.dataset.id);
  document.querySelectorAll('.tree-tab').forEach(t => {
    t.classList.remove('active');
    t.style.borderColor = ''; t.style.color = ''; t.style.background = '';
  });
  tab.classList.add('active');
  tab.style.borderColor = tree.color;
  tab.style.color = tree.color;
  tab.style.background = `${tree.color}18`;
  document.querySelectorAll('.tree-panel').forEach(p => p.classList.remove('active'));
  document.getElementById('panel-' + tab.dataset.id).classList.add('active');
});

// NATIONS
const NATIONS = [
  { name:"Concordia", insp:"World Government", stats:["Tech 4/5","Magic 5/5","Army 2/5"], desc:"The seat of global power. Home of the Academy, the Foundation Engine, and the only known source of Orichalcum. Run by the Genius, the Luminary Council, and enforced by the Holy Knights." },
  { name:"Galfond", insp:"USA-inspired", stats:["Tech 6/5","Magic 0/5","Army 4.5/5"], desc:"Forsaken by the Constellations and devoid of magic, but the most technologically advanced nation in the world. They invented the Foundation Engine. Presidential government. Home to the largest Old World library." },
  { name:"Venetus", insp:"UK-inspired", stats:["Tech 3/5","Magic 5/5","Army 4/5"], desc:"A super-magical kingdom protected by King Arthur Pendragon and the Round Table Knights. Concordia's biggest political enemy. Home of Stallwarts Academy — second only to Concordia for general education." },
  { name:"Hérault", insp:"France-inspired", stats:["Tech 3/5","Magic 4/5","Army 3/5"], desc:"Known as the Dogs of Concordia. A nation of art, drama, and heavy stratification between noble class and commoners. Currently ruled by Queen Elisabeth Bathory." },
  { name:"Malum", insp:"Mediterranean-inspired", stats:["Tech 4/5","Magic 3/5","Army 4/5"], desc:"Once an empire that owned vast amounts of land. Now a vibrant nation known for endless celebrations, grand stadiums, and love for competition. Where MagiTube was created." },
  { name:"Ular Naga", insp:"India-inspired", stats:["Tech 3/5","Magic 4/5","Army 2/5"], desc:"Where gods live among humans. Three elevated cities constructed above the plains to escape the Disaster Tribes — ferocious anti-technology cults that worship and summon strange gods." },
  { name:"Tribao", insp:"Ancient China-inspired", stats:["Tech 5/5","Magic 5/5","Army 5/5"], desc:"Cares deeply about wisdom, tradition, and powerful monsters. Multiple islands each governed by a Heavenly General. One island — Black Tortoise — has been lost to the Glitch. Do not approach it." },
  { name:"Urgora", insp:"Russia-inspired", stats:["Tech 4/5","Magic 2/5","Army 3/5"], desc:"After the Great Holy World War, the lower lands became uninhabitable. Survivors ascended to mountain cities, each owned by corporations. Every citizen is born into a job. Unemployment is at 0.1%." },
  { name:"Shi-Tenzan", insp:"Edo Japan-inspired", stats:["Tech 4/5","Magic 1/5","Army 2/5"], desc:"A small island nation with colossal monsters that defy classification. Neo Edo is a shining capital surrounded by a force field. Outside it, small villages fend for themselves with the Hunters Guild." },
  { name:"Pietoria", insp:"Brazil-inspired", stats:["Tech 2/5","Magic 4/5","Army 3/5"], desc:"A mystical land of lush jungles, towering mountains, and ancient secrets. Ruled by four main tribes that formed cities around giant temples said to have been made by The Father and The Mother." },
  { name:"Kirkbay", insp:"Bilgewater-inspired", stats:["Tech 3/5","Magic 1/5","Army 4/5"], desc:"A haven for pirates, assassins, and thieves. The only rule: respect each other's loot and lives. Currently under the loose oversight of the Pirate Queen Yi, who killed her father to earn the title." },
  { name:"Forest of Amicitia", insp:"Mystical Forest", stats:["Tech 2/5","Magic 5/5","Army 3/5"], desc:"A vast enchanted woodland between Venetus and Hérault. Once oppressed and enslaved by Hérault. Home to Elves, Viera, Fairies, and Amazons. Mystical dungeons appear randomly within it." },
  { name:"Misir", insp:"Egypt-inspired", stats:["Tech ?","Magic ?","Army ?"], desc:"Once a beacon of knowledge and historical preservation. In 5098, the Pharaoh declared Misir closed to the outside world. Those who approach find themselves thwarted by a mysterious mist. No one knows what happened inside." }
];

const nationsGrid = document.getElementById('nations-grid');
NATIONS.forEach(n => {
  const stats = n.stats.map(s=>`<span class="nation-stat">${s}</span>`).join('');
  nationsGrid.innerHTML += `
    <div class="nation-card">
      <div class="nation-name">${n.name}</div>
      <div class="nation-insp">${n.insp}</div>
      <div class="nation-stats">${stats}</div>
      <div class="nation-desc">${n.desc}</div>
    </div>`;
});
</script>
</body>
</html>
HTMLEOF
Output

exit code 0

Check the file size and
