<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Miraj Marketing Agency</title>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@300;400;600;700&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --gold: #C9A84C;
    --gold-light: #E8C97A;
    --gold-dim: #8B6E2F;
    --black: #0A0A0A;SS
    --dark: #111111;
    --dark2: #1A1A1A;
    --dark3: #222222;
    --white: #F5F0E8;
    --muted: #888880;
    --border: rgba(201,168,76,0.2);
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  html { scroll-behavior: smooth; }

  body {
    background: var(--black);
    color: var(--white);
    font-family: 'DM Sans', sans-serif;
    font-weight: 300;
    overflow-x: hidden;
  }

  /* NOISE TEXTURE */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.04'/%3E%3C/svg%3E");
    pointer-events: none;
    z-index: 0;
    opacity: 0.4;
  }

  /* NAV */
  nav {
    position: fixed;
    top: 0;
    width: 100%;
    z-index: 100;
    padding: 1.5rem 5%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    border-bottom: 1px solid var(--border);
    background: rgba(10,10,10,0.85);
    backdrop-filter: blur(12px);
  }

  .logo {
    font-family: 'Cormorant Garamond', serif;
    font-size: 1.6rem;
    font-weight: 600;
    letter-spacing: 0.08em;
    color: var(--gold);
  }
  .logo span { color: var(--white); font-weight: 300; }

  .nav-links {
    display: flex;
    gap: 2.5rem;
    list-style: none;
  }
  .nav-links a {
    color: var(--muted);
    text-decoration: none;
    font-size: 0.8rem;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    transition: color 0.3s;
  }
  .nav-links a:hover { color: var(--gold); }

  .nav-cta {
    padding: 0.5rem 1.5rem;
    border: 1px solid var(--gold);
    color: var(--gold);
    text-decoration: none;
    font-size: 0.75rem;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    transition: all 0.3s;
  }
  .nav-cta:hover { background: var(--gold); color: var(--black); }

  /* HERO */
  .hero {
    min-height: 100vh;
    display: flex;
    align-items: center;
    padding: 8rem 5% 4rem;
    position: relative;
    overflow: hidden;
  }

  .hero-bg-circle {
    position: absolute;
    width: 600px;
    height: 600px;
    border-radius: 50%;
    background: radial-gradient(circle, rgba(201,168,76,0.08) 0%, transparent 70%);
    right: -100px;
    top: 50%;
    transform: translateY(-50%);
    pointer-events: none;
  }

  .hero-tag {
    display: inline-block;
    font-size: 0.72rem;
    letter-spacing: 0.25em;
    text-transform: uppercase;
    color: var(--gold);
    border: 1px solid var(--border);
    padding: 0.4rem 1rem;
    margin-bottom: 2rem;
    animation: fadeUp 0.8s ease both;
  }

  .hero h1 {
    font-family: 'Cormorant Garamond', serif;
    font-size: clamp(3.5rem, 7vw, 7rem);
    font-weight: 300;
    line-height: 1.05;
    letter-spacing: -0.02em;
    margin-bottom: 1.5rem;
    animation: fadeUp 0.8s ease 0.1s both;
  }

  .hero h1 em {
    font-style: italic;
    color: var(--gold);
  }

  .hero-sub {
    max-width: 520px;
    color: var(--muted);
    font-size: 1rem;
    line-height: 1.8;
    margin-bottom: 2.5rem;
    animation: fadeUp 0.8s ease 0.2s both;
  }

  .hero-btns {
    display: flex;
    gap: 1rem;
    flex-wrap: wrap;
    animation: fadeUp 0.8s ease 0.3s both;
  }

  .btn-gold {
    padding: 0.9rem 2.2rem;
    background: var(--gold);
    color: var(--black);
    text-decoration: none;
    font-size: 0.8rem;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    font-weight: 500;
    transition: all 0.3s;
  }
  .btn-gold:hover { background: var(--gold-light); transform: translateY(-2px); }

  .btn-outline {
    padding: 0.9rem 2.2rem;
    border: 1px solid var(--border);
    color: var(--white);
    text-decoration: none;
    font-size: 0.8rem;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    transition: all 0.3s;
  }
  .btn-outline:hover { border-color: var(--gold); color: var(--gold); }

  .hero-stats {
    display: flex;
    gap: 3rem;
    margin-top: 4rem;
    padding-top: 3rem;
    border-top: 1px solid var(--border);
    animation: fadeUp 0.8s ease 0.4s both;
  }

  .stat-num {
    font-family: 'Cormorant Garamond', serif;
    font-size: 2.8rem;
    font-weight: 600;
    color: var(--gold);
    line-height: 1;
  }

  .stat-label {
    font-size: 0.75rem;
    color: var(--muted);
    letter-spacing: 0.1em;
    text-transform: uppercase;
    margin-top: 0.3rem;
  }

  /* MARQUEE */
  .marquee-section {
    border-top: 1px solid var(--border);
    border-bottom: 1px solid var(--border);
    padding: 1rem 0;
    overflow: hidden;
    background: var(--dark2);
  }

  .marquee-track {
    display: flex;
    gap: 4rem;
    animation: marquee 18s linear infinite;
    white-space: nowrap;
  }

  .marquee-item {
    font-size: 0.72rem;
    letter-spacing: 0.25em;
    text-transform: uppercase;
    color: var(--gold-dim);
    flex-shrink: 0;
  }

  .marquee-dot {
    display: inline-block;
    width: 4px;
    height: 4px;
    background: var(--gold);
    border-radius: 50%;
    vertical-align: middle;
    margin: 0 1rem;
  }

  @keyframes marquee {
    0% { transform: translateX(0); }
    100% { transform: translateX(-50%); }
  }

  /* ABOUT */
  .about {
    padding: 7rem 5%;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 6rem;
    align-items: center;
  }

  .section-label {
    font-size: 0.72rem;
    letter-spacing: 0.25em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 1rem;
  }

  .section-title {
    font-family: 'Cormorant Garamond', serif;
    font-size: clamp(2.2rem, 4vw, 3.5rem);
    font-weight: 300;
    line-height: 1.15;
    margin-bottom: 1.5rem;
  }

  .section-title em { font-style: italic; color: var(--gold); }

  .about-text {
    color: var(--muted);
    line-height: 1.9;
    margin-bottom: 1.5rem;
    font-size: 0.95rem;
  }

  .about-visual {
    position: relative;
  }

  .about-card {
    background: var(--dark2);
    border: 1px solid var(--border);
    padding: 2.5rem;
    margin-bottom: 1rem;
  }

  .about-card-num {
    font-family: 'Cormorant Garamond', serif;
    font-size: 3rem;
    color: var(--gold);
    font-weight: 600;
    line-height: 1;
    margin-bottom: 0.5rem;
  }

  .about-card-label {
    color: var(--muted);
    font-size: 0.85rem;
  }

  .about-card-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1rem;
  }

  /* SERVICES */
  .services {
    padding: 7rem 5%;
    background: var(--dark2);
    border-top: 1px solid var(--border);
  }

  .services-header {
    display: flex;
    justify-content: space-between;
    align-items: flex-end;
    margin-bottom: 4rem;
  }

  .services-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 1px;
    background: var(--border);
  }

  .service-card {
    background: var(--dark2);
    padding: 2.5rem;
    transition: background 0.3s;
    cursor: default;
    position: relative;
    overflow: hidden;
  }

  .service-card::before {
    content: '';
    position: absolute;
    bottom: 0;
    left: 0;
    width: 0;
    height: 2px;
    background: var(--gold);
    transition: width 0.4s ease;
  }

  .service-card:hover::before { width: 100%; }
  .service-card:hover { background: var(--dark3); }

  .service-num {
    font-family: 'Cormorant Garamond', serif;
    font-size: 0.85rem;
    color: var(--gold-dim);
    letter-spacing: 0.1em;
    margin-bottom: 1.5rem;
  }

  .service-icon {
    font-size: 1.8rem;
    margin-bottom: 1rem;
  }

  .service-name {
    font-family: 'Cormorant Garamond', serif;
    font-size: 1.5rem;
    font-weight: 600;
    margin-bottom: 0.75rem;
    color: var(--white);
  }

  .service-desc {
    color: var(--muted);
    font-size: 0.87rem;
    line-height: 1.8;
  }

  /* WHY US */
  .why {
    padding: 7rem 5%;
  }

  .why-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
    gap: 2rem;
    margin-top: 4rem;
  }

  .why-item {
    padding: 2rem;
    border: 1px solid var(--border);
    transition: border-color 0.3s;
  }
  .why-item:hover { border-color: var(--gold); }

  .why-icon {
    width: 44px;
    height: 44px;
    border: 1px solid var(--border);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1.2rem;
    margin-bottom: 1.2rem;
    color: var(--gold);
  }

  .why-title {
    font-weight: 500;
    margin-bottom: 0.5rem;
    font-size: 0.95rem;
  }

  .why-desc {
    color: var(--muted);
    font-size: 0.85rem;
    line-height: 1.7;
  }

  /* PROCESS */
  .process {
    padding: 7rem 5%;
    background: var(--dark2);
    border-top: 1px solid var(--border);
  }

  .process-steps {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 0;
    margin-top: 4rem;
    position: relative;
  }

  .process-step {
    padding: 2rem 1.5rem;
    border-right: 1px solid var(--border);
    position: relative;
  }
  .process-step:last-child { border-right: none; }

  .step-num {
    font-family: 'Cormorant Garamond', serif;
    font-size: 3.5rem;
    font-weight: 600;
    color: var(--border);
    line-height: 1;
    margin-bottom: 1rem;
  }

  .step-title {
    font-weight: 500;
    margin-bottom: 0.5rem;
    font-size: 0.95rem;
    color: var(--gold);
  }

  .step-desc {
    color: var(--muted);
    font-size: 0.84rem;
    line-height: 1.7;
  }

  /* TESTIMONIALS */
  .testimonials {
    padding: 7rem 5%;
  }

  .testi-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 1.5rem;
    margin-top: 4rem;
  }

  .testi-card {
    background: var(--dark2);
    border: 1px solid var(--border);
    padding: 2rem;
    position: relative;
  }

  .testi-quote {
    font-family: 'Cormorant Garamond', serif;
    font-size: 3rem;
    color: var(--gold);
    line-height: 0.5;
    margin-bottom: 1rem;
  }

  .testi-text {
    color: var(--muted);
    font-size: 0.9rem;
    line-height: 1.8;
    margin-bottom: 1.5rem;
    font-style: italic;
  }

  .testi-author {
    font-weight: 500;
    font-size: 0.87rem;
  }

  .testi-role {
    color: var(--gold-dim);
    font-size: 0.78rem;
    margin-top: 0.2rem;
  }

  /* CONTACT */
  .contact {
    padding: 7rem 5%;
    background: var(--dark2);
    border-top: 1px solid var(--border);
  }

  .contact-inner {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 6rem;
    align-items: start;
  }

  .contact-info-item {
    display: flex;
    gap: 1rem;
    margin-bottom: 1.5rem;
    align-items: flex-start;
  }

  .contact-icon {
    width: 40px;
    height: 40px;
    border: 1px solid var(--border);
    display: flex;
    align-items: center;
    justify-content: center;
    flex-shrink: 0;
    font-size: 1rem;
    color: var(--gold);
  }

  .contact-label {
    font-size: 0.75rem;
    color: var(--muted);
    letter-spacing: 0.1em;
    text-transform: uppercase;
    margin-bottom: 0.25rem;
  }

  .contact-value {
    font-size: 0.95rem;
    color: var(--white);
  }

  .contact-form input,
  .contact-form textarea,
  .contact-form select {
    width: 100%;
    background: transparent;
    border: none;
    border-bottom: 1px solid var(--border);
    color: var(--white);
    padding: 0.8rem 0;
    font-family: 'DM Sans', sans-serif;
    font-size: 0.9rem;
    outline: none;
    margin-bottom: 1.5rem;
    transition: border-color 0.3s;
    -webkit-appearance: none;
  }

  .contact-form input::placeholder,
  .contact-form textarea::placeholder {
    color: var(--muted);
  }

  .contact-form input:focus,
  .contact-form textarea:focus {
    border-bottom-color: var(--gold);
  }

  .contact-form textarea { resize: none; height: 100px; }

  .contact-form select {
    color: var(--muted);
    cursor: pointer;
    background: var(--dark2);
  }

  .contact-form select option { background: var(--dark2); color: var(--white); }

  /* FOOTER */
  footer {
    padding: 2rem 5%;
    border-top: 1px solid var(--border);
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    gap: 1rem;
  }

  .footer-copy {
    color: var(--muted);
    font-size: 0.78rem;
    letter-spacing: 0.05em;
  }

  .footer-links {
    display: flex;
    gap: 1.5rem;
  }
  .footer-links a {
    color: var(--muted);
    text-decoration: none;
    font-size: 0.78rem;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    transition: color 0.3s;
  }
  .footer-links a:hover { color: var(--gold); }

  /* ANIMATIONS */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(24px); }
    to { opacity: 1; transform: translateY(0); }
  }

  .reveal {
    opacity: 0;
    transform: translateY(30px);
    transition: opacity 0.7s ease, transform 0.7s ease;
  }
  .reveal.visible { opacity: 1; transform: none; }

  /* MOBILE */
  @media (max-width: 768px) {
    nav { padding: 1.2rem 5%; }
    .nav-links { display: none; }
    .about { grid-template-columns: 1fr; gap: 3rem; }
    .contact-inner { grid-template-columns: 1fr; gap: 3rem; }
    .hero-stats { gap: 2rem; flex-wrap: wrap; }
    .services-header { flex-direction: column; align-items: flex-start; gap: 1rem; }
    .process-step { border-right: none; border-bottom: 1px solid var(--border); }
    .process-step:last-child { border-bottom: none; }
  }

  /* WHATSAPP FLOAT */
  .wa-float {
    position: fixed;
    bottom: 2rem;
    right: 2rem;
    width: 52px;
    height: 52px;
    background: #25D366;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    text-decoration: none;
    z-index: 999;
    box-shadow: 0 4px 20px rgba(37,211,102,0.3);
    transition: transform 0.3s;
  }
  .wa-float:hover { transform: scale(1.1); }
  .wa-float svg { width: 26px; height: 26px; fill: white; }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="logo">MIRAJ<span> Marketing</span></div>
  <ul class="nav-links">
    <li><a href="#about">About</a></li>
    <li><a href="#services">Services</a></li>
    <li><a href="#process">Process</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
  <a href="#contact" class="nav-cta">Get Started</a>
