<!-- ULTIMATE LEVEL -->
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Ra-Studios — Ultimate Dimension</title>
<style>
@import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&family=Share+Tech+Mono&family=Rajdhani:wght@300;500;700&display=swap');

:root {
  --cyan: #00f0ff;
  --purple: #b829f7;
  --slate: #0a0e1a;
  --neon-pink: #ff0090;
  --gold: #ffd700;
  --glass: rgba(10, 14, 26, 0.6);
}

* { margin: 0; padding: 0; box-sizing: border-box; }

body {
  background: var(--slate);
  color: #e8e8f8;
  font-family: 'Share Tech Mono', monospace;
  overflow-x: hidden;
  min-height: 100vh;
}

/* Animated Matrix Grid Background */
.grid-bg {
  position: fixed;
  top: 0; left: 0; width: 100%; height: 100%;
  background:
    linear-gradient(rgba(0, 240, 255, 0.03) 1px, transparent 1px),
    linear-gradient(90deg, rgba(184, 41, 247, 0.03) 1px, transparent 1px);
  background-size: 40px 40px;
  z-index: -2;
  animation: gridPulse 8s ease-in-out infinite;
}
@keyframes gridPulse {
  0%, 100% { opacity: 0.5; }
  50% { opacity: 1; }
}

/* Glowing Orbs */
.orb {
  position: fixed;
  border-radius: 50%;
  filter: blur(120px);
  z-index: -1;
  pointer-events: none;
  animation: orbFloat 20s ease-in-out infinite alternate;
}
.orb.cyan { width: 600px; height: 600px; background: radial-gradient(circle, rgba(0,240,255,0.15) 0%, transparent 70%); top: -10%; left: -5%; animation-delay: 0s; }
.orb.purple { width: 500px; height: 500px; background: radial-gradient(circle, rgba(184,41,247,0.15) 0%, transparent 70%); bottom: 10%; right: -10%; animation-delay: -7s; }
.orb.pink { width: 400px; height: 400px; background: radial-gradient(circle, rgba(255,0,144,0.12) 0%, transparent 70%); top: 40%; left: 60%; animation-delay: -14s; }
@keyframes orbFloat {
  from { transform: translate(0, 0) scale(1); }
  to { transform: translate(50px, -30px) scale(1.2); }
}

/* Center Container */
.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 120px 24px;
  position: relative;
}

/* Glitch Header */
.glitch-wrapper {
  position: relative;
  text-align: center;
  padding: 60px 0;
}
.glitch-wrapper h1 {
  font-family: 'Orbitron', sans-serif;
  font-size: 6rem;
  font-weight: 900;
  letter-spacing: -0.05em;
  color: #fff;
  position: relative;
  text-transform: uppercase;
  text-shadow:
    3px 3px 0 var(--cyan),
    -3px -3px 0 var(--purple),
    0 0 60px rgba(0,240,255,0.5);
  animation: glitchShift 4s infinite;
}
.glitch-wrapper h1::before,
.glitch-wrapper h1::after {
  content: 'RA-STUDIOS';
  position: absolute;
  top: 0; left: 0; width: 100%; height: 100%;
  opacity: 0.8;
}
.glitch-wrapper h1::before {
  color: var(--cyan);
  clip-path: polygon(0 0, 100% 0, 100% 45%, 0 45%);
  transform: translate(-2px, -2px);
  animation: glitchBefore 3s infinite linear alternate-reverse;
}
.glitch-wrapper h1::after {
  color: var(--purple);
  clip-path: polygon(0 55%, 100% 55%, 100% 100%, 0 100%);
  transform: translate(2px, 2px);
  animation: glitchAfter 3s infinite linear alternate-reverse;
}
@keyframes glitchShift {
  0%, 90%, 100% { filter: hue-rotate(0deg); }
  92% { filter: hue-rotate(30deg); }
  94% { filter: hue-rotate(-30deg); }
}
@keyframes glitchBefore {
  0% { transform: translate(-2px, -2px); }
  20% { transform: translate(2px, 2px); }
  40% { transform: translate(-2px, 2px); }
  60% { transform: translate(2px, -2px); }
  80% { transform: translate(3px, -1px); }
  100% { transform: translate(-3px, 1px); }
}
@keyframes glitchAfter {
  0% { transform: translate(2px, 2px); }
  20% { transform: translate(-2px, -2px); }
  40% { transform: translate(2px, -2px); }
  60% { transform: translate(-2px, 2px); }
  80% { transform: translate(-3px, 1px); }
  100% { transform: translate(3px, -1px); }
}

