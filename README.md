<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>ADS Agro – Tecnologia para o Campo</title>

  <!-- Google Fonts -->
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700;900&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet" />

  <!-- Font Awesome (ícones) -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css" />

  <style>
    /* ===== TOKENS ===== */
    :root {
      --verde-escuro:  #1a3a1e;
      --verde-medio:   #2d6a35;
      --verde-claro:   #4caf50;
      --ouro:          #c8941a;
      --ouro-claro:    #f0b429;
      --terra:         #8b5e3c;
      --creme:         #f9f6f0;
      --branco:        #ffffff;
      --cinza-leve:    #f2f2f2;
      --cinza-texto:   #444444;
      --preto-suave:   #1a1a1a;
      --font-display:  'Playfair Display', serif;
      --font-body:     'Inter', sans-serif;
      --radius:        10px;
      --sombra:        0 4px 20px rgba(0,0,0,.12);
    }

    /* ===== RESET & BASE ===== */
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
    html { scroll-behavior: smooth; }
    body { font-family: var(--font-body); color: var(--cinza-texto); background: var(--branco); }
    img  { max-width: 100%; display: block; }
    a    { text-decoration: none; color: inherit; }

    /* ===== UTILITÁRIOS ===== */
    .container { width: 92%; max-width: 1180px; margin: 0 auto; }
    .section-label { font-size: .75rem; letter-spacing: .18em; text-transform: uppercase; color: var(--ouro); font-weight: 600; margin-bottom: .4rem; }
    .section-title  { font-family: var(--font-display); font-size: clamp(1.8rem, 4vw, 2.8rem); color: var(--verde-escuro); line-height: 1.2; }
    .section-sub    { margin-top: .8rem; font-size: 1rem; color: #666; max-width: 620px; line-height: 1.7; }
    .btn-primary    { display: inline-block; padding: .75rem 2rem; background: var(--verde-claro); color: #fff; border-radius: 50px; font-weight: 600; font-size: .95rem; transition: background .2s, transform .15s; border: none; cursor: pointer; }
    .btn-primary:hover { background: var(--verde-medio); transform: translateY(-2px); }
    .btn-outline    { display: inline-block; padding: .75rem 2rem; border: 2px solid var(--verde-claro); color: var(--verde-claro); border-radius: 50px; font-weight: 600; font-size: .95rem; transition: all .2s; cursor: pointer; background: transparent; }
    .btn-outline:hover { background: var(--verde-claro); color: #fff; }
    section { padding: 90px 0; }

    /* ===== NAVBAR ===== */
    #navbar {
      position: fixed; top: 0; left: 0; width: 100%; z-index: 1000;
      background: rgba(26, 58, 30, .97); backdrop-filter: blur(8px);
      box-shadow: 0 2px 12px rgba(0,0,0,.25);
      transition: padding .3s;
    }
    #navbar .container { display: flex; align-items: center; justify-content: space-between; padding: 1rem 0; }
    .nav-logo { display: flex; align-items: center; gap: .6rem; }
    .nav-logo .logo-icon { width: 42px; height: 42px; background: var(--ouro); border-radius: 8px; display: flex; align-items: center; justify-content: center; }
    .nav-logo .logo-icon i { color: #fff; font-size: 1.2rem; }
    .nav-logo span { font-family: var(--font-display); color: #fff; font-size: 1.3rem; font-weight: 700; }
    .nav-logo span em { color: var(--ouro-claro); font-style: normal; }
    .nav-links { display: flex; gap: 1.8rem; list-style: none; }
    .nav-links a { color: rgba(255,255,255,.82); font-size: .9rem; font-weight: 500; transition: color .2s; }
    .nav-links a:hover { color: var(--ouro-claro); }
    .nav-cta { padding: .5rem 1.4rem; background: var(--ouro); color: #fff; border-radius: 50px; font-weight: 600; font-size: .88rem; transition: background .2s; }
    .nav-cta:hover { background: var(--ouro-claro); }
    .hamburger { display: none; flex-direction: column; gap: 5px; cursor: pointer; }
    .hamburger span { width: 26px; height: 2px; background: #fff; border-radius: 2px; transition: all .3s; }

    /* ===== HERO ===== */
    #hero {
      min-height: 100vh; padding-top: 80px;
      background:
        linear-gradient(135deg, rgba(26,58,30,.88) 0%, rgba(45,106,53,.75) 55%, rgba(200,148,26,.35) 100%),
        url('https://images.unsplash.com/photo-1501854140801-50d01698950b?w=1600&q=80') center/cover no-repeat;
      display: flex; align-items: center;
    }
    .hero-inner { max-width: 680px; }
    .hero-badge { display: inline-block; padding: .35rem 1rem; background: rgba(200,148,26,.25); border: 1px solid var(--ouro); border-radius: 50px; color: var(--ouro-claro); font-size: .8rem; font-weight: 600; letter-spacing: .1em; text-transform: uppercase; margin-bottom: 1.2rem; }
    .hero-title { font-family: var(--font-display); font-size: clamp(2.4rem, 6vw, 4.2rem); color: #fff; line-height: 1.1; margin-bottom: 1.2rem; }
    .hero-title span { color: var(--ouro-claro); }
    .hero-sub { color: rgba(255,255,255,.85); font-size: 1.1rem; line-height: 1.7; margin-bottom: 2.2rem; max-width: 520px; }
    .hero-actions { display: flex; gap: 1rem; flex-wrap: wrap; }
    .hero-actions .btn-primary { background: var(--ouro); }
    .hero-actions .btn-primary:hover { background: var(--ouro-claro); }
    .hero-actions .btn-outline { border-color: rgba(255,255,255,.6); color: #fff; }
    .hero-actions .btn-outline:hover { background: rgba(255,255,255,.15); }
    .hero-stats { display: flex; gap: 2.5rem; margin-top: 3.5rem; flex-wrap: wrap; }
    .hero-stat strong { display: block; font-family: var(--font-display); font-size: 2rem; color: var(--ouro-claro); }
    .hero-stat span { font-size: .82rem; color: rgba(255,255,255,.7); }

    /* ===== SOBRE ===== */
    #sobre { background: var(--creme); }
    .sobre-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 4rem; align-items: center; margin-top: 3rem; }
    .sobre-img { position: relative; border-radius: var(--radius); overflow: hidden; box-shadow: var(--sombra); }
    .sobre-img img { width: 100%; height: 420px; object-fit: cover; }
    .sobre-img .badge-anos { position: absolute; bottom: 1.4rem; left: 1.4rem; background: var(--verde-escuro); color: #fff; padding: .8rem 1.2rem; border-radius: var(--radius); }
    .sobre-img .badge-anos strong { font-family: var(--font-display); font-size: 1.8rem; color: var(--ouro-claro); }
    .sobre-img .badge-anos span { display: block; font-size: .75rem; opacity: .8; }
    .mvv { display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 1rem; margin-top: 1.8rem; }
    .mvv-card { background: #fff; padding: 1.2rem; border-radius: var(--radius); border-left: 4px solid var(--verde-claro); }
    .mvv-card h4 { font-size: .85rem; font-weight: 700; color: var(--verde-escuro); margin-bottom: .4rem; text-transform: uppercase; letter-spacing: .06em; }
    .mvv-card p { font-size: .82rem; color: #666; line-height: 1.6; }

    /* ===== DIFERENCIAIS ===== */
    #diferenciais { background: var(--verde-escuro); }
    #diferenciais .section-title { color: #fff; }
    #diferenciais .section-sub { color: rgba(255,255,255,.7); }
    .diferenciais-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 1.6rem; margin-top: 3rem; }
    .dif-card { background: rgba(255,255,255,.07); border: 1px solid rgba(255,255,255,.12); border-radius: var(--radius); padding: 2rem 1.6rem; transition: background .2s; }
    .dif-card:hover { background: rgba(255,255,255,.13); }
    .dif-icon { width: 52px; height: 52px; background: var(--ouro); border-radius: 12px; display: flex; align-items: center; justify-content: center; margin-bottom: 1.2rem; }
    .dif-icon i { color: #fff; font-size: 1.4rem; }
    .dif-card h3 { font-family: var(--font-display); font-size: 1.15rem; color: #fff; margin-bottom: .6rem; }
    .dif-card p { font-size: .87rem; color: rgba(255,255,255,.65); line-height: 1.7; }

    /* ===== NUMEROS ===== */
    #numeros { background: var(--ouro); padding: 60px 0; }
    .numeros-grid { display: grid; grid-template-columns: repeat(4, 1fr); gap: 2rem; text-align: center; }
    .num-item strong { font-family: var(--font-display); font-size: 3rem; color: var(--verde-escuro); }
    .num-item span { display: block; font-size: .9rem; color: rgba(26,58,30,.75); font-weight: 500; }

    /* ===== SERVIÇOS ===== */
    #servicos { background: var(--branco); }
    .servicos-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 1.8rem; margin-top: 3rem; }
    .serv-card { border-radius: var(--radius); overflow: hidden; box-shadow: var(--sombra); transition: transform .25s; }
    .serv-card:hover { transform: translateY(-6px); }
    .serv-card img { width: 100%; height: 200px; object-fit: cover; }
    .serv-body { padding: 1.5rem; }
    .serv-body .tag { display: inline-block; font-size: .72rem; padding: .25rem .7rem; background: #e8f5e9; color: var(--verde-medio); border-radius: 50px; font-weight: 600; margin-bottom: .7rem; }
    .serv-body h3 { font-family: var(--font-display); font-size: 1.15rem; color: var(--verde-escuro); margin-bottom: .5rem; }
    .serv-body p { font-size: .87rem; color: #666; line-height: 1.65; }
    .serv-body a { display: inline-block; margin-top: 1rem; font-size: .85rem; color: var(--verde-claro); font-weight: 600; }
    .serv-body a i { margin-left: .3rem; font-size: .7rem; }

    /* ===== GALERIA ===== */
    #galeria { background: var(--cinza-leve); }
    .galeria-grid { display: grid; grid-template-columns: repeat(3, 1fr); grid-auto-rows: 220px; gap: .8rem; margin-top: 3rem; }
    .galeria-item { border-radius: var(--radius); overflow: hidden; position: relative; cursor: pointer; }
    .galeria-item img { width: 100%; height: 100%; object-fit: cover; transition: transform .4s; }
    .galeria-item:hover img { transform: scale(1.07); }
    .galeria-item.wide  { grid-column: span 2; }
    .galeria-overlay { position: absolute; inset: 0; background: rgba(26,58,30,.5); opacity: 0; transition: opacity .3s; display: flex; align-items: center; justify-content: center; }
    .galeria-overlay i { color: #fff; font-size: 1.8rem; }
    .galeria-item:hover .galeria-overlay { opacity: 1; }

    /* ===== EQUIPE ===== */
    #equipe { background: var(--creme); }
    .equipe-grid { display: grid; grid-template-columns: repeat(4, 1fr); gap: 1.8rem; margin-top: 3rem; }
    .membro-card { text-align: center; }
    .membro-foto { width: 110px; height: 110px; border-radius: 50%; margin: 0 auto 1rem; overflow: hidden; border: 4px solid var(--verde-claro); }
    .membro-foto img { width: 100%; height: 100%; object-fit: cover; }
    .membro-card h4 { font-family: var(--font-display); font-size: 1rem; color: var(--verde-escuro); }
    .membro-card p  { font-size: .82rem; color: var(--ouro); font-weight: 600; margin: .2rem 0 .5rem; }
    .membro-card .membro-bio { font-size: .8rem; color: #777; line-height: 1.5; }
    .membro-socials { margin-top: .7rem; display: flex; justify-content: center; gap: .6rem; }
    .membro-socials a { width: 30px; height: 30px; background: var(--verde-escuro); border-radius: 50%; display: flex; align-items: center; justify-content: center; color: #fff; font-size: .75rem; transition: background .2s; }
    .membro-socials a:hover { background: var(--verde-claro); }

    /* ===== DEPOIMENTOS ===== */
    #depoimentos { background: var(--verde-escuro); }
    #depoimentos .section-title { color: #fff; }
    #depoimentos .section-sub { color: rgba(255,255,255,.7); }
    .depo-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 1.6rem; margin-top: 3rem; }
    .depo-card { background: rgba(255,255,255,.08); border-radius: var(--radius); padding: 1.8rem; }
    .depo-stars { color: var(--ouro-claro); margin-bottom: .8rem; font-size: .9rem; }
    .depo-card blockquote { font-size: .92rem; color: rgba(255,255,255,.82); line-height: 1.7; font-style: italic; }
    .depo-autor { display: flex; align-items: center; gap: .8rem; margin-top: 1.2rem; }
    .depo-avatar { width: 44px; height: 44px; border-radius: 50%; overflow: hidden; flex-shrink: 0; }
    .depo-avatar img { width: 100%; height: 100%; object-fit: cover; }
    .depo-autor strong { display: block; color: #fff; font-size: .9rem; }
    .depo-autor span { color: rgba(255,255,255,.55); font-size: .8rem; }

    /* ===== PORTFÓLIO ===== */
    #portfolio { background: var(--branco); }
    .port-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 1.8rem; margin-top: 3rem; }
    .port-card { position: relative; border-radius: var(--radius); overflow: hidden; box-shadow: var(--sombra); }
    .port-card img { width: 100%; height: 230px; object-fit: cover; transition: transform .4s; }
    .port-card:hover img { transform: scale(1.08); }
    .port-info { position: absolute; bottom: 0; left: 0; right: 0; padding: 1.4rem; background: linear-gradient(to top, rgba(26,58,30,.9) 0%, transparent 100%); }
    .port-info h4 { font-family: var(--font-display); color: #fff; font-size: 1rem; }
    .port-info span { font-size: .78rem; color: var(--ouro-claro); }

    /* ===== BLOG ===== */
    #blog { background: var(--cinza-leve); }
    .blog-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 1.8rem; margin-top: 3rem; }
    .blog-card { background: #fff; border-radius: var(--radius); overflow: hidden; box-shadow: var(--sombra); transition: transform .25s; }
    .blog-card:hover { transform: translateY(-5px); }
    .blog-card img { width: 100%; height: 180px; object-fit: cover; }
    .blog-body { padding: 1.4rem; }
    .blog-body .meta { font-size: .75rem; color: var(--ouro); font-weight: 600; margin-bottom: .5rem; }
    .blog-body h3 { font-family: var(--font-display); font-size: 1.05rem; color: var(--verde-escuro); margin-bottom: .5rem; line-height: 1.4; }
    .blog-body p { font-size: .84rem; color: #777; line-height: 1.6; }
    .blog-body a { display: inline-block; margin-top: .8rem; font-size: .83rem; color: var(--verde-claro); font-weight: 600; }

    /* ===== FAQ ===== */
    #faq { background: var(--creme); }
    .faq-list { max-width: 740px; margin: 3rem auto 0; }
    .faq-item { border-bottom: 1px solid #ddd; }
    .faq-q { width: 100%; background: none; border: none; display: flex; align-items: center; justify-content: space-between; padding: 1.2rem 0; cursor: pointer; text-align: left; font-size: .97rem; font-weight: 600; color: var(--verde-escuro); font-family: var(--font-body); }
    .faq-q i { color: var(--verde-claro); transition: transform .3s; flex-shrink: 0; }
    .faq-a { max-height: 0; overflow: hidden; transition: max-height .35s ease, padding .3s; }
    .faq-a p { padding-bottom: 1.2rem; font-size: .9rem; color: #666; line-height: 1.7; }
    .faq-item.open .faq-q i { transform: rotate(45deg); }
    .faq-item.open .faq-a { max-height: 300px; }

    /* ===== LOCALIZAÇÃO ===== */
    #localizacao { background: var(--verde-escuro); }
    #localizacao .section-title { color: #fff; }
    #localizacao .section-sub { color: rgba(255,255,255,.7); }
    .loc-grid { display: grid; grid-template-columns: 1fr 2fr; gap: 3rem; margin-top: 3rem; align-items: start; }
    .loc-info h4 { font-family: var(--font-display); color: var(--ouro-claro); font-size: 1.1rem; margin-bottom: 1rem; }
    .loc-detail { display: flex; gap: .8rem; margin-bottom: 1rem; }
    .loc-detail i { color: var(--verde-claro); margin-top: .1rem; flex-shrink: 0; }
    .loc-detail p { color: rgba(255,255,255,.75); font-size: .9rem; line-height: 1.6; }
    .map-wrapper { border-radius: var(--radius); overflow: hidden; box-shadow: var(--sombra); height: 380px; }
    .map-wrapper iframe { width: 100%; height: 100%; border: none; }

    /* ===== CONTATO ===== */
    #contato { background: var(--branco); }
    .contato-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 4rem; margin-top: 3rem; align-items: start; }
    .contato-info h3 { font-family: var(--font-display); font-size: 1.5rem; color: var(--verde-escuro); margin-bottom: 1.2rem; }
    .contato-detalhe { display: flex; gap: .9rem; margin-bottom: 1.2rem; }
    .contato-detalhe .icon { width: 44px; height: 44px; background: #e8f5e9; border-radius: 10px; display: flex; align-items: center; justify-content: center; flex-shrink: 0; }
    .contato-detalhe .icon i { color: var(--verde-claro); }
    .contato-detalhe h5 { font-size: .82rem; color: #999; font-weight: 600; text-transform: uppercase; letter-spacing: .06em; margin-bottom: .15rem; }
    .contato-detalhe p { font-size: .93rem; color: var(--preto-suave); }
    .form-group { margin-bottom: 1.2rem; }
    .form-group label { display: block; font-size: .85rem; font-weight: 600; color: var(--verde-escuro); margin-bottom: .4rem; }
    .form-group input,
    .form-group select,
    .form-group textarea { width: 100%; padding: .75rem 1rem; border: 1.5px solid #ddd; border-radius: var(--radius); font-family: var(--font-body); font-size: .92rem; color: var(--preto-suave); transition: border-color .2s; outline: none; background: #fff; }
    .form-group input:focus,
    .form-group select:focus,
    .form-group textarea:focus { border-color: var(--verde-claro); }
    .form-group textarea { resize: vertical; min-height: 120px; }
    .form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; }

    /* ===== FOOTER ===== */
    #footer { background: var(--preto-suave); padding: 60px 0 0; }
    .footer-grid { display: grid; grid-template-columns: 2fr 1fr 1fr 1fr; gap: 3rem; }
    .footer-brand p { color: rgba(255,255,255,.55); font-size: .88rem; line-height: 1.7; margin-top: .8rem; }
    .footer-socials { display: flex; gap: .6rem; margin-top: 1.2rem; }
    .footer-socials a { width: 36px; height: 36px; background: rgba(255,255,255,.1); border-radius: 8px; display: flex; align-items: center; justify-content: center; color: #fff; font-size: .85rem; transition: background .2s; }
    .footer-socials a:hover { background: var(--verde-claro); }
    .footer-col h5 { color: #fff; font-size: .88rem; font-weight: 700; letter-spacing: .06em; text-transform: uppercase; margin-bottom: 1rem; }
    .footer-col ul { list-style: none; }
    .footer-col ul li { margin-bottom: .55rem; }
    .footer-col ul li a { color: rgba(255,255,255,.55); font-size: .88rem; transition: color .2s; }
    .footer-col ul li a:hover { color: var(--ouro-claro); }
    .footer-bottom { margin-top: 3rem; padding: 1.2rem 0; border-top: 1px solid rgba(255,255,255,.08); display: flex; align-items: center; justify-content: space-between; flex-wrap: wrap; gap: .5rem; }
    .footer-bottom p { color: rgba(255,255,255,.4); font-size: .82rem; }

    /* ===== SCROLL REVEAL ===== */
    .reveal { opacity: 0; transform: translateY(30px); transition: opacity .6s ease, transform .6s ease; }
    .reveal.visible { opacity: 1; transform: translateY(0); }

    /* ===== RESPONSIVO ===== */
    @media (max-width: 900px) {
      .nav-links, .nav-cta { display: none; }
      .hamburger { display: flex; }
      .nav-links.open { display: flex; flex-direction: column; position: absolute; top: 70px; left: 0; width: 100%; background: var(--verde-escuro); padding: 1.5rem 1.5rem 2rem; gap: 1rem; }
      .nav-cta.open { display: block; margin: 0 1.5rem; }
      .sobre-grid, .contato-grid, .loc-grid { grid-template-columns: 1fr; }
      .mvv { grid-template-columns: 1fr; }
      .diferenciais-grid, .servicos-grid, .depo-grid, .port-grid, .blog-grid { grid-template-columns: 1fr 1fr; }
      .equipe-grid { grid-template-columns: 1fr 1fr; }
      .numeros-grid { grid-template-columns: 1fr 1fr; }
      .galeria-grid { grid-template-columns: 1fr 1fr; }
      .galeria-item.wide { grid-column: span 1; }
      .footer-grid { grid-template-columns: 1fr 1fr; }
    }
    @media (max-width: 600px) {
      .diferenciais-grid, .servicos-grid, .depo-grid, .port-grid, .blog-grid, .equipe-grid, .numeros-grid, .galeria-grid { grid-template-columns: 1fr; }
      .form-row { grid-template-columns: 1fr; }
      .footer-grid { grid-template-columns: 1fr; }
      .hero-stats { gap: 1.5rem; }
    }

    /* ===== TOAST ===== */
    #toast { position: fixed; bottom: 2rem; right: 2rem; background: var(--verde-escuro); color: #fff; padding: 1rem 1.6rem; border-radius: var(--radius); font-size: .9rem; box-shadow: var(--sombra); opacity: 0; pointer-events: none; transform: translateY(20px); transition: opacity .3s, transform .3s; z-index: 9999; }
    #toast.show { opacity: 1; transform: translateY(0); }
  </style>
</head>
<body>

<!-- ============================
     NAVBAR
============================= -->
<nav id="navbar">
  <div class="container">
    <div class="nav-logo">
      <div class="logo-icon"><i class="fas fa-seedling"></i></div>
      <span>ADS<em>Agro</em></span>
    </div>
    <ul class="nav-links" id="navLinks">
      <li><a href="#sobre">Sobre</a></li>
      <li><a href="#servicos">Serviços</a></li>
      <li><a href="#equipe">Equipe</a></li>
      <li><a href="#galeria">Galeria</a></li>
      <li><a href="#faq">FAQ</a></li>
      <li><a href="#blog">Blog</a></li>
      <li><a href="#localizacao">Localização</a></li>
    </ul>
    <a href="#contato" class="nav-cta" id="navCta">Fale Conosco</a>
    <div class="hamburger" id="hamburger">
      <span></span><span></span><span></span>
    </div>
  </div>
</nav>

<!-- ============================
     HERO
============================= -->
<section id="hero">
  <div class="container">
    <div class="hero-inner">
      <div class="hero-badge"><i class="fas fa-leaf"></i> &nbsp;Sorriso – MT • Agro Tech</div>
      <h1 class="hero-title">
        Da terra ao mercado,<br /><span>tecnologia que colhe</span> resultados.
      </h1>
      <p class="hero-sub">
        A ADS Agro une engenharia de precisão e inteligência de dados para transformar
        a produção rural de Mato Grosso em referência nacional de eficiência e sustentabilidade.
      </p>
      <div class="hero-actions">
        <a href="#servicos" class="btn-primary"><i class="fas fa-arrow-right"></i>&ensp;Conheça nossos serviços</a>
        <a href="#sobre" class="btn-outline">Nossa história</a>
      </div>
      <div class="hero-stats">
        <div class="hero-stat"><strong>+12</strong><span>Anos no agro</span></div>
        <div class="hero-stat"><strong>350+</strong><span>Clientes atendidos</span></div>
        <div class="hero-stat"><strong>18</strong><span>Municípios de atuação</span></div>
        <div class="hero-stat"><strong>98%</strong><span>Satisfação</span></div>
      </div>
    </div>
  </div>
</section>

<!-- ============================
     SOBRE
============================= -->
<section id="sobre">
  <div class="container reveal">
    <p class="section-label">Quem somos</p>
    <h2 class="section-title">Uma empresa nascida<br />no coração do agronegócio</h2>
    <div class="sobre-grid">
      <div class="sobre-img">
        <img src="https://images.unsplash.com/photo-1625246333195-78d9c38ad449?w=800&q=80" alt="Plantação em Sorriso MT" />
        <div class="badge-anos"><strong>12+</strong><span>anos de história</span></div>
      </div>
      <div class="sobre-texto">
        <p class="section-sub">
          Fundada em 2012 em Sorriso – MT, a <strong>ADS Agro</strong> nasceu com a missão de democratizar o acesso
          à tecnologia de precisão para produtores rurais de todos os portes. Com uma equipe multidisciplinar
          que une agronomia, engenharia de dados e TI, desenvolvemos soluções que reduzem custos,
          aumentam a produtividade e promovem a rastreabilidade da produção.
        </p>
        <p class="section-sub" style="margin-top:1rem">
          Hoje somos parceiros de mais de 350 propriedades em 18 municípios mato-grossenses, com projetos
          que já recuperaram mais de 40 mil hectares degradados e elevaram a produtividade média
          em 27% nas fazendas atendidas.
        </p>
        <div class="mvv">
          <div class="mvv-card">
            <h4><i class="fas fa-bullseye"></i> Missão</h4>
            <p>Levar tecnologia acessível e sustentável ao produtor rural brasileiro.</p>
          </div>
          <div class="mvv-card">
            <h4><i class="fas fa-eye"></i> Visão</h4>
            <p>Ser a principal plataforma agtech do Centro-Oeste até 2030.</p>
          </div>
          <div class="mvv-card">
            <h4><i class="fas fa-heart"></i> Valores</h4>
            <p>Inovação, ética, sustentabilidade e compromisso com o campo.</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ============================
     DIFERENCIAIS
============================= -->
<section id="diferenciais">
  <div class="container reveal">
    <p class="section-label">Por que nos escolher</p>
    <h2 class="section-title">Vantagens que fazem diferença<br />na sua produção</h2>
    <p class="section-sub">Escolher a ADS Agro é investir em resultados reais, respaldados por ciência e experiência local.</p>
    <div class="diferenciais-grid">
      <div class="dif-card">
        <div class="dif-icon"><i class="fas fa-satellite-dish"></i></div>
        <h3>Agricultura de Precisão</h3>
        <p>Uso de sensores IoT, drones e imagens de satélite para monitoramento em tempo real das lavouras.</p>
      </div>
      <div class="dif-card">
        <div class="dif-icon"><i class="fas fa-chart-line"></i></div>
        <h3>Analytics & BI Rural</h3>
        <p>Dashboards personalizados com dados operacionais da fazenda integrados a índices de mercado.</p>
      </div>
      <div class="dif-card">
        <div class="dif-icon"><i class="fas fa-leaf"></i></div>
        <h3>Sustentabilidade Certificada</h3>
        <p>Apoio à regularização ambiental (CAR, ART) e protocolos ESG para agroexportadores.</p>
      </div>
      <div class="dif-card">
        <div class="dif-icon"><i class="fas fa-headset"></i></div>
        <h3>Suporte Local 24/7</h3>
        <p>Equipe baseada em Sorriso com atendimento em campo e suporte remoto a qualquer hora.</p>
      </div>
      <div class="dif-card">
        <div class="dif-icon"><i class="fas fa-robot"></i></div>
        <h3>Inteligência Artificial</h3>
        <p>Modelos preditivos para pragas, clima e produtividade baseados em dados históricos regionais.</p>
      </div>
      <div class="dif-card">
        <div class="dif-icon"><i class="fas fa-handshake"></i></div>
        <h3>Parceria de Longo Prazo</h3>
        <p>Contratos de gestão contínua com revisões semestrais de metas e indicadores de desempenho.</p>
      </div>
    </div>
  </div>
</section>

<!-- ============================
     NÚMEROS
============================= -->
<section id="numeros">
  <div class="container reveal">
    <div class="numeros-grid">
      <div class="num-item"><strong>350+</strong><span>Clientes ativos</span></div>
      <div class="num-item"><strong>40k ha</strong><span>Hectares recuperados</span></div>
      <div class="num-item"><strong>27%</strong><span>Aumento médio de produtividade</span></div>
      <div class="num-item"><strong>18</strong><span>Municípios atendidos</span></div>
    </div>
  </div>
</section>

<!-- ============================
     SERVIÇOS
============================= -->
<section id="servicos">
  <div class="container reveal">
    <p class="section-label">O que oferecemos</p>
    <h2 class="section-title">Soluções completas para<br />o produtor moderno</h2>
    <p class="section-sub">Do diagnóstico à colheita, cobrimos cada etapa da sua operação rural com tecnologia de ponta.</p>
    <div class="servicos-grid">
      <div class="serv-card">
        <img src="https://images.unsplash.com/photo-1464226184884-fa280b87c399?w=600&q=75" alt="Drone agrícola" />
        <div class="serv-body">
          <span class="tag">Monitoramento</span>
          <h3>Mapeamento por Drone</h3>
          <p>Imagens NDVI de alta resolução para análise de solo, fitossanidade e estresse hídrico nas lavouras.</p>
          <a href="#contato">Saiba mais <i class="fas fa-arrow-right"></i></a>
        </div>
      </div>
      <div class="serv-card">
        <img src="https://images.unsplash.com/photo-1586771107445-d3ca888129ce?w=600&q=75" alt="Análise de dados agrícolas" />
        <div class="serv-body">
          <span class="tag">Tecnologia</span>
          <h3>Plataforma ADS DataFarm</h3>
          <p>Software próprio de gestão agrícola com módulos de estoque, financeiro e planejamento de safra.</p>
          <a href="#contato">Saiba mais <i class="fas fa-arrow-right"></i></a>
        </div>
      </div>
      <div class="serv-card">
        <img src="https://images.unsplash.com/photo-1574943320219-553eb213f72d?w=600&q=75" alt="Solo e fertilidade" />
        <div class="serv-body">
          <span class="tag">Consultoria</span>
          <h3>Análise de Solo & Fertilidade</h3>
          <p>Amostragem georreferenciada com recomendações de correção e aplicação a taxa variável (VRA).</p>
          <a href="#contato">Saiba mais <i class="fas fa-arrow-right"></i></a>
        </div>
      </div>
      <div class="serv-card">
        <img src="https://images.unsplash.com/photo-1581094794329-c8112a89af12?w=600&q=75" alt="Estação meteorológica" />
        <div class="serv-body">
          <span class="tag">Clima & Irrigação</span>
          <h3>Estações Agrometeorológicas</h3>
          <p>Instalação e integração de estações IoT com alertas de geada, seca e excesso hídrico via app.</p>
          <a href="#contato">Saiba mais <i class="fas fa-arrow-right"></i></a>
        </div>
      </div>
      <div class="serv-card">
        <img src="https://images.unsplash.com/photo-1603908209248-9d3b5f0a4b79?w=600&q=75" alt="Rastreabilidade" />
        <div class="serv-body">
          <span class="tag">Rastreabilidade</span>
          <h3>Rastreio de Grãos</h3>
          <p>Certificação de origem com QR Code e blockchain, atendendo exigências de mercados internacionais.</p>
          <a href="#contato">Saiba mais <i class="fas fa-arrow-right"></i></a>
        </div>
      </div>
      <div class="serv-card">
        <img src="https://images.unsplash.com/photo-1588072432836-e10032774350?w=600&q=75" alt="Treinamento capacitação" />
        <div class="serv-body">
          <span class="tag">Capacitação</span>
          <h3>Treinamentos & Workshops</h3>
          <p>Cursos presenciais e online sobre uso de tecnologia, legislação ambiental e boas práticas agrícolas.</p>
          <a href="#contato">Saiba mais <i class="fas fa-arrow-right"></i></a>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ============================
     GALERIA
============================= -->
<section id="galeria">
  <div class="container reveal">
    <p class="section-label">Galeria</p>
    <h2 class="section-title">Registros do campo</h2>
    <p class="section-sub">Momentos da operação da ADS Agro nas fazendas parceiras de Sorriso e região.</p>
    <div class="galeria-grid">
      <div class="galeria-item wide">
        <img src="https://images.unsplash.com/photo-1500382017468-9049fed747ef?w=900&q=75" alt="Soja Mato Grosso" />
        <div class="galeria-overlay"><i class="fas fa-expand"></i></div>
      </div>
      <div class="galeria-item">
        <img src="https://images.unsplash.com/photo-1560493676-04071c5f467b?w=500&q=75" alt="Drone em ação" />
        <div class="galeria-overlay"><i class="fas fa-expand"></i></div>
      </div>
      <div class="galeria-item">
        <img src="https://images.unsplash.com/photo-1543076548-0e9c45cfccf4?w=500&q=75" alt="Plantio de milho" />
        <div class="galeria-overlay"><i class="fas fa-expand"></i></div>
      </div>
      <div class="galeria-item">
        <img src="https://images.unsplash.com/photo-1595841696677-6489ff3f8cd1?w=500&q=75" alt="Análise solo" />
        <div class="galeria-overlay"><i class="fas fa-expand"></i></div>
      </div>
      <div class="galeria-item wide">
        <img src="https://images.unsplash.com/photo-1574943320219-553eb213f72d?w=900&q=75" alt="Colheita" />
        <div class="galeria-overlay"><i class="fas fa-expand"></i></div>
      </div>
    </div>
  </div>
</section>

<!-- ============================
     EQUIPE
============================= -->
<section id="equipe">
  <div class="container reveal">
    <p class="section-label">Nossa equipe</p>
    <h2 class="section-title">As pessoas por trás<br />da inovação no campo</h2>
    <p class="section-sub">Profissionais apaixonados por agro e tecnologia, comprometidos com o sucesso do produtor.</p>
    <div class="equipe-grid">
      <div class="membro-card">
        <div class="membro-foto"><img src="https://randomuser.me/api/portraits/men/32.jpg" alt="André Santana" /></div>
        <h4>André Santana</h4>
        <p>CEO & Fundador</p>
        <span class="membro-bio">Engenheiro agrônomo com 18 anos no setor de precisão e tecnologia rural.</span>
        <div class="membro-socials">
          <a href="#"><i class="fab fa-linkedin-in"></i></a>
          <a href="#"><i class="fab fa-instagram"></i></a>
        </div>
      </div>
      <div class="membro-card">
        <div class="membro-foto"><img src="https://randomuser.me/api/portraits/women/44.jpg" alt="Daniela Souza" /></div>
        <h4>Daniela Souza</h4>
        <p>CTO</p>
        <span class="membro-bio">Especialista em IA aplicada ao agro, MSc em Ciência de Dados pela UFV.</span>
        <div class="membro-socials">
          <a href="#"><i class="fab fa-linkedin-in"></i></a>
          <a href="#"><i class="fab fa-github"></i></a>
        </div>
      </div>
      <div class="membro-card">
        <div class="membro-foto"><img src="https://randomuser.me/api/portraits/men/67.jpg" alt="Ricardo Melo" /></div>
        <h4>Ricardo Melo</h4>
        <p>Gerente de Campo</p>
        <span class="membro-bio">Técnico agrícola com vivência em 6 estados e especialização em irrigação de precisão.</span>
        <div class="membro-socials">
          <a href="#"><i class="fab fa-linkedin-in"></i></a>
          <a href="#"><i class="fab fa-instagram"></i></a>
        </div>
      </div>
      <div class="membro-card">
        <div class="membro-foto"><img src="https://randomuser.me/api/portraits/women/28.jpg" alt="Fernanda Lima" /></div>
        <h4>Fernanda Lima</h4>
        <p>Gerente Comercial</p>
        <span class="membro-bio">MBA em Agronegócio, responsável pelas parcerias estratégicas com cooperativas.</span>
        <div class="membro-socials">
          <a href="#"><i class="fab fa-linkedin-in"></i></a>
          <a href="#"><i class="fab fa-instagram"></i></a>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ============================
     DEPOIMENTOS
============================= -->
<section id="depoimentos">
  <div class="container reveal">
    <p class="section-label">Depoimentos</p>
    <h2 class="section-title">O que nossos clientes dizem</h2>
    <p class="section-sub">Histórias reais de produtores que transformaram suas fazendas com a ADS Agro.</p>
    <div class="depo-grid">
      <div class="depo-card">
        <div class="depo-stars"><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i></div>
        <blockquote>Desde que adotei o sistema de mapeamento por drone da ADS Agro, reduzi o uso de defensivos em 22% e aumentei a produtividade de soja em 3 sacas por hectare.</blockquote>
        <div class="depo-autor">
          <div class="depo-avatar"><img src="https://randomuser.me/api/portraits/men/54.jpg" alt="João Pereira" /></div>
          <div><strong>João Pereira</strong><span>Produtor de soja – Lucas do Rio Verde</span></div>
        </div>
      </div>
      <div class="depo-card">
        <div class="depo-stars"><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i></div>
        <blockquote>O DataFarm facilitou demais o controle financeiro da propriedade. Agora tenho clareza do custo real por hectare e consigo planejar a safra com muito mais segurança.</blockquote>
        <div class="depo-autor">
          <div class="depo-avatar"><img src="https://randomuser.me/api/portraits/women/61.jpg" alt="Mariana Costa" /></div>
          <div><strong>Mariana Costa</strong><span>Fazendeira – Sorriso MT</span></div>
        </div>
      </div>
      <div class="depo-card">
        <div class="depo-stars"><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star-half-alt"></i></div>
        <blockquote>A equipe da ADS Agro é diferenciada: conhecem o campo de verdade. O suporte técnico deles é rápido e sempre presente na hora que mais preciso.</blockquote>
        <div class="depo-autor">
          <div class="depo-avatar"><img src="https://randomuser.me/api/portraits/men/77.jpg" alt="Carlos Brandão" /></div>
          <div><strong>Carlos Brandão</strong><span>Pecuarista – Nova Mutum</span></div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ============================
     PORTFÓLIO
============================= -->
<section id="portfolio">
  <div class="container reveal">
    <p class="section-label">Portfólio</p>
    <h2 class="section-title">Projetos realizados</h2>
    <p class="section-sub">Alguns dos trabalhos que nos orgulham ao longo desses 12 anos de atuação.</p>
    <div class="port-grid">
      <div class="port-card">
        <img src="https://images.unsplash.com/photo-1593113598332-cd288d649433?w=600&q=75" alt="Projeto Recuperação" />
        <div class="port-info"><h4>Recuperação de Pastagem – Fazenda Santa Rosa</h4><span>2.400 ha recuperados • 2023</span></div>
      </div>
      <div class="port-card">
        <img src="https://images.unsplash.com/photo-1454165804606-c3d57bc86b40?w=600&q=75" alt="BI Safra" />
        <div class="port-info"><h4>Painel BI de Gestão de Safra – Grupo Agroverde</h4><span>Dashboards em tempo real • 2024</span></div>
      </div>
      <div class="port-card">
        <img src="https://images.unsplash.com/photo-1617791160505-6f00504e3519?w=600&q=75" alt="Rastreabilidade soja" />
        <div class="port-info"><h4>Rastreabilidade de Grãos para Exportação</h4><span>Certificação blockchain • 2024</span></div>
      </div>
    </div>
  </div>
</section>

<!-- ============================
     BLOG
============================= -->
<section id="blog">
  <div class="container reveal">
    <p class="section-label">Blog & Novidades</p>
    <h2 class="section-title">Conhecimento que<br />transforma o campo</h2>
    <p class="section-sub">Artigos, análises e novidades sobre tecnologia e agronegócio no Mato Grosso.</p>
    <div class="blog-grid">
      <div class="blog-card">
        <img src="https://images.unsplash.com/photo-1512621776951-a57141f2eefd?w=500&q=75" alt="IA no Agro" />
        <div class="blog-body">
          <div class="meta">10 Jun 2026 &nbsp;·&nbsp; IA no Agro</div>
          <h3>Como a Inteligência Artificial está prevendo pragas antes que apareçam</h3>
          <p>Modelos preditivos treinados com dados regionais antecipam infestações e reduzem perdas nas lavouras de soja.</p>
          <a href="#">Ler artigo <i class="fas fa-arrow-right"></i></a>
        </div>
      </div>
      <div class="blog-card">
        <img src="https://images.unsplash.com/photo-1469474968028-56623f02e42e?w=500&q=75" alt="Sustentabilidade" />
        <div class="blog-body">
          <div class="meta">28 Mai 2026 &nbsp;·&nbsp; Sustentabilidade</div>
          <h3>CAR e ESG: por que regularizar sua propriedade vale cada centavo</h3>
          <p>Descubra como a conformidade ambiental abre portas para novos mercados e melhores condições de crédito rural.</p>
          <a href="#">Ler artigo <i class="fas fa-arrow-right"></i></a>
        </div>
      </div>
      <div class="blog-card">
        <img src="https://images.unsplash.com/photo-1551836022-8b2858c9c69b?w=500&q=75" alt="Drone Agricultura" />
        <div class="blog-body">
          <div class="meta">15 Mai 2026 &nbsp;·&nbsp; Precisão</div>
          <h3>5 motivos para mapear sua lavoura com drone antes da próxima safra</h3>
          <p>O mapeamento NDVI entrega informações que nenhuma visita a pé consegue revelar. Entenda o que você pode ganhar.</p>
          <a href="#">Ler artigo <i class="fas fa-arrow-right"></i></a>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ============================
     FAQ
============================= -->
<section id="faq">
  <div class="container reveal">
    <p class="section-label">Dúvidas Frequentes</p>
    <h2 class="section-title">Respostas rápidas<br />para você começar logo</h2>
    <div class="faq-list">
      <div class="faq-item">
        <button class="faq-q">A ADS Agro atende pequenos produtores? <i class="fas fa-plus"></i></button>
        <div class="faq-a"><p>Sim! Temos planos adaptados para propriedades de todos os tamanhos. Oferecemos pacotes de entrada a partir de 50 ha, com foco em diagnóstico e um serviço piloto para que o produtor sinta os resultados antes de ampliar o escopo.</p></div>
      </div>
      <div class="faq-item">
        <button class="faq-q">Quanto tempo leva para implantar a plataforma DataFarm? <i class="fas fa-plus"></i></button>
        <div class="faq-a"><p>Em média entre 7 e 15 dias úteis, incluindo configuração, integração com dados existentes e treinamento da equipe da fazenda. Para operações maiores ou com sistemas legados, o prazo pode ser estendido após avaliação técnica.</p></div>
      </div>
      <div class="faq-item">
        <button class="faq-q">Vocês oferecem suporte presencial em Sorriso e região? <i class="fas fa-plus"></i></button>
        <div class="faq-a"><p>Sim. Nossa base fica em Sorriso-MT e contamos com técnicos de campo que atendem toda a região do médio-norte mato-grossense. O atendimento remoto está disponível 24/7 para emergências.</p></div>
      </div>
      <div class="faq-item">
        <button class="faq-q">Como funciona o mapeamento por drone nas lavouras? <i class="fas fa-plus"></i></button>
        <div class="faq-a"><p>Nossos pilotos homologados pela ANAC realizam o voo com drones equipados com câmeras multiespectrais. As imagens são processadas em até 48 h e entregues como mapas de prescrição (NDVI, NDRE, altura de plantas) e relatório técnico assinado por agrônomo.</p></div>
      </div>
      <div class="faq-item">
        <button class="faq-q">É possível integrar o DataFarm com sistemas já existentes na fazenda? <i class="fas fa-plus"></i></button>
        <div class="faq-a"><p>Sim. Temos API aberta e integrações nativas com as principais ERPs agrícolas (Agrosoft, Siagri, Agrotools) e com os portais de cooperativas. Nossa equipe de TI realiza a integração durante a implantação.</p></div>
      </div>
      <div class="faq-item">
        <button class="faq-q">Vocês ajudam com a regularização ambiental (CAR, ART)? <i class="fas fa-plus"></i></button>
        <div class="faq-a"><p>Sim. Oferecemos consultoria ambiental completa: georreferenciamento, elaboração do CAR, emissão de ARTs e suporte ao PRA (Programa de Regularização Ambiental) junto ao órgão competente estadual.</p></div>
      </div>
    </div>
  </div>
</section>

<!-- ============================
     LOCALIZAÇÃO
============================= -->
<section id="localizacao">
  <div class="container reveal">
    <p class="section-label">Onde estamos</p>
    <h2 class="section-title">No centro do agronegócio<br />mato-grossense</h2>
    <p class="section-sub">Nossa sede em Sorriso – MT nos coloca a menos de 3 horas dos maiores polos produtores do estado.</p>
    <div class="loc-grid">
      <div class="loc-info">
        <h4>ADS Agro – Sede</h4>
        <div class="loc-detail">
          <i class="fas fa-map-marker-alt"></i>
          <p>Av. Tancredo Neves, 1247<br />Bairro Industrial – Sorriso, MT<br />CEP 78.890-000</p>
        </div>
        <div class="loc-detail">
          <i class="fas fa-phone"></i>
          <p>(66) 3544-1200</p>
        </div>
        <div class="loc-detail">
          <i class="fas fa-envelope"></i>
          <p>contato@adsagro.com.br</p>
        </div>
        <div class="loc-detail">
          <i class="fas fa-clock"></i>
          <p>Seg – Sex: 07h30 às 18h00<br />Sáb: 08h00 às 12h00</p>
        </div>
      </div>
      <div class="map-wrapper">
        <!-- Mapa do Google Maps incorporado – Sorriso MT -->
        <iframe
          src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d124890.44948741867!2d-55.7609013!3d-12.5444567!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x93a5a8ae0a8e4f97%3A0x7a86e67e6c33f3c5!2sSorriso%2C%20MT!5e0!3m2!1spt-BR!2sbr!4v1717521600000"
          allowfullscreen=""
          loading="lazy"
          referrerpolicy="no-referrer-when-downgrade"
          title="Mapa de Sorriso MT">
        </iframe>
      </div>
    </div>
  </div>
</section>

<!-- ============================
     CONTATO
============================= -->
<section id="contato">
  <div class="container reveal">
    <p class="section-label">Fale conosco</p>
    <h2 class="section-title">Pronto para levar<br />tecnologia à sua fazenda?</h2>
    <div class="contato-grid">
      <div class="contato-info">
        <h3>Entre em contato com nossa equipe</h3>
        <p style="color:#666;line-height:1.7;margin-bottom:1.8rem">Preencha o formulário ou use um dos canais abaixo. Nossa equipe retorna em até 24 horas úteis com uma proposta personalizada para sua propriedade.</p>
        <div class="contato-detalhe">
          <div class="icon"><i class="fas fa-phone"></i></div>
          <div><h5>Telefone</h5><p>(66) 3544-1200</p></div>
        </div>
        <div class="contato-detalhe">
          <div class="icon"><i class="fab fa-whatsapp"></i></div>
          <div><h5>WhatsApp</h5><p>(66) 99801-4500</p></div>
        </div>
        <div class="contato-detalhe">
          <div class="icon"><i class="fas fa-envelope"></i></div>
          <div><h5>E-mail</h5><p>contato@adsagro.com.br</p></div>
        </div>
        <div class="contato-detalhe">
          <div class="icon"><i class="fas fa-map-marker-alt"></i></div>
          <div><h5>Endereço</h5><p>Av. Tancredo Neves, 1247 – Sorriso MT</p></div>
        </div>
      </div>

      <form id="formContato" onsubmit="enviarForm(event)">
        <div class="form-row">
          <div class="form-group">
            <label for="nome">Nome completo *</label>
            <input type="text" id="nome" placeholder="João da Silva" required />
          </div>
          <div class="form-group">
            <label for="telefone">Telefone / WhatsApp *</label>
            <input type="tel" id="telefone" placeholder="(66) 99000-0000" required />
          </div>
        </div>
        <div class="form-group">
          <label for="email">E-mail *</label>
          <input type="email" id="email" placeholder="joao@fazenda.com.br" required />
        </div>
        <div class="form-group">
          <label for="servico">Serviço de interesse</label>
          <select id="servico">
            <option value="">Selecione um serviço</option>
            <option>Mapeamento por Drone</option>
            <option>Plataforma DataFarm</option>
            <option>Análise de Solo & Fertilidade</option>
            <option>Estações Agrometeorológicas</option>
            <option>Rastreio de Grãos</option>
            <option>Treinamentos & Workshops</option>
            <option>Consultoria Ambiental</option>
          </select>
        </div>
        <div class="form-group">
          <label for="mensagem">Mensagem</label>
          <textarea id="mensagem" placeholder="Descreva sua propriedade e como podemos ajudar..."></textarea>
        </div>
        <button type="submit" class="btn-primary" style="width:100%;font-size:1rem">
          <i class="fas fa-paper-plane"></i>&ensp;Enviar mensagem
        </button>
      </form>
    </div>
  </div>
</section>

<!-- ============================
     FOOTER
============================= -->
<footer id="footer">
  <div class="container">
    <div class="footer-grid">
      <div class="footer-brand">
        <div class="nav-logo" style="margin-bottom:.6rem">
          <div class="logo-icon"><i class="fas fa-seedling"></i></div>
          <span style="color:#fff;font-family:var(--font-display);font-size:1.2rem">ADS<em style="color:var(--ouro-claro);font-style:normal">Agro</em></span>
        </div>
        <p>Tecnologia e inovação a serviço do produtor rural de Sorriso e do Mato Grosso. Juntos, construímos o agro do futuro.</p>
        <div class="footer-socials">
          <a href="#" aria-label="Instagram"><i class="fab fa-instagram"></i></a>
          <a href="#" aria-label="Facebook"><i class="fab fa-facebook-f"></i></a>
          <a href="#" aria-label="LinkedIn"><i class="fab fa-linkedin-in"></i></a>
          <a href="#" aria-label="YouTube"><i class="fab fa-youtube"></i></a>
          <a href="#" aria-label="WhatsApp"><i class="fab fa-whatsapp"></i></a>
        </div>
      </div>
      <div class="footer-col">
        <h5>Navegação</h5>
        <ul>
          <li><a href="#sobre">Sobre</a></li>
          <li><a href="#diferenciais">Diferenciais</a></li>
          <li><a href="#servicos">Serviços</a></li>
          <li><a href="#portfolio">Portfólio</a></li>
          <li><a href="#equipe">Equipe</a></li>
          <li><a href="#blog">Blog</a></li>
        </ul>
      </div>
      <div class="footer-col">
        <h5>Serviços</h5>
        <ul>
          <li><a href="#servicos">Mapeamento por Drone</a></li>
          <li><a href="#servicos">Plataforma DataFarm</a></li>
          <li><a href="#servicos">Análise de Solo</a></li>
          <li><a href="#servicos">Estações IoT</a></li>
          <li><a href="#servicos">Rastreio de Grãos</a></li>
          <li><a href="#servicos">Treinamentos</a></li>
        </ul>
      </div>
      <div class="footer-col">
        <h5>Contato</h5>
        <ul>
          <li><a href="tel:+556635441200"><i class="fas fa-phone fa-xs"></i>&ensp;(66) 3544-1200</a></li>
          <li><a href="https://wa.me/5566998014500"><i class="fab fa-whatsapp fa-xs"></i>&ensp;(66) 99801-4500</a></li>
          <li><a href="mailto:contato@adsagro.com.br"><i class="fas fa-envelope fa-xs"></i>&ensp;contato@adsagro.com.br</a></li>
          <li><a href="#localizacao"><i class="fas fa-map-marker-alt fa-xs"></i>&ensp;Sorriso – MT</a></li>
        </ul>
      </div>
    </div>
    <div class="footer-bottom">
      <p>© 2026 ADS Agro – Todos os direitos reservados · Sorriso, MT · CNPJ 12.345.678/0001-90</p>
      <p><a href="#" style="color:rgba(255,255,255,.4)">Política de Privacidade</a> &nbsp;|&nbsp; <a href="#" style="color:rgba(255,255,255,.4)">Termos de Uso</a></p>
    </div>
  </div>
</footer>

<div id="toast">✅ Mensagem enviada com sucesso! Retornaremos em até 24h.</div>

<!-- ============================
     JAVASCRIPT
============================= -->
<script>
  /* --- NAVBAR HAMBURGER --- */
  const hamburger = document.getElementById('hamburger');
  const navLinks  = document.getElementById('navLinks');
  const navCta    = document.getElementById('navCta');

  hamburger.addEventListener('click', () => {
    navLinks.classList.toggle('open');
    navCta.classList.toggle('open');
  });

  /* Fecha menu ao clicar em link */
  document.querySelectorAll('.nav-links a').forEach(link => {
    link.addEventListener('click', () => {
      navLinks.classList.remove('open');
      navCta.classList.remove('open');
    });
  });

  /* --- FAQ ACCORDION --- */
  document.querySelectorAll('.faq-q').forEach(btn => {
    btn.addEventListener('click', () => {
      const item = btn.parentElement;
      const isOpen = item.classList.contains('open');
      document.querySelectorAll('.faq-item').forEach(i => i.classList.remove('open'));
      if (!isOpen) item.classList.add('open');
    });
  });

  /* --- SCROLL REVEAL (IntersectionObserver) --- */
  const revealEls = document.querySelectorAll('.reveal');
  const observer  = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('visible');
        observer.unobserve(entry.target);
      }
    });
  }, { threshold: 0.1 });
  revealEls.forEach(el => observer.observe(el));

  /* --- FORMULÁRIO DE CONTATO --- */
  function enviarForm(e) {
    e.preventDefault();
    const toast = document.getElementById('toast');
    toast.classList.add('show');
    setTimeout(() => toast.classList.remove('show'), 4000);
    e.target.reset();
  }

  /* --- ACTIVE NAV LINK NO SCROLL --- */
  const sections = document.querySelectorAll('section[id]');
  window.addEventListener('scroll', () => {
    let current = '';
    sections.forEach(sec => {
      if (window.scrollY >= sec.offsetTop - 100) current = sec.getAttribute('id');
    });
    document.querySelectorAll('.nav-links a').forEach(a => {
      a.style.color = a.getAttribute('href') === '#' + current
        ? 'var(--ouro-claro)'
        : '';
    });
  });
</script>
</body>
</html>