</nav>

<!-- HERO -->
<section class="hero" id="home">
  <div class="hero-bg-circle"></div>
  <div>
    <div class="hero-tag">✦ Digital Marketing Agency — Pakistan</div>
    <h1>We Grow<br>Brands <em>That</em><br>Demand Attention</h1>
    <p class="hero-sub">Strategic digital marketing that delivers real results. From social media to SEO, we craft campaigns that convert — led by 5 years of proven expertise.</p>
    <div class="hero-btns">
      <a href="#services" class="btn-gold">Explore Services</a>
      <a href="#contact" class="btn-outline">Book Free Consultation</a>
    </div>
    <div class="hero-stats">
      <div>
        <div class="stat-num">50+</div>
        <div class="stat-label">Clients Served</div>
      </div>
      <div>
        <div class="stat-num">5yr</div>
        <div class="stat-label">Experience</div>
      </div>
      <div>
        <div class="stat-num">300%</div>
        <div class="stat-label">Avg. ROI Growth</div>
      </div>
      <div>
        <div class="stat-num">100%</div>
        <div class="stat-label">Dedication</div>
      </div>
    </div>
  </div>
</section>

<!-- MARQUEE -->
<div class="marquee-section">
  <div class="marquee-track">
    <span class="marquee-item">Social Media Marketing</span><span class="marquee-dot"></span>
    <span class="marquee-item">SEO & Google Ads</span><span class="marquee-dot"></span>
    <span class="marquee-item">Content Creation</span><span class="marquee-dot"></span>
    <span class="marquee-item">Email Marketing</span><span class="marquee-dot"></span>
    <span class="marquee-item">Brand Strategy</span><span class="marquee-dot"></span>
    <span class="marquee-item">Performance Marketing</span><span class="marquee-dot"></span>
    <span class="marquee-item">Social Media Marketing</span><span class="marquee-dot"></span>
    <span class="marquee-item">SEO & Google Ads</span><span class="marquee-dot"></span>
    <span class="marquee-item">Content Creation</span><span class="marquee-dot"></span>
    <span class="marquee-item">Email Marketing</span><span class="marquee-dot"></span>
    <span class="marquee-item">Brand Strategy</span><span class="marquee-dot"></span>
    <span class="marquee-item">Performance Marketing</span><span class="marquee-dot"></span>
  </div>
