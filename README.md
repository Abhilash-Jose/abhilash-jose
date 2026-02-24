<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Abhilash Jose — Data Scientist</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;500;600;700;800&family=DM+Mono:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --blue: #0073e6;
    --blue-light: #3399ff;
    --blue-glow: rgba(0,115,230,0.3);
    --dark: #060a12;
    --card: #0d1525;
    --card2: #111c30;
    --border: rgba(0,115,230,0.2);
    --text: #cdd6f0;
    --muted: #5a6a8a;
    --white: #f0f6ff;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--dark);
    color: var(--text);
    font-family: 'DM Mono', monospace;
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* Background grid */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(0,115,230,0.04) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,115,230,0.04) 1px, transparent 1px);
    background-size: 60px 60px;
    pointer-events: none;
    z-index: 0;
  }

  /* Radial glow */
  body::after {
    content: '';
    position: fixed;
    top: -200px;
    left: 50%;
    transform: translateX(-50%);
    width: 800px;
    height: 600px;
    background: radial-gradient(ellipse, rgba(0,115,230,0.12) 0%, transparent 70%);
    pointer-events: none;
    z-index: 0;
  }

  .container {
    max-width: 880px;
    margin: 0 auto;
    padding: 60px 24px;
    position: relative;
    z-index: 1;
  }

  /* HERO */
  .hero {
    text-align: center;
    padding: 80px 0 60px;
    position: relative;
  }

  .greeting {
    font-size: 12px;
    letter-spacing: 4px;
    text-transform: uppercase;
    color: var(--blue-light);
    margin-bottom: 24px;
    opacity: 0;
    animation: fadeUp 0.6s ease forwards;
  }

  .hero h1 {
    font-family: 'Syne', sans-serif;
    font-size: clamp(48px, 8vw, 88px);
    font-weight: 800;
    line-height: 0.95;
    letter-spacing: -3px;
    color: var(--white);
    margin-bottom: 8px;
    opacity: 0;
    animation: fadeUp 0.6s 0.1s ease forwards;
  }

  .hero h1 span {
    display: block;
    background: linear-gradient(135deg, var(--blue) 0%, var(--blue-light) 50%, #66c2ff 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .hero-subtitle {
    font-size: 13px;
    color: var(--muted);
    margin-top: 24px;
    letter-spacing: 2px;
    text-transform: uppercase;
    opacity: 0;
    animation: fadeUp 0.6s 0.2s ease forwards;
  }

  .hero-desc {
    max-width: 540px;
    margin: 32px auto 0;
    font-size: 14px;
    line-height: 1.9;
    color: var(--text);
    font-family: 'DM Mono', monospace;
    font-weight: 300;
    opacity: 0;
    animation: fadeUp 0.6s 0.3s ease forwards;
  }

  .hero-desc em {
    color: var(--blue-light);
    font-style: normal;
  }

  /* STATUS BADGE */
  .status {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    background: rgba(0,115,230,0.08);
    border: 1px solid var(--border);
    border-radius: 100px;
    padding: 8px 18px;
    font-size: 11px;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--blue-light);
    margin-bottom: 32px;
    opacity: 0;
    animation: fadeUp 0.6s 0.15s ease forwards;
  }

  .status-dot {
    width: 7px;
    height: 7px;
    background: #00e676;
    border-radius: 50%;
    animation: pulse 2s ease infinite;
  }

  /* DIVIDER */
  .section-label {
    display: flex;
    align-items: center;
    gap: 16px;
    margin: 64px 0 32px;
    opacity: 0;
    animation: fadeUp 0.5s ease forwards;
  }

  .section-label span {
    font-size: 10px;
    letter-spacing: 4px;
    text-transform: uppercase;
    color: var(--blue);
    white-space: nowrap;
  }

  .section-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: linear-gradient(90deg, var(--blue), transparent);
    opacity: 0.4;
  }

  /* TECH STACK GRID */
  .tech-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    gap: 2px;
  }

  .tech-category {
    background: var(--card);
    border: 1px solid var(--border);
    padding: 24px;
    position: relative;
    overflow: hidden;
    transition: background 0.3s;
    opacity: 0;
    animation: fadeUp 0.5s ease forwards;
  }

  .tech-category:hover {
    background: var(--card2);
  }

  .tech-category::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--blue), transparent);
    opacity: 0;
    transition: opacity 0.3s;
  }

  .tech-category:hover::before { opacity: 1; }

  .tech-icon {
    font-size: 22px;
    margin-bottom: 12px;
  }

  .tech-cat-name {
    font-family: 'Syne', sans-serif;
    font-size: 12px;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: var(--blue-light);
    margin-bottom: 12px;
  }

  .tech-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
  }

  .tag {
    background: rgba(0,115,230,0.08);
    border: 1px solid rgba(0,115,230,0.15);
    border-radius: 4px;
    padding: 3px 8px;
    font-size: 11px;
    color: var(--text);
    transition: all 0.2s;
  }

  .tag:hover {
    background: rgba(0,115,230,0.2);
    border-color: var(--blue);
    color: var(--white);
  }

  /* FEATURED PROJECT */
  .project-card {
    display: grid;
    grid-template-columns: 1fr 1.4fr;
    gap: 0;
    border: 1px solid var(--border);
    overflow: hidden;
    background: var(--card);
    transition: border-color 0.3s;
    opacity: 0;
    animation: fadeUp 0.6s ease forwards;
  }

  .project-card:hover {
    border-color: rgba(0,115,230,0.5);
  }

  .project-image {
    position: relative;
    overflow: hidden;
    background: var(--card2);
    min-height: 280px;
  }

  .project-image img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    display: block;
    transition: transform 0.6s ease;
    filter: brightness(0.9);
  }

  .project-card:hover .project-image img {
    transform: scale(1.04);
  }

  .project-image-overlay {
    position: absolute;
    inset: 0;
    background: linear-gradient(135deg, rgba(0,115,230,0.15) 0%, transparent 60%);
  }

  .project-content {
    padding: 40px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    border-left: 1px solid var(--border);
  }

  .project-meta {
    font-size: 10px;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 12px;
  }

  .project-title {
    font-family: 'Syne', sans-serif;
    font-size: 26px;
    font-weight: 700;
    color: var(--white);
    line-height: 1.2;
    margin-bottom: 16px;
  }

  .project-desc {
    font-size: 13px;
    line-height: 1.8;
    color: var(--text);
    font-weight: 300;
    flex: 1;
    margin-bottom: 28px;
  }

  .project-link {
    display: inline-flex;
    align-items: center;
    gap: 10px;
    background: var(--blue);
    color: #fff;
    text-decoration: none;
    font-size: 11px;
    letter-spacing: 3px;
    text-transform: uppercase;
    padding: 14px 24px;
    font-family: 'DM Mono', monospace;
    transition: all 0.2s;
    align-self: flex-start;
  }

  .project-link:hover {
    background: var(--blue-light);
    gap: 16px;
  }

  .project-link svg {
    width: 14px;
    height: 14px;
    transition: transform 0.2s;
  }

  .project-link:hover svg { transform: translateX(4px); }

  /* STATS */
  .stats-row {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 2px;
    margin-top: 2px;
  }

  .stat-card {
    background: var(--card);
    border: 1px solid var(--border);
    padding: 32px 24px;
    text-align: center;
    transition: background 0.3s;
    opacity: 0;
    animation: fadeUp 0.5s ease forwards;
  }

  .stat-card:hover { background: var(--card2); }

  .stat-num {
    font-family: 'Syne', sans-serif;
    font-size: 40px;
    font-weight: 800;
    background: linear-gradient(135deg, var(--blue), var(--blue-light));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    line-height: 1;
    margin-bottom: 8px;
  }

  .stat-label {
    font-size: 10px;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: var(--muted);
  }

  /* CONNECT */
  .connect-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(160px, 1fr));
    gap: 2px;
  }

  .connect-card {
    background: var(--card);
    border: 1px solid var(--border);
    padding: 24px;
    text-decoration: none;
    color: var(--text);
    display: flex;
    align-items: center;
    gap: 14px;
    font-size: 12px;
    letter-spacing: 2px;
    text-transform: uppercase;
    transition: all 0.2s;
    opacity: 0;
    animation: fadeUp 0.5s ease forwards;
  }

  .connect-card:hover {
    background: rgba(0,115,230,0.12);
    border-color: var(--blue);
    color: var(--white);
  }

  .connect-card svg {
    width: 20px;
    height: 20px;
    opacity: 0.7;
    flex-shrink: 0;
  }

  .connect-card:hover svg { opacity: 1; }

  /* FOOTER */
  .footer {
    margin-top: 80px;
    padding-top: 32px;
    border-top: 1px solid var(--border);
    display: flex;
    justify-content: space-between;
    align-items: center;
    font-size: 11px;
    color: var(--muted);
    letter-spacing: 2px;
    opacity: 0;
    animation: fadeUp 0.5s ease forwards;
  }

  .footer-dot {
    width: 6px;
    height: 6px;
    background: var(--blue);
    border-radius: 50%;
  }

  /* ANIMATIONS */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
  }

  @keyframes pulse {
    0%, 100% { box-shadow: 0 0 0 0 rgba(0,230,118,0.4); }
    50% { box-shadow: 0 0 0 6px rgba(0,230,118,0); }
  }

  /* Stagger delays for tech cards */
  .tech-category:nth-child(1) { animation-delay: 0.0s; }
  .tech-category:nth-child(2) { animation-delay: 0.05s; }
  .tech-category:nth-child(3) { animation-delay: 0.1s; }
  .tech-category:nth-child(4) { animation-delay: 0.15s; }

  .stat-card:nth-child(1) { animation-delay: 0.0s; }
  .stat-card:nth-child(2) { animation-delay: 0.08s; }
  .stat-card:nth-child(3) { animation-delay: 0.16s; }

  .connect-card:nth-child(1) { animation-delay: 0.0s; }
  .connect-card:nth-child(2) { animation-delay: 0.05s; }
  .connect-card:nth-child(3) { animation-delay: 0.1s; }

  /* Scrolled sections */
  .reveal {
    opacity: 0;
    transform: translateY(24px);
    transition: opacity 0.6s ease, transform 0.6s ease;
  }
  .reveal.visible { opacity: 1; transform: none; }

  @media (max-width: 640px) {
    .project-card { grid-template-columns: 1fr; }
    .project-image { min-height: 200px; }
    .project-content { border-left: none; border-top: 1px solid var(--border); }
    .stats-row { grid-template-columns: 1fr 1fr; }
    .footer { flex-direction: column; gap: 12px; text-align: center; }
  }
