<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Guido Saban — GitHub Profile Preview</title>
<link rel="preconnect" href="https://fonts.googleapis.com"/>
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;600;700&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet"/>
<style>
  /* ── NEUMORPHISM DESIGN SYSTEM ── */
  :root {
    --neu-bg:       #E0E5EC;
    --neu-shadow-l: #FFFFFF;
    --neu-shadow-d: #A3B1C6;
    --neu-accent:   #4A8BC4;
    --neu-accent2:  #5EA3DC;
    --neu-text:     #5B6D8A;
    --neu-text-m:   #7B93B0;
    --neu-text-d:   #3D4F63;
    --neu-raised:   6px 6px 14px #A3B1C6, -6px -6px 14px #FFFFFF;
    --neu-inset:    inset 4px 4px 10px #A3B1C6, inset -4px -4px 10px #FFFFFF;
    --neu-sm:       3px 3px 8px #A3B1C6, -3px -3px 8px #FFFFFF;
  }

  * { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    background: var(--neu-bg);
    font-family: 'Inter', sans-serif;
    color: var(--neu-text);
    min-height: 100vh;
    padding: 2rem 1rem;
  }

  .container {
    max-width: 900px;
    margin: 0 auto;
  }

  /* ── HERO ── */
  .hero {
    background: linear-gradient(135deg, #C8D0E7 0%, #D4DAE8 50%, #BEC8D9 100%);
    border-radius: 28px;
    box-shadow: var(--neu-raised);
    padding: 3rem 2rem;
    text-align: center;
    margin-bottom: 2rem;
    position: relative;
    overflow: hidden;
  }

  .hero::before {
    content: '';
    position: absolute;
    top: -60px; right: -60px;
    width: 200px; height: 200px;
    border-radius: 50%;
    background: rgba(255,255,255,0.15);
  }

  .hero::after {
    content: '';
    position: absolute;
    bottom: -40px; left: -40px;
    width: 150px; height: 150px;
    border-radius: 50%;
    background: rgba(163,177,198,0.2);
  }

  .hero h1 {
    font-size: 3.2rem;
    font-weight: 700;
    color: var(--neu-text-d);
    letter-spacing: -1px;
    margin-bottom: 0.5rem;
  }

  .hero .subtitle {
    font-size: 1.1rem;
    color: var(--neu-text-m);
    font-weight: 400;
    margin-bottom: 1.5rem;
    font-family: 'JetBrains Mono', monospace;
  }

  .badge-row {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    justify-content: center;
  }

  .badge {
    background: var(--neu-bg);
    box-shadow: var(--neu-sm);
    border-radius: 50px;
    padding: 8px 20px;
    font-size: 0.82rem;
    font-weight: 600;
    color: var(--neu-text);
    text-decoration: none;
    transition: all 0.3s ease;
    display: flex;
    align-items: center;
    gap: 6px;
  }

  .badge:hover {
    box-shadow: var(--neu-inset);
    color: var(--neu-accent);
    transform: scale(0.98);
  }

  .badge.accent {
    background: var(--neu-accent);
    color: #fff;
    box-shadow: 3px 3px 8px #3A7BB4, -2px -2px 6px #5A9BD4;
  }

  /* ── CARDS GRID ── */
  .grid-2 {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1.5rem;
    margin-bottom: 2rem;
  }

  .grid-3 {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 1rem;
    margin-bottom: 2rem;
  }

  .card {
    background: var(--neu-bg);
    border-radius: 20px;
    box-shadow: var(--neu-raised);
    padding: 1.5rem;
    transition: all 0.35s ease;
  }

  .card:hover {
    box-shadow: 8px 8px 18px #A3B1C6, -8px -8px 18px #FFFFFF;
    transform: translateY(-2px);
  }

  .card.inset {
    box-shadow: var(--neu-inset);
  }

  .card h3 {
    font-size: 1rem;
    font-weight: 600;
    color: var(--neu-text-d);
    margin-bottom: 0.75rem;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .card p, .card li {
    font-size: 0.875rem;
    color: var(--neu-text-m);
    line-height: 1.6;
  }

  .card ul {
    list-style: none;
    padding: 0;
  }

  .card ul li::before {
    content: '▸ ';
    color: var(--neu-accent);
    font-size: 0.75rem;
  }

  /* ── SECTION HEADING ── */
  .section {
    margin-bottom: 2rem;
  }

  .section-title {
    font-size: 1.3rem;
    font-weight: 700;
    color: var(--neu-text-d);
    margin-bottom: 1.25rem;
    display: flex;
    align-items: center;
    gap: 10px;
    padding-bottom: 0.5rem;
    border-bottom: 2px solid;
    border-image: linear-gradient(90deg, var(--neu-accent), transparent) 1;
  }

  /* ── CODE BLOCK ── */
  .code-block {
    background: var(--neu-bg);
    box-shadow: var(--neu-inset);
    border-radius: 16px;
    padding: 1.25rem 1.5rem;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.82rem;
    line-height: 1.7;
    color: var(--neu-text);
    white-space: pre;
    overflow-x: auto;
  }

  .kw  { color: #4A8BC4; }
  .str { color: #E86A4A; }
  .num { color: #7B93B0; }
  .cmt { color: #A3B1C6; font-style: italic; }
  .ok  { color: #3BAD8B; }

  /* ── TECH PILLS ── */
  .tech-group {
    margin-bottom: 1.5rem;
  }

  .tech-label {
    font-size: 0.75rem;
    font-weight: 600;
    color: var(--neu-text-m);
    text-transform: uppercase;
    letter-spacing: 1.5px;
    margin-bottom: 0.6rem;
  }

  .pills {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }

  .pill {
    background: var(--neu-bg);
    box-shadow: var(--neu-sm);
    border-radius: 50px;
    padding: 5px 14px;
    font-size: 0.78rem;
    font-weight: 500;
    color: var(--neu-text);
    transition: all 0.25s;
    cursor: default;
  }

  .pill:hover {
    box-shadow: var(--neu-inset);
    color: var(--neu-accent);
  }

  /* ── TIMELINE ITEM ── */
  .timeline-item {
    display: flex;
    gap: 1rem;
    margin-bottom: 1.25rem;
  }

  .tl-dot {
    width: 40px;
    height: 40px;
    border-radius: 50%;
    background: var(--neu-bg);
    box-shadow: var(--neu-sm);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1.1rem;
    flex-shrink: 0;
    margin-top: 2px;
  }

  .tl-content { flex: 1; }

  .tl-content h4 {
    font-size: 0.95rem;
    font-weight: 600;
    color: var(--neu-text-d);
    margin-bottom: 2px;
  }

  .tl-content .date {
    font-size: 0.75rem;
    color: var(--neu-accent);
    font-family: 'JetBrains Mono', monospace;
    margin-bottom: 4px;
    font-weight: 600;
  }

  .tl-content p {
    font-size: 0.83rem;
    color: var(--neu-text-m);
    line-height: 1.5;
  }

  /* ── STAT RING ── */
  .stats-row {
    display: flex;
    gap: 1rem;
    flex-wrap: wrap;
    margin-bottom: 2rem;
  }

  .stat-card {
    flex: 1;
    min-width: 120px;
    background: var(--neu-bg);
    box-shadow: var(--neu-raised);
    border-radius: 18px;
    padding: 1.2rem;
    text-align: center;
    transition: all 0.3s;
  }

  .stat-card:hover {
    box-shadow: var(--neu-inset);
  }

  .stat-num {
    font-size: 2rem;
    font-weight: 700;
    color: var(--neu-accent);
    font-family: 'JetBrains Mono', monospace;
    line-height: 1;
    margin-bottom: 4px;
  }

  .stat-label {
    font-size: 0.72rem;
    color: var(--neu-text-m);
    font-weight: 500;
    text-transform: uppercase;
    letter-spacing: 0.8px;
  }

  /* ── CERT TABLE ── */
  .cert-table {
    width: 100%;
    border-collapse: separate;
    border-spacing: 0 8px;
  }

  .cert-table td {
    padding: 10px 14px;
    font-size: 0.83rem;
    color: var(--neu-text);
  }

  .cert-table tr {
    background: var(--neu-bg);
    box-shadow: var(--neu-sm);
    border-radius: 12px;
  }

  .cert-table tr td:first-child {
    border-radius: 12px 0 0 12px;
    font-weight: 500;
    color: var(--neu-text-d);
  }

  .cert-table tr td:last-child {
    border-radius: 0 12px 12px 0;
    color: var(--neu-text-m);
    text-align: right;
  }

  /* ── QUOTE ── */
  .quote {
    background: var(--neu-bg);
    box-shadow: var(--neu-inset);
    border-radius: 16px;
    padding: 1.5rem 2rem;
    text-align: center;
    font-size: 1rem;
    font-style: italic;
    color: var(--neu-text-m);
    margin: 2rem 0;
    position: relative;
  }

  .quote::before {
    content: '"';
    font-size: 4rem;
    color: var(--neu-shadow-d);
    position: absolute;
    top: -10px; left: 20px;
    line-height: 1;
    font-family: Georgia, serif;
  }

  /* ── FOOTER ── */
  .footer {
    text-align: center;
    margin-top: 3rem;
    padding: 1.5rem;
    font-size: 0.82rem;
    color: var(--neu-text-m);
    background: linear-gradient(135deg, #BEC8D9, #D4DAE8);
    border-radius: 20px;
    box-shadow: var(--neu-raised);
  }

  /* ── ANIMATIONS ── */
  @keyframes fadeInUp {
    from { opacity: 0; transform: translateY(24px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  @keyframes pulse {
    0%, 100% { box-shadow: var(--neu-raised); }
    50%       { box-shadow: 8px 8px 20px #A3B1C6, -8px -8px 20px #FFFFFF; }
  }

  .animate { animation: fadeInUp 0.6s ease both; }
  .delay-1 { animation-delay: 0.1s; }
  .delay-2 { animation-delay: 0.2s; }
  .delay-3 { animation-delay: 0.3s; }
  .delay-4 { animation-delay: 0.4s; }

  .badge.accent { animation: pulse 3s ease-in-out infinite; }

  /* ── TYPING CURSOR ── */
  .typing-wrap {
    font-family: 'JetBrains Mono', monospace;
    font-size: 1rem;
    color: var(--neu-accent);
    text-align: center;
    margin: 1rem 0 1.5rem;
    min-height: 28px;
  }

  .cursor { animation: blink 1s step-end infinite; }
  @keyframes blink { 0%,100% { opacity:1; } 50% { opacity:0; } }

  /* ── RESPONSIVE ── */
  @media (max-width: 640px) {
    .grid-2, .grid-3 { grid-template-columns: 1fr; }
    .hero h1 { font-size: 2rem; }
  }
</style>
</head>
<body>
<div class="container">

  <!-- HERO -->
  <div class="hero animate">
    <h1>Guido Saban</h1>
    <div class="subtitle">Full Stack Engineer SSR — Buenos Aires, Argentina 🇦🇷</div>
    <div class="typing-wrap">
      <span id="typing-text"></span><span class="cursor">|</span>
    </div>
    <div class="badge-row">
      <a class="badge accent" href="https://linkedin.com/in/sabanguido" target="_blank">🔗 LinkedIn</a>
      <a class="badge" href="mailto:sabanguido@gmail.com">✉️ sabanguido@gmail.com</a>
      <a class="badge" href="https://wa.me/5491132266433" target="_blank">📱 +54 9 11 3226-6433</a>
    </div>
  </div>

  <!-- STATS QUICK -->
  <div class="stats-row animate delay-1">
    <div class="stat-card"><div class="stat-num">6+</div><div class="stat-label">Años en Indra</div></div>
    <div class="stat-card"><div class="stat-num">90%</div><div class="stat-label">Reducción Carga Manual</div></div>
    <div class="stat-card"><div class="stat-num">3+</div><div class="stat-label">Años Freelance</div></div>
    <div class="stat-card"><div class="stat-num">5</div><div class="stat-label">Certificaciones SAP</div></div>
    <div class="stat-card"><div class="stat-num">B1</div><div class="stat-label">Inglés Técnico</div></div>
  </div>

  <!-- ABOUT + CODE -->
  <div class="section animate delay-2">
    <div class="section-title">🧠 Sobre mí</div>
    <div class="grid-2">
      <div class="card">
        <h3>👤 Perfil</h3>
        <p>Full Stack Engineer SSR especializado en el ecosistema TypeScript, enfocado en el diseño de arquitecturas backend escalables, APIs robustas y sistemas en tiempo real.</p>
        <br/>
        <p>Experiencia en entornos corporativos y proyectos freelance, desarrollando soluciones orientadas a automatización, mantenibilidad y performance.</p>
      </div>
      <div class="card inset code-block"><span class="kw">const</span> guido: Developer = {
  ubicacion:  <span class="str">"Buenos Aires 🇦🇷"</span>,
  roles:      [<span class="str">"Full Stack"</span>, <span class="str">"Backend"</span>],
  stack: {
    frontend: [<span class="str">"React"</span>, <span class="str">"Next.js"</span>],
    backend:  [<span class="str">"Node.js"</span>, <span class="str">"NestJS"</span>],
    cloud:    [<span class="str">"AWS"</span>, <span class="str">"Docker"</span>],
  },
  disponible: <span class="ok">true</span>, <span class="cmt">// 🟢 Open to work</span>
};</div>
    </div>
  </div>

  <!-- TECH STACK -->
  <div class="section animate delay-2">
    <div class="section-title">🛠️ Stack Tecnológico</div>
    <div class="card">
      <div class="tech-group">
        <div class="tech-label">Frontend</div>
        <div class="pills">
          <span class="pill">React</span><span class="pill">Next.js</span><span class="pill">Astro</span>
          <span class="pill">TypeScript</span><span class="pill">Tailwind CSS</span><span class="pill">HTML5 / CSS3</span>
          <span class="pill">React Native</span>
        </div>
      </div>
      <div class="tech-group">
        <div class="tech-label">Backend & APIs</div>
        <div class="pills">
          <span class="pill">Node.js</span><span class="pill">NestJS</span><span class="pill">Express.js</span>
          <span class="pill">REST APIs</span><span class="pill">WebSockets</span><span class="pill">JWT / RBAC</span>
        </div>
      </div>
      <div class="tech-group">
        <div class="tech-label">Bases de Datos</div>
        <div class="pills">
          <span class="pill">PostgreSQL</span><span class="pill">MongoDB</span><span class="pill">DynamoDB</span>
          <span class="pill">HANA Cloud</span>
        </div>
      </div>
      <div class="tech-group">
        <div class="tech-label">Cloud & DevOps</div>
        <div class="pills">
          <span class="pill">AWS (S3, Lambda, API Gateway)</span><span class="pill">Docker</span>
          <span class="pill">Git / GitHub</span><span class="pill">Serverless</span>
        </div>
      </div>
      <div class="tech-group">
        <div class="tech-label">Arquitectura & Prácticas</div>
        <div class="pills">
          <span class="pill">Clean Architecture</span><span class="pill">Modular Design</span>
          <span class="pill">Scrum / Agile</span><span class="pill">SAP BTP</span>
        </div>
      </div>
    </div>
  </div>

  <!-- EXPERIENCE -->
  <div class="section animate delay-3">
    <div class="section-title">💼 Experiencia Profesional</div>
    <div class="card">
      <div class="timeline-item">
        <div class="tl-dot">🏢</div>
        <div class="tl-content">
          <h4>Indra — Full Stack / Backend Developer</h4>
          <div class="date">Ene 2023 – Feb 2026 · Ciudad Autónoma de Buenos Aires</div>
          <ul>
            <li>Automaticé flujos contables → reducción del 90% de carga manual</li>
            <li>Flujos de aprobación con notificaciones móviles</li>
            <li>Plataforma de gestión de proveedores con integración SAP BTP</li>
            <li>APIs REST, PostgreSQL, HANA Cloud, Docker</li>
          </ul>
        </div>
      </div>
      <div class="timeline-item">
        <div class="tl-dot">💻</div>
        <div class="tl-content">
          <h4>Freelance — Full Stack Developer (Part-Time)</h4>
          <div class="date">Ene 2023 – Presente · Remoto</div>
          <ul>
            <li>E-commerce y sistemas de gestión end-to-end</li>
            <li>SEO técnico, performance web y visibilidad digital</li>
            <li>Autenticación, RBAC, WebSockets en tiempo real</li>
            <li>Deploys con Docker y AWS · Stack: React, Next.js, Astro, Node.js</li>
          </ul>
        </div>
      </div>
      <div class="timeline-item">
        <div class="tl-dot">🧩</div>
        <div class="tl-content">
          <h4>Indra — SAP Support Analyst</h4>
          <div class="date">Mar 2020 – Dic 2022 · Clientes: Telefónica · Carrefour · Molinos Río de la Plata</div>
          <p>Soporte funcional y técnico en SAP MM · FI/CO · S/4HANA. Gestión de incidencias, usuarios, roles y procesos críticos de negocio.</p>
        </div>
      </div>
    </div>
  </div>

  <!-- CERTS -->
  <div class="section animate delay-4">
    <div class="section-title">🏆 Educación & Certificaciones</div>
    <div class="grid-2">
      <div class="card">
        <h3>🎓 Educación</h3>
        <br/>
        <p><strong>Universidad Argentina de la Empresa (UADE)</strong></p>
        <p style="font-size:0.82rem;color:var(--neu-accent);font-family:'JetBrains Mono',monospace;margin:4px 0;">Ingeniería de Sistemas · 2020 – Presente</p>
        <p>Buenos Aires, Argentina 🇦🇷</p>
      </div>
      <div class="card">
        <h3>📜 Certificaciones</h3>
        <table class="cert-table">
          <tr><td>SAP Business Technology Platform</td><td>SAP</td></tr>
          <tr><td>SAP ABAP Completo</td><td>SAP</td></tr>
          <tr><td>Managing Clean Core S/4HANA</td><td>SAP</td></tr>
          <tr><td>SAP Cloud App Programming</td><td>SAP</td></tr>
          <tr><td>Creative HTML5 & CSS3</td><td>Udemy</td></tr>
        </table>
      </div>
    </div>
  </div>

  <!-- QUOTE -->
  <div class="quote animate">
    Transformando necesidades complejas de negocio en software eficiente y escalable.
  </div>

  <!-- FOOTER -->
  <div class="footer">
    Crafted with 💙 by <strong>Guido Saban</strong> · Buenos Aires, Argentina 🇦🇷 · 2025
  </div>

</div>

<script>
  // Typing animation
  const lines = [
    "TypeScript • Node.js • React • NestJS 🚀",
    "Backend Architecture & Scalable Systems",
    "APIs REST • WebSockets • Serverless",
    "Open to Work 🟢",
  ];
  let li = 0, ci = 0, del = false;
  const el = document.getElementById("typing-text");

  function type() {
    const cur = lines[li];
    if (!del) {
      el.textContent = cur.slice(0, ++ci);
      if (ci === cur.length) { del = true; return setTimeout(type, 2200); }
      setTimeout(type, 55);
    } else {
      el.textContent = cur.slice(0, --ci);
      if (ci === 0) { del = false; li = (li + 1) % lines.length; return setTimeout(type, 400); }
      setTimeout(type, 28);
    }
  }
  type();

  // Intersection observer for scroll animations
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        e.target.style.opacity = "1";
        e.target.style.transform = "translateY(0)";
      }
    });
  }, { threshold: 0.1 });

  document.querySelectorAll(".animate").forEach(el => {
    el.style.opacity = "0";
    el.style.transform = "translateY(20px)";
    el.style.transition = "opacity 0.6s ease, transform 0.6s ease";
    observer.observe(el);
  });

  // Pill hover count (easter egg)
  document.querySelectorAll(".pill").forEach(p => {
    p.addEventListener("click", () => {
      p.style.background = "var(--neu-accent)";
      p.style.color = "#fff";
      p.style.boxShadow = "var(--neu-inset)";
    });
  });
</script>
</body>
</html>
