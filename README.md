<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Claudiana Carvalho | Portfólio</title>
  <link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=DM+Sans:ital,wght@0,300;0,400;0,500;1,300&display=swap" rel="stylesheet" />
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
    :root {
      --bg: #0a0a0f; --surface: #12121a; --card: #1a1a26;
      --accent: #7c3aed; --accent2: #06b6d4; --accent3: #f59e0b;
      --text: #f1f0f7; --muted: #8b8aa3; --border: rgba(124,58,237,0.25);
    }
    html { scroll-behavior: smooth; }
    body { background: var(--bg); color: var(--text); font-family: 'DM Sans', sans-serif; font-size: 16px; line-height: 1.6; overflow-x: hidden; }
    body::before { content: ''; position: fixed; inset: 0; background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.04'/%3E%3C/svg%3E"); pointer-events: none; z-index: 0; opacity: 0.5; }
    header { position: fixed; top: 0; left: 0; right: 0; z-index: 100; padding: 1rem 2rem; display: flex; align-items: center; justify-content: space-between; background: rgba(10,10,15,0.75); backdrop-filter: blur(16px); border-bottom: 1px solid var(--border); }
    .logo { font-family: 'Syne', sans-serif; font-weight: 800; font-size: 1.4rem; background: linear-gradient(135deg, var(--accent), var(--accent2)); -webkit-background-clip: text; -webkit-text-fill-color: transparent; letter-spacing: -0.5px; }
    nav { display: flex; gap: 2rem; align-items: center; }
    nav a { color: var(--muted); text-decoration: none; font-size: 0.9rem; font-weight: 500; transition: color 0.2s; position: relative; }
    nav a::after { content: ''; position: absolute; bottom: -4px; left: 0; width: 0; height: 2px; background: var(--accent); transition: width 0.3s; border-radius: 2px; }
    nav a:hover { color: var(--text); }
    nav a:hover::after { width: 100%; }
    .nav-btn { background: var(--accent); color: #fff !important; padding: 0.5rem 1.2rem; border-radius: 100px; font-size: 0.85rem !important; font-weight: 600 !important; }
    .nav-btn:hover { background: #6d28d9; }
    .nav-btn::after { display: none !important; }
    .hamburger { display: none; flex-direction: column; gap: 5px; cursor: pointer; padding: 4px; }
    .hamburger span { display: block; width: 24px; height: 2px; background: var(--text); border-radius: 2px; transition: all 0.3s; }
    .hamburger.open span:nth-child(1) { transform: rotate(45deg) translate(5px, 5px); }
    .hamburger.open span:nth-child(2) { opacity: 0; }
    .hamburger.open span:nth-child(3) { transform: rotate(-45deg) translate(5px, -5px); }
    #home { min-height: 100vh; display: flex; align-items: center; padding: 8rem 2rem 4rem; position: relative; overflow: hidden; }
    #home::before, #home::after { content: ''; position: absolute; border-radius: 50%; filter: blur(80px); opacity: 0.18; }
    #home::before { width: 500px; height: 500px; background: var(--accent); top: -100px; left: -100px; animation: drift 8s ease-in-out infinite alternate; }
    #home::after { width: 400px; height: 400px; background: var(--accent2); bottom: -80px; right: -80px; animation: drift 10s ease-in-out infinite alternate-reverse; }
    @keyframes drift { from { transform: translate(0,0) scale(1); } to { transform: translate(30px, 20px) scale(1.08); } }
    .hero-inner { max-width: 900px; margin: 0 auto; position: relative; z-index: 1; }
    .hero-tag { display: inline-flex; align-items: center; gap: 0.5rem; background: rgba(124,58,237,0.15); border: 1px solid var(--border); border-radius: 100px; padding: 0.35rem 1rem; font-size: 0.8rem; color: var(--accent2); font-weight: 500; margin-bottom: 1.5rem; animation: fadeUp 0.6s ease both; }
    .hero-tag span { width: 6px; height: 6px; background: var(--accent2); border-radius: 50%; animation: pulse 2s infinite; }
    @keyframes pulse { 0%,100% { opacity: 1; transform: scale(1); } 50% { opacity: 0.4; transform: scale(1.5); } }
    h1 { font-family: 'Syne', sans-serif; font-size: clamp(2.8rem, 8vw, 5.5rem); font-weight: 800; line-height: 1.05; letter-spacing: -2px; margin-bottom: 1.5rem; animation: fadeUp 0.6s 0.1s ease both; }
    h1 em { font-style: normal; background: linear-gradient(135deg, var(--accent), var(--accent2)); -webkit-background-clip: text; -webkit-text-fill-color: transparent; }
    .hero-desc { font-size: 1.1rem; color: var(--muted); max-width: 560px; margin-bottom: 2.5rem; font-weight: 300; line-height: 1.8; animation: fadeUp 0.6s 0.2s ease both; }
    .hero-actions { display: flex; gap: 1rem; flex-wrap: wrap; animation: fadeUp 0.6s 0.3s ease both; }
    .btn-primary { background: linear-gradient(135deg, var(--accent), #5b21b6); color: #fff; padding: 0.85rem 2rem; border-radius: 100px; text-decoration: none; font-weight: 600; font-size: 0.95rem; transition: transform 0.2s, box-shadow 0.2s; box-shadow: 0 0 30px rgba(124,58,237,0.4); }
    .btn-primary:hover { transform: translateY(-2px); box-shadow: 0 0 45px rgba(124,58,237,0.6); }
    .btn-secondary { border: 1px solid var(--border); color: var(--text); padding: 0.85rem 2rem; border-radius: 100px; text-decoration: none; font-weight: 500; font-size: 0.95rem; transition: border-color 0.2s, background 0.2s; }
    .btn-secondary:hover { border-color: var(--accent); background: rgba(124,58,237,0.08); }
    .scroll-hint { position: absolute; bottom: 2rem; left: 50%; transform: translateX(-50%); display: flex; flex-direction: column; align-items: center; gap: 0.4rem; color: var(--muted); font-size: 0.75rem; letter-spacing: 1px; text-transform: uppercase; animation: fadeUp 1s 1s ease both; }
    .scroll-hint::after { content: ''; width: 1px; height: 40px; background: linear-gradient(to bottom, var(--accent), transparent); animation: scrollLine 1.5s ease-in-out infinite; }
    @keyframes scrollLine { 0% { transform: scaleY(0); transform-origin: top; } 50% { transform: scaleY(1); transform-origin: top; } 51% { transform: scaleY(1); transform-origin: bottom; } 100% { transform: scaleY(0); transform-origin: bottom; } }
    section { padding: 6rem 2rem; position: relative; z-index: 1; }
    .section-label { font-size: 0.75rem; text-transform: uppercase; letter-spacing: 3px; color: var(--accent2); font-weight: 600; margin-bottom: 0.75rem; }
    h2 { font-family: 'Syne', sans-serif; font-size: clamp(2rem, 5vw, 3rem); font-weight: 800; letter-spacing: -1px; line-height: 1.1; margin-bottom: 1rem; }
    .container { max-width: 1100px; margin: 0 auto; }
    #sobre { background: var(--surface); }
    .sobre-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 4rem; align-items: center; }
    .sobre-text p { color: var(--muted); line-height: 1.9; margin-bottom: 1rem; font-weight: 300; }
    .sobre-text p strong { color: var(--text); font-weight: 500; }
    .skills-list { display: flex; flex-wrap: wrap; gap: 0.6rem; margin-top: 1.5rem; }
    .skill-tag { background: rgba(124,58,237,0.12); border: 1px solid rgba(124,58,237,0.3); color: var(--accent2); padding: 0.35rem 0.9rem; border-radius: 100px; font-size: 0.8rem; font-weight: 500; }
    .sobre-stats { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; }
    .stat-card { background: var(--card); border: 1px solid var(--border); border-radius: 16px; padding: 1.5rem; transition: transform 0.2s, border-color 0.2s; }
    .stat-card:hover { transform: translateY(-3px); border-color: var(--accent); }
    .stat-number { font-family: 'Syne', sans-serif; font-size: 2.2rem; font-weight: 800; background: linear-gradient(135deg, var(--accent), var(--accent2)); -webkit-background-clip: text; -webkit-text-fill-color: transparent; line-height: 1; margin-bottom: 0.3rem; }
    .stat-label { font-size: 0.8rem; color: var(--muted); }
    .stat-card.wide { grid-column: 1 / -1; display: flex; align-items: center; gap: 1rem; }
    .stat-icon { font-size: 2rem; flex-shrink: 0; }
    #projetos { background: var(--bg); }
    .projects-header { display: flex; justify-content: space-between; align-items: flex-end; margin-bottom: 3rem; flex-wrap: wrap; gap: 1rem; }
    .projects-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(310px, 1fr)); gap: 1.5rem; }
    .project-card { background: var(--card); border: 1px solid var(--border); border-radius: 20px; overflow: hidden; transition: transform 0.3s, border-color 0.3s, box-shadow 0.3s; opacity: 0; transform: translateY(30px); animation: fadeUp 0.5s ease forwards; }
    .project-card:hover { transform: translateY(-6px); border-color: var(--accent); box-shadow: 0 20px 60px rgba(124,58,237,0.2); }
    .project-thumb { height: 180px; display: flex; align-items: center; justify-content: center; font-size: 4rem; position: relative; overflow: hidden; }
    .project-body { padding: 1.5rem; }
    .project-tags { display: flex; gap: 0.4rem; flex-wrap: wrap; margin-bottom: 0.75rem; }
    .project-tag { font-size: 0.7rem; padding: 0.2rem 0.6rem; border-radius: 100px; font-weight: 600; text-transform: uppercase; letter-spacing: 0.5px; }
    .tag-html { background: rgba(239,68,68,0.15); color: #f87171; }
    .tag-css { background: rgba(59,130,246,0.15); color: #60a5fa; }
    .tag-js { background: rgba(245,158,11,0.15); color: #fbbf24; }
    .tag-ux { background: rgba(16,185,129,0.15); color: #34d399; }
    .tag-figma { background: rgba(168,85,247,0.15); color: #c084fc; }
    .project-title { font-family: 'Syne', sans-serif; font-size: 1.15rem; font-weight: 700; margin-bottom: 0.5rem; color: var(--text); }
    .project-desc { font-size: 0.88rem; color: var(--muted); line-height: 1.7; margin-bottom: 1.2rem; }
    .project-links { display: flex; gap: 0.75rem; }
    .project-link { font-size: 0.8rem; font-weight: 600; text-decoration: none; color: var(--accent2); display: flex; align-items: center; gap: 0.3rem; transition: color 0.2s; }
    .project-link:hover { color: var(--accent); }
    footer { background: var(--surface); border-top: 1px solid var(--border); padding: 3rem 2rem; position: relative; z-index: 1; }
    .footer-inner { max-width: 1100px; margin: 0 auto; display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 1.5rem; }
    .footer-logo { font-family: 'Syne', sans-serif; font-weight: 800; font-size: 1.3rem; background: linear-gradient(135deg, var(--accent), var(--accent2)); -webkit-background-clip: text; -webkit-text-fill-color: transparent; }
    .footer-links { display: flex; gap: 1.5rem; }
    .footer-links a { color: var(--muted); text-decoration: none; font-size: 0.85rem; transition: color 0.2s; }
    .footer-links a:hover { color: var(--accent2); }
    .footer-copy { color: var(--muted); font-size: 0.8rem; width: 100%; text-align: center; padding-top: 1.5rem; border-top: 1px solid var(--border); margin-top: 1rem; }
    .contact-strip { background: linear-gradient(135deg, rgba(124,58,237,0.15), rgba(6,182,212,0.1)); border: 1px solid var(--border); border-radius: 24px; padding: 3rem; text-align: center; margin: 0 auto 4rem; max-width: 700px; }
    .contact-strip h3 { font-family: 'Syne', sans-serif; font-size: 1.8rem; font-weight: 800; margin-bottom: 0.75rem; }
    .contact-strip p { color: var(--muted); margin-bottom: 1.5rem; }
    .contact-email { display: inline-flex; align-items: center; gap: 0.5rem; background: var(--accent); color: #fff; padding: 0.85rem 2rem; border-radius: 100px; text-decoration: none; font-weight: 600; transition: transform 0.2s; }
    .contact-email:hover { transform: translateY(-2px); }
    @keyframes fadeUp { from { opacity: 0; transform: translateY(30px); } to { opacity: 1; transform: translateY(0); } }
    @media (max-width: 768px) {
      nav { display: none; flex-direction: column; position: fixed; inset: 0; top: 60px; background: var(--bg); padding: 2rem; gap: 1.5rem; }
      nav.open { display: flex; }
      nav a { font-size: 1.2rem; }
      .hamburger { display: flex; }
      .sobre-grid { grid-template-columns: 1fr; gap: 2rem; }
      .sobre-stats { grid-template-columns: 1fr 1fr; }
      .stat-card.wide { grid-column: 1 / -1; }
      .contact-strip { padding: 2rem 1.5rem; }
      .footer-inner { flex-direction: column; align-items: flex-start; }
    }
    @media (max-width: 480px) {
      h1 { letter-spacing: -1px; }
      .hero-actions { flex-direction: column; }
      .sobre-stats { grid-template-columns: 1fr; }
      .stat-card.wide { flex-direction: column; text-align: center; }
    }
  </style>
</head>
<body>
  <header>
    <div class="logo">Claudiana.dev</div>
    <nav id="nav">
      <a href="#home">Início</a>
      <a href="#sobre">Sobre</a>
      <a href="#projetos">Projetos</a>
      <a href="#contato" class="nav-btn">Contato</a>
    </nav>
    <div class="hamburger" id="hamburger" onclick="toggleMenu()">
      <span></span><span></span><span></span>
    </div>
  </header>

  <section id="home">
    <div class="hero-inner">
      <div class="hero-tag"><span></span>Disponível para novos desafios</div>
      <h1>Olá, eu sou<br /><em>Claudiana</em><br />Carvalho 👋</h1>
      <p class="hero-desc">Estudante de <strong>Tecnólogo em Sistemas para Internet</strong> na UESPI. Mãe, esposa, trabalho em <strong>home office</strong> e ainda encontro tempo para aprender tecnologia — porque acredito que <strong>respeito e autoestima</strong> são a base de tudo!</p>
      <div class="hero-actions">
        <a href="#projetos" class="btn-primary">Ver meus projetos</a>
        <a href="#sobre" class="btn-secondary">Saber mais sobre mim</a>
      </div>
    </div>
    <div class="scroll-hint">scroll</div>
  </section>

  <section id="sobre">
    <div class="container">
      <div class="sobre-grid">
        <div class="sobre-text">
          <p class="section-label">// sobre mim</p>
          <h2>Quem sou<br /><em style="background:linear-gradient(135deg,#7c3aed,#06b6d4);-webkit-background-clip:text;-webkit-text-fill-color:transparent;font-style:normal;">eu?</em></h2>
          <p>Sou <strong>Claudiana Ferreira da Silva Carvalho</strong>, do <strong>Piauí</strong> — mãe, esposa e mulher que escolheu a tecnologia por pura <strong>vontade de desafio e de crescer</strong>. Entrei nessa área porque adoro aprender coisas novas e nunca me conformo com o que já sei.</p>
          <p>Estudo <strong>Tecnólogo em Sistemas para Internet</strong> na UESPI (EAD) e trabalho em <strong>home office</strong>, conciliando tudo com minha vida de mãe e esposa. Cada disciplina, cada linha de código é mais uma conquista que me orgulha.</p>
          <p>Tenho valores sólidos: acredito que <strong>respeito e autoestima</strong> são a base de qualquer relação — pessoal ou profissional. Quero construir soluções digitais que façam diferença real na vida das pessoas.</p>
          <div class="skills-list">
            <span class="skill-tag">HTML5</span>
            <span class="skill-tag">CSS3</span>
            <span class="skill-tag">JavaScript</span>
            <span class="skill-tag">React</span>
            <span class="skill-tag">Git & GitHub</span>
            <span class="skill-tag">Flexbox & Grid</span>
            <span class="skill-tag">Design UI/UX</span>
            <span class="skill-tag">Figma</span>
          </div>
        </div>
        <div class="sobre-stats">
          <div class="stat-card"><div class="stat-number">💜</div><div class="stat-label">Mãe & esposa</div></div>
          <div class="stat-card"><div class="stat-number">∞</div><div class="stat-label">Vontade de aprender</div></div>
          <div class="stat-card"><div class="stat-number">PI</div><div class="stat-label">Com orgulho do Piauí</div></div>
          <div class="stat-card"><div class="stat-number">100%</div><div class="stat-label">Respeito & autoestima</div></div>
          <div class="stat-card wide">
            <div class="stat-icon">🏠</div>
            <div>
              <div class="stat-number" style="font-size:1.3rem">Home Office</div>
              <div class="stat-label">Conciliando trabalho, família e estudos com determinação todos os dias</div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <section id="projetos">
    <div class="container">
      <div class="projects-header">
        <div>
          <p class="section-label">// meus projetos</p>
          <h2>O que já<br /><em style="background:linear-gradient(135deg,#7c3aed,#06b6d4);-webkit-background-clip:text;-webkit-text-fill-color:transparent;font-style:normal;">construí</em></h2>
        </div>
      </div>
      <div class="projects-grid" id="projects-grid"></div>
    </div>
  </section>

  <section id="contato" style="padding-bottom:2rem;">
    <div class="container">
      <div class="contact-strip">
        <h3>Vamos nos conectar? 🚀</h3>
        <p>Estou sempre aberta a novas oportunidades, projetos e aprendizados. Manda uma mensagem!</p>
        <a href="mailto:seuemail@email.com" class="contact-email">✉️ &nbsp;Entrar em contato</a>
      </div>
    </div>
  </section>

  <footer>
    <div class="footer-inner">
      <div class="footer-logo">Claudiana.dev</div>
      <div class="footer-links">
        <a href="https://github.com/" target="_blank">GitHub</a>
        <a href="#sobre">Sobre</a>
        <a href="#projetos">Projetos</a>
      </div>
    </div>
    <div class="footer-copy">© 2025 Claudiana Carvalho · Feito com 💜 e muito aprendizado · UESPI — Sistemas para Internet</div>
  </footer>

  <script>
    const projetos = [
      { emoji: "💜", bg: "linear-gradient(135deg, #7c3aed, #ec4899)", tags: [{label:"HTML",classe:"tag-html"},{label:"CSS",classe:"tag-css"},{label:"JS",classe:"tag-js"}], titulo: "Autoestima & Aceitação de Si", descricao: "Página interativa sobre amor próprio com frases inspiradoras, afirmações personalizadas, os 6 pilares da autoestima e ritual diário de autocuidado.", linkDemo: "#", linkCodigo: "#" },
      { emoji: "🧠", bg: "linear-gradient(135deg, #fbbf24, #f59e0b)", tags: [{label:"UI/UX",classe:"tag-ux"},{label:"Figma",classe:"tag-fi