</div>

<!-- ABOUT -->
<section class="about" id="about">
  <div class="reveal">
    <div class="section-label">✦ Who We Are</div>
    <h2 class="section-title">Meet <em>Kinza Murtaza</em> — The Mind Behind Miraj</h2>
    <p class="about-text">I'm Kinza Murtaza, founder of Miraj Marketing Agency with 5 years of hands-on digital marketing experience. I've helped businesses across industries grow their online presence, generate leads, and build brands that people remember.</p>
    <p class="about-text">At Miraj, we don't believe in one-size-fits-all. Every strategy is crafted specifically for your brand, your audience, and your goals.</p>
    <a href="#contact" class="btn-gold" style="display:inline-block; margin-top:0.5rem;">Work With Me</a>
  </div>
  <div class="about-visual reveal">
    <div class="about-card-grid">
      <div class="about-card">
        <div class="about-card-num">5+</div>
        <div class="about-card-label">Years of Experience</div>
      </div>
      <div class="about-card">
        <div class="about-card-num">50+</div>
        <div class="about-card-label">Happy Clients</div>
      </div>
      <div class="about-card">
        <div class="about-card-num">200+</div>
        <div class="about-card-label">Campaigns Launched</div>
      </div>
      <div class="about-card">
        <div class="about-card-num">10+</div>
        <div class="about-card-label">Industries Served</div>
      </div>
    </div>
  </div>