</style>
</head>
<body>

<div class="container">

  <!-- HERO -->
  <header class="hero">
    <div class="greeting">👋 Hey, welcome to my profile</div>
    <h1>Abhilash<span>Jose</span></h1>
    <div class="status">
      <span class="status-dot"></span>
      Available for collaboration
    </div>
    <div class="hero-subtitle">Data Scientist &nbsp;·&nbsp; Analyst &nbsp;·&nbsp; Visualizer</div>
    <p class="hero-desc">
      Passionate about <em>exploring</em>, <em>learning</em>, and sharing knowledge in data science.
      I dive deep into problems, uncover insights, and challenge myself to grow.
      Teaching and relearning are just as important as learning—because the journey never truly ends.
    </p>
  </header>

  <!-- TECH STACK -->
  <div class="section-label reveal">
    <span>Technical Arsenal</span>
  </div>

  <div class="tech-grid">
    <div class="tech-category">
      <div class="tech-icon">📊</div>
      <div class="tech-cat-name">Data Analysis</div>
      <div class="tech-tags">
        <span class="tag">Python</span>
        <span class="tag">Pandas</span>
        <span class="tag">NumPy</span>
        <span class="tag">Excel</span>
      </div>
    </div>
    <div class="tech-category">
      <div class="tech-icon">📈</div>
      <div class="tech-cat-name">Visualization</div>
      <div class="tech-tags">
        <span class="tag">Power BI</span>
        <span class="tag">Matplotlib</span>
        <span class="tag">Seaborn</span>
        <span class="tag">Tableau</span>
      </div>
    </div>
    <div class="tech-category">
      <div class="tech-icon">🗄️</div>
      <div class="tech-cat-name">Databases</div>
      <div class="tech-tags">
        <span class="tag">SQL</span>
        <span class="tag">MySQL</span>
        <span class="tag">PostgreSQL</span>
      </div>
    </div>
    <div class="tech-category">
      <div class="tech-icon">🤖</div>
      <div class="tech-cat-name">Machine Learning</div>
      <div class="tech-tags">
        <span class="tag">Scikit-learn</span>
        <span class="tag">TensorFlow</span>
        <span class="tag">Keras</span>
        <span class="tag">NLP</span>
      </div>
    </div>
  </div>

  <!-- STATS -->
  <div class="stats-row reveal">
    <div class="stat-card">
      <div class="stat-num">3+</div>
      <div class="stat-label">Years Learning</div>
    </div>
    <div class="stat-card">
      <div class="stat-num">10+</div>
      <div class="stat-label">Projects Built</div>
    </div>
    <div class="stat-card">
      <div class="stat-num">∞</div>
      <div class="stat-label">Curiosity Level</div>
    </div>
  </div>

  <!-- CONNECT -->
  <div class="section-label reveal">
    <span>Let's Connect</span>
  </div>

  <div class="connect-grid">
    <a href="https://github.com/Abhilash-Jose" target="_blank" class="connect-card">
      <svg viewBox="0 0 24 24" fill="currentColor">
        <path d="M12 0C5.37 0 0 5.37 0 12c0 5.31 3.435 9.795 8.205 11.385.6.105.825-.255.825-.57 0-.285-.015-1.23-.015-2.235-3.015.555-3.795-.735-4.035-1.41-.135-.345-.72-1.41-1.23-1.695-.42-.225-1.02-.78-.015-.795.945-.015 1.62.87 1.845 1.23 1.08 1.815 2.805 1.305 3.495.99.105-.78.42-1.305.765-1.605-2.67-.3-5.46-1.335-5.46-5.925 0-1.305.465-2.385 1.23-3.225-.12-.3-.54-1.53.12-3.18 0 0 1.005-.315 3.3 1.23.96-.27 1.98-.405 3-.405s2.04.135 3 .405c2.295-1.56 3.3-1.23 3.3-1.23.66 1.65.24 2.88.12 3.18.765.84 1.23 1.905 1.23 3.225 0 4.605-2.805 5.625-5.475 5.925.435.375.81 1.095.81 2.22 0 1.605-.015 2.895-.015 3.3 0 .315.225.69.825.57A12.02 12.02 0 0 0 24 12c0-6.63-5.37-12-12-12z"/>
      </svg>
      GitHub
    </a>
    <a href="https://www.linkedin.com/in/abhilash-jose" target="_blank" class="connect-card">
      <svg viewBox="0 0 24 24" fill="currentColor">
        <path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 0 1-2.063-2.065 2.064 2.064 0 1 1 2.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/>
      </svg>
      LinkedIn
    </a>
    <a href="https://mavenanalytics.io/profile/Abhilash-Jose" target="_blank" class="connect-card">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
        <circle cx="12" cy="12" r="10"/>
        <path d="M2 12h20M12 2a15.3 15.3 0 0 1 4 10 15.3 15.3 0 0 1-4 10 15.3 15.3 0 0 1-4-10 15.3 15.3 0 0 1 4-10z"/>
      </svg>
      Maven
    </a>
  </div>

  <!-- FOOTER -->
  <footer class="footer reveal">
    <span>abhilash-jose &nbsp;·&nbsp; data + curiosity</span>
    <span class="footer-dot"></span>
    <span>Built with ♥ and Python</span>
  </footer>

</div>

<script>
  // Intersection observer for reveal on scroll
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        e.target.classList.add('visible');
        // Also animate children if they have animation classes
      }
    });
  }, { threshold: 0.1 });

  document.querySelectorAll('.reveal').forEach(el => observer.observe(el));

  // Animated number counter
  const nums = document.querySelectorAll('.stat-num');
  nums.forEach(n => {
    const target = n.textContent;
    if (target === '∞') return;
    const num = parseInt(target);
    if (isNaN(num)) return;
    let start = 0;
    const step = () => {
      start += Math.ceil(num / 20);
      if (start >= num) { n.textContent = target; return; }
      n.textContent = start + '+';
      requestAnimationFrame(step);
    };
    setTimeout(step, 400);
  });
</script>

</body>
</html>