/* Subtitle Glow */
.subtitle {
  font-family: 'Rajdhani', sans-serif;
  font-size: 1.4rem;
  letter-spacing: 0.3em;
  color: var(--cyan);
  text-align: center;
  margin-top: 20px;
  text-shadow: 0 0 20px var(--cyan);
  animation: subtitlePulse 3s ease-in-out infinite;
}
@keyframes subtitlePulse {
  0%, 100% { opacity: 1; text-shadow: 0 0 20px var(--cyan); }
  50% { opacity: 0.7; text-shadow: 0 0 40px var(--cyan), 0 0 80px var(--purple); }
}

/* Animated Divider Line */
.divider {
  height: 2px;
  width: 300px;
  margin: 40px auto;
  background: linear-gradient(90deg, transparent, var(--cyan), var(--purple), var(--cyan), transparent);
  position: relative;
  animation: dividerSlide 2s ease-in-out infinite alternate;
}
.divider::before {
  content: '';
  position: absolute;
  top: -4px; left: 50%; transform: translateX(-50%);
  width: 12px; height: 10px;
  background: var(--cyan);
  border-radius: 50%;
  box-shadow: 0 0 20px var(--cyan), 0 0 40px var(--purple);
  animation: dotBounce 2s ease-in-out infinite alternate;
}
@keyframes dividerSlide {
  from { width: 200px; }
  to { width: 500px; }
}
@keyframes dotBounce {
  from { top: -4px; box-shadow: 0 0 10px var(--cyan); }
  to { top: 6px; box-shadow: 0 0 30px var(--cyan), 0 0 60px var(--purple); }
}

/* Sections */
.section-card {
  background: linear-gradient(135deg, rgba(0,240,255,0.05), rgba(184,41,247,0.05));
  border: 1px solid rgba(0,240,255,0.2);
  border-radius: 24px;
  padding: 48px 32px;
  margin: 60px 0;
  backdrop-filter: blur(12px);
  box-shadow: 0 0 40px rgba(0,240,255,0.05), inset 0 0 60px rgba(184,41,247,0.05);
  transition: all 0.5s ease;
  position: relative;
  overflow: hidden;
}
.section-card::before {
  content: '';
  position: absolute;
  top: 0; left: -100%; width: 100%; height: 100%;
  background: linear-gradient(90deg, transparent, rgba(255,255,255,0.05), transparent);
  animation: shimmer 3s infinite;
}
@keyframes shimmer {
  0% { left: -100%; }
  50%, 100% { left: 100%; }
}
.section-card:hover {
  border-color: rgba(0,240,255,0.5);
  box-shadow: 0 0 80px rgba(0,240,255,0.15), 0 0 120px rgba(184,41,247,0.1);
  transform: translateY(-5px);
}

/* Section Titles */
.section-title {
  font-family: 'Orbitron', sans-serif;
  font-size: 2.2rem;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  color: #fff;
  text-align: center;
  margin-bottom: 30px;
  position: relative;
  display: inline-block;
}
.section-title::after {
  content: '';
  display: block;
  width: 60px; height: 3px;
  background: linear-gradient(90deg, var(--cyan), var(--purple));
  margin: 12px auto 0;
  border-radius: 2px;
  box-shadow: 0 0 10px var(--cyan);
}

/* Typing SVG Area */
.typing-area {
  text-align: center;
  padding: 20px 0;
}
.typing-area img {
  border-radius: 16px;
  box-shadow: 0 0 30px rgba(0,240,255,0.3), 0 0 60px rgba(184,41,247,0.2);
  transition: transform 0.3s ease;
}
.typing-area img:hover {
  transform: scale(1.02);
}