</section>

<!-- SERVICES -->
<section class="services" id="services">
  <div class="services-header">
    <div>
      <div class="section-label">✦ What We Offer</div>
      <h2 class="section-title reveal">Our <em>Services</em></h2>
    </div>
    <a href="#contact" class="btn-outline reveal">Get a Quote →</a>
  </div>
  <div class="services-grid">
    <div class="service-card reveal">
      <div class="service-num">01</div>
      <div class="service-icon">📱</div>
      <div class="service-name">Social Media Marketing</div>
      <p class="service-desc">Instagram, Facebook, TikTok & LinkedIn growth strategies. Content calendars, community management, and paid social campaigns that build loyal audiences.</p>
    </div>
    <div class="service-card reveal">
      <div class="service-num">02</div>
      <div class="service-icon">🔍</div>
      <div class="service-name">SEO & Google Ads</div>
      <p class="service-desc">Rank higher on Google organically and through targeted paid ads. Keyword research, on-page optimization, and high-ROI PPC campaigns.</p>
    </div>
    <div class="service-card reveal">
      <div class="service-num">03</div>
      <div class="service-icon">✍️</div>
      <div class="service-name">Content Creation</div>
      <p class="service-desc">Compelling copy, graphics, reels, and blog posts that tell your story. Content that educates, entertains, and converts your target audience.</p>
    </div>
    <div class="service-card reveal">
      <div class="service-num">04</div>
      <div class="service-icon">📧</div>
      <div class="service-name">Email Marketing</div>
      <p class="service-desc">Automated email sequences, newsletters, and drip campaigns. Build relationships at scale with personalized messaging that drives repeat business.</p>
    </div>
    <div class="service-card reveal">
      <div class="service-num">05</div>
      <div class="service-icon">🎯</div>
      <div class="service-name">Brand Strategy</div>
      <p class="service-desc">Identity, positioning, and messaging that sets you apart. From logo direction to brand voice — we build brands that people trust and remember.</p>
    </div>
    <div class="service-card reveal">
      <div class="service-num">06</div>
      <div class="service-icon">📊</div>
      <div class="service-name">Performance Marketing</div>
      <p class="service-desc">Data-driven campaigns with measurable results. A/B testing, analytics tracking, and conversion optimization to maximize every rupee spent.</p>
    </div>
  </div>
