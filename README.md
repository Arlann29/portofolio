<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Arlan — Design Grafis, Thumbnail & Web Design</title>
<meta name="description" content="Arlan bikin desain, thumbnail, dan website yang gampang dipakai dan enak diliat. Cek portofolio dan langsung chat kalau cocok.">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Baloo+2:wght@500;600;700;800&family=Plus+Jakarta+Sans:wght@400;500;600;700;800&display=swap" rel="stylesheet">
<style>
  :root{
    --bg: #EAF3FF;
    --bg-soft: #DCEAFB;
    --surface: #FFFFFF;
    --ink: #17233D;
    --ink-dim: #5C6B85;
    --ink-faint: #93A2BD;
    --accent: #4C8DFF;
    --accent-hover: #3B78E8;
    --accent-dark: #142446;
    --accent-dark-2: #1D3A6E;
    --pop: #FFB454;
    --pop-2: #FF8A73;
    --mint: #6FDCC6;
    --line: rgba(23,35,61,0.10);
    --line-strong: rgba(23,35,61,0.18);
    --radius-lg: 26px;
    --radius-md: 18px;
    --radius-sm: 12px;
    --maxw: 1180px;
    --shadow: 0 14px 34px rgba(76,141,255,0.16);
    --shadow-dark: 0 18px 40px rgba(20,36,70,0.35);
  }
  *{box-sizing:border-box;}
  html{scroll-behavior:smooth;}
  body{
    margin:0;
    background:var(--bg);
    color:var(--ink);
    font-family:'Plus Jakarta Sans',sans-serif;
    -webkit-font-smoothing:antialiased;
    overflow-x:hidden;
  }
  img,svg{display:block;max-width:100%;}
  a{color:inherit;text-decoration:none;}
  .wrap{max-width:var(--maxw);margin:0 auto;padding:0 28px;position:relative;z-index:2;}
  .eyebrow{
    font-size:12px;letter-spacing:.04em;
    color:var(--accent-hover);font-weight:700;
    display:inline-flex;align-items:center;gap:8px;
    background:#fff;padding:8px 16px;border-radius:999px;box-shadow:var(--shadow);
  }
  .eyebrow .dot{width:7px;height:7px;border-radius:50%;background:var(--pop);animation:pulse 1.8s infinite;}
  @keyframes pulse{0%,100%{opacity:1;}50%{opacity:.3;}}
  h1,h2,h3{font-family:'Baloo 2',sans-serif;font-weight:700;line-height:1.08;margin:0;letter-spacing:-0.01em;color:var(--ink);}
  em{font-style:normal;background:linear-gradient(90deg,var(--accent),var(--mint));-webkit-background-clip:text;background-clip:text;color:transparent;}
  ::selection{background:var(--pop);color:var(--ink);}

  /* blobs */
  .blob{position:absolute;border-radius:50%;filter:blur(2px);z-index:0;opacity:.55;}

  /* ---------- marquee bar ---------- */
  .marquee-bar{
    background:var(--accent-dark);
    color:#fff;
    overflow:hidden;
    white-space:nowrap;
    font-size:12px;font-weight:700;letter-spacing:.03em;
    padding:10px 0;
  }
  .marquee-track{display:inline-flex;animation:scroll 26s linear infinite;}
  .marquee-track span{padding:0 24px;display:inline-flex;align-items:center;gap:10px;}
  .marquee-track span::before{content:"✦";color:var(--pop);font-size:11px;}
  @keyframes scroll{from{transform:translateX(0);}to{transform:translateX(-50%);}}

  /* ---------- nav ---------- */
  header{
    position:sticky;top:0;z-index:50;
    background:rgba(234,243,255,0.88);
    backdrop-filter:blur(10px);
    border-bottom:1px solid var(--line);
  }
  nav{
    display:flex;align-items:center;justify-content:space-between;
    padding:16px 28px;max-width:var(--maxw);margin:0 auto;
  }
  .logo{font-family:'Baloo 2',sans-serif;font-size:24px;font-weight:800;letter-spacing:-0.02em;}
  .logo span{color:var(--accent);}
  .nav-links{display:flex;gap:30px;font-size:14px;font-weight:600;color:var(--ink-dim);}
  .nav-links a{transition:color .2s;}
  .nav-links a:hover{color:var(--ink);}
  .nav-cta{
    font-size:13px;font-weight:700;letter-spacing:.01em;
    padding:12px 22px;background:var(--accent);color:#fff;border-radius:999px;
    box-shadow:var(--shadow);transition:all .2s;
  }
  .nav-cta:hover{background:var(--accent-hover);transform:translateY(-1px);}
  .burger{display:none;flex-direction:column;gap:5px;cursor:pointer;background:none;border:none;}
  .burger span{width:22px;height:2px;background:var(--ink);border-radius:2px;}
  .mobile-menu{display:none;}

  /* ---------- hero ---------- */
  .hero{padding:80px 0 60px;position:relative;overflow:hidden;}
  .hero-grid{display:grid;grid-template-columns:1.15fr .85fr;gap:56px;align-items:end;position:relative;z-index:2;}
  .hero h1{font-size:clamp(38px,5.6vw,64px);}
  .hero-sub{margin-top:20px;max-width:490px;color:var(--ink-dim);font-size:16px;line-height:1.65;font-weight:500;}
  .hero-actions{display:flex;gap:14px;margin-top:30px;flex-wrap:wrap;}
  .btn-primary{
    background:var(--accent);color:#fff;
    padding:16px 28px;font-weight:700;font-size:14px;border-radius:999px;
    display:inline-flex;align-items:center;gap:8px;transition:all .2s;box-shadow:var(--shadow);
  }
  .btn-primary:hover{transform:translateY(-2px);background:var(--accent-hover);}
  .btn-ghost{
    padding:16px 28px;font-weight:700;font-size:14px;border-radius:999px;
    background:#fff;border:1px solid var(--line-strong);transition:all .2s;
  }
  .btn-ghost:hover{border-color:var(--accent);color:var(--accent-hover);}
  .hero-strip{
    margin-top:26px;padding-top:18px;
    display:flex;gap:10px;flex-wrap:wrap;
  }
  .chip{
    background:#fff;border:1px solid var(--line);padding:8px 16px;border-radius:999px;
    font-size:12px;font-weight:700;color:var(--ink-dim);
  }

  /* hero mock thumbnail card - signature element */
  .hero-visual{position:relative;}
  .thumb-card{
    aspect-ratio:16/10;border-radius:var(--radius-lg);position:relative;overflow:hidden;
    background:linear-gradient(150deg,#BFE0FF,#7FB2FF 55%,#4C8DFF);
    box-shadow:var(--shadow);
  }
  .thumb-card .glow{
    position:absolute;inset:0;
    background:radial-gradient(circle at 75% 15%, rgba(255,180,84,.55), transparent 55%),
               radial-gradient(circle at 15% 90%, rgba(111,220,198,.5), transparent 50%);
    mix-blend-mode:overlay;
  }
  .thumb-card .tag{
    position:absolute;top:16px;left:16px;background:var(--pop);color:#1a1206;
    font-family:'Baloo 2';font-size:12px;font-weight:700;padding:7px 14px;border-radius:999px;
    transform:rotate(-6deg);box-shadow:0 6px 14px rgba(0,0,0,.15);
  }
  .thumb-card .cap{
    position:absolute;bottom:18px;left:18px;right:18px;
    font-family:'Baloo 2',sans-serif;font-weight:700;font-size:27px;color:#fff;line-height:1.1;
    text-shadow:0 2px 14px rgba(20,36,70,.35);
  }
  .thumb-card .play{
    position:absolute;inset:0;display:flex;align-items:center;justify-content:center;
    opacity:0;transition:opacity .25s;background:rgba(20,36,70,.25);
  }
  .thumb-card:hover .play{opacity:1;}
  .play-btn{
    width:58px;height:58px;border-radius:50%;background:#fff;
    display:flex;align-items:center;justify-content:center;box-shadow:0 8px 20px rgba(20,36,70,.3);
  }
  .play-btn::after{content:"";border-left:14px solid var(--accent);border-top:9px solid transparent;border-bottom:9px solid transparent;margin-left:4px;}
  .hero-visual-caption{margin-top:16px;font-size:12px;color:var(--ink-faint);display:flex;justify-content:space-between;font-weight:600;}

  /* ---------- tentang (conversational intro + student id card) ---------- */
  .about-grid{display:grid;grid-template-columns:1.15fr .85fr;gap:56px;align-items:center;}
  .about-text p{
    font-size:16px;line-height:1.75;color:var(--ink-dim);font-weight:500;margin:18px 0 0;max-width:520px;
  }
  .about-text p strong{color:var(--ink);font-weight:700;}
  .about-chips{display:flex;gap:10px;flex-wrap:wrap;margin-top:26px;}
  .id-card-wrap{display:flex;justify-content:center;position:relative;}
  .id-card{
    width:280px;background:var(--surface);border-radius:22px;padding:26px 24px 24px;
    box-shadow:0 20px 44px rgba(23,35,61,.14);transform:rotate(-4deg);position:relative;
  }
  .id-clip{
    width:70px;height:22px;background:#fff;border:1px solid var(--line-strong);border-radius:8px;
    position:absolute;top:-11px;left:50%;transform:translateX(-50%);box-shadow:0 4px 8px rgba(23,35,61,.1);
  }
  .id-top{display:flex;align-items:center;gap:14px;padding-top:6px;}
  .id-avatar{
    width:56px;height:56px;border-radius:16px;background:linear-gradient(150deg,var(--accent),var(--mint));
    display:flex;align-items:center;justify-content:center;color:#fff;font-family:'Baloo 2';font-weight:800;font-size:24px;flex-shrink:0;
  }
  .id-name{font-family:'Baloo 2';font-weight:700;font-size:19px;}
  .id-role{font-size:12px;color:var(--ink-faint);font-weight:600;margin-top:2px;}
  .id-divider{border-top:1px dashed var(--line-strong);margin:18px 0;}
  .id-row{display:flex;justify-content:space-between;font-size:12px;font-weight:700;color:var(--ink-dim);margin-bottom:10px;}
  .id-row span:last-child{color:var(--ink);}
  .id-status{
    margin-top:16px;display:inline-flex;align-items:center;gap:7px;background:var(--bg-soft);
    padding:8px 14px;border-radius:999px;font-size:11px;font-weight:800;color:var(--accent-hover);
  }
  .id-status .dot{width:7px;height:7px;border-radius:50%;background:var(--mint);animation:pulse 1.8s infinite;}
  .id-barcode{margin-top:18px;height:26px;background:repeating-linear-gradient(90deg,var(--ink) 0 2px,transparent 2px 5px);opacity:.4;border-radius:3px;}
  @media(max-width:860px){
    .about-grid{grid-template-columns:1fr;}
    .id-card-wrap{margin-top:20px;}
  }

  /* ---------- section shell ---------- */
  section{padding:90px 0;position:relative;}
  .section-head{display:flex;justify-content:space-between;align-items:flex-end;gap:24px;margin-bottom:50px;flex-wrap:wrap;}
  .section-head h2{font-size:clamp(28px,3.6vw,42px);max-width:560px;}
  .section-head p{color:var(--ink-dim);max-width:320px;font-size:14px;line-height:1.6;font-weight:500;}

  /* ---------- skills / layanan ---------- */
  .skill-menu{display:grid;grid-template-columns:repeat(3,1fr);gap:22px;}
  .skill-card{
    background:var(--surface);padding:32px 28px;border-radius:var(--radius-lg);
    box-shadow:0 10px 26px rgba(23,35,61,.06);transition:transform .25s,box-shadow .25s;
  }
  .skill-card:hover{transform:translateY(-5px);box-shadow:var(--shadow);}
  .skill-icon{
    width:52px;height:52px;border-radius:16px;display:flex;align-items:center;justify-content:center;
    font-family:'Baloo 2';font-weight:700;font-size:18px;color:#fff;
  }
  .skill-card:nth-child(1) .skill-icon{background:var(--accent);}
  .skill-card:nth-child(2) .skill-icon{background:var(--pop-2);}
  .skill-card:nth-child(3) .skill-icon{background:var(--mint);}
  .skill-card h3{font-size:24px;margin-top:18px;}
  .skill-card p{color:var(--ink-dim);font-size:14px;line-height:1.6;margin-top:10px;font-weight:500;}
  .skill-list{list-style:none;padding:0;margin:20px 0 0;display:flex;flex-direction:column;gap:9px;}
  .skill-list li{
    font-size:13px;color:var(--ink-dim);padding-left:20px;position:relative;font-weight:600;
  }
  .skill-list li::before{content:"✓";position:absolute;left:0;color:var(--accent);font-weight:800;}
  .skill-price{
    margin-top:22px;padding-top:16px;border-top:1px dashed var(--line-strong);
    font-size:12px;color:var(--ink-faint);font-weight:700;
  }
  .skill-price b{color:var(--ink);font-family:'Baloo 2',sans-serif;font-size:16px;}

  /* ---------- portfolio ---------- */
  .filter-tabs{display:flex;gap:10px;flex-wrap:wrap;margin-bottom:36px;}
  .filter-tab{
    padding:10px 20px;font-size:13px;font-weight:700;border:none;border-radius:999px;
    color:var(--ink-dim);cursor:pointer;background:#fff;transition:all .2s;box-shadow:0 4px 12px rgba(23,35,61,.05);
  }
  .filter-tab.active,.filter-tab:hover{background:var(--accent);color:#fff;}
  .portfolio-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:22px;}
  .p-card{
    background:var(--surface);border-radius:var(--radius-md);overflow:hidden;
    box-shadow:0 10px 24px rgba(23,35,61,.06);transition:transform .25s,box-shadow .25s;
  }
  .p-card:hover{transform:translateY(-5px);box-shadow:var(--shadow);}
  .p-thumb{aspect-ratio:16/10;position:relative;overflow:hidden;}
  .p-thumb .cap{
    position:absolute;bottom:14px;left:14px;right:14px;font-family:'Baloo 2',sans-serif;font-weight:700;
    font-size:18px;color:#fff;line-height:1.15;text-shadow:0 2px 10px rgba(20,36,70,.4);
  }
  .p-thumb .kicker{
    position:absolute;top:12px;left:12px;font-size:10px;font-weight:800;color:var(--ink);
    background:#fff;padding:5px 10px;border-radius:999px;
  }
  .p-body{padding:16px 18px 20px;display:flex;justify-content:space-between;align-items:center;}
  .p-body .client{font-size:12px;color:var(--ink-faint);font-weight:600;}
  .p-body .arrow{font-size:16px;color:var(--accent);font-weight:800;}
  .g1{background:linear-gradient(150deg,#BFE0FF,#4C8DFF);}
  .g1 .glow{background:radial-gradient(circle at 80% 15%, rgba(255,180,84,.5), transparent 55%);}
  .g2{background:linear-gradient(150deg,#B9F1E4,#3FBFA4);}
  .g2 .glow{background:radial-gradient(circle at 20% 80%, rgba(76,141,255,.4), transparent 55%);}
  .g3{background:linear-gradient(150deg,#FFD3A8,#FF8A73);}
  .g3 .glow{background:radial-gradient(circle at 70% 75%, rgba(76,141,255,.4), transparent 55%);}
  .glow{position:absolute;inset:0;mix-blend-mode:overlay;}

  /* ---------- stats (dark accent band) ---------- */
  .stats-band{background:var(--accent-dark);padding:64px 0;position:relative;overflow:hidden;}
  .stats{display:grid;grid-template-columns:repeat(4,1fr);gap:22px;position:relative;z-index:2;}
  .stat{background:rgba(255,255,255,0.06);padding:28px 24px;border-radius:var(--radius-md);border:1px solid rgba(255,255,255,0.08);}
  .stat .num{font-family:'Baloo 2',sans-serif;font-size:36px;color:var(--pop);}
  .stat .label{margin-top:8px;font-size:13px;color:rgba(255,255,255,0.75);line-height:1.5;font-weight:600;}

  /* ---------- process ---------- */
  .process-list{display:grid;grid-template-columns:repeat(4,1fr);gap:20px;}
  .process-item{
    background:var(--surface);border-radius:var(--radius-md);padding:26px 22px;
    box-shadow:0 10px 24px rgba(23,35,61,.06);
  }
  .process-item .idx{
    width:34px;height:34px;border-radius:10px;background:var(--accent);color:#fff;
    display:flex;align-items:center;justify-content:center;font-family:'Baloo 2';font-weight:700;font-size:14px;
  }
  .process-item h3{font-size:19px;margin-top:16px;}
  .process-item p{color:var(--ink-dim);font-size:13px;line-height:1.6;margin:8px 0 0;font-weight:500;}

  /* ---------- testimonial ---------- */
  .testi{
    background:var(--surface);padding:56px;border-radius:var(--radius-lg);
    display:grid;grid-template-columns:1fr auto;gap:30px;align-items:center;
    box-shadow:0 10px 26px rgba(23,35,61,.06);
  }
  .testi blockquote{
    margin:0;font-family:'Baloo 2',sans-serif;font-weight:600;font-size:clamp(20px,2.4vw,28px);line-height:1.4;
  }
  .testi cite{display:block;margin-top:20px;font-style:normal;font-size:13px;color:var(--ink-faint);font-weight:600;}
  .testi-mark{font-family:'Baloo 2',sans-serif;font-size:80px;color:var(--pop);line-height:1;}

  /* ---------- CTA / kontak ---------- */
  .cta-section{padding-top:0;}
  .cta-card{
    background:var(--accent-dark);border-radius:var(--radius-lg);padding:76px 40px;text-align:center;
    position:relative;overflow:hidden;
  }
  .cta-card h2{color:#fff;font-size:clamp(32px,4.6vw,50px);max-width:720px;margin:0 auto;position:relative;z-index:2;}
  .cta-card .hero-sub{margin:18px auto 0;text-align:center;color:rgba(255,255,255,0.75);position:relative;z-index:2;}
  .cta-form{margin:34px auto 0;max-width:460px;display:flex;gap:10px;position:relative;z-index:2;}
  .cta-form input{
    flex:1;background:rgba(255,255,255,0.08);border:1px solid rgba(255,255,255,0.18);color:#fff;
    padding:15px 20px;border-radius:999px;font-family:'Plus Jakarta Sans';font-size:14px;
  }
  .cta-form input::placeholder{color:rgba(255,255,255,0.5);}
  .cta-form button{border:none;cursor:pointer;}
  .cta-note{margin-top:16px;font-size:12px;color:rgba(255,255,255,0.55);position:relative;z-index:2;font-weight:600;}

  /* ---------- footer ---------- */
  footer{padding:60px 0 30px;}
  .footer-top{display:grid;grid-template-columns:1.4fr 1fr 1fr 1fr;gap:40px;padding-bottom:44px;border-bottom:1px solid var(--line);}
  .footer-top p{color:var(--ink-dim);font-size:13px;line-height:1.7;max-width:270px;margin-top:14px;font-weight:500;}
  .footer-col h4{font-size:12px;text-transform:uppercase;letter-spacing:.06em;color:var(--ink-faint);margin-bottom:16px;font-weight:800;}
  .footer-col ul{list-style:none;padding:0;margin:0;display:flex;flex-direction:column;gap:10px;}
  .footer-col a{font-size:13px;color:var(--ink-dim);font-weight:600;transition:color .2s;}
  .footer-col a:hover{color:var(--accent);}
  .footer-bottom{display:flex;justify-content:space-between;padding-top:22px;font-size:12px;color:var(--ink-faint);flex-wrap:wrap;gap:10px;font-weight:600;}

  /* ---------- responsive ---------- */
  @media(max-width:860px){
    .nav-links{display:none;}
    .burger{display:flex;}
    .hero-grid{grid-template-columns:1fr;}
    .skill-menu{grid-template-columns:1fr;}
    .portfolio-grid{grid-template-columns:1fr 1fr;}
    .stats{grid-template-columns:1fr 1fr;}
    .process-list{grid-template-columns:1fr 1fr;}
    .testi{grid-template-columns:1fr;padding:36px 24px;}
    .testi-mark{display:none;}
    .footer-top{grid-template-columns:1fr 1fr;}
    .cta-form{flex-direction:column;}
    .cta-card{padding:56px 26px;}
  }
  @media(max-width:560px){
    .portfolio-grid{grid-template-columns:1fr;}
    .stats{grid-template-columns:1fr 1fr;}
    .process-list{grid-template-columns:1fr;}
    .footer-top{grid-template-columns:1fr;}
    .mobile-menu.open{
      display:flex;flex-direction:column;gap:2px;background:var(--bg-soft);
      padding:10px 28px 22px;border-bottom:1px solid var(--line);
    }
    .mobile-menu a{padding:12px 0;font-size:15px;font-weight:700;border-bottom:1px solid var(--line);color:var(--ink-dim);}
  }
</style>
</head>
<body>

<div class="marquee-bar">
  <div class="marquee-track" id="marquee">
    <span>Slot Juli masih available, gaskeun!</span>
    <span>Revisi 2× gratis, no drama</span>
    <span>Auto dibales max 24 jam</span>
    <span>150+ project udah kelar sejak 2020</span>
    <span>Slot Juli masih available, gaskeun!</span>
    <span>Revisi 2× gratis, no drama</span>
    <span>Auto dibales max 24 jam</span>
    <span>150+ project udah kelar sejak 2020</span>
  </div>
</div>

<header>
  <nav>
    <a href="#beranda" class="logo">Arlan<span>.</span></a>
    <div class="nav-links">
      <a href="#tentang">Tentang</a>
      <a href="#layanan">Layanan</a>
      <a href="#karya">Karya</a>
      <a href="#proses">Proses</a>
      <a href="#testimoni">Testimoni</a>
    </div>
    <a href="#kontak" class="nav-cta">Gas Ngobrol</a>
    <button class="burger" id="burger" aria-label="Buka menu"><span></span><span></span><span></span></button>
  </nav>
  <div class="mobile-menu" id="mobileMenu">
    <a href="#tentang">Tentang</a>
    <a href="#layanan">Layanan</a>
    <a href="#karya">Karya</a>
    <a href="#proses">Proses</a>
    <a href="#testimoni">Testimoni</a>
    <a href="#kontak">Kontak</a>
  </div>
</header>

<section class="hero" id="beranda">
  <div class="blob" style="width:340px;height:340px;background:#FFD9A8;top:-80px;right:-60px;"></div>
  <div class="blob" style="width:220px;height:220px;background:#BFEFE2;bottom:-40px;left:-40px;opacity:.5;"></div>
  <div class="wrap hero-grid">
    <div>
      <span class="eyebrow"><span class="dot"></span> Sisa 3 slot proyek bulan ini</span>
      <h1 style="margin-top:20px;">Desain yang bikin orang <em>berhenti scroll.</em></h1>
      <p class="hero-sub">Halo, Arlan di sini! 👋 Gue suka ngeracik landing page kece pakai Tailwind, bikin aset grafis estetik yang eye-catching, plus thumbnail YouTube yang asik dan gampang bikin klik. Semuanya punya satu tugas: nyantol di kepala orang dan bikin mereka klik — dikerjain santai, tapi tetap terukur dan bergaransi. Bukan cuma cantik doang, tapi kerja.</p>
      <div class="hero-actions">
        <a href="#kontak" class="btn-primary">Gas Mulai Proyek →</a>
        <a href="#karya" class="btn-ghost">Intip Karya</a>
      </div>
      <div class="hero-strip">
        <span class="chip">🎨 Design Grafis</span>
        <span class="chip">🖼️ Thumbnail</span>
        <span class="chip">💻 Web Design</span>
      </div>
    </div>
    <div class="hero-visual">
      <div class="thumb-card">
        <div class="glow"></div>
        <span class="tag">CTR +48% 🔥</span>
        <div class="cap">Ganti Thumbnail-nya,<br>Ganti Nasib Video-nya.</div>
        <div class="play"><div class="play-btn"></div></div>
      </div>
      <div class="hero-visual-caption">
        <span>Thumbnail — Channel edukasi, 210K subscriber</span>
        <span>16:9</span>
      </div>
    </div>
  </div>
</section>

<section id="tentang">
  <div class="wrap about-grid">
    <div class="about-text">
      <span class="eyebrow"><span class="dot"></span> Sebelum lanjut, kenalan dulu yuk</span>
      <h2 style="margin-top:20px;">Iya, gue masih SMA. <em>Tapi portofolio gak nanya umur.</em></h2>
      <p>Gue Arlan, baru aja naik ke kelas 12 — dan portofolio ini sengaja gue bikin buat ngerayain itu, sekaligus mulai lebih serius nawarin skill design ke orang lain. Awalnya desain cuma pelarian dari tugas Matematika: iseng bikin poster buat mading sekolah, eh malah dilirik. Terus dipercaya bikin logo ekskul, thumbnail buat channel YouTube kakak kelas, sampe akhirnya berani nerima klien beneran.</p>
      <p>Sekarang, tiap malem abis pulang sekolah, laptop gue kebuka bukan buat scroll TikTok doang — tapi buat ngulik brief klien, mainin warna, sampe nyari font yang <strong>pas banget</strong> rasanya. Prosesnya gak selalu mulus, PR numpuk juga tetep jalan. Tapi soal hasil, biar karya yang ngomong — scroll dikit lagi ke bawah, lo bakal liat sendiri.</p>
      <div class="about-chips">
        <span class="chip">📚 Baru naik kelas 12</span>
        <span class="chip">🎨 Belajar desain sejak 2020</span>
        <span class="chip">📦 150+ project kelar</span>
      </div>
    </div>
    <div class="id-card-wrap">
      <div class="id-card">
        <div class="id-clip"></div>
        <div class="id-top">
          <div class="id-avatar">A</div>
          <div>
            <div class="id-name">Arlan</div>
            <div class="id-role">Siswa Kelas 12 · Designer Lepas</div>
          </div>
        </div>
        <div class="id-divider"></div>
        <div class="id-row"><span>Skill utama</span><span>Grafis, Thumbnail, Web</span></div>
        <div class="id-row"><span>Ngedesain sejak</span><span>2020</span></div>
        <div class="id-row"><span>Jam kerja favorit</span><span>Malem, abis PR kelar</span></div>
        <span class="id-status"><span class="dot"></span> Available buat proyek</span>
        <div class="id-barcode"></div>
      </div>
    </div>
  </div>
</section>

<section id="layanan">
  <div class="wrap">
    <div class="section-head">
      <h2>Pilih skill, <em>langsung gaspol.</em></h2>
      <p>Bukan sekadar jasa desain — ini biar kontenmu susah dilewatin orang.</p>
    </div>
    <div class="skill-menu">
      <div class="skill-card">
        <div class="skill-icon">01</div>
        <h3>Design Grafis</h3>
        <p>Visual yang bikin brand-mu keinget, bukan cuma keliatan sekilas.</p>
        <ul class="skill-list">
          <li>Logo & brand identity</li>
          <li>Social media kit</li>
          <li>Poster & banner promo</li>
          <li>Desain kemasan produk</li>
        </ul>
        <div class="skill-price">Mulai dari <b>Rp350K</b> / proyek</div>
      </div>
      <div class="skill-card">
        <div class="skill-icon">02</div>
        <h3>Thumbnail Design</h3>
        <p>Thumbnail yang bikin jempol orang berhenti scroll, terus klik.</p>
        <ul class="skill-list">
          <li>Thumbnail YouTube</li>
          <li>Cover podcast & reels</li>
          <li>Set A/B testing thumbnail</li>
          <li>Channel branding kit</li>
        </ul>
        <div class="skill-price">Mulai dari <b>Rp75K</b> / thumbnail</div>
      </div>
      <div class="skill-card">
        <div class="skill-icon">03</div>
        <h3>Web Design</h3>
        <p>Website yang bikin orang betah, bukan langsung tutup tab.</p>
        <ul class="skill-list">
          <li>Landing page</li>
          <li>UI/UX web app</li>
          <li>Redesign website</li>
          <li>Prototype interaktif</li>
        </ul>
        <div class="skill-price">Mulai dari <b>Rp850K</b> / halaman</div>
      </div>
    </div>
  </div>
</section>

<section id="karya">
  <div class="wrap">
    <div class="section-head">
      <h2>Bukti kerja, <em>bukan cuma omongan.</em></h2>
      <p>Proyek asli dari klien asli — bukan mockup pajangan doang.</p>
    </div>
    <div class="filter-tabs" id="filterTabs">
      <button class="filter-tab active" data-filter="all">Semua</button>
      <button class="filter-tab" data-filter="grafis">Design Grafis</button>
      <button class="filter-tab" data-filter="thumbnail">Thumbnail</button>
      <button class="filter-tab" data-filter="web">Web Design</button>
    </div>
    <div class="portfolio-grid" id="portfolioGrid">

      <div class="p-card" data-cat="grafis">
        <div class="p-thumb g1"><div class="glow"></div><span class="kicker">Design Grafis</span><div class="cap">Rebranding Kopi Lokal</div></div>
        <div class="p-body"><span class="client">Klien — Kedai Kopi Rebun</span><span class="arrow">↗</span></div>
      </div>

      <div class="p-card" data-cat="thumbnail">
        <div class="p-thumb g3"><div class="glow"></div><span class="kicker">Thumbnail</span><div class="cap">Seri "Bongkar Skill"</div></div>
        <div class="p-body"><span class="client">Klien — Channel edukasi 210K</span><span class="arrow">↗</span></div>
      </div>

      <div class="p-card" data-cat="web">
        <div class="p-thumb g2"><div class="glow"></div><span class="kicker">Web Design</span><div class="cap">Landing Page SaaS</div></div>
        <div class="p-body"><span class="client">Klien — Studio Alur</span><span class="arrow">↗</span></div>
      </div>

      <div class="p-card" data-cat="grafis">
        <div class="p-thumb g2"><div class="glow"></div><span class="kicker">Design Grafis</span><div class="cap">Kit Sosial Media</div></div>
        <div class="p-body"><span class="client">Klien — Ruang Belajar</span><span class="arrow">↗</span></div>
      </div>

      <div class="p-card" data-cat="thumbnail">
        <div class="p-thumb g1"><div class="glow"></div><span class="kicker">Thumbnail</span><div class="cap">Review Gadget Mingguan</div></div>
        <div class="p-body"><span class="client">Klien — TechTalk ID</span><span class="arrow">↗</span></div>
      </div>

      <div class="p-card" data-cat="web">
        <div class="p-thumb g3"><div class="glow"></div><span class="kicker">Web Design</span><div class="cap">Redesign Portal Komunitas</div></div>
        <div class="p-body"><span class="client">Klien — Komunitas Kreator</span><span class="arrow">↗</span></div>
      </div>

    </div>
  </div>
</section>

<div class="stats-band">
  <div class="wrap">
    <div class="stats">
      <div class="stat"><div class="num">150+</div><div class="label">Proyek kelar, 0 drama</div></div>
      <div class="stat"><div class="num">4.9/5</div><div class="label">Rating dari klien asli</div></div>
      <div class="stat"><div class="num">24 jam</div><div class="label">Respon, gak bikin nunggu</div></div>
      <div class="stat"><div class="num">2×</div><div class="label">Revisi, tanpa biaya tambahan</div></div>
    </div>
  </div>
</div>

<section id="proses">
  <div class="wrap">
    <div class="section-head">
      <h2>Prosesnya jelas, <em>gak ada drama tambahan.</em></h2>
      <p>4 langkah, dari brief lo sampe file di tangan lo.</p>
    </div>
    <div class="process-list">
      <div class="process-item">
        <span class="idx">01</span>
        <h3>Brief & riset</h3>
        <p>Cerita kebutuhan & referensi lo — langsung ditanggepin, gak didiemin.</p>
      </div>
      <div class="process-item">
        <span class="idx">02</span>
        <h3>Konsep awal</h3>
        <p>2–3 arah desain meluncur, lengkap sama alasan kenapa itu cocok buat lo.</p>
      </div>
      <div class="process-item">
        <span class="idx">03</span>
        <h3>Revisi terarah</h3>
        <p>2× revisi biar hasilnya bener sesuai bayangan lo, bukan asal "oke deh".</p>
      </div>
      <div class="process-item">
        <span class="idx">04</span>
        <h3>Delivery</h3>
        <p>File final rapi & lengkap dikirim, gak ada bagian yang ketinggalan.</p>
      </div>
    </div>
  </div>
</section>

<section id="testimoni">
  <div class="wrap">
    <div class="testi">
      <div>
        <blockquote>Thumbnail dari Arlan naikin CTR channel gue hampir <em>dua kali lipat</em> dalam sebulan — komunikasinya juga gercep, gak pernah bikin nunggu.</blockquote>
        <cite>— Reza, Pemilik Channel TechTalk ID</cite>
      </div>
      <div class="testi-mark">”</div>
    </div>
  </div>
</section>

<section class="cta-section" id="kontak">
  <div class="wrap">
    <div class="cta-card">
      <div class="blob" style="width:260px;height:260px;background:rgba(255,180,84,.18);top:-60px;left:-40px;"></div>
      <div class="blob" style="width:200px;height:200px;background:rgba(111,220,198,.18);bottom:-50px;right:-30px;"></div>
      <span class="eyebrow" style="background:rgba(255,255,255,0.1);color:#fff;box-shadow:none;">Slot Juli terbatas</span>
      <h2 style="margin-top:18px;">Ada ide? <em style="background:none;-webkit-background-clip:unset;background-clip:unset;color:var(--pop);">Jangan cuma disimpen di Notes.</em></h2>
      <p class="hero-sub">Auto dibales max 24 jam, lengkap sama estimasi harga & waktu kelarnya.</p>
      <form class="cta-form" onsubmit="event.preventDefault(); this.querySelector('button').textContent='Terkirim ✓';">
        <input type="email" placeholder="Email kamu" required>
        <button type="submit" class="btn-primary">Kirim brief →</button>
      </form>
      <p class="cta-note">Atau gas langsung chat via WhatsApp / Instagram di footer bawah ini.</p>
    </div>
  </div>
</section>

<footer>
  <div class="wrap">
    <div class="footer-top">
      <div>
        <a href="#beranda" class="logo">Arlan<span>.</span></a>
        <p>Freelance designer yang gaskeun bikin identitas visual, thumbnail, sampe website — based di Indonesia, layanin klien dari mana aja.</p>
      </div>
      <div class="footer-col">
        <h4>Layanan</h4>
        <ul>
          <li><a href="#layanan">Design Grafis</a></li>
          <li><a href="#layanan">Thumbnail Design</a></li>
          <li><a href="#layanan">Web Design</a></li>
        </ul>
      </div>
      <div class="footer-col">
        <h4>Halaman</h4>
        <ul>
          <li><a href="#karya">Karya</a></li>
          <li><a href="#proses">Proses</a></li>
          <li><a href="#testimoni">Testimoni</a></li>
        </ul>
      </div>
      <div class="footer-col">
        <h4>Kontak</h4>
        <ul>
          <li><a href="mailto:hello@arlan.design">hello@arlan.design</a></li>
          <li><a href="#">Instagram</a></li>
          <li><a href="#">WhatsApp</a></li>
        </ul>
      </div>
    </div>
    <div class="footer-bottom">
      <span>© 2026 Arlan. Semua hak cipta dilindungi.</span>
      <span>Didesain & dikembangin sendiri, dari nol.</span>
    </div>
  </div>
</footer>

<script>
  const burger = document.getElementById('burger');
  const mobileMenu = document.getElementById('mobileMenu');
  burger.addEventListener('click', () => mobileMenu.classList.toggle('open'));
  mobileMenu.querySelectorAll('a').forEach(a => a.addEventListener('click', () => mobileMenu.classList.remove('open')));

  const tabs = document.querySelectorAll('.filter-tab');
  const cards = document.querySelectorAll('.p-card');
  tabs.forEach(tab => {
    tab.addEventListener('click', () => {
      tabs.forEach(t => t.classList.remove('active'));
      tab.classList.add('active');
      const filter = tab.dataset.filter;
      cards.forEach(card => {
        card.style.display = (filter === 'all' || card.dataset.cat === filter) ? '' : 'none';
      });
    });
  });
</script>
</body>
</html>
