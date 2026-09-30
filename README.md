<link rel="stylesheet" href="https://unpkg.com/aos@next/dist/aos.css" />
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Outfit:wght@300;400;500;600&family=Syne:wght@700;800&family=Space+Mono&display=swap" rel="stylesheet">

<style>
  :root {
    --bg-color: #e6e9ef;
    --text-color: #1b3d6f;
    --text-light: #ffffff;
    --accent-glow: rgba(255, 153, 51, 0.25);
    --font-titles: 'Syne', sans-serif;
    --font-body: 'Outfit', sans-serif;
    --font-mono: 'Space Mono', monospace;
  }

  html, body {
    margin: 0;
    padding: 0;
    width: 100%;
    height: 100%;
    overflow: hidden;
    background-color: var(--bg-color);
    -webkit-font-smoothing: antialiased;
  }

  .actome-home-screen {
    width: 100%;
    height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    position: relative;
    font-family: var(--font-body);
    color: var(--text-color);
    padding: 0 6%;
    box-sizing: border-box;
  }

  /* --- HEADER CENTRATO PERFETTO --- */
  .actome-top-header {
    position: absolute;
    top: 30px;
    left: 6%;
    right: 6%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    z-index: 20;
  }

  .actome-corner-brand-logo {
    position: absolute;
    left: 50%;
    transform: translateX(-50%);
    top: 0;
  }

  .actome-home-logo-img {
    height: 140px;
    width: auto;
    object-fit: contain;
    display: block;
    transition: transform 0.6s cubic-bezier(0.16, 1, 0.3, 1);
    filter: drop-shadow(0 4px 10px rgba(27, 61, 111, 0.05));
  }

  .actome-home-logo-img:hover {
    transform: scale(1.05) rotate(-2deg);
  }

  .actome-corner-counter {
    font-family: var(--font-mono);
    font-size: 0.75rem;
    opacity: 0.6;
    letter-spacing: 1.5px;
    margin-left: auto;
  }

  /* --- CORNER TAGS --- */
  .actome-corner-tags {
    position: absolute;
    bottom: 40px;
    left: 6%;
    font-family: var(--font-mono);
    font-size: 0.75rem;
    text-transform: uppercase;
    opacity: 0.5;
    line-height: 2;
    letter-spacing: 1px;
  }

  /* --- SFONDO ORBITALE FLUIDO --- */
  .actome-home-screen::before, .actome-home-screen::after {
    content: '';
    position: absolute;
    border-radius: 50%;
    z-index: 1;
    pointer-events: none;
  }

  .actome-home-screen::before {
    top: 15%;
    right: 10%;
    width: 500px;
    height: 500px;
    background: radial-gradient(circle, var(--accent-glow) 0%, transparent 70%);
    filter: blur(80px);
    animation: dynamicOrbit1 22s infinite ease-in-out;
  }

  .actome-home-screen::after {
    bottom: 10%;
    left: 5%;
    width: 600px;
    height: 600px;
    background: radial-gradient(circle, rgba(27, 61, 111, 0.08) 0%, transparent 70%);
    filter: blur(90px);
    animation: dynamicOrbit2 26s infinite ease-in-out;
  }

  @keyframes dynamicOrbit1 {
    0%, 100% { transform: translate(0, 0) scale(1); }
    33% { transform: translate(-80px, 50px) scale(1.15); }
    66% { transform: translate(40px, 90px) scale(0.9); }
  }

  @keyframes dynamicOrbit2 {
    0%, 100% { transform: translate(0, 0) scale(1); }
    50% { transform: translate(60px, -80px) scale(1.1); }
  }

  /* --- CORE CENTRALE & TITOLO STATICO/PULITO --- */
  .actome-main-focus {
    position: relative;
    z-index: 10;
    text-align: center;
    margin-top: 60px;
  }

  .actome-main-focus h1 {
    font-family: var(--font-titles);
    font-size: 6.5rem; /* Ridotto per eleganza e proporzione */
    font-weight: 800;
    line-height: 1;
    margin: 0 0 35px 0;
    text-transform: uppercase;
    letter-spacing: -2px;
    color: var(--text-color);
    cursor: default;
    user-select: none;
    /* Nessuna animazione o trasformazione hover attiva */
  }

  /* --- CTA BUTTON "DISCOVER NOW" IPER-ANIMATO --- */
  .actome-btn-discover {
    display: inline-flex;
    align-items: center;
    gap: 16px;
    font-family: var(--font-mono);
    font-size: 0.85rem;
    color: var(--text-color);
    text-decoration: none;
    text-transform: uppercase;
    font-weight: 600;
    letter-spacing: 3px;
    padding: 18px 42px;
    border: 2px solid var(--text-color);
    border-radius: 50px;
    background: transparent;
    overflow: hidden;
    position: relative;
    transition: color 0.4s cubic-bezier(0.16, 1, 0.3, 1), transform 0.3s ease, border-color 0.4s;
  }

  /* Effetto impulso radar esterno */
  .actome-btn-discover::after {
    content: '';
    position: absolute;
    top: -2px; left: -2px; right: -2px; bottom: -2px;
    border: 2px solid var(--text-color);
    border-radius: 50px;
    opacity: 0.8;
    animation: pulseRadar 2.5s infinite cubic-bezier(0.24, 0, 0.38, 1);
    z-index: -1;
  }

  /* Sfondo riempitivo all'hover */
  .actome-btn-discover::before {
    content: '';
    position: absolute;
    top: 100%;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: var(--text-color);
    z-index: -2;
    transition: top 0.4s cubic-bezier(0.16, 1, 0.3, 1);
  }

  .actome-btn-discover svg {
    width: 16px;
    height: 16px;
    fill: none;
    stroke: var(--text-color);
    stroke-width: 2.5;
    transition: transform 0.4s cubic-bezier(0.16, 1, 0.3, 1), stroke 0.4s ease;
  }

  /* Stati Hover */
  .actome-btn-discover:hover {
    color: var(--text-light);
    border-color: var(--text-color);
    transform: translateY(-4px) scale(1.02);
  }

  .actome-btn-discover:hover::before {
    top: 0;
  }

  .actome-btn-discover:hover::after {
    animation-play-state: paused;
    opacity: 0;
  }

  .actome-btn-discover:hover svg {
    stroke: var(--text-light);
    transform: translateX(8px) scale(1.1);
  }

  @keyframes pulseRadar {
    0% { transform: scale(1); opacity: 0.6; }
    100% { transform: scale(1.18, 1.4); opacity: 0; }
  }

  /* --- RESPONSIVE OPTIMIZATION --- */
  @media (max-width: 992px) {
    .actome-main-focus h1 { font-size: 5rem; letter-spacing: -1px; }
    .actome-corner-tags { display: none; }
    .actome-home-logo-img { height: 100px; }
    .actome-corner-counter { display: none; }
  }

  @media (max-width: 576px) {
    .actome-main-focus h1 { font-size: 3.5rem; margin-bottom: 30px; }
    .actome-btn-discover { padding: 16px 32px; font-size: 0.8rem; }
    .actome-home-logo-img { height: 80px; }
    .actome-top-header { top: 20px; }
  }