</section>

<!-- WHY US -->
<section class="why">
  <div class="section-label">✦ Why Miraj</div>
  <h2 class="section-title reveal">The <em>Difference</em> We Make</h2>
  <div class="why-grid">
    <div class="why-item reveal">
      <div class="why-icon">✦</div>
      <div class="why-title">Strategy First</div>
      <p class="why-desc">No guesswork. Every campaign starts with deep research and a clear roadmap tailored to your business goals.</p>
    </div>
    <div class="why-item reveal">
      <div class="why-icon">📈</div>
      <div class="why-title">Results Focused</div>
      <p class="why-desc">We measure everything. Leads, conversions, ROI — transparent reporting so you always know what's working.</p>
    </div>
    <div class="why-item reveal">
      <div class="why-icon">⚡</div>
      <div class="why-title">Fast Execution</div>
      <p class="why-desc">No endless delays. We move quickly, test fast, and iterate to get your campaigns live and generating results.</p>
    </div>
    <div class="why-item reveal">
      <div class="why-icon">🤝</div>
      <div class="why-title">Personal Attention</div>
      <p class="why-desc">You work directly with Kinza — not an account manager. Real expertise, real communication, real care.</p>
    </div>
  </div>
</section>

<!-- PROCESS -->
<section class="process" id="process">
  <div class="section-label">✦ How We Work</div>
  <h2 class="section-title reveal">Our Simple <em>Process</em></h2>
  <div class="process-steps">
    <div class="process-step reveal">
      <div class="step-num">01</div>
      <div class="step-title">Discovery Call</div>
      <p class="step-desc">Free 30-minute consultation to understand your brand, goals, and current challenges.</p>
    </div>
    <div class="process-step reveal">
      <div class="step-num">02</div>
      <div class="step-title">Strategy Design</div>
      <p class="step-desc">We craft a custom digital marketing strategy tailored specifically to your business.</p>
    </div>
    <div class="process-step reveal">
      <div class="step-num">03</div>
      <div class="step-title">Execution</div>
      <p class="step-desc">Our team launches campaigns, creates content, and manages everything end-to-end.</p>
    </div>
    <div class="process-step reveal">
      <div class="step-num">04</div>
      <div class="step-title">Optimize & Scale</div>
      <p class="step-desc">We analyze performance data, optimize what works, and scale results for maximum growth.</p>
    </div>
  </div>