/* Visitor Counter Badge */
.counter-wrap {
  display: inline-flex;
  align-items: center;
  gap: 10px;
  padding: 8px 20px;
  background: rgba(0,240,255,0.1);
  border: 1px solid rgba(0,240,255,0.3);
  border-radius: 50px;
  margin-top: 20px;
  animation: pulseBorder 3s infinite;
}
@keyframes pulseBorder {
  0%, 100% { border-color: rgba(0,240,255,0.3); box-shadow: 0 0 10px rgba(0,240,255,0.1); }
  50% { border-color: rgba(184,41,247,0.5); box-shadow: 0 0 25px rgba(184,41,247,0.2); }
}

/* Status Pills */
.pill-row {
  display: flex;
  justify-content: center;
  gap: 12px;
  flex-wrap: wrap;
  margin-top: 20px;
}
.pill {
  padding: 8px 20px;
  border-radius: 50px;
  font-family: 'Orbitron', sans-serif;
  font-weight: 700;
  font-size: 0.85rem;
  letter-spacing: 0.05em;
  text-transform: uppercase;
  border: 1px solid;
  transition: all 0.3s ease;
  position: relative;
  overflow: hidden;
}
.pill.cyan { color: var(--cyan); border-color: var(--cyan); box-shadow: 0 0 15px rgba(0,240,255,0.2); }
.pill.purple { color: var(--purple); border-color: var(--purple); box-shadow: 0 0 15px rgba(184,41,247,0.2); }
.pill.slate { color: #8899aa; border-color: #8899aa; box-shadow: 0 0 15px rgba(136,153,170,0.1); }
.pill:hover { transform: scale(1.08) rotate(-1deg); filter: brightness(1.3); }

/* Skill Icons */
.skill-icons {
  display: flex;
  justify-content: center;
  gap: 16px;
  flex-wrap: wrap;
  margin-top: 30px;
}
.skill-icons img {
  width: 48px; height: 48px; border-radius: 12px;
  transition: all 0.3s ease;
  filter: grayscale(0.3) brightness(1.2);
  box-shadow: 0 0 10px rgba(255,255,255,0.05);
}
.skill-icons img:hover {
  transform: scale(1.3) rotate(5deg);
  filter: grayscale(0) brightness(1.5);
  box-shadow: 0 0 25px var(--cyan), 0 0 40px var(--purple);
}

/* About Section */
.about-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 20px;
}
.about-card {
  background: rgba(255,255,255,0.02);
  border: 1px solid rgba(255,255,255,0.08);
  border-radius: 16px;
  padding: 28px;
  transition: all 0.4s ease;
  position: relative;
  overflow: hidden;
}
.about-card::after {
  content: '';
  position: absolute;
  bottom: 0; left: 0; height: 3px; width: 0%;
  background: linear-gradient(90deg, var(--cyan), var(--purple));
  transition: width 0.5s ease;
}
.about-card:hover { border-color: rgba(0,240,255,0.4); background: rgba(255,255,255,0.04); }
.about-card:hover::after { width: 100%; }
.about-card h3 {
  font-family: 'Orbitron', sans-serif;
  color: var(--cyan);
  font-size: 1.1rem;
  margin-bottom: 12px;
  letter-spacing: 0.05em;
}
.about-card p { color: #ccddee; line-height: 1.6; font-size: 0.95rem; }

/* Tech Stack */
.category {
  margin: 30px 0;
  text-align: center;
}
.category h4 {
  font-family: 'Rajdhani', sans-serif;
  font-weight: 700;
  font-size: 1.3rem;
  letter-spacing: 0.15em;
  text-transform: uppercase;
  color: #fff;
  margin-bottom: 16px;
  text-shadow: 0 0 15px rgba(0,240,255,0.3);
}
.badge-grid {
  display: flex;
  justify-content: center;
  gap: 12px;
  flex-wrap: wrap;
}
.badge-grid img {
  height: 32px;
  border-radius: 8px;
  transition: all 0.3s ease;
  filter: brightness(1.1);
}
.badge-grid img:hover {
  transform: translateY(-6px) scale(1.1);
  filter: brightness(1.4) drop-shadow(0 0 8px var(--cyan));
}

/* Stats Layout */
.stats-wrap {
  display: flex;
  justify-content: center;
  gap: 20px;
  flex-wrap: wrap;
  margin-top: 30px;
}
.stats-wrap img {
  border-radius: 16px;
  border: 1px solid rgba(0,240,255,0.15);
  box-shadow: 0 0 40px rgba(0,240,255,0.1);
  transition: all 0.4s ease;
}
.stats-wrap img:hover {
  border-color: rgba(0,240,255,0.5);
  box-shadow: 0 0 60px rgba(0,240,255,0.3), 0 0 80px rgba(184,41,247,0.2);
  transform: scale(1.03) rotate(0.5deg);
}

/* Featured Asset */
.featured-card {
  background: linear-gradient(135deg, rgba(0,240,255,0.08), rgba(184,41,247,0.08));
  border: 2px solid rgba(0,240,255,0.2);
  border-radius: 24px;
  padding: 40px;
  text-align: center;
  position: relative;
  overflow: hidden;
}
.featured-card::before {
  content: '★';
  position: absolute;
  top: -30px; right: -30px;
  font-size: 12rem;
  color: rgba(255,255,255,0.02);
  font-family: 'Orbitron', sans-serif;
  animation: starSpin 20s linear infinite;
}
@keyframes starSpin {
  from { transform: rotate(0deg); }
  to { transform: rotate(360deg); }
}
.featured-card img {
  border-radius: 12px;
  margin-bottom: 20px;
  border: 1px solid rgba(0,240,255,0.2);
}
.featured-card h3 {
  font-family: 'Orbitron', sans-serif;
  color: var(--cyan);
  font-size: 1.5rem;
  margin-bottom: 10px;
}
.featured-card p {
  color: #ccddee;
  font-size: 1rem;
  line-height: 1.6;
}

/* Socials */
.social-row {
  display: flex;
  justify-content: center;
  gap: 14px;
  flex-wrap: wrap;
  margin-top: 30px;
}
.social-row a {
  text-decoration: none;
  transition: all 0.3s ease;
  border-radius: 50px;
  overflow: hidden;
}
.social-row a img {
  height: 40px;
  border-radius: 50px;
  transition: all 0.3s ease;
  filter: brightness(1.1);
}
.social-row a:hover {
  transform: translateY(-8px) scale(1.05);
}
.social-row a:hover img {
  filter: brightness(1.4) drop-shadow(0 0 15px var(--cyan));
}

/* Footer Quote */
.quote-block {
  text-align: center;
  padding: 60px 20px;
  background: linear-gradient(180deg, transparent, rgba(0,240,255,0.03), transparent);
  border-top: 1px solid rgba(0,240,255,0.1);
  border-bottom: 1px solid rgba(0,240,255,0.1);
  margin-top: 40px;
  position: relative;
}
.quote-block::before {
  content: '❝';
  position: absolute;
  top: 10px; left: 50%; transform: translateX(-50%);
  font-size: 4rem;
  color: rgba(0,240,255,0.1);
  font-family: serif;
}
.quote-block p {
  font-family: 'Rajdhani', sans-serif;
  font-size: 2rem;
  font-weight: 300;
  letter-spacing: 0.1em;
  color: #fff;
  text-shadow: 0 0 20px rgba(0,240,255,0.3);
  line-height: 1.5;
}
.quote-block .author {
  margin-top: 15px;
  font-family: 'Orbitron', sans-serif;
  color: var(--purple);
  letter-spacing: 0.2em;
  font-size: 1rem;
}

/* Wave Footer Image */
.wave-footer img {
  width: 100%;
  max-width: 100%;
  display: block;
  border-radius: 0 0 0 0;
  filter: contrast(1.2) brightness(0.9);
  border-top: 2px solid rgba(0,240,255,0.2);
}

/* Canvas Particle Overlay */
#particle-canvas {
  position: fixed;
  top: 0; left: 0;
  width: 100%; height: 100%;
  z-index: 9999;
  pointer-events: none;
  mix-blend-mode: screen;
}