</style>

<div class="actome-home-screen">

  <div class="actome-top-header" data-aos="fade-down" data-aos-duration="1200">
    <div class="actome-corner-brand-logo">
      <img class="actome-home-logo-img" src="http://www.ezenale.eu/2026/leonardogariboldi/wp-content/uploads/sites/10/2026/06/Tavola-disegno-1.png" alt="Logo">
    </div>
    <div class="actome-corner-counter">// INDEX: 2026 PROJECTS</div>
  </div>
  
  <div class="actome-corner-tags" data-aos="fade-right" data-aos-delay="400" data-aos-duration="1200">
    // VISUAL IDENTITY<br>
    // PACKAGING DESIGN<br>
    // EDITORIAL ART
  </div>

  <div class="actome-main-focus">
    <h1 data-aos="fade-up" data-aos-delay="200" data-aos-duration="1200">Portfolio</h1>
    
    <a href="https://www.ezenale.eu/2026/leonardogariboldi/header-scelta/" class="actome-btn-discover" data-aos="fade-up" data-aos-delay="500" data-aos-duration="1200">
      DISCOVER NOW
      <svg viewBox="0 0 24 24">
        <path d="M5 12h14M12 5l7 7-7 7"/>
      </svg>
    </a>
  </div>

</div>

<script src="https://unpkg.com/aos@next/dist/aos.js"></script>
<script>
  AOS.init({
    once: true
  });
</script>
