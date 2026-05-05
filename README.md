<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Albano Consultoria e Agrimensura</title>
<link rel="preconnect" href="https://fonts.googleapis.com"/>
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin/>
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Barlow:ital,wght@0,300;0,400;0,500;0,600;0,700;1,300;1,400&family=Barlow+Condensed:wght@400;500;600;700&display=swap" rel="stylesheet"/>
<style>
  :root {
    --lime: #C9F000;
    --black: #0B0B0B;
    --dark: #111111;
    --card: #181818;
    --border: #242424;
    --white: #F5F5F0;
    --muted: #888;
    --font-display: 'Bebas Neue', sans-serif;
    --font-cond: 'Barlow Condensed', sans-serif;
    --font-body: 'Barlow', sans-serif;
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  html { scroll-behavior: smooth; }

  body {
    background: var(--black);
    color: var(--white);
    font-family: var(--font-body);
    font-weight: 400;
    line-height: 1.6;
    overflow-x: hidden;
  }

  /* ─── NOISE OVERLAY ─── */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='1'/%3E%3C/svg%3E");
    opacity: 0.025;
    pointer-events: none;
    z-index: 999;
  }

  /* ─── SCROLLBAR ─── */
  ::-webkit-scrollbar { width: 4px; }
  ::-webkit-scrollbar-track { background: var(--black); }
  ::-webkit-scrollbar-thumb { background: var(--lime); border-radius: 2px; }

  /* ─── NAV ─── */
  nav {
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 100;
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 1.25rem 3rem;
    background: rgba(11,11,11,0.85);
    backdrop-filter: blur(12px);
    border-bottom: 1px solid var(--border);
    transition: padding 0.3s;
  }

  .nav-logo {
    display: flex;
    align-items: center;
    gap: 0.75rem;
    text-decoration: none;
  }

  .nav-symbol {
    width: 32px;
    height: 32px;
  }

  .nav-wordmark {
    font-family: var(--font-display);
    font-size: 1.5rem;
    letter-spacing: 0.05em;
    color: var(--white);
  }
  .nav-wordmark span { color: var(--lime); }

  .nav-logo-img {
    height: 32px;
    width: auto;
    display: block;
  }

  .nav-links {
    display: flex;
    gap: 2rem;
    list-style: none;
  }
  .nav-links a {
    font-family: var(--font-cond);
    font-size: 0.8rem;
    font-weight: 600;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: var(--muted);
    text-decoration: none;
    transition: color 0.2s;
  }
  .nav-links a:hover { color: var(--lime); }

  .nav-cta {
    font-family: var(--font-cond);
    font-size: 0.8rem;
    font-weight: 700;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    background: var(--lime);
    color: var(--black);
    padding: 0.5rem 1.25rem;
    border: none;
    cursor: pointer;
    text-decoration: none;
    transition: background 0.2s, transform 0.15s;
  }
  .nav-cta:hover { background: #d4ff00; transform: translateY(-1px); }

  /* ─── HERO ─── */
  #hero {
    min-height: 100vh;
    display: grid;
    grid-template-columns: 1fr 1fr;
    position: relative;
    overflow: hidden;
  }

  .hero-left {
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 8rem 3rem 5rem 3rem;
    position: relative;
    z-index: 2;
  }

  .hero-tag {
    font-family: var(--font-cond);
    font-size: 0.75rem;
    font-weight: 600;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--lime);
    margin-bottom: 1.5rem;
    display: flex;
    align-items: center;
    gap: 0.75rem;
  }
  .hero-tag::before {
    content: '';
    display: block;
    width: 2rem;
    height: 2px;
    background: var(--lime);
  }

  .hero-title {
    font-family: var(--font-display);
    font-size: clamp(3.5rem, 6vw, 6.5rem);
    line-height: 0.92;
    letter-spacing: 0.02em;
    color: var(--white);
    margin-bottom: 2rem;
  }
  .hero-title .accent { color: var(--lime); }

  .hero-sub {
    font-family: var(--font-body);
    font-size: 1.05rem;
    font-weight: 300;
    color: var(--muted);
    max-width: 440px;
    line-height: 1.75;
    margin-bottom: 3rem;
  }

  .hero-actions {
    display: flex;
    gap: 1rem;
    flex-wrap: wrap;
  }

  .btn-primary {
    font-family: var(--font-cond);
    font-size: 0.85rem;
    font-weight: 700;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    background: var(--lime);
    color: var(--black);
    padding: 0.9rem 2.25rem;
    text-decoration: none;
    transition: transform 0.2s, background 0.2s;
    display: inline-block;
  }
  .btn-primary:hover { background: #d4ff00; transform: translateY(-2px); }

  .btn-outline {
    font-family: var(--font-cond);
    font-size: 0.85rem;
    font-weight: 600;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    background: transparent;
    color: var(--white);
    padding: 0.9rem 2.25rem;
    border: 1px solid var(--border);
    text-decoration: none;
    transition: border-color 0.2s, color 0.2s;
    display: inline-block;
  }
  .btn-outline:hover { border-color: var(--lime); color: var(--lime); }

  .hero-right {
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
    overflow: hidden;
  }

  .hero-geo {
    position: absolute;
    inset: 0;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  /* Topographic lines SVG background */
  .topo-bg {
    position: absolute;
    inset: 0;
    opacity: 0.06;
  }

  .hero-symbol-wrap {
    position: relative;
    z-index: 2;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 2rem;
    transform: translateY(-40px);
  }

  .big-symbol {
    width: 220px;
    height: 220px;
    animation: float 6s ease-in-out infinite;
    margin-bottom: 1rem;
  }

  @keyframes float {
    0%, 100% { transform: translateY(0); }
    50% { transform: translateY(-18px); }
  }

  .hero-stats {
    display: flex;
    gap: 3rem;
  }

  .stat {
    text-align: center;
  }
  .stat-num {
    font-family: var(--font-display);
    font-size: 2.5rem;
    color: var(--lime);
    line-height: 1;
  }
  .stat-label {
    font-family: var(--font-cond);
    font-size: 0.7rem;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: var(--muted);
    margin-top: 0.25rem;
  }

  /* diagonal divider */
  .hero-divider {
    position: absolute;
    left: 50%;
    top: 0;
    bottom: 0;
    width: 1px;
    background: linear-gradient(to bottom, transparent, var(--border) 20%, var(--border) 80%, transparent);
  }

  /* scroll indicator */
  .scroll-hint {
    position: absolute;
    bottom: 2.5rem;
    left: 3rem;
    display: flex;
    align-items: center;
    gap: 0.75rem;
    font-family: var(--font-cond);
    font-size: 0.7rem;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--muted);
  }
  .scroll-line {
    width: 40px;
    height: 1px;
    background: var(--muted);
    animation: scrollLine 2s ease-in-out infinite;
  }
  @keyframes scrollLine {
    0%, 100% { width: 40px; opacity: 0.4; }
    50% { width: 20px; opacity: 1; }
  }

  /* ─── SECTION COMMON ─── */
  section { padding: 7rem 3rem; }

  .section-tag {
    font-family: var(--font-cond);
    font-size: 0.75rem;
    font-weight: 600;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--lime);
    display: flex;
    align-items: center;
    gap: 0.75rem;
    margin-bottom: 1rem;
  }
  .section-tag::before {
    content: '';
    display: block;
    width: 1.5rem;
    height: 2px;
    background: var(--lime);
  }

  .section-title {
    font-family: var(--font-display);
    font-size: clamp(2.5rem, 4vw, 4rem);
    line-height: 0.95;
    letter-spacing: 0.02em;
    margin-bottom: 1.5rem;
  }

  /* ─── SOBRE ─── */
  #sobre {
    background: var(--dark);
    border-top: 1px solid var(--border);
    border-bottom: 1px solid var(--border);
  }

  .sobre-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 5rem;
    align-items: center;
    max-width: 1200px;
    margin: 0 auto;
  }

  .sobre-text p {
    font-size: 1rem;
    font-weight: 300;
    color: #aaa;
    line-height: 1.8;
    margin-bottom: 1.25rem;
  }
  .sobre-text p strong { color: var(--white); font-weight: 600; }

  .sobre-highlights {
    display: flex;
    flex-direction: column;
    gap: 1px;
  }

  .highlight-item {
    display: flex;
    align-items: flex-start;
    gap: 1.25rem;
    padding: 1.5rem;
    background: var(--card);
    border-left: 2px solid transparent;
    transition: border-color 0.3s, background 0.3s;
    cursor: default;
  }
  .highlight-item:hover {
    border-left-color: var(--lime);
    background: #1e1e1e;
  }

  .hi-icon {
    font-size: 1.5rem;
    margin-top: 0.1rem;
    flex-shrink: 0;
  }

  .hi-title {
    font-family: var(--font-cond);
    font-size: 1rem;
    font-weight: 700;
    letter-spacing: 0.05em;
    text-transform: uppercase;
    margin-bottom: 0.25rem;
  }

  .hi-desc {
    font-size: 0.85rem;
    color: var(--muted);
    line-height: 1.5;
  }

  /* ─── SERVIÇOS ─── */
  #servicos { max-width: 1300px; margin: 0 auto; }
  #servicos > .container { max-width: 1300px; margin: 0 auto; }

  .services-header {
    display: flex;
    justify-content: space-between;
    align-items: flex-end;
    margin-bottom: 4rem;
    flex-wrap: wrap;
    gap: 2rem;
  }

  .services-intro {
    font-size: 1rem;
    color: var(--muted);
    max-width: 360px;
    line-height: 1.7;
  }

  .services-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1px;
    background: var(--border);
  }

  .service-card {
    background: var(--black);
    padding: 2.5rem;
    position: relative;
    overflow: hidden;
    transition: background 0.3s;
  }
  .service-card::before {
    content: '';
    position: absolute;
    bottom: 0; left: 0; right: 0;
    height: 2px;
    background: var(--lime);
    transform: scaleX(0);
    transform-origin: left;
    transition: transform 0.4s ease;
  }
  .service-card:hover { background: var(--card); }
  .service-card:hover::before { transform: scaleX(1); }

  .service-num {
    font-family: var(--font-display);
    font-size: 4rem;
    color: var(--border);
    line-height: 1;
    margin-bottom: 1.5rem;
    transition: color 0.3s;
  }
  .service-card:hover .service-num { color: #2a2a2a; }

  .service-icon {
    font-size: 2rem;
    margin-bottom: 1rem;
  }

  .service-name {
    font-family: var(--font-cond);
    font-size: 1.3rem;
    font-weight: 700;
    letter-spacing: 0.05em;
    text-transform: uppercase;
    color: var(--white);
    margin-bottom: 0.75rem;
  }

  .service-desc {
    font-size: 0.9rem;
    color: var(--muted);
    line-height: 1.7;
    margin-bottom: 1.5rem;
  }

  .service-list {
    list-style: none;
    display: flex;
    flex-direction: column;
    gap: 0.4rem;
  }
  .service-list li {
    font-size: 0.8rem;
    color: #666;
    font-family: var(--font-cond);
    letter-spacing: 0.03em;
    display: flex;
    align-items: center;
    gap: 0.5rem;
    transition: color 0.2s;
  }
  .service-card:hover .service-list li { color: #999; }
  .service-list li::before {
    content: '—';
    color: var(--lime);
    flex-shrink: 0;
  }

  /* ─── PÚBLICOS ─── */
  #publicos {
    background: var(--dark);
    border-top: 1px solid var(--border);
    border-bottom: 1px solid var(--border);
  }

  .publicos-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 2rem;
    max-width: 1100px;
    margin: 3rem auto 0;
  }

  .publico-card {
    background: var(--black);
    border: 1px solid var(--border);
    padding: 3rem;
    position: relative;
    overflow: hidden;
    transition: border-color 0.3s;
  }
  .publico-card:hover { border-color: var(--lime); }

  .publico-badge {
    font-family: var(--font-cond);
    font-size: 0.7rem;
    font-weight: 700;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    background: var(--lime);
    color: var(--black);
    padding: 0.25rem 0.75rem;
    display: inline-block;
    margin-bottom: 1.5rem;
  }

  .publico-title {
    font-family: var(--font-display);
    font-size: 2rem;
    margin-bottom: 0.75rem;
  }

  .publico-desc {
    font-size: 0.9rem;
    color: var(--muted);
    line-height: 1.7;
    margin-bottom: 1.75rem;
  }

  .publico-items {
    list-style: none;
    display: flex;
    flex-direction: column;
    gap: 0.6rem;
  }
  .publico-items li {
    font-size: 0.875rem;
    color: #aaa;
    display: flex;
    align-items: center;
    gap: 0.75rem;
  }
  .publico-items li .dot {
    width: 6px;
    height: 6px;
    background: var(--lime);
    border-radius: 50%;
    flex-shrink: 0;
  }

  .publico-bg-num {
    position: absolute;
    bottom: -1.5rem;
    right: 1rem;
    font-family: var(--font-display);
    font-size: 8rem;
    color: var(--border);
    line-height: 1;
    pointer-events: none;
    transition: color 0.3s;
  }
  .publico-card:hover .publico-bg-num { color: #1e1e1e; }

  /* ─── DIFERENCIAIS ─── */
  #diferenciais {
    max-width: 1200px;
    margin: 0 auto;
  }

  .dif-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 2rem;
    margin-top: 4rem;
  }

  .dif-card {
    padding: 2rem 0;
    border-top: 1px solid var(--border);
    transition: border-color 0.3s;
  }
  .dif-card:hover { border-top-color: var(--lime); }

  .dif-icon {
    font-size: 2rem;
    margin-bottom: 1rem;
    display: block;
  }

  .dif-title {
    font-family: var(--font-cond);
    font-size: 1rem;
    font-weight: 700;
    letter-spacing: 0.06em;
    text-transform: uppercase;
    color: var(--white);
    margin-bottom: 0.5rem;
  }

  .dif-desc {
    font-size: 0.85rem;
    color: var(--muted);
    line-height: 1.65;
  }

  /* ─── JOÃO PAULO ─── */
  #joao-paulo {
    background: var(--lime);
    color: var(--black);
  }

  .jp-grid {
    display: grid;
    grid-template-columns: 1fr 1.2fr;
    gap: 5rem;
    align-items: center;
    max-width: 1100px;
    margin: 0 auto;
  }

  #joao-paulo .section-tag { color: var(--black); }
  #joao-paulo .section-tag::before { background: var(--black); }
  #joao-paulo .section-title { color: var(--black); }

  .jp-text p {
    font-size: 0.95rem;
    font-weight: 400;
    color: #3a3a00;
    line-height: 1.8;
    margin-bottom: 1rem;
  }

  .jp-skills {
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
    margin-top: 1.5rem;
  }

  .jp-skill-tag {
    font-family: var(--font-cond);
    font-size: 0.75rem;
    font-weight: 700;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    background: var(--black);
    color: var(--lime);
    padding: 0.35rem 0.85rem;
  }

  .jp-exp {
    display: flex;
    flex-direction: column;
    gap: 1.5rem;
  }

  .exp-item {
    background: var(--black);
    color: var(--white);
    padding: 1.75rem 2rem;
    border-left: 3px solid var(--lime);
  }

  .exp-year {
    font-family: var(--font-cond);
    font-size: 0.7rem;
    font-weight: 600;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--lime);
    margin-bottom: 0.4rem;
  }

  .exp-title {
    font-family: var(--font-cond);
    font-size: 1.05rem;
    font-weight: 700;
    letter-spacing: 0.04em;
    text-transform: uppercase;
    margin-bottom: 0.35rem;
  }

  .exp-desc {
    font-size: 0.85rem;
    color: var(--muted);
    line-height: 1.55;
  }

  /* ─── ATUAÇÃO ─── */
  #atuacao {
    border-top: 1px solid var(--border);
    background: var(--dark);
  }

  .atuacao-inner {
    max-width: 900px;
    margin: 0 auto;
    text-align: center;
  }

  .atuacao-inner .section-tag { justify-content: center; }
  .atuacao-inner .section-tag::before { display: none; }

  .atuacao-desc {
    font-size: 1.05rem;
    color: var(--muted);
    line-height: 1.8;
    margin: 1.5rem 0 3rem;
  }

  .regioes {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 0.75rem;
  }

  .regiao-tag {
    font-family: var(--font-cond);
    font-size: 0.8rem;
    font-weight: 600;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    border: 1px solid var(--border);
    padding: 0.5rem 1.25rem;
    color: var(--muted);
    transition: border-color 0.2s, color 0.2s;
    cursor: default;
  }
  .regiao-tag:hover { border-color: var(--lime); color: var(--lime); }
  .regiao-tag.destaque {
    border-color: var(--lime);
    color: var(--lime);
  }

  .brasil-wrap {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 0.5rem;
    margin-top: 1rem;
  }

  .brasil-label {
    font-family: var(--font-cond);
    font-size: 1rem;
    font-weight: 600;
    letter-spacing: 0.35em;
    text-transform: uppercase;
    color: var(--muted);
  }

  .brasil-main {
    font-family: var(--font-display);
    font-size: clamp(5rem, 12vw, 10rem);
    line-height: 0.9;
    color: var(--lime);
    letter-spacing: 0.04em;
  }

  .brasil-sub {
    font-size: 0.95rem;
    color: var(--muted);
    margin-top: 1rem;
    font-style: italic;
    font-weight: 300;
    letter-spacing: 0.02em;
  }

  /* ─── CONTATO ─── */
  #contato {
    border-top: 1px solid var(--border);
    max-width: 1200px;
    margin: 0 auto;
    padding: 7rem 3rem;
  }

  .contato-grid {
    display: grid;
    grid-template-columns: 1.2fr 1fr;
    gap: 5rem;
    align-items: start;
    max-width: 1100px;
    margin: 0 auto;
  }

  .contato-left .big-cta {
    font-family: var(--font-display);
    font-size: clamp(2.5rem, 4vw, 5rem);
    line-height: 0.95;
    margin: 1.5rem 0 2rem;
  }
  .big-cta .accent { color: var(--lime); }

  .contato-left p {
    font-size: 0.95rem;
    color: var(--muted);
    line-height: 1.75;
    max-width: 420px;
  }

  .contact-links {
    margin-top: 3rem;
    display: flex;
    flex-direction: column;
    gap: 0px;
  }

  .contact-link {
    display: flex;
    align-items: center;
    gap: 1.25rem;
    padding: 1.25rem 0;
    border-bottom: 1px solid var(--border);
    text-decoration: none;
    color: var(--white);
    transition: padding-left 0.3s;
    group: true;
  }
  .contact-link:first-child { border-top: 1px solid var(--border); }
  .contact-link:hover { padding-left: 0.5rem; }

  .cl-icon {
    width: 40px;
    height: 40px;
    background: var(--card);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1.1rem;
    flex-shrink: 0;
    transition: background 0.2s;
  }
  .contact-link:hover .cl-icon { background: var(--lime); }

  .cl-info { flex: 1; }
  .cl-label {
    font-family: var(--font-cond);
    font-size: 0.7rem;
    font-weight: 600;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 0.15rem;
  }
  .cl-value {
    font-size: 0.9rem;
    color: var(--white);
  }

  .cl-arrow {
    color: var(--muted);
    font-size: 1rem;
    transition: color 0.2s, transform 0.2s;
  }
  .contact-link:hover .cl-arrow { color: var(--lime); transform: translateX(4px); }

  /* form side */
  .contato-form {
    background: var(--card);
    border: 1px solid var(--border);
    padding: 2.5rem;
  }

  .form-title {
    font-family: var(--font-cond);
    font-size: 1.2rem;
    font-weight: 700;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    margin-bottom: 2rem;
    padding-bottom: 1rem;
    border-bottom: 1px solid var(--border);
  }

  .form-group {
    margin-bottom: 1.25rem;
  }

  .form-group label {
    display: block;
    font-family: var(--font-cond);
    font-size: 0.7rem;
    font-weight: 600;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 0.5rem;
  }

  .form-group input,
  .form-group select,
  .form-group textarea {
    width: 100%;
    background: var(--black);
    border: 1px solid var(--border);
    color: var(--white);
    font-family: var(--font-body);
    font-size: 0.9rem;
    padding: 0.75rem 1rem;
    outline: none;
    transition: border-color 0.2s;
    resize: vertical;
  }
  .form-group input:focus,
  .form-group select:focus,
  .form-group textarea:focus { border-color: var(--lime); }
  .form-group select option { background: var(--black); }

  .form-submit {
    width: 100%;
    font-family: var(--font-cond);
    font-size: 0.9rem;
    font-weight: 700;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    background: var(--lime);
    color: var(--black);
    border: none;
    padding: 1rem;
    cursor: pointer;
    transition: background 0.2s, transform 0.15s;
    margin-top: 0.5rem;
  }
  .form-submit:hover { background: #d4ff00; transform: translateY(-2px); }

  /* ─── FOOTER ─── */
  footer {
    border-top: 1px solid var(--border);
    padding: 2.5rem 3rem;
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-wrap: wrap;
    gap: 1rem;
  }

  .footer-logo {
    display: flex;
    align-items: center;
    gap: 0.6rem;
    text-decoration: none;
  }
  .footer-wordmark {
    font-family: var(--font-display);
    font-size: 1.1rem;
    letter-spacing: 0.06em;
    color: var(--white);
  }

  .footer-copy {
    font-size: 0.75rem;
    color: var(--muted);
    text-align: center;
  }

  .footer-social {
    display: flex;
    gap: 1rem;
  }
  .footer-social a {
    font-family: var(--font-cond);
    font-size: 0.7rem;
    font-weight: 600;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: var(--muted);
    text-decoration: none;
    transition: color 0.2s;
  }
  .footer-social a:hover { color: var(--lime); }

  /* ─── FADE-IN ANIMATIONS ─── */
  .fade-up {
    opacity: 0;
    transform: translateY(30px);
    transition: opacity 0.7s ease, transform 0.7s ease;
  }
  .fade-up.visible {
    opacity: 1;
    transform: translateY(0);
  }
  .fade-up:nth-child(2) { transition-delay: 0.1s; }
  .fade-up:nth-child(3) { transition-delay: 0.2s; }
  .fade-up:nth-child(4) { transition-delay: 0.3s; }
  .fade-up:nth-child(5) { transition-delay: 0.4s; }

  /* ─── RESPONSIVE ─── */
  @media (max-width: 900px) {
    nav { padding: 1rem 1.5rem; }
    .nav-links { display: none; }

    #hero { grid-template-columns: 1fr; min-height: auto; }
    .hero-left { padding: 7rem 1.5rem 3rem; }
    .hero-right { padding: 3rem 1.5rem; }
    .hero-divider { display: none; }
    .big-symbol { width: 160px; height: 160px; mix-blend-mode: screen; }

    section { padding: 5rem 1.5rem; }

    .sobre-grid,
    .jp-grid,
    .contato-grid,
    .publicos-grid { grid-template-columns: 1fr; gap: 3rem; }

    .services-grid { grid-template-columns: 1fr; }
    .dif-grid { grid-template-columns: 1fr 1fr; }

    footer { flex-direction: column; text-align: center; }

    .services-header { flex-direction: column; }
  }

  @media (max-width: 560px) {
    .dif-grid { grid-template-columns: 1fr; }
    .hero-stats { gap: 1.5rem; }
    .stat-num { font-size: 2rem; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <a href="#hero" class="nav-logo">
    <img src="data:image/png;base64,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" alt="Albano Consultoria" class="nav-logo-img"/>
  </a>
  <ul class="nav-links">
    <li><a href="#sobre">Sobre</a></li>
    <li><a href="#servicos">Serviços</a></li>
    <li><a href="#publicos">Público</a></li>
    <li><a href="#joao-paulo">Quem somos</a></li>
    <li><a href="#contato">Contato</a></li>
  </ul>
  <a href="#contato" class="nav-cta">Solicitar Orçamento</a>
</nav>

<!-- HERO -->
<section id="hero">
  <div class="hero-left">
    <div class="hero-tag">Consultoria Técnica Especializada</div>
    <h1 class="hero-title">
      PRECISÃO<br>
      TÉCNICA<br>
      NO <span class="accent">CAMPO</span><br>
      E NO <span class="accent">ESCRITÓRIO.</span>
    </h1>
    <p class="hero-sub">
      Agrimensura, regularização imobiliária e projetos de infraestrutura urbana — com clareza, organização e proximidade que seu projeto merece.
    </p>
    <div class="hero-actions">
      <a href="#servicos" class="btn-primary">Ver Serviços</a>
      <a href="#contato" class="btn-outline">Falar Conosco</a>
    </div>
    <div class="scroll-hint">
      <div class="scroll-line"></div>
      Role para explorar
    </div>
  </div>

  <div class="hero-right">
    <!-- Topographic SVG background -->
    <svg class="topo-bg" viewBox="0 0 600 600" fill="none" xmlns="http://www.w3.org/2000/svg" preserveAspectRatio="xMidYMid slice">
      <circle cx="300" cy="300" r="50" stroke="#C9F000" stroke-width="1" fill="none"/>
      <circle cx="300" cy="300" r="100" stroke="#C9F000" stroke-width="1" fill="none"/>
      <circle cx="300" cy="300" r="155" stroke="#C9F000" stroke-width="1" fill="none"/>
      <circle cx="300" cy="300" r="215" stroke="#C9F000" stroke-width="1" fill="none"/>
      <circle cx="300" cy="300" r="280" stroke="#C9F000" stroke-width="1" fill="none"/>
      <circle cx="300" cy="300" r="350" stroke="#C9F000" stroke-width="1" fill="none"/>
      <circle cx="300" cy="300" r="425" stroke="#C9F000" stroke-width="1" fill="none"/>
      <!-- cross hairs -->
      <line x1="300" y1="0" x2="300" y2="600" stroke="#C9F000" stroke-width="0.5"/>
      <line x1="0" y1="300" x2="600" y2="300" stroke="#C9F000" stroke-width="0.5"/>
      <!-- diagonal lines -->
      <line x1="0" y1="0" x2="600" y2="600" stroke="#C9F000" stroke-width="0.5"/>
      <line x1="600" y1="0" x2="0" y2="600" stroke="#C9F000" stroke-width="0.5"/>
    </svg>

    <div class="hero-symbol-wrap">
      <!-- Albano Symbol -->
      <img src="data:image/png;base64,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" alt="Albano" class="big-symbol"/>

      <div class="hero-stats">
        <div class="stat">
          <div class="stat-num">10+</div>
          <div class="stat-label">Anos de experiência</div>
        </div>
        <div class="stat">
          <div class="stat-num">3</div>
          <div class="stat-label">Áreas de atuação</div>
        </div>
        <div class="stat">
          <div class="stat-num">100%</div>
          <div class="stat-label">Dedicação Total</div>
        </div>
      </div>
    </div>

    <div class="hero-divider"></div>
  </div>
</section>

<!-- SOBRE -->
<section id="sobre">
  <div class="sobre-grid">
    <div class="sobre-text fade-up">
      <div class="section-tag">Sobre a Empresa</div>
      <h2 class="section-title">TÉCNICA<br>POR NATUREZA.<br>ACESSÍVEL<br>POR ESCOLHA.</h2>
      <p>
        A <strong>Albano Consultoria e Agrimensura</strong> é uma empresa especializada e estruturada para atuar com excelência em agrimensura, regularização imobiliária e projetos de infraestrutura urbana.
      </p>
      <p>
        Nossa atuação é <strong>focada e escalável</strong>: serviços técnicos de alto padrão com atenção individualizada a cada projeto, desde o escritório até o campo, priorizando agilidade e atendimento regional e remoto.
      </p>
      <p>
        A Albano nasceu para ser o <strong>parceiro técnico de referência</strong> que você encontra com facilidade, entende sem dificuldade e confia no resultado. Clareza, organização e rigor técnico em cada entrega.
      </p>
    </div>

    <div class="sobre-highlights fade-up">
      <div class="highlight-item">
        <div class="hi-icon">🎯</div>
        <div>
          <div class="hi-title">Foco Técnico</div>
          <div class="hi-desc">Projetos desenvolvidos com rigor metodológico e atenção aos detalhes normativos.</div>
        </div>
      </div>
      <div class="highlight-item">
        <div class="hi-icon">🌐</div>
        <div>
          <div class="hi-title">Atendimento Remoto</div>
          <div class="hi-desc">Estrutura home-office que permite atender clientes em qualquer região do Brasil.</div>
        </div>
      </div>
      <div class="highlight-item">
        <div class="hi-icon">🤝</div>
        <div>
          <div class="hi-title">Rede de Parceiros</div>
          <div class="hi-desc">Parcerias estratégicas para execução de trabalhos de campo quando necessário.</div>
        </div>
      </div>
      <div class="highlight-item">
        <div class="hi-icon">📐</div>
        <div>
          <div class="hi-title">CAD & Tecnologia</div>
          <div class="hi-desc">Uso intensivo do Civil 3D e ferramentas modernas para projetos precisos e documentados.</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- SERVIÇOS -->
<section id="servicos">
  <div class="services-header fade-up">
    <div>
      <div class="section-tag">O Que Fazemos</div>
      <h2 class="section-title">NOSSOS<br>SERVIÇOS</h2>
    </div>
    <p class="services-intro">
      Soluções técnicas especializadas para clientes finais e para outros profissionais da área.
    </p>
  </div>

  <div class="services-grid">
    <div class="service-card fade-up">
      <div class="service-num">01</div>
      <div class="service-icon">🗺️</div>
      <div class="service-name">Agrimensura</div>
      <p class="service-desc">Levantamentos, georreferenciamento e toda a documentação técnica necessária para a regularização e gestão de imóveis.</p>
      <ul class="service-list">
        <li>Levantamento planialtimétrico cadastral</li>
        <li>Georreferenciamento de imóveis</li>
        <li>Locação de obras</li>
        <li>Cadastro técnico</li>
        <li>Apoio à regularização imobiliária</li>
        <li>Memorial descritivo e plantas técnicas</li>
      </ul>
    </div>

    <div class="service-card fade-up">
      <div class="service-num">02</div>
      <div class="service-icon">🏗️</div>
      <div class="service-name">Infraestrutura Urbana</div>
      <p class="service-desc">Projetos de infraestrutura urbana e estudos técnicos para parcelamento do solo, com foco em qualidade e conformidade técnica.</p>
      <ul class="service-list">
        <li>Projetos de terraplenagem</li>
        <li>Projetos de drenagem pluvial</li>
        <li>Estudos técnicos e apoio ao desenvolvimento de loteamentos</li>
        <li>Compatibilização de projetos</li>
        <li>Quantitativos técnicos</li>
      </ul>
    </div>

    <div class="service-card fade-up">
      <div class="service-num">03</div>
      <div class="service-icon">💻</div>
      <div class="service-name">Suporte Técnico B2B</div>
      <p class="service-desc">Apoio técnico remoto para engenheiros, arquitetos, topógrafos e escritórios que precisam de reforço especializado.</p>
      <ul class="service-list">
        <li>Desenho técnico CAD</li>
        <li>Tratamento de dados de levantamento</li>
        <li>Elaboração de plantas e memoriais</li>
        <li>Organização e padronização de materiais</li>
        <li>Compatibilização de projetos</li>
        <li>Apoio remoto a escritórios</li>
      </ul>
    </div>
  </div>
</section>

<!-- PÚBLICOS -->
<section id="publicos">
  <div style="max-width:1200px;margin:0 auto;">
    <div class="section-tag fade-up">Para Quem Atendemos</div>
    <h2 class="section-title fade-up">DOIS PÚBLICOS,<br>UMA SOLUÇÃO.</h2>

    <div class="publicos-grid">
      <div class="publico-card fade-up">
        <div class="publico-badge">B2C — Cliente Final</div>
        <h3 class="publico-title">Proprietários &amp; Empreendedores</h3>
        <p class="publico-desc">Proprietários, incorporadoras, loteadores e empreendedores que buscam suporte técnico especializado para seus imóveis, empreendimentos e projetos.</p>
        <ul class="publico-items">
          <li><span class="dot"></span>Levantamentos topográficos</li>
          <li><span class="dot"></span>Regularização de imóveis</li>
          <li><span class="dot"></span>Projetos de Infraestrutura</li>
          <li><span class="dot"></span>Apoio técnico em processos imobiliários</li>
        </ul>
        <div class="publico-bg-num">01</div>
      </div>

      <div class="publico-card fade-up">
        <div class="publico-badge">B2B — Profissionais &amp; Escritórios</div>
        <h3 class="publico-title">Parceiros Técnicos &amp; Escritórios Especializados</h3>
        <p class="publico-desc">Um <strong style="color:var(--white)">diferencial estratégico da Albano</strong>: atuamos como braço técnico de engenheiros, arquitetos, topógrafos e escritórios multidisciplinares que precisam de reforço especializado e confiável.</p>
        <ul class="publico-items">
          <li><span class="dot"></span>Elaboração de plantas e memoriais</li>
          <li><span class="dot"></span>Tratamento de dados de levantamento</li>
          <li><span class="dot"></span>Desenhos técnicos CAD</li>
          <li><span class="dot"></span>Compatibilização de projetos</li>
          <li><span class="dot"></span>Organização de materiais técnicos</li>
        </ul>
        <div class="publico-bg-num">02</div>
      </div>
    </div>
  </div>
</section>

<!-- DIFERENCIAIS -->
<section id="diferenciais" style="background:var(--black);border-bottom:1px solid var(--border);">
  <div style="max-width:1200px;margin:0 auto;">
    <div class="section-tag fade-up">Por que a Albano</div>
    <h2 class="section-title fade-up">NOSSOS<br>DIFERENCIAIS</h2>

    <div class="dif-grid">
      <div class="dif-card fade-up">
        <span class="dif-icon">📋</span>
        <div class="dif-title">Clareza Técnica</div>
        <p class="dif-desc">Documentação organizada e linguagem acessível. Entregamos projetos que você entende e que passam nas aprovações.</p>
      </div>
      <div class="dif-card fade-up">
        <span class="dif-icon">🔒</span>
        <div class="dif-title">Confiabilidade</div>
        <p class="dif-desc">Mais de 10 anos de experiência em projetos técnicos de engenharia, infraestrutura urbana e agrimensura.</p>
      </div>
      <div class="dif-card fade-up">
        <span class="dif-icon">🚀</span>
        <div class="dif-title">Agilidade Remota</div>
        <p class="dif-desc">Estrutura de home-office com ferramentas modernas permite entregas rápidas para qualquer região.</p>
      </div>
      <div class="dif-card fade-up">
        <span class="dif-icon">🔧</span>
        <div class="dif-title">Civil 3D &amp; Tecnologias de Projeto</div>
        <p class="dif-desc">Uso avançado de ferramentas como Autodesk Civil 3D, AutoCAD e softwares de análise técnica para entregas precisas e bem documentadas.</p>
      </div>
    </div>
  </div>
</section>

<!-- JOÃO PAULO -->
<section id="joao-paulo">
  <div class="jp-grid">
    <div class="jp-text fade-up">
      <div class="section-tag">Quem está por trás</div>
      <h2 class="section-title">JOÃO PAULO<br>ALBANO</h2>
      <p>
        Profissional com mais de 10 anos de experiência em topografia, regularização de imóveis, projetos técnicos e infraestrutura urbana.
      </p>
      <p>
        Ao longo da carreira, atuou no desenvolvimento de levantamentos topográficos, documentação técnica, compatibilização de projetos e projetos de engenharia em diferentes contextos e escalas.
      </p>
      <p>
        A Albano Consultoria nasce dessa trajetória — da experiência acumulada em campo e escritório — com o objetivo de oferecer serviços técnicos confiáveis, acessíveis e com comunicação clara.
      </p>
      <div class="jp-skills">
        <span class="jp-skill-tag">Civil 3D</span>
        <span class="jp-skill-tag">Agrimensura</span>
        <span class="jp-skill-tag">AutoCAD</span>
        <span class="jp-skill-tag">Geotecnia</span>
        <span class="jp-skill-tag">Regularização</span>
        <span class="jp-skill-tag">Drenagem</span>
        <span class="jp-skill-tag">Terraplenagem</span>
        <span class="jp-skill-tag">Infraestrutura</span>
      </div>
    </div>

    <div class="jp-exp fade-up">
      <div class="exp-item">
        <div class="exp-year">Atual</div>
        <div class="exp-title">Projetista Pleno — Infraestrutura &amp; Geotecnia</div>
        <div class="exp-desc">Desenvolvimento de projetos técnicos complexos nas áreas de infraestrutura e geotecnia, com foco em qualidade, precisão e conformidade técnica.</div>
      </div>
      <div class="exp-item">
        <div class="exp-year">Formação</div>
        <div class="exp-title">Técnico em Agrimensura</div>
        <div class="exp-desc">Base sólida em medições, georreferenciamento, levantamentos e documentação técnica de imóveis.</div>
      </div>
      <div class="exp-item">
        <div class="exp-year">Formação</div>
        <div class="exp-title">Formação Técnica em Informática</div>
        <div class="exp-desc">Base em tecnologia e sistemas que potencializa o domínio de softwares técnicos e ferramentas digitais aplicadas à engenharia.</div>
      </div>
      <div class="exp-item">
        <div class="exp-year">10+ anos</div>
        <div class="exp-title">Projetos Técnicos &amp; CAD</div>
        <div class="exp-desc">Elaboração de projetos, desenhos e modelagem CAD com foco em engenharia e infraestrutura urbana.</div>
      </div>
    </div>
  </div>
</section>

<!-- ATUAÇÃO -->
<section id="atuacao">
  <div class="atuacao-inner fade-up">
    <div class="section-tag">Área de Atuação</div>
    <h2 class="section-title">ATENDEMOS ONDE<br>VOCÊ ESTIVER.</h2>
    <p class="atuacao-desc">
      A Albano tem base em Santa Catarina e atende clientes em todo o território nacional. Projetos técnicos sem fronteiras geográficas — onde o seu negócio precisar, estamos prontos para contribuir.
    </p>
    <div class="brasil-wrap">
      <div class="brasil-label">TODO O</div>
      <div class="brasil-main">BRASIL</div>
      <div class="brasil-sub">Do Sul ao Norte. Do interior ao litoral. Onde o seu projeto estiver, a Albano chega.</div>
    </div>
  </div>
</section>

<!-- CONTATO -->
<section id="contato">
  <div class="contato-grid">
    <div class="contato-left fade-up">
      <div class="section-tag">Entre em Contato</div>
      <h2 class="big-cta">VAMOS<br>TRABALHAR<br>JUNTOS<span class="accent">.</span></h2>
      <p>
        Seja um projeto de regularização, um levantamento topográfico, uma consultoria técnica ou o reforço que o seu escritório precisa — a Albano está pronta para somar ao seu projeto.
      </p>

      <div class="contact-links">
        <a href="https://wa.me/5548984460660" class="contact-link" target="_blank">
          <div class="cl-icon">📱</div>
          <div class="cl-info">
            <div class="cl-label">WhatsApp &amp; Telefone</div>
            <div class="cl-value">(48) 98446-0660</div>
          </div>
          <div class="cl-arrow">→</div>
        </a>
        <a href="mailto:contato@albanoconsultoria.com" class="contact-link">
          <div class="cl-icon">✉️</div>
          <div class="cl-info">
            <div class="cl-label">E-mail</div>
            <div class="cl-value">contato@albanoconsultoria.com</div>
          </div>
          <div class="cl-arrow">→</div>
        </a>
        <a href="http://www.albanoconsultoria.com" class="contact-link" target="_blank">
          <div class="cl-icon">🌐</div>
          <div class="cl-info">
            <div class="cl-label">Site</div>
            <div class="cl-value">www.albanoconsultoria.com</div>
          </div>
          <div class="cl-arrow">→</div>
        </a>
        <a href="https://www.instagram.com/albano.consultoria" class="contact-link" target="_blank">
          <div class="cl-icon">📸</div>
          <div class="cl-info">
            <div class="cl-label">Instagram</div>
            <div class="cl-value">@albano.consultoria</div>
          </div>
          <div class="cl-arrow">→</div>
        </a>
        <a href="https://www.linkedin.com/in/jo%C3%A3o-paulo-albano-24b844123/" class="contact-link" target="_blank">
          <div class="cl-icon">💼</div>
          <div class="cl-info">
            <div class="cl-label">LinkedIn</div>
            <div class="cl-value">João Paulo Albano</div>
          </div>
          <div class="cl-arrow">→</div>
        </a>
      </div>
    </div>

    <div class="contato-form fade-up">
      <div class="form-title">Solicitar Orçamento</div>
      <div class="form-group">
        <label>Nome Completo</label>
        <input type="text" placeholder="Seu nome"/>
      </div>
      <div class="form-group">
        <label>E-mail</label>
        <input type="email" placeholder="seu@email.com"/>
      </div>
      <div class="form-group">
        <label>Telefone / WhatsApp</label>
        <input type="tel" placeholder="(00) 00000-0000"/>
      </div>
      <div class="form-group">
        <label>Tipo de Serviço</label>
        <select>
          <option value="" disabled selected>Selecione um serviço</option>
          <option>Agrimensura / Levantamento</option>
          <option>Regularização Imobiliária</option>
          <option>Projetos de Infraestrutura Urbana</option>
          <option>Suporte Técnico para Escritórios</option>
          <option>Documentação e Projetos CAD</option>
          <option>Compatibilização de Projetos</option>
          <option>Outro</option>
        </select>
      </div>
      <div class="form-group">
        <label>Mensagem</label>
        <textarea rows="4" placeholder="Descreva brevemente sua necessidade..."></textarea>
      </div>
      <button class="form-submit" onclick="handleForm()">Enviar Mensagem →</button>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <a href="#hero" class="footer-logo">
    <img src="data:image/png;base64,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" alt="Albano Consultoria" style="height:28px;width:auto;display:block;mix-blend-mode:screen;"/>
  </a>

  <div class="footer-copy">
    © 2026 Albano Consultoria e Agrimensura · Todos os direitos reservados
  </div>

  <div class="footer-social">
    <a href="https://www.instagram.com/albano.consultoria" target="_blank">Instagram</a>
    <a href="https://www.linkedin.com/in/jo%C3%A3o-paulo-albano-24b844123/" target="_blank">LinkedIn</a>
    <a href="https://wa.me/5548984460660" target="_blank">WhatsApp</a>
  </div>
</footer>

<script>
  // Intersection Observer for fade-up animations
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('visible');
      }
    });
  }, { threshold: 0.1 });

  document.querySelectorAll('.fade-up').forEach(el => observer.observe(el));

  // Nav shrink on scroll
  window.addEventListener('scroll', () => {
    const nav = document.querySelector('nav');
    if (window.scrollY > 60) {
      nav.style.padding = '0.75rem 3rem';
    } else {
      nav.style.padding = '1.25rem 3rem';
    }
  });

  // Form handler (redirects to WhatsApp)
  function handleForm() {
    const name = document.querySelector('input[type="text"]').value;
    const service = document.querySelector('select').value;
    const msg = document.querySelector('textarea').value;

    if (!name || !service) {
      alert('Por favor, preencha ao menos nome e tipo de serviço.');
      return;
    }

    const text = encodeURIComponent(
      `Olá! Me chamo ${name}.\n\nGostaria de solicitar orçamento para: ${service}.\n\n${msg}`
    );
    window.open(`https://wa.me/5548984460660?text=${text}`, '_blank');
  }
</script>
</body>
</html>