/* Responsive */
@media (max-width: 768px) {
  .glitch-wrapper h1 { font-size: 3rem; }
  .subtitle { font-size: 1rem; }
  .section-card { padding: 28px 16px; }
  .stats-wrap img { max-width: 45%; }
}
</style>
</head>
<body>

<div class="grid-bg"></div>
<div class="orb cyan"></div>
<div class="orb purple"></div>
<div class="orb pink"></div>

canvas id="particle-canvas"></canvas>

<div class="container">

  <!-- GLITCH HEADER -->
  <div class="glitch-wrapper">
    <h1>RA-STUDIOS</h1>
    <div class="subtitle">CREATIVE STUDIO &bull; DEVELOPER &bull; OPEN SOURCE ARCHITECT</div>
  </div>

  <div class="divider"></div>

  <!-- TYPING SVG -->
  <div class="typing-area" align="center">
    <img src="https://readme-typing-svg.demolab.com?font=Orbitron&weight=900&size=28&pause=800&color=00F0FF&center=true&vCenter=true&width=900&lines=Hey+there%2C+I'm+Ra-Studios!+%F0%9F%91%8B;Creative+Studio+%26+Digital+Architect+%F0%9F%9A%80;Open+Source+Contributor+%F0%9F%8C%9F;Building+Modern+Experiences+%E2%9C%A8;Welcome+to+the+Ultimate+Dimension+%F0%9F%8C%8C" alt="Ultimate Typing SVG" />
    <br>
    <div class="counter-wrap">
      <span>👁</span>
      <img src="https://komarev.com/ghpvc/?username=Ra-Studios&label=PROFILE+VISITORS&color=B829F7&style=for-the-badge&logo=github" alt="Visitors" />
    </div>
  </div>

  <div class="pill-row">
    <span class="pill cyan">● LIVE</span>
    <span class="pill purple">◉ BUILDING</span>
    <span class="pill slate">◆ CYBERPUNK</span>
  </div>

  <div class="skill-icons">
    <img src="https://skillicons.dev/icons?i=react,nextjs,typescript,tailwind,python,figma" alt="Tech Stack" title="Tech Stack" />
  </div>

  <!-- ABOUT -->
  <section class="section-card">
    <h2 class="section-title">ABOUT DIMENSION</h2>
    <div class="about-grid">
      <div class="about-card">
        <h3>🔭 CURRENT WORK</h3>
        <p>Building modern web experiences, interactive UI libraries, and open-source font asset collections that redefine digital typography.</p>
      </div>
      <div class="about-card">
        <h3>🌱 CURRENT LEARNING</h3>
        <p>Deep-diving into creative coding (Three.js / WebGL), generative design algorithms, and scalable design-system architecture.</p>
      </div>
      <div class="about-card">
        <h3>💬 ASK ME ABOUT</h3>
        <p>Full-stack development, UI/UX design, typography & font assets (<code>Font_Styles</code>), and anything neon-cyberpunk themed.</p>
      </div>
      <div class="about-card">
        <h3>⚡ FUN FACT</h3>
        <p>I collect fonts like they're trading cards — over 1,097 folders of pure typographic gold in my archive.</p>
      </div>
    </div>
  </section>

  <!-- TECH STACK -->
  <section class="section-card">
    <h2 class="section-title">TECH STACK & SKILLS</h2>

    <div class="category">
      <h4>💻 LANGUAGES</h4>
      <div class="badge-grid">
        <img src="https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black&style=for-the-badge" alt="JS">
        <img src="https://img.shields.io/badge/TypeScript-3178C6?logo=typescript&logoColor=white&style=for-the-badge" alt="TS">
        <img src="https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white&style=for-the-badge" alt="Python">
        <img src="https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white&style=for-the-badge" alt="HTML">
        <img src="https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white&style=for-the-badge" alt="CSS">
      </div>
    </div>

    <div class="category">
      <h4>🌐 FRONTEND</h4>
      <div class="badge-grid">
        <img src="https://img.shields.io/badge/React-61DAFB?logo=react&logoColor=black&style=for-the-badge" alt="React">
        <img src="https://img.shields.io/badge/Next.js-000000?logo=nextdotjs&logoColor=white&style=for-the-badge" alt="Next">
        <img src="https://img.shields.io/badge/Vue.js-4FC08D?logo=vue.js&logoColor=white&style=for-the-badge" alt="Vue">
        <img src="https://img.shields.io/badge/Svelte-FF3E00?logo=svelte&logoColor=white&style=for-the-badge" alt="Svelte">
        <img src="https://img.shields.io/badge/Tailwind-06B6D4?logo=tailwindcss&logoColor=white&style=for-the-badge" alt="Tailwind">
      </div>
    </div>

    <div class="category">
      <h4>⚙️ BACKEND & RUNTIME</h4>
      <div class="badge-grid">
        <img src="https://img.shields.io/badge/Node.js-339933?logo=nodedotjs&logoColor=white&style=for-the-badge" alt="Node">
        <img src="https://img.shields.io/badge/Express-000000?logo=express&logoColor=white&style=for-the-badge" alt="Express">
        <img src="https://img.shields.io/badge/Django-092E20?logo=django&logoColor=white&style=for-the-badge" alt="Django">
        <img src="https://img.shields.io/badge/PostgreSQL-4169E1?logo=postgresql&logoColor=white&style=for-the-badge" alt="Postgres">
        <img src="https://img.shields.io/badge/MongoDB-47A248?logo=mongodb&logoColor=white&style=for-the-badge" alt="Mongo">
      </div>
    </div>

    <div class="category">
      <h4>☁️ TOOLS & CLOUD</h4>
      <div class="badge-grid">
        <img src="https://img.shields.io/badge/Git-F05032?logo=git&logoColor=white&style=for-the-badge" alt="Git">
        <img src="https://img.shields.io/badge/GitHub-181717?logo=github&logoColor=white&style=for-the-badge" alt="GitHub">
        <img src="https://img.shields.io/badge/Docker-2496ED?logo=docker&logoColor=white&style=for-the-badge" alt="Docker">
        <img src="https://img.shields.io/badge/AWS-232F3E?logo=amazonaws&logoColor=white&style=for-the-badge" alt="AWS">
        <img src="https://img.shields.io/badge/Vercel-000000?logo=vercel&logoColor=white&style=for-the-badge" alt="Vercel">
      </div>
    </div>

    <div class="category">
      <h4>🎨 DESIGN</h4>
      <div class="badge-grid">
        <img src="https://img.shields.io/badge/Figma-F24E1E?logo=figma&logoColor=white&style=for-the-badge" alt="Figma">
        <img src="https://img.shields.io/badge/Photoshop-31A8FF?logo=adobephotoshop&logoColor=white&style=for-the-badge" alt="Photoshop">
        <img src="https://img.shields.io/badge/Illustrator-FF9A00?logo=adobeillustrator&logoColor=white&style=for-the-badge" alt="Illustrator">
        <img src="https://img.shields.io/badge/Blender-F5792A?logo=blender&logoColor=white&style=for-the-badge" alt="Blender">
      </div>
    </div>
  </section>

  <!-- DYNAMIC STATS -->
  <section class="section-card">
    <h2 class="section-title">DYNAMIC STATS</h2>
    <div class="stats-wrap">
      <a href="https://github.com/Ra-Studios"><img src="https://github-readme-stats.vercel.app/api?username=Ra-Studios&show_icons=true&theme=tokyonight&hide_border=true&title_color=00f0ff&icon_color=b829f7&text_color=eaeaea" alt="GitHub Stats" /></a>
      <a href="https://github.com/Ra-Studios"><img src="https://streak-stats.demolab.com/?user=Ra-Studios&theme=tokyonight&hide_border=true&border=00f0ff&background=0a0e1a" alt="GitHub Streak" /></a>
    </div>
    <div align="center" style="margin-top: 30px;">
      <a href="https://github.com/Ra-Studios"><img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Ra-Studios&layout=compact&theme=tokyonight&hide_border=true&border_radius=12&text_color=eaeaea&title_color=00f0ff" alt="Top Languages" /></a>
    </div>
  </section>

  <!-- FEATURED ASSET -->
  <section class="featured-card">
    <a href="https://github.com/Ra-Studios/Font_Styles" style="text-decoration: none; color: inherit;">
      <img src="https://github-readme-stats.vercel.app/api/pin/?username=Ra-Studios&repo=Font_Styles&theme=tokyonight&hide_border=true&title_color=00f0ff&icon_color=b829f7" alt="Font_Styles" />
      <h3>🖋 FONT_STYLES — A CURATED COLLECTION</h3>
      <p>Over <strong style="color: var(--cyan);">1,097 font folders</strong>, meticulously organized into a 3-column collapsible Markdown table with letter headers, sorted A-Z from a local directory. A living archive for designers, developers, and anyone obsessed with beautiful letterforms.</p>
    </a>
  </section>

  <!-- SOCIALS -->
  <section class="section-card" style="text-align: center;">
    <h2 class="section-title">CONNECT ACROSS DIMENSIONS</h2>
    <div class="social-row">
      <a href="https://github.com/Ra-Studios" title="GitHub"><img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=00f0ff" alt="GitHub" /></a>
      <a href="https://twitter.com/Ra_Studios" title="Twitter / X"><img src="https://img.shields.io/badge/X-1DA1F2?style=for-the-badge&logo=x&logoColor=white" alt="X" /></a>
      <a href="https://discord.com/users/ra_studios" title="Discord"><img src="https://img.shields.io/badge/Discord-5865F2?style=for-the-badge&logo=discord&logoColor=white" alt="Discord" /></a>
      <a href="https://ra-studios.dev" title="Portfolio"><img src="https://img.shields.io/badge/Portfolio-B829F7?style=for-the-badge&logo=firefox&logoColor=white" alt="Portfolio" /></a>
      <a href="https://linkedin.com/in/ra-studios" title="LinkedIn"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" /></a>
    </div>
  </section>

  <!-- FOOTER -->
  <div class="quote-block">
    <p>"Good design is obvious.<br>Great design is invisible."</p>
    <div class="author">— RA-STUDIOS / CREATIVE STUDIO</div>
  </div>

  <div class="wave-footer">
    <img src="https://capsule-render.vercel.app/api?type=waving&color=0d1117&height=150&section=footer&text=%E2%9C%A8+Thanks+for+visiting+my+universe+%E2%9C%A8&fontSize=30&fontColor=b829f7&animation=fadeIn" alt="Footer Wave" />
  </div>

