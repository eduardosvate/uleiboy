<!DOCTYPE html>
<html lang="ro">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>UleiBoy – Schimb Ulei la Domiciliu | Cluj-Napoca</title>
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Barlow:wght@300;400;600;700&display=swap" rel="stylesheet">
<style>
  :root {
    --black: #0a0a0a;
    --dark: #111111;
    --card: #181818;
    --accent: #f5a623;
    --accent2: #e8890a;
    --text: #e8e8e8;
    --muted: #888;
    --border: #2a2a2a;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  html { scroll-behavior: smooth; }

  body {
    background: var(--black);
    color: var(--text);
    font-family: 'Barlow', sans-serif;
    font-weight: 400;
    overflow-x: hidden;
  }

  /* NAV */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    padding: 18px 5%;
    display: flex; align-items: center; justify-content: space-between;
    background: rgba(10,10,10,0.92);
    backdrop-filter: blur(12px);
    border-bottom: 1px solid var(--border);
  }

  .logo {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 2rem;
    letter-spacing: 3px;
    color: var(--accent);
    text-decoration: none;
  }

  .logo span { color: var(--text); }

  nav ul {
    list-style: none;
    display: flex; gap: 36px;
  }

  nav ul a {
    color: var(--muted);
    text-decoration: none;
    font-size: 0.85rem;
    font-weight: 600;
    letter-spacing: 1.5px;
    text-transform: uppercase;
    transition: color 0.2s;
  }

  nav ul a:hover { color: var(--accent); }

  .nav-cta {
    background: var(--accent);
    color: var(--black) !important;
    padding: 10px 22px;
    border-radius: 4px;
    transition: background 0.2s !important;
  }

  .nav-cta:hover { background: var(--accent2) !important; color: var(--black) !important; }

  /* HERO */
  .hero {
    min-height: 100vh;
    display: flex; align-items: center;
    padding: 120px 5% 60px;
    position: relative;
    overflow: hidden;
  }

  .hero-bg {
    position: absolute; inset: 0;
    background:
      radial-gradient(ellipse 80% 60% at 70% 50%, rgba(245,166,35,0.07) 0%, transparent 70%),
      linear-gradient(135deg, #0a0a0a 0%, #141414 100%);
  }

  .hero-grid {
    position: absolute; inset: 0; opacity: 0.04;
    background-image: linear-gradient(var(--border) 1px, transparent 1px),
      linear-gradient(90deg, var(--border) 1px, transparent 1px);
    background-size: 60px 60px;
  }

  .hero-content {
    position: relative; z-index: 2;
    max-width: 700px;
  }

  .hero-badge {
    display: inline-flex; align-items: center; gap: 8px;
    background: rgba(245,166,35,0.12);
    border: 1px solid rgba(245,166,35,0.3);
    color: var(--accent);
    padding: 6px 16px;
    border-radius: 20px;
    font-size: 0.78rem;
    font-weight: 700;
    letter-spacing: 2px;
    text-transform: uppercase;
    margin-bottom: 28px;
    animation: fadeUp 0.7s ease both;
  }

  .hero h1 {
    font-family: 'Bebas Neue', sans-serif;
    font-size: clamp(4rem, 10vw, 8rem);
    line-height: 0.92;
    letter-spacing: 2px;
    margin-bottom: 24px;
    animation: fadeUp 0.7s 0.1s ease both;
  }

  .hero h1 .highlight { color: var(--accent); }

  .hero p {
    font-size: 1.15rem;
    font-weight: 300;
    line-height: 1.7;
    color: #aaa;
    max-width: 520px;
    margin-bottom: 44px;
    animation: fadeUp 0.7s 0.2s ease both;
  }

  .hero-ctas {
    display: flex; gap: 16px; flex-wrap: wrap;
    animation: fadeUp 0.7s 0.3s ease both;
  }

  .btn-primary {
    background: var(--accent);
    color: var(--black);
    font-family: 'Barlow', sans-serif;
    font-weight: 700;
    font-size: 0.9rem;
    letter-spacing: 1.5px;
    text-transform: uppercase;
    padding: 16px 36px;
    border: none; border-radius: 4px;
    cursor: pointer;
    text-decoration: none;
    transition: all 0.2s;
    display: inline-block;
  }

  .btn-primary:hover {
    background: var(--accent2);
    transform: translateY(-2px);
    box-shadow: 0 8px 30px rgba(245,166,35,0.3);
  }

  .btn-outline {
    background: transparent;
    color: var(--text);
    font-family: 'Barlow', sans-serif;
    font-weight: 700;
    font-size: 0.9rem;
    letter-spacing: 1.5px;
    text-transform: uppercase;
    padding: 16px 36px;
    border: 1px solid var(--border);
    border-radius: 4px;
    cursor: pointer;
    text-decoration: none;
    transition: all 0.2s;
    display: inline-block;
  }

  .btn-outline:hover {
    border-color: var(--accent);
    color: var(--accent);
    transform: translateY(-2px);
  }

  /* STATS BAR */
  .stats-bar {
    background: var(--card);
    border-top: 1px solid var(--border);
    border-bottom: 1px solid var(--border);
    padding: 32px 5%;
    display: flex; justify-content: center; gap: 0;
    flex-wrap: wrap;
  }

  .stat-item {
    text-align: center;
    padding: 0 48px;
    border-right: 1px solid var(--border);
  }

  .stat-item:last-child { border-right: none; }

  .stat-number {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 2.8rem;
    color: var(--accent);
    letter-spacing: 2px;
    line-height: 1;
  }

  .stat-label {
    font-size: 0.78rem;
    color: var(--muted);
    font-weight: 600;
    letter-spacing: 1.5px;
    text-transform: uppercase;
    margin-top: 6px;
  }

  /* SECTION */
  section {
    padding: 100px 5%;
  }

  .section-tag {
    font-size: 0.75rem;
    font-weight: 700;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 16px;
  }

  .section-title {
    font-family: 'Bebas Neue', sans-serif;
    font-size: clamp(2.5rem, 5vw, 4rem);
    letter-spacing: 2px;
    line-height: 1;
    margin-bottom: 20px;
  }

  .section-subtitle {
    color: var(--muted);
    font-size: 1.05rem;
    font-weight: 300;
    line-height: 1.7;
    max-width: 520px;
    margin-bottom: 60px;
  }

  /* HOW IT WORKS */
  .how-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
    gap: 2px;
    background: var(--border);
  }

  .how-card {
    background: var(--card);
    padding: 44px 36px;
    position: relative;
    overflow: hidden;
    transition: background 0.2s;
  }

  .how-card:hover { background: #1e1e1e; }

  .how-number {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 5rem;
    color: rgba(245,166,35,0.08);
    position: absolute;
    top: 10px; right: 20px;
    letter-spacing: 0;
    line-height: 1;
    pointer-events: none;
  }

  .how-icon {
    font-size: 2rem;
    margin-bottom: 20px;
  }

  .how-card h3 {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 1.5rem;
    letter-spacing: 1px;
    margin-bottom: 12px;
    color: var(--text);
  }

  .how-card p {
    font-size: 0.92rem;
    color: var(--muted);
    line-height: 1.65;
    font-weight: 300;
  }

  /* SERVICES */
  .services-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 20px;
  }

  .service-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 36px;
    transition: all 0.3s;
    position: relative;
    overflow: hidden;
  }

  .service-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 3px;
    background: var(--accent);
    transform: scaleX(0);
    transform-origin: left;
    transition: transform 0.3s;
  }

  .service-card:hover {
    border-color: rgba(245,166,35,0.3);
    transform: translateY(-4px);
    box-shadow: 0 20px 60px rgba(0,0,0,0.4);
  }

  .service-card:hover::before { transform: scaleX(1); }

  .service-icon {
    width: 52px; height: 52px;
    background: rgba(245,166,35,0.1);
    border-radius: 8px;
    display: flex; align-items: center; justify-content: center;
    font-size: 1.5rem;
    margin-bottom: 20px;
  }

  .service-card h3 {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 1.4rem;
    letter-spacing: 1px;
    margin-bottom: 12px;
  }

  .service-card p {
    font-size: 0.9rem;
    color: var(--muted);
    line-height: 1.65;
    font-weight: 300;
  }

  /* WHY US */
  .why-layout {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 80px;
    align-items: center;
  }

  .why-visual {
    position: relative;
  }

  .why-visual-box {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 48px;
    text-align: center;
    position: relative;
    overflow: hidden;
  }

  .why-visual-box::after {
    content: '';
    position: absolute;
    bottom: -40px; right: -40px;
    width: 200px; height: 200px;
    background: radial-gradient(circle, rgba(245,166,35,0.15) 0%, transparent 70%);
    pointer-events: none;
  }

  .big-icon {
    font-size: 6rem;
    display: block;
    margin-bottom: 20px;
    animation: spin 8s linear infinite;
  }

  @keyframes spin {
    from { transform: rotate(0deg); }
    to { transform: rotate(360deg); }
  }

  .why-list {
    list-style: none;
    display: flex; flex-direction: column; gap: 20px;
  }

  .why-item {
    display: flex; gap: 16px; align-items: flex-start;
  }

  .why-check {
    width: 28px; height: 28px; min-width: 28px;
    background: rgba(245,166,35,0.15);
    border: 1px solid rgba(245,166,35,0.4);
    border-radius: 50%;
    display: flex; align-items: center; justify-content: center;
    color: var(--accent);
    font-size: 0.8rem;
    font-weight: 700;
    margin-top: 2px;
  }

  .why-item h4 {
    font-weight: 700;
    font-size: 1rem;
    margin-bottom: 4px;
  }

  .why-item p {
    font-size: 0.88rem;
    color: var(--muted);
    font-weight: 300;
    line-height: 1.6;
  }

  /* CONTACT */
  #contact {
    background: var(--dark);
  }

  .contact-layout {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 80px;
    align-items: start;
  }

  .contact-info {
    display: flex; flex-direction: column; gap: 28px;
  }

  .contact-item {
    display: flex; gap: 20px; align-items: flex-start;
  }

  .contact-icon {
    width: 48px; height: 48px; min-width: 48px;
    background: rgba(245,166,35,0.1);
    border: 1px solid rgba(245,166,35,0.2);
    border-radius: 8px;
    display: flex; align-items: center; justify-content: center;
    font-size: 1.3rem;
  }

  .contact-item h4 {
    font-size: 0.75rem;
    font-weight: 700;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 6px;
  }

  .contact-item a, .contact-item p {
    color: var(--text);
    text-decoration: none;
    font-size: 1.05rem;
    font-weight: 600;
    transition: color 0.2s;
  }

  .contact-item a:hover { color: var(--accent); }

  .contact-form {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 40px;
  }

  .form-title {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 1.8rem;
    letter-spacing: 1px;
    margin-bottom: 28px;
  }

  .form-group {
    margin-bottom: 20px;
  }

  .form-group label {
    display: block;
    font-size: 0.78rem;
    font-weight: 700;
    letter-spacing: 1.5px;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 8px;
  }

  .form-group input,
  .form-group textarea,
  .form-group select {
    width: 100%;
    background: var(--black);
    border: 1px solid var(--border);
    border-radius: 4px;
    padding: 14px 16px;
    color: var(--text);
    font-family: 'Barlow', sans-serif;
    font-size: 0.95rem;
    transition: border-color 0.2s;
    outline: none;
    -webkit-appearance: none;
  }

  .form-group select option { background: var(--black); }

  .form-group input:focus,
  .form-group textarea:focus,
  .form-group select:focus {
    border-color: var(--accent);
  }

  .form-group textarea {
    resize: vertical;
    min-height: 100px;
  }

  .form-submit {
    width: 100%;
    background: var(--accent);
    color: var(--black);
    font-family: 'Barlow', sans-serif;
    font-weight: 700;
    font-size: 0.9rem;
    letter-spacing: 2px;
    text-transform: uppercase;
    padding: 16px;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    transition: all 0.2s;
    margin-top: 8px;
  }

  .form-submit:hover {
    background: var(--accent2);
    transform: translateY(-2px);
    box-shadow: 0 8px 30px rgba(245,166,35,0.3);
  }

  /* FOOTER */
  footer {
    background: #080808;
    border-top: 1px solid var(--border);
    padding: 32px 5%;
    display: flex; align-items: center; justify-content: space-between;
    flex-wrap: wrap; gap: 16px;
  }

  .footer-logo {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 1.6rem;
    letter-spacing: 3px;
    color: var(--accent);
    text-decoration: none;
  }

  footer p {
    font-size: 0.8rem;
    color: var(--muted);
  }

  .footer-links {
    display: flex; gap: 24px;
  }

  .footer-links a {
    color: var(--muted);
    text-decoration: none;
    font-size: 0.8rem;
    transition: color 0.2s;
  }

  .footer-links a:hover { color: var(--accent); }

  /* ANIMATIONS */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(30px); }
    to { opacity: 1; transform: translateY(0); }
  }

  .fade-in {
    opacity: 0;
    transform: translateY(20px);
    transition: opacity 0.6s ease, transform 0.6s ease;
  }

  .fade-in.visible {
    opacity: 1;
    transform: translateY(0);
  }

  /* RESPONSIVE */
  @media (max-width: 768px) {
    nav ul { display: none; }
    .stats-bar { gap: 20px; }
    .stat-item { border: none; padding: 12px 24px; }
    .why-layout, .contact-layout { grid-template-columns: 1fr; gap: 40px; }
    .hero h1 { font-size: 4.5rem; }
    section { padding: 70px 5%; }
    .how-grid { background: transparent; gap: 16px; }
    .how-card { border: 1px solid var(--border); border-radius: 8px; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <a href="#" class="logo">Ulei<span>Boy</span></a>
  <ul>
    <li><a href="#cum-functioneaza">Cum funcționează</a></li>
    <li><a href="#servicii">Servicii</a></li>
    <li><a href="#despre-noi">De ce noi</a></li>
    <li><a href="#contact" class="nav-cta">Programează</a></li>
  </ul>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-bg"></div>
  <div class="hero-grid"></div>
  <div class="hero-content">
    <div class="hero-badge">📍 Cluj-Napoca · Schimb Ulei la Domiciliu</div>
    <h1>Ulei<br><span class="highlight">Proaspăt.</span><br>La Tine.</h1>
    <p>Nu mai pierde timp la service. Venim noi la tine — oriunde în Cluj-Napoca — și schimbăm uleiul mașinii tale rapid, profesional, fără bătăi de cap.</p>
    <div class="hero-ctas">
      <a href="tel:0746460038" class="btn-primary">📞 Sună Acum</a>
      <a href="#cum-functioneaza" class="btn-outline">Cum funcționează →</a>
    </div>
  </div>
</section>

<!-- STATS -->
<div class="stats-bar">
  <div class="stat-item fade-in">
    <div class="stat-number">30'</div>
    <div class="stat-label">Timp mediu</div>
  </div>
  <div class="stat-item fade-in">
    <div class="stat-number">100%</div>
    <div class="stat-label">La domiciliu</div>
  </div>
  <div class="stat-item fade-in">
    <div class="stat-number">0</div>
    <div class="stat-label">Timp pierdut</div>
  </div>
  <div class="stat-item fade-in">
    <div class="stat-number">CLJ</div>
    <div class="stat-label">Cluj-Napoca</div>
  </div>
</div>

<!-- HOW IT WORKS -->
<section id="cum-functioneaza">
  <div class="section-tag">Procesul nostru</div>
  <h2 class="section-title fade-in">Simplu în 4 Pași</h2>
  <p class="section-subtitle fade-in">De la programare la schimbul de ulei — totul se întâmplă la tine acasă, fără stres.</p>
  <div class="how-grid">
    <div class="how-card fade-in">
      <div class="how-number">01</div>
      
      <h3>Programează</h3>
      <p>Sună-ne sau trimite un mesaj. Îți oferim o fereastră orară convenabilă pentru tine.</p>
    </div>
    <div class="how-card fade-in">
      <div class="how-number">02</div>
      
      <h3>Venim la tine</h3>
      <p>Tehnicianul nostru ajunge la adresa ta din Cluj-Napoca cu toate echipamentele necesare.</p>
    </div>
    <div class="how-card fade-in">
      <div class="how-number">03</div>
      
      <h3>Schimbăm uleiul</h3>
      <p>Lucrare profesională în circa 30 de minute. Ulei de calitate, filtru nou, totul corect.</p>
    </div>
    <div class="how-card fade-in">
      <div class="how-number">04</div>
      
      <h3>Gata de drum</h3>
      <p>Îți prezentăm lucrarea efectuată, îți eliberăm bon și mașina ta e gata de mers.</p>
    </div>
  </div>
</section>

<!-- SERVICES -->
<section id="servicii" style="background: var(--dark);">
  <div class="section-tag">Ce oferim</div>
  <h2 class="section-title fade-in">Serviciile Noastre</h2>
  <p class="section-subtitle fade-in">Specializați în schimbul de ulei, cu opțiuni adaptate oricărui tip de vehicul.</p>
  <div class="services-grid">
    <div class="service-card fade-in">
      <div class="service-icon">🛢️</div>
      <h3>Schimb Ulei Motor</h3>
      <p>Ulei mineral, semi-sintetic sau sintetic, conform specificațiilor producătorului. Includem filtrul de ulei.</p>
    </div>
    <div class="service-card fade-in">
      <div class="service-icon">🔧</div>
      <h3>Verificare Tehnică</h3>
      <p>La fiecare vizită inspectăm gratuit nivelul lichidelor, frânele și presiunea în anvelope.</p>
    </div>
    <div class="service-card fade-in">
      <div class="service-icon">🚗</div>
      <h3>Orice Marcă de Mașină</h3>
      <p>Lucrăm pe toate marcile — Dacia, Ford, BMW, Volkswagen, Toyota și altele.</p>
    </div>
    <div class="service-card fade-in">
      <div class="service-icon">📅</div>
      <h3>Programare Flexibilă</h3>
      <p>Dimineață, după-masă sau weekend — ne adaptăm programului tău.</p>
    </div>
  </div>
</section>

<!-- WHY US -->
<section id="despre-noi">
  <div class="why-layout">
    <div class="why-left fade-in">
      <div class="section-tag">De ce UleiBoy</div>
      <h2 class="section-title">Fără Cozi.<br>Fără Drum.<br>Fără Stres.</h2>
      <p class="section-subtitle">Suntem prima echipă din Cluj-Napoca specializată exclusiv în schimbul de ulei la domiciliu.</p>
      <ul class="why-list">
        <li class="why-item">
          <div class="why-check">✓</div>
          <div>
            <h4>Economiști de timp</h4>
            <p>Nu mai pierzi jumătate de zi la service. Noi venim în pauza ta de prânz sau când ești acasă.</p>
          </div>
        </li>
        <li class="why-item">
          <div class="why-check">✓</div>
          <div>
            <h4>Tehnicieni certificați</h4>
            <p>Personal calificat, cu experiență reală în mecanică auto și produse de calitate.</p>
          </div>
        </li>
        <li class="why-item">
          <div class="why-check">✓</div>
          <div>
            <h4>Prețuri transparente</h4>
            <p>Știi prețul înainte să ajungem. Fără surprize, fără costuri ascunse.</p>
          </div>
        </li>
        <li class="why-item">
          <div class="why-check">✓</div>
          <div>
            <h4>Ecologici</h4>
            <p>Uleiul uzat este colectat și predat pentru reciclare conform normelor în vigoare.</p>
          </div>
        </li>
      </ul>
    </div>
    <div class="why-visual fade-in">
      <div class="why-visual-box">
        <span class="big-icon">⚙️</span>
        <div class="section-title" style="font-size:2.5rem;">Service<br><span style="color:var(--accent)">Mobil</span></div>
        <p style="color:var(--muted); margin-top: 16px; font-size: 0.95rem; font-weight: 300; line-height: 1.6;">Toată logistica unui service auto — compact, în furgoneta noastră, la ușa ta.</p>
      </div>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <div class="contact-layout">
    <div>
      <div class="section-tag">Contact</div>
      <h2 class="section-title fade-in">Programează<br>Acum</h2>
      <p class="section-subtitle fade-in">Sună-ne sau completează formularul și te contactăm noi în cel mai scurt timp.</p>
      <div class="contact-info">
        <div class="contact-item fade-in">
          <div class="contact-icon">📞</div>
          <div>
            <h4>Telefon</h4>
            <a href="tel:0746460038">0746 460 038</a>
          </div>
        </div>
        <div class="contact-item fade-in">
          <div class="contact-icon">📍</div>
          <div>
            <h4>Zona de activitate</h4>
            <p>Cluj-Napoca și împrejurimi</p>
          </div>
        </div>
        <div class="contact-item fade-in">
          <div class="contact-icon">🕐</div>
          <div>
            <h4>Program</h4>
            <p>Luni – Sâmbătă: 08:00 – 20:00</p>
          </div>
        </div>
      </div>
    </div>
    <div class="fade-in">
      <div class="contact-form">
        <div class="form-title">Trimite o Programare</div>
        <div class="form-group">
          <label>Numele tău</label>
          <input type="text" placeholder="ex: Ion Popescu">
        </div>
        <div class="form-group">
          <label>Telefon</label>
          <input type="tel" placeholder="07XX XXX XXX">
        </div>
        <div class="form-group">
          <label>Marca mașinii</label>
          <input type="text" placeholder="ex: Dacia Logan, BMW X5...">
        </div>
        <div class="form-group">
          <label>Data preferată</label>
          <input type="date">
        </div>
        <div class="form-group">
          <label>Mesaj (opțional)</label>
          <textarea placeholder="Orice detaliu util..."></textarea>
        </div>
        <button class="form-submit" onclick="handleSubmit()">Trimite Programarea →</button>
      </div>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <a href="#" class="footer-logo">UleiBoy</a>
  <p>© 2024 UleiBoy · Cluj-Napoca · Schimb Ulei la Domiciliu</p>
  <div class="footer-links">
    <a href="tel:0746460038">0746 460 038</a>
    <a href="#contact">Programează</a>
  </div>
</footer>

<script>
  // Scroll animations
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(el => {
      if (el.isIntersecting) {
        el.target.classList.add('visible');
      }
    });
  }, { threshold: 0.1 });

  document.querySelectorAll('.fade-in').forEach(el => observer.observe(el));

  // Form submit
  function handleSubmit() {
    alert('Mulțumim! Te vom contacta în curând pentru confirmare.\n\nAlternativ, ne poți suna direct la: 0746 460 038');
  }

  // Smooth scroll for nav links
  document.querySelectorAll('a[href^="#"]').forEach(a => {
    a.addEventListener('click', e => {
      const target = document.querySelector(a.getAttribute('href'));
      if (target) {
        e.preventDefault();
        target.scrollIntoView({ behavior: 'smooth' });
      }
    });
  });
</script>
</body>
</html>
