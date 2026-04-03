# Cloud_Coffee_Cafe
Website for a cafe in maitidevi.
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Coffee Cloud Café — Kathmandu</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;0,900;1,400&family=DM+Sans:wght@300;400;500&family=Bebas+Neue&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --black: #0a0a0a;
    --white: #f5f0eb;
    --red: #c0392b;
    --red-dark: #922b21;
    --gray: #1e1e1e;
    --gray-light: #2d2d2d;
    --text-muted: #888;
  }

  html { scroll-behavior: smooth; }

  body {
    background: var(--black);
    color: var(--white);
    font-family: 'DM Sans', sans-serif;
    overflow-x: hidden;
  }

  /* ── NAV ── */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    display: flex; align-items: center; justify-content: space-between;
    padding: 1.4rem 3rem;
    background: rgba(10,10,10,0.85);
    backdrop-filter: blur(12px);
    border-bottom: 1px solid rgba(192,57,43,0.2);
  }
  .nav-logo {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 1.8rem;
    letter-spacing: 3px;
    color: var(--white);
    text-decoration: none;
  }
  .nav-logo span { color: var(--red); }
  .nav-links { display: flex; gap: 2.5rem; list-style: none; }
  .nav-links a {
    color: var(--text-muted);
    text-decoration: none;
    font-size: 0.85rem;
    font-weight: 500;
    letter-spacing: 1.5px;
    text-transform: uppercase;
    transition: color 0.25s;
  }
  .nav-links a:hover { color: var(--red); }
  .nav-cta {
    background: var(--red);
    color: var(--white);
    border: none;
    padding: 0.65rem 1.8rem;
    font-family: 'DM Sans', sans-serif;
    font-size: 0.8rem;
    font-weight: 500;
    letter-spacing: 1.5px;
    text-transform: uppercase;
    cursor: pointer;
    transition: background 0.25s;
  }
  .nav-cta:hover { background: var(--red-dark); }

  /* ── HERO ── */
  #hero {
    min-height: 100vh;
    display: grid;
    grid-template-columns: 1fr 1fr;
    position: relative;
    overflow: hidden;
  }
  .hero-left {
    display: flex; flex-direction: column; justify-content: center;
    padding: 8rem 4rem 4rem 6rem;
    position: relative; z-index: 2;
  }
  .hero-badge {
    display: inline-flex; align-items: center; gap: 0.5rem;
    background: rgba(192,57,43,0.15);
    border: 1px solid rgba(192,57,43,0.4);
    color: var(--red);
    font-size: 0.75rem;
    font-weight: 500;
    letter-spacing: 2px;
    text-transform: uppercase;
    padding: 0.4rem 1rem;
    margin-bottom: 2rem;
    width: fit-content;
  }
  .hero-badge::before { content: '●'; font-size: 0.5rem; }
  .hero-title {
    font-family: 'Playfair Display', serif;
    font-size: clamp(3.5rem, 6vw, 7rem);
    line-height: 1.0;
    font-weight: 900;
    margin-bottom: 1.5rem;
  }
  .hero-title em { color: var(--red); font-style: italic; }
  .hero-sub {
    color: var(--text-muted);
    font-size: 1.05rem;
    line-height: 1.7;
    max-width: 420px;
    margin-bottom: 3rem;
  }
  .hero-actions { display: flex; gap: 1.2rem; align-items: center; }
  .btn-primary {
    background: var(--red);
    color: var(--white);
    border: none;
    padding: 1rem 2.5rem;
    font-family: 'DM Sans', sans-serif;
    font-size: 0.9rem;
    font-weight: 500;
    letter-spacing: 1px;
    text-transform: uppercase;
    cursor: pointer;
    text-decoration: none;
    display: inline-block;
    transition: background 0.25s, transform 0.2s;
  }
  .btn-primary:hover { background: var(--red-dark); transform: translateY(-2px); }
  .btn-outline {
    background: transparent;
    color: var(--white);
    border: 1px solid rgba(245,240,235,0.3);
    padding: 1rem 2.5rem;
    font-family: 'DM Sans', sans-serif;
    font-size: 0.9rem;
    font-weight: 400;
    letter-spacing: 1px;
    text-transform: uppercase;
    cursor: pointer;
    text-decoration: none;
    display: inline-block;
    transition: border-color 0.25s, color 0.25s;
  }
  .btn-outline:hover { border-color: var(--red); color: var(--red); }
  .hero-stats {
    display: flex; gap: 3rem; margin-top: 4rem;
    padding-top: 2.5rem;
    border-top: 1px solid rgba(245,240,235,0.1);
  }
  .stat-val {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 2.8rem;
    color: var(--white);
    line-height: 1;
  }
  .stat-val span { color: var(--red); }
  .stat-label {
    font-size: 0.75rem;
    color: var(--text-muted);
    letter-spacing: 1px;
    text-transform: uppercase;
    margin-top: 0.3rem;
  }

  .hero-right {
    position: relative; overflow: hidden;
  }
  .hero-visual {
    width: 100%; height: 100%;
    background:
      radial-gradient(ellipse at 30% 40%, rgba(192,57,43,0.35) 0%, transparent 55%),
      radial-gradient(ellipse at 80% 80%, rgba(192,57,43,0.15) 0%, transparent 50%),
      #111;
    display: flex; align-items: center; justify-content: center;
    position: relative;
  }
  /* Big decorative coffee cup SVG */
  .cup-wrap {
    position: relative; z-index: 2;
  }
  .cup-wrap svg { width: 340px; height: 340px; filter: drop-shadow(0 0 60px rgba(192,57,43,0.5)); }
  .hero-grain {
    position: absolute; inset: 0; z-index: 1;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.04'/%3E%3C/svg%3E");
    pointer-events: none; opacity: 0.5;
  }
  .floating-tag {
    position: absolute;
    background: var(--black);
    border: 1px solid rgba(192,57,43,0.4);
    padding: 0.8rem 1.2rem;
    font-size: 0.8rem;
    letter-spacing: 1px;
    animation: float 4s ease-in-out infinite;
  }
  .floating-tag:nth-child(3) { top: 20%; left: 5%; animation-delay: 0s; }
  .floating-tag:nth-child(4) { bottom: 25%; right: 5%; animation-delay: 2s; }
  @keyframes float {
    0%,100% { transform: translateY(0); }
    50% { transform: translateY(-10px); }
  }

  /* ── MARQUEE ── */
  .marquee-wrap {
    background: var(--red);
    overflow: hidden;
    padding: 0.9rem 0;
    border-top: 1px solid var(--red-dark);
    border-bottom: 1px solid var(--red-dark);
  }
  .marquee {
    display: flex; gap: 0;
    white-space: nowrap;
    animation: marquee 22s linear infinite;
  }
  .marquee span {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 1.1rem;
    letter-spacing: 3px;
    padding: 0 2.5rem;
    color: rgba(245,240,235,0.9);
  }
  .marquee span.dot { color: rgba(245,240,235,0.5); padding: 0 0.5rem; }
  @keyframes marquee {
    from { transform: translateX(0); }
    to { transform: translateX(-50%); }
  }

  /* ── ABOUT ── */
  #about {
    display: grid; grid-template-columns: 1fr 1fr;
    gap: 0; min-height: 80vh;
  }
  .about-img {
    background:
      linear-gradient(135deg, rgba(192,57,43,0.2) 0%, transparent 60%),
      #1a1a1a;
    display: flex; align-items: center; justify-content: center;
    padding: 4rem;
    position: relative; overflow: hidden;
  }
  .about-img::after {
    content: '';
    position: absolute; inset: 0;
    background: repeating-linear-gradient(
      45deg,
      transparent,
      transparent 40px,
      rgba(192,57,43,0.04) 40px,
      rgba(192,57,43,0.04) 41px
    );
  }
  .about-img-inner {
    width: 280px; height: 280px;
    border: 2px solid rgba(192,57,43,0.5);
    border-radius: 50%;
    display: flex; align-items: center; justify-content: center;
    position: relative; z-index: 2;
    background: radial-gradient(circle, rgba(192,57,43,0.15), transparent);
  }
  .about-img-inner svg { width: 160px; height: 160px; }
  .about-content {
    background: var(--gray);
    padding: 6rem 5rem;
    display: flex; flex-direction: column; justify-content: center;
  }
  .section-tag {
    font-size: 0.7rem;
    font-weight: 500;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: var(--red);
    margin-bottom: 1.5rem;
  }
  .section-title {
    font-family: 'Playfair Display', serif;
    font-size: clamp(2rem, 3.5vw, 3.5rem);
    line-height: 1.15;
    margin-bottom: 1.5rem;
  }
  .section-title em { color: var(--red); font-style: italic; }
  .section-body {
    color: var(--text-muted);
    line-height: 1.8;
    font-size: 0.95rem;
    max-width: 480px;
    margin-bottom: 2.5rem;
  }
  .detail-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; margin-top: 2rem; }
  .detail-item { border-left: 2px solid var(--red); padding-left: 1rem; }
  .detail-label { font-size: 0.7rem; text-transform: uppercase; letter-spacing: 2px; color: var(--text-muted); margin-bottom: 0.3rem; }
  .detail-val { font-size: 0.9rem; font-weight: 500; color: var(--white); }

  /* ── MENU ── */
  #menu {
    padding: 8rem 6rem;
    background: var(--black);
  }
  .menu-header {
    display: flex; align-items: flex-end; justify-content: space-between;
    margin-bottom: 4rem;
  }
  .menu-title { font-family: 'Playfair Display', serif; font-size: clamp(2.5rem, 4vw, 4.5rem); }
  .menu-title em { color: var(--red); font-style: italic; }
  .menu-note { color: var(--text-muted); font-size: 0.85rem; max-width: 260px; text-align: right; line-height: 1.6; }
  .menu-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1.5px;
    background: rgba(245,240,235,0.07);
  }
  .menu-item {
    background: var(--black);
    padding: 2.5rem;
    position: relative;
    overflow: hidden;
    transition: background 0.3s;
    cursor: default;
  }
  .menu-item::before {
    content: '';
    position: absolute; left: 0; top: 0; bottom: 0; width: 3px;
    background: var(--red);
    transform: scaleY(0); transform-origin: bottom;
    transition: transform 0.3s;
  }
  .menu-item:hover { background: var(--gray); }
  .menu-item:hover::before { transform: scaleY(1); }
  .menu-item-icon { font-size: 2rem; margin-bottom: 1.2rem; }
  .menu-item-name {
    font-family: 'Playfair Display', serif;
    font-size: 1.3rem;
    font-weight: 700;
    margin-bottom: 0.5rem;
  }
  .menu-item-desc { color: var(--text-muted); font-size: 0.82rem; line-height: 1.6; }

  /* ── REVIEWS ── */
  #reviews {
    padding: 8rem 6rem;
    background: var(--gray);
  }
  .reviews-header { text-align: center; margin-bottom: 5rem; }
  .rating-big {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 8rem;
    color: var(--white);
    line-height: 1;
  }
  .rating-big span { color: var(--red); }
  .stars { color: var(--red); font-size: 1.5rem; letter-spacing: 3px; margin: 0.5rem 0; }
  .rating-note { color: var(--text-muted); font-size: 0.85rem; letter-spacing: 2px; text-transform: uppercase; }
  .reviews-grid {
    display: grid; grid-template-columns: repeat(3, 1fr); gap: 1.5rem;
    margin-top: 4rem;
  }
  .review-card {
    background: var(--black);
    padding: 2rem;
    border-top: 2px solid var(--red);
    transition: transform 0.2s;
  }
  .review-card:hover { transform: translateY(-4px); }
  .review-quote {
    font-family: 'Playfair Display', serif;
    font-size: 3rem;
    color: var(--red);
    line-height: 0.5;
    margin-bottom: 1rem;
  }
  .review-text { font-size: 0.88rem; line-height: 1.7; color: var(--text-muted); margin-bottom: 1.5rem; }
  .review-author { font-size: 0.78rem; font-weight: 500; letter-spacing: 1px; text-transform: uppercase; }
  .review-meta { font-size: 0.72rem; color: var(--text-muted); margin-top: 0.2rem; }

  /* ── HOURS & LOCATION ── */
  #visit {
    display: grid; grid-template-columns: 1fr 1fr;
    min-height: 60vh;
  }
  .visit-info {
    background: var(--black);
    padding: 6rem;
    display: flex; flex-direction: column; justify-content: center;
  }
  .hours-list { list-style: none; margin-top: 2rem; }
  .hours-list li {
    display: flex; justify-content: space-between;
    padding: 0.9rem 0;
    border-bottom: 1px solid rgba(245,240,235,0.08);
    font-size: 0.9rem;
  }
  .hours-list li .day { color: var(--text-muted); }
  .hours-list li .time { color: var(--white); font-weight: 500; }
  .open-badge {
    display: inline-flex; align-items: center; gap: 0.5rem;
    color: #27ae60; font-size: 0.8rem; font-weight: 500;
    letter-spacing: 1px; text-transform: uppercase;
    margin-top: 1.5rem;
  }
  .open-badge::before { content: '●'; font-size: 0.6rem; animation: pulse 2s ease-in-out infinite; }
  @keyframes pulse { 0%,100% { opacity:1; } 50% { opacity:0.3; } }

  .visit-map {
    background:
      linear-gradient(180deg, rgba(192,57,43,0.1) 0%, transparent 100%),
      #1a1a1a;
    display: flex; flex-direction: column; align-items: center; justify-content: center;
    padding: 4rem;
    gap: 2rem;
  }
  .map-box {
    width: 100%; max-width: 440px; aspect-ratio: 4/3;
    background: #111;
    border: 1px solid rgba(192,57,43,0.3);
    display: flex; align-items: center; justify-content: center;
    position: relative; overflow: hidden;
  }
  /* Simple map illustration */
  .map-box svg { width: 100%; height: 100%; }
  .address-card {
    width: 100%; max-width: 440px;
    background: var(--gray);
    padding: 1.5rem 2rem;
    display: flex; gap: 1rem; align-items: flex-start;
  }
  .address-icon { color: var(--red); font-size: 1.4rem; flex-shrink: 0; margin-top: 2px; }
  .address-text h4 { font-size: 0.85rem; font-weight: 600; margin-bottom: 0.3rem; }
  .address-text p { font-size: 0.8rem; color: var(--text-muted); line-height: 1.5; }
  .phone-link {
    display: inline-block; margin-top: 0.5rem;
    color: var(--red); font-size: 0.82rem; text-decoration: none;
    letter-spacing: 1px;
    transition: opacity 0.2s;
  }
  .phone-link:hover { opacity: 0.7; }

  /* ── FOOTER ── */
  footer {
    background: var(--gray);
    border-top: 1px solid rgba(192,57,43,0.3);
    padding: 4rem 6rem 2.5rem;
  }
  .footer-top {
    display: grid; grid-template-columns: 2fr 1fr 1fr 1fr;
    gap: 4rem; padding-bottom: 3rem;
    border-bottom: 1px solid rgba(245,240,235,0.08);
  }
  .footer-brand h2 {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 2.2rem; letter-spacing: 3px; margin-bottom: 1rem;
  }
  .footer-brand h2 span { color: var(--red); }
  .footer-brand p { color: var(--text-muted); font-size: 0.85rem; line-height: 1.7; max-width: 300px; }
  .footer-col h4 { font-size: 0.72rem; letter-spacing: 2px; text-transform: uppercase; color: var(--red); margin-bottom: 1.2rem; }
  .footer-col ul { list-style: none; }
  .footer-col ul li { margin-bottom: 0.6rem; }
  .footer-col ul li a { color: var(--text-muted); text-decoration: none; font-size: 0.85rem; transition: color 0.2s; }
  .footer-col ul li a:hover { color: var(--white); }
  .footer-bottom {
    display: flex; justify-content: space-between; align-items: center;
    padding-top: 2rem; font-size: 0.75rem; color: var(--text-muted);
  }
  .footer-bottom a { color: var(--red); text-decoration: none; }

  /* ── MOBILE ── */
  .hamburger { display: none; flex-direction: column; gap: 5px; cursor: pointer; }
  .hamburger span { width: 24px; height: 2px; background: var(--white); display: block; }

  @media (max-width: 900px) {
    nav { padding: 1.2rem 1.5rem; }
    .nav-links, .nav-cta { display: none; }
    .hamburger { display: flex; }
    #hero { grid-template-columns: 1fr; min-height: auto; }
    .hero-left { padding: 7rem 1.8rem 3rem; }
    .hero-right { height: 320px; }
    .hero-stats { gap: 1.5rem; flex-wrap: wrap; }
    #about { grid-template-columns: 1fr; }
    .about-img { height: 280px; }
    .about-content { padding: 4rem 1.8rem; }
    #menu { padding: 5rem 1.8rem; }
    .menu-header { flex-direction: column; align-items: flex-start; gap: 1rem; }
    .menu-note { text-align: left; }
    .menu-grid { grid-template-columns: 1fr; }
    #reviews { padding: 5rem 1.8rem; }
    .reviews-grid { grid-template-columns: 1fr; }
    #visit { grid-template-columns: 1fr; }
    .visit-info { padding: 4rem 1.8rem; }
    footer { padding: 3rem 1.8rem 2rem; }
    .footer-top { grid-template-columns: 1fr; gap: 2rem; }
    .footer-bottom { flex-direction: column; gap: 0.5rem; text-align: center; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <a class="nav-logo" href="#"><span>☁</span> COFFEE CLOUD</a>
  <ul class="nav-links">
    <li><a href="#about">About</a></li>
    <li><a href="#menu">Menu</a></li>
    <li><a href="#reviews">Reviews</a></li>
    <li><a href="#visit">Visit</a></li>
  </ul>
  <button class="nav-cta" onclick="document.getElementById('visit').scrollIntoView({behavior:'smooth'})">Find Us</button>
  <div class="hamburger" onclick="this.classList.toggle('open')">
    <span></span><span></span><span></span>
  </div>
</nav>

<!-- HERO -->
<section id="hero">
  <div class="hero-left">
    <div class="hero-badge">Now Open · Closes 8 PM</div>
    <h1 class="hero-title">
      Where<br>
      Every Cup<br>
      Tells a <em>Story</em>
    </h1>
    <p class="hero-sub">
      Tucked inside LBEF College, Maitidevi — your neighbourhood cloud of calm. Specialty coffee, cozy bites & warm company.
    </p>
    <div class="hero-actions">
      <a href="#menu" class="btn-primary">Explore Menu</a>
      <a href="#visit" class="btn-outline">Get Directions</a>
    </div>
    <div class="hero-stats">
      <div>
        <div class="stat-val">3<span>.7</span></div>
        <div class="stat-label">Google Rating</div>
      </div>
      <div>
        <div class="stat-val">6<span>+</span></div>
        <div class="stat-label">Years Open</div>
      </div>
      <div>
        <div class="stat-val">13</div>
        <div class="stat-label">Reviews</div>
      </div>
    </div>
  </div>
  <div class="hero-right">
    <div class="hero-visual">
      <div class="hero-grain"></div>
      <div class="floating-tag">☕ Specialty Coffee</div>
      <div class="floating-tag">🌶 Kothe Momo</div>
      <div class="cup-wrap">
        <!-- Decorative SVG Coffee Cup -->
        <svg viewBox="0 0 300 300" fill="none" xmlns="http://www.w3.org/2000/svg">
          <!-- Steam -->
          <path d="M100 70 Q95 50 100 30 Q105 10 100 0" stroke="#c0392b" stroke-width="2.5" stroke-linecap="round" opacity="0.7"/>
          <path d="M150 60 Q145 38 150 18 Q155 0 150 -10" stroke="#c0392b" stroke-width="2.5" stroke-linecap="round" opacity="0.5"/>
          <path d="M200 70 Q195 50 200 30 Q205 10 200 0" stroke="#c0392b" stroke-width="2.5" stroke-linecap="round" opacity="0.7"/>
          <!-- Cup body -->
          <path d="M60 100 L80 240 Q82 258 100 258 L200 258 Q218 258 220 240 L240 100 Z" fill="#1e1e1e" stroke="#c0392b" stroke-width="2"/>
          <!-- Coffee liquid top -->
          <ellipse cx="150" cy="100" rx="90" ry="20" fill="#3d1a0a"/>
          <ellipse cx="150" cy="100" rx="85" ry="16" fill="#5a2a10"/>
          <!-- Latte art swirl -->
          <path d="M120 100 Q135 88 150 100 Q165 112 180 100" stroke="#c9956a" stroke-width="2" stroke-linecap="round" fill="none" opacity="0.8"/>
          <ellipse cx="150" cy="100" rx="18" ry="8" fill="#c9956a" opacity="0.4"/>
          <!-- Handle -->
          <path d="M238 130 Q275 130 275 165 Q275 200 238 200" stroke="#c0392b" stroke-width="3" fill="none" stroke-linecap="round"/>
          <!-- Saucer -->
          <ellipse cx="150" cy="265" rx="110" ry="16" fill="#1e1e1e" stroke="#c0392b" stroke-width="1.5"/>
          <ellipse cx="150" cy="262" rx="95" ry="11" fill="#161616"/>
          <!-- Cloud logo on cup -->
          <text x="120" y="180" font-family="serif" font-size="13" fill="#c0392b" opacity="0.6">☁ CLOUD</text>
        </svg>
      </div>
    </div>
  </div>
</section>

<!-- MARQUEE -->
<div class="marquee-wrap">
  <div class="marquee">
    <span>SPECIALTY COFFEE</span><span class="dot">✦</span>
    <span>KOTHE MOMO</span><span class="dot">✦</span>
    <span>OREO SHAKE</span><span class="dot">✦</span>
    <span>FRENCH FRIES</span><span class="dot">✦</span>
    <span>CARDAMOM TEA</span><span class="dot">✦</span>
    <span>NACHOS WITH CHEESE</span><span class="dot">✦</span>
    <span>OPEN DAILY TILL 8 PM</span><span class="dot">✦</span>
    <span>MAITIDEVI, KATHMANDU</span><span class="dot">✦</span>
    <!-- duplicate for infinite loop -->
    <span>SPECIALTY COFFEE</span><span class="dot">✦</span>
    <span>KOTHE MOMO</span><span class="dot">✦</span>
    <span>OREO SHAKE</span><span class="dot">✦</span>
    <span>FRENCH FRIES</span><span class="dot">✦</span>
    <span>CARDAMOM TEA</span><span class="dot">✦</span>
    <span>NACHOS WITH CHEESE</span><span class="dot">✦</span>
    <span>OPEN DAILY TILL 8 PM</span><span class="dot">✦</span>
    <span>MAITIDEVI, KATHMANDU</span><span class="dot">✦</span>
  </div>
</div>

<!-- ABOUT -->
<section id="about">
  <div class="about-img">
    <div class="about-img-inner">
      <svg viewBox="0 0 160 160" fill="none" xmlns="http://www.w3.org/2000/svg">
        <!-- cloud + cup combo icon -->
        <path d="M30 75 Q25 45 55 42 Q58 22 80 22 Q102 22 105 42 Q135 45 130 75 Q128 90 110 90 L50 90 Q32 90 30 75Z" fill="#c0392b" opacity="0.15" stroke="#c0392b" stroke-width="1.5"/>
        <rect x="55" y="85" width="50" height="45" rx="6" fill="#c0392b" opacity="0.8"/>
        <path d="M102 100 Q118 100 118 115 Q118 130 102 130" stroke="white" stroke-width="2" fill="none"/>
        <rect x="45" y="130" width="70" height="8" rx="4" fill="#c0392b" opacity="0.5"/>
        <text x="68" y="115" font-family="serif" font-size="10" fill="white" opacity="0.9">☁</text>
      </svg>
    </div>
  </div>
  <div class="about-content">
    <div class="section-tag">Our Story</div>
    <h2 class="section-title">A <em>Cozy Cloud</em><br>Above the City</h2>
    <p class="section-body">
      Nestled inside the Lord Buddha Education Foundation (LBEF College) — Nepal's first IT college — Coffee Cloud Café has been a beloved retreat for students, professionals, and locals near Maitidevi Temple for over six years. We serve great coffee, quick bites, and genuine warmth.
    </p>
    <p class="section-body">
      Whether you're winding down after a walk to a Kathmandu landmark or looking for a clean, casual spot with outdoor seating — Coffee Cloud is your corner of calm.
    </p>
    <div class="detail-grid">
      <div class="detail-item">
        <div class="detail-label">Location</div>
        <div class="detail-val">Maitidevi, Kathmandu</div>
      </div>
      <div class="detail-item">
        <div class="detail-label">Hours</div>
        <div class="detail-val">Until 8:00 PM</div>
      </div>
      <div class="detail-item">
        <div class="detail-label">Seating</div>
        <div class="detail-val">Indoor + Outdoor</div>
      </div>
      <div class="detail-item">
        <div class="detail-label">Phone</div>
        <div class="detail-val">986-0886259</div>
      </div>
    </div>
  </div>
</section>

<!-- MENU -->
<section id="menu">
  <div class="menu-header">
    <h2 class="menu-title">Our <em>Menu</em></h2>
    <p class="menu-note">Crafted with care, served with a smile. Something for every craving.</p>
  </div>
  <div class="menu-grid">
    <div class="menu-item">
      <div class="menu-item-icon">☕</div>
      <div class="menu-item-name">Coffee</div>
      <div class="menu-item-desc">Rich, aromatic blends brewed fresh every morning. Our signature specialty.</div>
    </div>
    <div class="menu-item">
      <div class="menu-item-icon">🍵</div>
      <div class="menu-item-name">Cardamom Tea</div>
      <div class="menu-item-desc">A warm, spiced Nepali classic — fragrant elaichi tea brewed to perfection.</div>
    </div>
    <div class="menu-item">
      <div class="menu-item-icon">🥤</div>
      <div class="menu-item-name">Oreo Shake</div>
      <div class="menu-item-desc">Thick, creamy Oreo milkshake — the crowd favourite for sweet indulgence.</div>
    </div>
    <div class="menu-item">
      <div class="menu-item-icon">🍟</div>
      <div class="menu-item-name">French Fries</div>
      <div class="menu-item-desc">Golden, crispy fries — the perfect companion to your coffee or shake.</div>
    </div>
    <div class="menu-item">
      <div class="menu-item-icon">🧀</div>
      <div class="menu-item-name">Nachos with Cheese</div>
      <div class="menu-item-desc">Crunchy nachos loaded with melted cheese. A great snack for groups.</div>
    </div>
    <div class="menu-item">
      <div class="menu-item-icon">🥟</div>
      <div class="menu-item-name">Kothe Momo</div>
      <div class="menu-item-desc">Pan-fried dumplings — crispy outside, juicy inside. A Nepali street food favourite.</div>
    </div>
  </div>
</section>

<!-- REVIEWS -->
<section id="reviews">
  <div class="reviews-header">
    <div class="rating-big">3<span>.7</span></div>
    <div class="stars">★★★★☆</div>
    <div class="rating-note">Based on 13 Google Reviews</div>
  </div>
  <div class="reviews-grid">
    <div class="review-card">
      <div class="review-quote">"</div>
      <p class="review-text">Cozy and clean place managed properly with outdoor seating too. Food is great and the service is really good.</p>
      <div class="review-author">Bibek Thapaliya</div>
      <div class="review-meta">Local Guide · 195 reviews</div>
    </div>
    <div class="review-card">
      <div class="review-quote">"</div>
      <p class="review-text">Good café around the Maitidevi temple area. Generally not crowded and the food and coffee are very enjoyable.</p>
      <div class="review-author">Diw Mishra</div>
      <div class="review-meta">Local Guide · 32 reviews</div>
    </div>
    <div class="review-card">
      <div class="review-quote">"</div>
      <p class="review-text">One of the good places around Maitidevi area. Convenient location with lots of spaces — a great spot to relax.</p>
      <div class="review-author">Anup Acharya</div>
      <div class="review-meta">Local Guide · 177 reviews</div>
    </div>
    <div class="review-card">
      <div class="review-quote">"</div>
      <p class="review-text">Great coffee shop to wind down after a long walk to the tourist attractions around the area. Very relaxing vibe.</p>
      <div class="review-author">T Rider</div>
      <div class="review-meta">Local Guide · 19 reviews</div>
    </div>
    <div class="review-card">
      <div class="review-quote">"</div>
      <p class="review-text">I had a great time there. Would definitely recommend to friends looking for a chill café near Maitidevi.</p>
      <div class="review-author">Sagar Panthi</div>
      <div class="review-meta">Local Guide · 48 reviews</div>
    </div>
    <div class="review-card" style="background:rgba(192,57,43,0.08); border-top-color: rgba(192,57,43,0.5);">
      <div class="review-quote" style="color:rgba(192,57,43,0.4)">"</div>
      <p class="review-text">We value every piece of feedback. We're constantly working to improve our menu availability, speed, and service quality. Thank you for visiting.</p>
      <div class="review-author" style="color:var(--red)">Coffee Cloud Café</div>
      <div class="review-meta">Our commitment to you</div>
    </div>
  </div>
</section>

<!-- VISIT -->
<section id="visit">
  <div class="visit-info">
    <div class="section-tag">Find Us</div>
    <h2 class="section-title">Come <em>Visit</em></h2>
    <p class="section-body">We're open every day near Maitidevi Temple. Walk in anytime — no reservation needed.</p>
    <ul class="hours-list">
      <li><span class="day">Monday – Friday</span><span class="time">Morning – 8:00 PM</span></li>
      <li><span class="day">Saturday</span><span class="time">Morning – 8:00 PM</span></li>
      <li><span class="day">Sunday</span><span class="time">Morning – 8:00 PM</span></li>
    </ul>
    <div class="open-badge">Currently Open</div>
  </div>
  <div class="visit-map">
    <div class="map-box">
      <!-- Illustrative simple map graphic -->
      <svg viewBox="0 0 400 300" xmlns="http://www.w3.org/2000/svg">
        <rect width="400" height="300" fill="#111"/>
        <!-- Grid lines -->
        <line x1="0" y1="75" x2="400" y2="75" stroke="#222" stroke-width="1"/>
        <line x1="0" y1="150" x2="400" y2="150" stroke="#222" stroke-width="1"/>
        <line x1="0" y1="225" x2="400" y2="225" stroke="#222" stroke-width="1"/>
        <line x1="100" y1="0" x2="100" y2="300" stroke="#222" stroke-width="1"/>
        <line x1="200" y1="0" x2="200" y2="300" stroke="#222" stroke-width="1"/>
        <line x1="300" y1="0" x2="300" y2="300" stroke="#222" stroke-width="1"/>
        <!-- Road -->
        <rect x="160" y="0" width="40" height="300" fill="#1e1e1e" stroke="#2a2a2a" stroke-width="1"/>
        <rect x="0" y="120" width="400" height="30" fill="#1e1e1e" stroke="#2a2a2a" stroke-width="1"/>
        <!-- Road center lines -->
        <line x1="180" y1="0" x2="180" y2="120" stroke="#333" stroke-width="1" stroke-dasharray="10,8"/>
        <line x1="180" y1="150" x2="180" y2="300" stroke="#333" stroke-width="1" stroke-dasharray="10,8"/>
        <line x1="0" y1="135" x2="160" y2="135" stroke="#333" stroke-width="1" stroke-dasharray="10,8"/>
        <line x1="200" y1="135" x2="400" y2="135" stroke="#333" stroke-width="1" stroke-dasharray="10,8"/>
        <!-- Buildings -->
        <rect x="15" y="15" width="60" height="80" rx="2" fill="#1a1a1a" stroke="#2d2d2d" stroke-width="1"/>
        <rect x="220" y="15" width="55" height="70" rx="2" fill="#1a1a1a" stroke="#2d2d2d" stroke-width="1"/>
        <rect x="290" y="15" width="95" height="90" rx="2" fill="#1a1a1a" stroke="#2d2d2d" stroke-width="1"/>
        <rect x="15" y="165" width="80" height="100" rx="2" fill="#1a1a1a" stroke="#2d2d2d" stroke-width="1"/>
        <rect x="220" y="165" width="60" height="80" rx="2" fill="#1a1a1a" stroke="#2d2d2d" stroke-width="1"/>
        <rect x="300" y="165" width="80" height="110" rx="2" fill="#1a1a1a" stroke="#2d2d2d" stroke-width="1"/>
        <!-- LBEF College block -->
        <rect x="85" y="165" width="70" height="100" rx="2" fill="#1e1210" stroke="#c0392b" stroke-width="1.5"/>
        <text x="120" y="205" font-family="sans-serif" font-size="7" fill="#c0392b" text-anchor="middle">LBEF</text>
        <text x="120" y="215" font-family="sans-serif" font-size="6" fill="#888" text-anchor="middle">College</text>
        <!-- Pin -->
        <circle cx="120" cy="150" r="14" fill="#c0392b"/>
        <circle cx="120" cy="148" r="7" fill="white"/>
        <circle cx="120" cy="148" r="3" fill="#c0392b"/>
        <polygon points="120,162 114,150 126,150" fill="#c0392b"/>
        <!-- Label -->
        <rect x="130" y="138" width="90" height="24" rx="3" fill="#c0392b"/>
        <text x="175" y="154" font-family="sans-serif" font-size="9" fill="white" text-anchor="middle" font-weight="bold">☁ Coffee Cloud</text>
      </svg>
    </div>
    <div class="address-card">
      <div class="address-icon">📍</div>
      <div class="address-text">
        <h4>Coffee Cloud Café</h4>
        <p>P84M+9CH, Maitidevi<br>Kathmandu 44600, Nepal<br>Inside LBEF College Campus</p>
        <a href="tel:9860886259" class="phone-link">📞 986-0886259</a>
      </div>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-top">
    <div class="footer-brand">
      <h2><span>☁</span> COFFEE CLOUD</h2>
      <p>Your cozy corner above the city. Specialty coffee, hearty bites & warm company — near Maitidevi Temple, Kathmandu.</p>
    </div>
    <div class="footer-col">
      <h4>Menu</h4>
      <ul>
        <li><a href="#menu">Coffee</a></li>
        <li><a href="#menu">Cardamom Tea</a></li>
        <li><a href="#menu">Oreo Shake</a></li>
        <li><a href="#menu">French Fries</a></li>
        <li><a href="#menu">Nachos</a></li>
        <li><a href="#menu">Kothe Momo</a></li>
      </ul>
    </div>
    <div class="footer-col">
      <h4>Info</h4>
      <ul>
        <li><a href="#about">About Us</a></li>
        <li><a href="#reviews">Reviews</a></li>
        <li><a href="#visit">Location</a></li>
        <li><a href="#visit">Opening Hours</a></li>
      </ul>
    </div>
    <div class="footer-col">
      <h4>Contact</h4>
      <ul>
        <li><a href="tel:9860886259">986-0886259</a></li>
        <li><a href="#">Dine-In</a></li>
        <li><a href="#">Takeaway</a></li>
        <li><a href="https://maps.google.com/?q=Coffee+Cloud+Cafe+Kathmandu" target="_blank">Google Maps</a></li>
      </ul>
    </div>
  </div>
  <div class="footer-bottom">
    <span>© 2025 Coffee Cloud Café, Kathmandu. All rights reserved.</span>
    <span>Made with ☕ &amp; ❤️ in Nepal</span>
  </div>
</footer>

<script>
  // Smooth scroll for all anchor links
  document.querySelectorAll('a[href^="#"]').forEach(a => {
    a.addEventListener('click', e => {
      const target = document.querySelector(a.getAttribute('href'));
      if (target) { e.preventDefault(); target.scrollIntoView({ behavior: 'smooth' }); }
    });
  });

  // Intersection observer for fade-in
  const observer = new IntersectionObserver(entries => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        e.target.style.opacity = '1';
        e.target.style.transform = 'translateY(0)';
      }
    });
  }, { threshold: 0.12 });

  document.querySelectorAll('.menu-item, .review-card, .detail-item').forEach(el => {
    el.style.opacity = '0';
    el.style.transform = 'translateY(24px)';
    el.style.transition = 'opacity 0.5s ease, transform 0.5s ease';
    observer.observe(el);
  });
</script>
</body>
</html>