</div>

<script>
// ULTIMATE CANVAS PARTICLE SYSTEM
const canvas = document.getElementById('particle-canvas');
const ctx = canvas.getContext('2d');
let particles = [];

function resize() {
  canvas.width = window.innerWidth;
  canvas.height = window.innerHeight;
}
window.addEventListener('resize', resize);
resize();

class Particle {
  constructor() {
    this.x = Math.random() * canvas.width;
    this.y = Math.random() * canvas.height;
    this.vx = (Math.random() - 0.5) * 1.5;
    this.vy = (Math.random() - 0.5) * 1.5;
    this.size = Math.random() * 3 + 1;
    this.color = Math.random() > 0.5 ? 'rgba(0,240,255,0.6)' : 'rgba(184,41,247,0.6)';
  }
  update() {
    this.x += this.vx;
    this.y += this.vy;
    if (this.x < 0 || this.x > canvas.width) this.vx *= -1;
    if (this.y < 0 || this.y > canvas.height) this.vy *= -1;
  }
  draw() {
    ctx.fillStyle = this.color;
    ctx.beginPath();
    ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2);
    ctx.fill();
  }
}

for (let i = 0; i < 120; i++) particles.push(new Particle());

function animate() {
  ctx.clearRect(0, 0, canvas.width, canvas.height);
  particles.forEach((p, i) => {
    p.update();
    p.draw();
    for (let j = i + 1; j < particles.length; j++) {
      const dx = p.x - particles[j].x;
      const dy = p.y - particles[j].y;
      const dist = Math.sqrt(dx*dx + dy*dy);
      if (dist < 100) {
        ctx.strokeStyle = `rgba(0,240,255,${0.15 * (1 - dist/100)})`;
        ctx.lineWidth = 0.5;
        ctx.beginPath();
        ctx.moveTo(p.x, p.y);
        ctx.lineTo(particles[j].x, particles[j].y);
        ctx.stroke();
      }
    }
  });
  requestAnimationFrame(animate);
}
animate();
</script>

</body>
</html>