</section>

<!-- TESTIMONIALS -->
<section class="testimonials">
  <div class="section-label">✦ Client Love</div>
  <h2 class="section-title reveal">What <em>Clients</em> Say</h2>
  <div class="testi-grid">
    <div class="testi-card reveal">
      <div class="testi-quote">"</div>
      <p class="testi-text">Kinza transformed our Instagram from zero to 10k followers in just 3 months. Our sales doubled. Best investment we made.</p>
      <div class="testi-author">Sara Ahmed</div>
      <div class="testi-role">Owner, Sara's Boutique</div>
    </div>
    <div class="testi-card reveal">
      <div class="testi-quote">"</div>
      <p class="testi-text">Our Google Ads ROI went from 120% to 380% after Miraj took over. Kinza truly knows what she's doing.</p>
      <div class="testi-author">Usman Khan</div>
      <div class="testi-role">CEO, TechFlow Solutions</div>
    </div>
    <div class="testi-card reveal">
      <div class="testi-quote">"</div>
      <p class="testi-text">The content strategy Kinza built for us completely changed how people perceive our brand. Professional, creative, and dedicated.</p>
      <div class="testi-author">Hina Malik</div>
      <div class="testi-role">Founder, Glow Beauty</div>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section class="contact" id="contact">
  <div class="contact-inner">
    <div class="reveal">
      <div class="section-label">✦ Let's Connect</div>
      <h2 class="section-title">Ready to <em>Grow</em> Your Brand?</h2>
      <p style="color: var(--muted); font-size: 0.9rem; line-height: 1.8; margin-bottom: 2.5rem;">Book a free consultation and let's discuss how Miraj Marketing can take your business to the next level.</p>

      <div class="contact-info-item">
        <div class="contact-icon">📱</div>
        <div>
          <div class="contact-label">WhatsApp</div>
          <div class="contact-value">+92 3248148933</div>
        </div>
      </div>
      <div class="contact-info-item">
        <div class="contact-icon">📧</div>
        <div>
          <div class="contact-label">Email</div>
          <div class="contact-value">kinza@mirajmarketing.com</div>
        </div>
      </div>
      <div class="contact-info-item">
        <div class="contact-icon">📍</div>
        <div>
          <div class="contact-label">Location</div>
          <div class="contact-value">Lahore, Pakistan</div>
        </div>
      </div>

      <div style="margin-top:2rem; display:flex; gap:1rem; flex-wrap:wrap;">
        <a href="https://wa.me/923000000000" class="btn-gold" target="_blank">WhatsApp Us</a>
        <a href="mailto:kinza@mirajmarketing.com" class="btn-outline">Send Email</a>
      </div>
    </div>

    <div class="reveal">
      <div class="contact-form">
        <input type="text" placeholder="Your Name *">
        <input type="email" placeholder="Email Address *">
        <input type="tel" placeholder="Phone / WhatsApp Number">
        <select>
          <option value="" disabled selected>Select Service Needed</option>
          <option>Social Media Marketing</option>
          <option>SEO & Google Ads</option>
          <option>Content Creation</option>
          <option>Email Marketing</option>
          <option>Brand Strategy</option>
          <option>Performance Marketing</option>
          <option>Full Package</option>
        </select>
        <textarea placeholder="Tell us about your project..."></textarea>
        <button class="btn-gold" style="width:100%; cursor:pointer; font-family:'DM Sans',sans-serif; font-size:0.8rem; letter-spacing:0.15em; text-transform:uppercase; border:none;" onclick="alert('Shukriya! We will contact you soon. ✦')">Send Message ✦</button>
      </div>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="logo" style="font-size:1.2rem;">MIRAJ<span> Marketing Agency</span></div>
  <div class="footer-copy">© 2025 Miraj Marketing. All rights reserved. | Rawalpindi, Pakistan</div>
  <div class="footer-links">
    <a href="#home">Home</a>
    <a href="#services">Services</a>
    <a href="#contact">Contact</a>
  </div>
</footer>

<!-- WHATSAPP FLOAT -->
<a href="https://wa.me/923000000000" class="wa-float" target="_blank" aria-label="Chat on WhatsApp">
  <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
    <path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z"/>
  </svg>
</a>

<script>
  const observer = new IntersectionObserver((entries) => {
    entries.forEach((e, i) => {
      if (e.isIntersecting) {
        setTimeout(() => e.target.classList.add('visible'), i * 80);
      }
    });
  }, { threshold: 0.1 });

  document.querySelectorAll('.reveal').forEach(el => observer.observe(el));

  document.querySelectorAll('a[href^="#"]').forEach(a => {
    a.addEventListener('click', e => {
      e.preventDefault();
      const t = document.querySelector(a.getAttribute('href'));
      if (t) t.scrollIntoView({ behavior: 'smooth', block: 'start' });
    });
  });
</script>
</body>
</html>
