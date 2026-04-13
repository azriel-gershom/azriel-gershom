
<style>
  :root { --c1: #00ff9f; --c2: #00cfff; --c3: #7b2fff; --dim: #0a0a0a; }
  * { box-sizing: border-box; margin: 0; padding: 0; }
  body { background: transparent; }
  .wrap { font-family: var(--font-mono, monospace); color: #c9d1d9; background: #0d1117; border-radius: 12px; overflow: hidden; padding: 0 0 2rem; border: 1px solid #30363d; }
  .banner { background: linear-gradient(135deg, #0d1117 0%, #161b22 50%, #0d1117 100%); border-bottom: 1px solid #21262d; padding: 2.5rem 2rem 2rem; position: relative; overflow: hidden; }
  .banner::before { content: ''; position: absolute; inset: 0; background: repeating-linear-gradient(0deg, transparent, transparent 28px, rgba(0,255,159,0.03) 28px, rgba(0,255,159,0.03) 29px), repeating-linear-gradient(90deg, transparent, transparent 28px, rgba(0,255,159,0.03) 28px, rgba(0,255,159,0.03) 29px); }
  .typing-row { display: flex; align-items: center; gap: 8px; margin-bottom: 1.2rem; }
  .prompt { color: var(--c1); font-size: 13px; }
  .typing { color: #fff; font-size: 22px; font-weight: 500; letter-spacing: 1px; }
  .cursor { display: inline-block; width: 2px; height: 22px; background: var(--c1); animation: blink 1s step-end infinite; vertical-align: middle; margin-left: 2px; }
  @keyframes blink { 0%,100%{opacity:1} 50%{opacity:0} }
  .subtitle { color: #8b949e; font-size: 13px; margin-bottom: 1.5rem; font-family: var(--font-sans); }
  .subtitle span { color: var(--c2); }
  .stat-row { display: flex; gap: 10px; flex-wrap: wrap; }
  .badge { font-size: 11px; padding: 3px 10px; border-radius: 20px; border: 1px solid; font-family: var(--font-mono); letter-spacing: 0.5px; }
  .badge-green { border-color: rgba(0,255,159,0.4); color: var(--c1); background: rgba(0,255,159,0.07); }
  .badge-blue { border-color: rgba(0,207,255,0.4); color: var(--c2); background: rgba(0,207,255,0.07); }
  .badge-purple { border-color: rgba(123,47,255,0.4); color: #a78bfa; background: rgba(123,47,255,0.07); }
  .section { padding: 1.5rem 2rem 0; }
  .sec-title { font-size: 11px; text-transform: uppercase; letter-spacing: 2px; color: #484f58; margin-bottom: 1rem; font-family: var(--font-mono); display: flex; align-items: center; gap: 8px; }
  .sec-title::after { content: ''; flex: 1; height: 1px; background: #21262d; }
  .about-box { background: #161b22; border: 1px solid #21262d; border-radius: 8px; padding: 1rem 1.25rem; font-size: 13px; line-height: 1.8; color: #8b949e; font-family: var(--font-sans); }
  .about-box strong { color: var(--c1); font-weight: 500; }
  .skills-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(130px, 1fr)); gap: 8px; }
  .skill-card { background: #161b22; border: 1px solid #21262d; border-radius: 8px; padding: 0.7rem 1rem; font-size: 12px; display: flex; flex-direction: column; gap: 4px; transition: border-color 0.2s; }
  .skill-card:hover { border-color: #30363d; }
  .skill-icon { font-size: 16px; }
  .skill-name { color: #e6edf3; font-weight: 500; }
  .skill-sub { color: #484f58; font-size: 10px; letter-spacing: 0.5px; text-transform: uppercase; }
  .stats-row { display: grid; grid-template-columns: repeat(3, 1fr); gap: 10px; }
  .stat-card { background: #161b22; border: 1px solid #21262d; border-radius: 8px; padding: 1rem; text-align: center; }
  .stat-num { font-size: 22px; font-weight: 500; font-family: var(--font-mono); }
  .stat-num.green { color: var(--c1); }
  .stat-num.blue { color: var(--c2); }
  .stat-num.purple { color: #a78bfa; }
  .stat-label { font-size: 10px; color: #484f58; text-transform: uppercase; letter-spacing: 1px; margin-top: 2px; }
  .project-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; }
  .proj-card { background: #161b22; border: 1px solid #21262d; border-radius: 8px; padding: 1rem; cursor: pointer; transition: border-color 0.2s; }
  .proj-card:hover { border-color: rgba(0,255,159,0.3); }
  .proj-title { color: var(--c2); font-size: 13px; font-weight: 500; margin-bottom: 4px; }
  .proj-desc { color: #8b949e; font-size: 11px; line-height: 1.5; }
  .proj-tags { display: flex; gap: 5px; margin-top: 8px; flex-wrap: wrap; }
  .proj-tag { font-size: 10px; color: #484f58; border: 1px solid #21262d; border-radius: 4px; padding: 1px 6px; }
  .quote-box { background: #161b22; border-left: 3px solid var(--c3); border-radius: 0 8px 8px 0; padding: 1rem 1.25rem; font-size: 13px; color: #8b949e; font-style: italic; font-family: var(--font-sans); line-height: 1.7; }
  .quote-box span { color: #a78bfa; }
  .connect-row { display: flex; gap: 8px; flex-wrap: wrap; }
  .connect-btn { font-size: 12px; padding: 6px 14px; border-radius: 6px; border: 1px solid #30363d; color: #8b949e; background: #161b22; cursor: pointer; font-family: var(--font-mono); transition: all 0.2s; text-decoration: none; display: inline-block; }
  .connect-btn:hover { border-color: rgba(0,255,159,0.5); color: var(--c1); }
  .scanner { position: absolute; top: 0; left: -100%; width: 60%; height: 100%; background: linear-gradient(90deg, transparent, rgba(0,255,159,0.04), transparent); animation: scan 4s linear infinite; }
  @keyframes scan { to { left: 150%; } }
  .avatar-area { display: flex; align-items: flex-start; gap: 1.5rem; position: relative; z-index: 1; }
  .avatar { width: 72px; height: 72px; border-radius: 50%; background: linear-gradient(135deg, #1a1a2e, #16213e); border: 2px solid rgba(0,255,159,0.3); display: flex; align-items: center; justify-content: center; font-size: 28px; flex-shrink: 0; position: relative; }
  .avatar::after { content: ''; position: absolute; inset: -4px; border-radius: 50%; border: 1px solid rgba(0,255,159,0.15); animation: pulse-ring 2s ease-out infinite; }
  @keyframes pulse-ring { 0%{transform:scale(1);opacity:0.5} 100%{transform:scale(1.2);opacity:0} }
  .avatar-info { flex: 1; }
  .username { font-size: 11px; color: #484f58; margin-bottom: 4px; font-family: var(--font-mono); }
</style>

<div class="wrap">
  <div class="banner">
    <div class="scanner"></div>
    <div class="avatar-area">
      <div class="avatar">⚡</div>
      <div class="avatar-info">
        <div class="username">// github.com/azriel-gershom</div>
        <div class="typing-row">
          <span class="prompt">~/</span>
          <span class="typing">Azriel Gershom Raj</span>
          <span class="cursor"></span>
        </div>
        <div class="subtitle">
          <span>AI &amp; ML Engineer</span> · Cyberpunk Coder · Builder of the Future
        </div>
        <div class="stat-row">
          <span class="badge badge-green">⬡ AI &amp; Machine Learning</span>
          <span class="badge badge-blue">⬡ Full Stack Dev</span>
          <span class="badge badge-purple">⬡ Cybersecurity</span>
          <span class="badge badge-green">⬡ IoT Systems</span>
        </div>
      </div>
    </div>
  </div>

  <div class="section">
    <div class="sec-title">whoami</div>
    <div class="about-box">
      <strong>&gt; Azriel Gershom Raj</strong> — CSE (AI &amp; ML) student at <strong>Karunya Institute of Technology &amp; Sciences</strong>.<br><br>
      I don't just write code. I <strong>architect intelligence</strong>. From training neural nets at 2am to deploying full-stack apps before breakfast — I operate at the intersection of creativity and raw technical precision.<br><br>
      Armed with <strong>Python · Java · JavaScript</strong> and an obsession with making machines think, I'm building systems that matter.
    </div>
  </div>

  <div class="section">
    <div class="sec-title">tech arsenal</div>
    <div class="skills-grid">
      <div class="skill-card"><span class="skill-icon">🧠</span><span class="skill-name">AI / ML</span><span class="skill-sub">Core Domain</span></div>
      <div class="skill-card"><span class="skill-icon">🐍</span><span class="skill-name">Python</span><span class="skill-sub">Primary Lang</span></div>
      <div class="skill-card"><span class="skill-icon">☕</span><span class="skill-name">Java</span><span class="skill-sub">OOP & Systems</span></div>
      <div class="skill-card"><span class="skill-icon">🌐</span><span class="skill-name">JavaScript</span><span class="skill-sub">Full Stack</span></div>
      <div class="skill-card"><span class="skill-icon">📡</span><span class="skill-name">IoT</span><span class="skill-sub">Systems Dev</span></div>
      <div class="skill-card"><span class="skill-icon">🔐</span><span class="skill-name">CyberSec</span><span class="skill-sub">Fundamentals</span></div>
      <div class="skill-card"><span class="skill-icon">🔀</span><span class="skill-name">Git / GitHub</span><span class="skill-sub">Version Control</span></div>
      <div class="skill-card"><span class="skill-icon">⚙️</span><span class="skill-name">Full Stack</span><span class="skill-sub">Web Dev</span></div>
    </div>
  </div>

  <div class="section">
    <div class="sec-title">github stats</div>
    <div class="stats-row">
      <div class="stat-card"><div class="stat-num green">∞</div><div class="stat-label">Lines Shipped</div></div>
      <div class="stat-card"><div class="stat-num blue">24/7</div><div class="stat-label">Online Status</div></div>
      <div class="stat-card"><div class="stat-num purple">100%</div><div class="stat-label">Commitment</div></div>
    </div>
  </div>

  <div class="section">
    <div class="sec-title">featured projects</div>
    <div class="project-grid">
      <div class="proj-card">
        <div class="proj-title">◈ AI Core</div>
        <div class="proj-desc">Machine learning pipeline with real-world impact. Models trained, deployed, dominating.</div>
        <div class="proj-tags"><span class="proj-tag">Python</span><span class="proj-tag">TensorFlow</span><span class="proj-tag">ML</span></div>
      </div>
      <div class="proj-card">
        <div class="proj-title">◈ IoT Nexus</div>
        <div class="proj-desc">Connected devices talking to each other. Smart systems for a smarter world.</div>
        <div class="proj-tags"><span class="proj-tag">IoT</span><span class="proj-tag">Python</span><span class="proj-tag">Hardware</span></div>
      </div>
      <div class="proj-card">
        <div class="proj-title">◈ Cyber Fortress</div>
        <div class="proj-desc">Security tools and explorations in the dark art of protecting digital systems.</div>
        <div class="proj-tags"><span class="proj-tag">Security</span><span class="proj-tag">Python</span><span class="proj-tag">Linux</span></div>
      </div>
      <div class="proj-card">
        <div class="proj-title">◈ Web Forge</div>
        <div class="proj-desc">Full-stack applications with clean UX. Because great tech deserves great design.</div>
        <div class="proj-tags"><span class="proj-tag">JavaScript</span><span class="proj-tag">React</span><span class="proj-tag">Node</span></div>
      </div>
    </div>
  </div>

  <div class="section">
    <div class="sec-title">the philosophy</div>
    <div class="quote-box">
      <span>"</span>In a world drowning in data, the ones who survive are not those who have the most — but those who understand the most. I build the intelligence that separates signal from noise.<span>"</span>
    </div>
  </div>

  <div class="section">
    <div class="sec-title">connect</div>
    <div class="connect-row">
      <a class="connect-btn" href="https://github.com/azriel-gershom">⬡ GitHub</a>
      <span class="connect-btn">◈ LinkedIn</span>
      <span class="connect-btn">✉ Email</span>
      <span class="connect-btn">⚡ Portfolio</span>
    </div>
  </div>
</div>
