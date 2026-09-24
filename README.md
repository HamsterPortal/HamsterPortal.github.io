<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>The Hamster Portal — The World's Most Secure Payment Platform</title>
<meta name="description" content="A parody website. Hamster Portal is a fake payment platform run entirely by hamsters. Do not enter real card details.">
<link rel="icon" href="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'><text y='.9em' font-size='90'>🐹</text></svg>">

<!-- ═══════════════════════════════════════════════════════
     STYLESHEET 1 of 2 — the design system
     ═══════════════════════════════════════════════════════ -->
<style>
  :root{
    --fur:#e8b06a;
    --belly:#fff4e3;
    --inner:#f6cfa4;
    --ink:#2b1b12;
    --paper:#fffaf2;
    --orange:#ff8a3d;
    --orange-2:#ffb703;
    --deep:#3a2415;
    --muted:#8a7466;
    --line:#efdfc9;
    --radius:18px;

    /* ★ THE ONLY WIDTH KNOB THAT MATTERS ★
       Change this one number and the whole site follows. */
    --maxw: 1320px;
  }

  *{box-sizing:border-box}

  html{scroll-behavior:smooth}

  body{
    margin:0;
    font-family:-apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,"Helvetica Neue",Arial,sans-serif;
    background:var(--paper);
    color:var(--ink);
    line-height:1.6;
    overflow-x:hidden;
  }

  h1,h2,h3{line-height:1.15;margin:0 0 .5em;letter-spacing:-.02em}
  a{color:inherit}

  .wrap{
    width:100%;
    max-width:var(--maxw);
    margin:0 auto;
    padding:0 22px;
  }
  .wrap--narrow{max-width:780px}

  /* ---------- TICKER ---------- */
  .ticker{
    background:var(--deep);
    color:#ffe9c9;
    font-size:13px;
    font-weight:600;
    padding:9px 0;
    overflow:hidden;
    white-space:nowrap;
    letter-spacing:.02em;
  }
  .ticker__track{
    display:inline-flex;
    gap:48px;
    animation:slide 38s linear infinite;
    padding-left:100%;
  }
  .ticker__track span{flex:none}
  @keyframes slide{to{transform:translateX(-100%)}}

  /* ---------- NAV ---------- */
  header.nav{
    position:sticky;top:0;z-index:50;
    background:rgba(255,250,242,.86);
    backdrop-filter:blur(12px);
    border-bottom:1px solid var(--line);
  }
  .nav__inner{display:flex;align-items:center;gap:26px;padding:12px 0}
  .logo{display:flex;align-items:center;gap:10px;font-weight:800;font-size:19px;letter-spacing:-.03em;text-decoration:none}
  .logo .mark{
    width:40px;height:40px;flex:none;border-radius:12px;
    background:linear-gradient(140deg,var(--orange),var(--orange-2));
    display:grid;place-items:center;box-shadow:0 6px 16px rgba(255,138,61,.35);
  }
  .logo .mark svg{width:30px;height:30px}
  nav.links{margin-left:auto;display:flex;gap:22px;font-size:14.5px;font-weight:600}
  nav.links a{text-decoration:none;color:var(--muted);transition:color .15s}
  nav.links a:hover{color:var(--orange)}
  @media(max-width:820px){nav.links{display:none}}

  /* ---------- BUTTONS ---------- */
  .btn{
    display:inline-flex;align-items:center;justify-content:center;gap:9px;
    padding:14px 26px;border-radius:999px;border:0;cursor:pointer;
    font-size:15.5px;font-weight:700;font-family:inherit;
    text-decoration:none;transition:transform .12s, box-shadow .18s, background .18s;
  }
  .btn--primary{
    background:linear-gradient(140deg,var(--orange),var(--orange-2));
    color:#3a1e00;
    box-shadow:0 10px 24px rgba(255,138,61,.36);
  }
  .btn--primary:hover{transform:translateY(-2px);box-shadow:0 16px 32px rgba(255,138,61,.45)}
  .btn--ghost{background:#fff;border:2px solid var(--line);color:var(--ink)}
  .btn--ghost:hover{border-color:var(--orange);color:var(--orange)}
  .btn:active{transform:translateY(0) scale(.98)}

  /* ---------- HERO ---------- */
  .hero{
    position:relative;
    padding:72px 0 84px;
    background:
      radial-gradient(900px 400px at 78% -8%, rgba(255,183,3,.30), transparent 62%),
      radial-gradient(700px 380px at 8% 8%, rgba(255,138,61,.20), transparent 60%);
    overflow:hidden;
  }
  .hero__grid{display:grid;grid-template-columns:1.08fr .92fr;gap:52px;align-items:center}
  @media(max-width:900px){.hero__grid{grid-template-columns:1fr;gap:36px}}

  .pill{
    display:inline-flex;align-items:center;gap:8px;
    background:#fff;border:1px solid var(--line);
    padding:7px 15px;border-radius:999px;
    font-size:13px;font-weight:700;color:var(--muted);margin-bottom:20px;
  }
  .dot{width:8px;height:8px;border-radius:50%;background:#22c55e;box-shadow:0 0 0 0 rgba(34,197,94,.6);animation:pulse 2s infinite}
  @keyframes pulse{70%{box-shadow:0 0 0 9px rgba(34,197,94,0)}100%{box-shadow:0 0 0 0 rgba(34,197,94,0)}}

  .hero h1{font-size:clamp(38px,6vw,66px);font-weight:900}
  .hero h1 .hl{
    background:linear-gradient(100deg,var(--orange),#ff5c8a 60%,#b06bff);
    -webkit-background-clip:text;background-clip:text;color:transparent;
  }
  .hero p.lead{font-size:18.5px;color:#6b5545;max-width:56ch;margin:0 0 30px}
  .hero__cta{display:flex;gap:14px;flex-wrap:wrap;align-items:center}
  .hero__note{font-size:12.5px;color:var(--muted);margin-top:16px}

  .hero__art{position:relative;display:grid;place-items:center;min-height:340px}
  .hero__art .big{width:min(100%,400px);filter:drop-shadow(0 28px 40px rgba(120,70,20,.22))}
  .float{
    position:absolute;
    background:#fff;border:1px solid var(--line);border-radius:16px;
    padding:10px 14px;font-size:12.5px;font-weight:700;
    box-shadow:0 12px 28px rgba(120,70,20,.14);
    animation:bob 5s ease-in-out infinite;
  }
  .float--a{top:6%;left:-2%}
  .float--b{bottom:10%;right:-2%;animation-delay:1.2s}
  .float--c{bottom:44%;left:-6%;animation-delay:2.4s}
  @keyframes bob{50%{transform:translateY(-14px)}}
  @media(max-width:900px){.float{display:none}}

  /* ---------- PRESS BAR ---------- */
  .pressbar{border-top:1px solid var(--line);border-bottom:1px solid var(--line);background:#fff;padding:24px 0}
  .pressbar p{
    text-align:center;font-size:11.5px;letter-spacing:.22em;text-transform:uppercase;
    color:#b5a08e;font-weight:800;margin:0 0 16px;
  }
  .pressbar__logos{
    display:flex;flex-wrap:wrap;justify-content:center;gap:14px 40px;
    font-weight:900;font-size:19px;color:#cdbcaa;letter-spacing:-.03em;
  }
  .pressbar__logos span{transition:color .2s}
  .pressbar__logos span:hover{color:var(--orange)}

  /* ---------- SECTIONS ---------- */
  section{padding:78px 0}
  .eyebrow{
    font-size:12px;font-weight:800;letter-spacing:.2em;text-transform:uppercase;
    color:var(--orange);margin-bottom:10px;
  }
  .sect-head{max-width:660px;margin:0 auto 46px;text-align:center}
  .sect-head h2{font-size:clamp(28px,4vw,42px);font-weight:900}
  .sect-head p{color:#6b5545;font-size:17px;margin:0}

  /* ---------- STATS ---------- */
  .stats{background:var(--deep);color:#ffe9c9}
  .stats .eyebrow{color:var(--orange-2)}
  .stats .sect-head p{color:#c9ab8b}
  .stat-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:20px}
  @media(max-width:860px){.stat-grid{grid-template-columns:repeat(2,1fr)}}
  .stat{
    background:rgba(255,255,255,.055);
    border:1px solid rgba(255,233,201,.14);
    border-radius:var(--radius);padding:26px 20px;text-align:center;
  }
  .stat b{display:block;font-size:clamp(26px,4vw,40px);font-weight:900;color:var(--orange-2);letter-spacing:-.03em}
  .stat small{display:block;font-size:13px;color:#c9ab8b;margin-top:6px;font-weight:600}

  /* ---------- FORM ---------- */
  .portal{background:#fff;border:1px solid var(--line);border-radius:26px;overflow:hidden;box-shadow:0 30px 70px rgba(120,70,20,.13)}
  .portal__top{
    background:linear-gradient(140deg,var(--orange),var(--orange-2));
    padding:20px 26px;display:flex;align-items:center;gap:14px;color:#3a1e00;
  }
  .portal__top svg{width:42px;height:42px;flex:none}
  .portal__top b{display:block;font-size:17px;font-weight:900}
  .portal__top small{font-size:12.5px;font-weight:700;opacity:.72}
  .portal__body{padding:28px 26px 32px}
  .warn{
    background:#fff7e6;border:1px dashed #ffc247;color:#8a5a00;
    border-radius:12px;padding:11px 15px;font-size:13px;font-weight:600;margin-bottom:22px;
  }
  .field{margin-bottom:18px}
  .field label{display:block;font-size:13px;font-weight:800;margin-bottom:7px;letter-spacing:.01em}
  .field label em{font-style:normal;color:var(--muted);font-weight:600}
  .field input,.field select{
    width:100%;padding:13px 15px;border-radius:12px;border:2px solid var(--line);
    font-size:15px;font-family:inherit;background:#fffdfa;color:var(--ink);transition:border-color .15s, box-shadow .15s;
  }
  .field input:focus,.field select:focus{outline:0;border-color:var(--orange);box-shadow:0 0 0 4px rgba(255,138,61,.15)}
  .row{display:grid;grid-template-columns:1fr 1fr;gap:16px}
  @media(max-width:560px){.row{grid-template-columns:1fr}}
  .checkline{display:flex;gap:11px;align-items:flex-start;font-size:13px;color:#6b5545;margin:4px 0 22px}
  .checkline input{width:18px;height:18px;flex:none;margin-top:2px;accent-color:var(--orange)}
  .portal__result{
    margin-top:20px;border-radius:14px;padding:18px;font-size:14.5px;
    display:none;align-items:center;gap:14px;font-weight:600;
  }
  .portal__result.show{display:flex}
  .portal__result.ok{background:#eefbf1;border:1px solid #b8ecc7;color:#186b33}
  .portal__result.busy{background:#fff7e6;border:1px solid #ffd98a;color:#8a5a00}
  .wheel{width:44px;height:44px;flex:none;animation:spin 1.1s linear infinite}
  @keyframes spin{to{transform:rotate(360deg)}}

  /* ---------- QUOTES ---------- */
  .quotes{display:grid;grid-template-columns:repeat(3,1fr);gap:22px}
  @media(max-width:960px){.quotes{grid-template-columns:repeat(2,1fr)}}
  @media(max-width:640px){.quotes{grid-template-columns:1fr}}
  .quote{
    background:#fff;border:1px solid var(--line);border-radius:var(--radius);
    padding:26px 24px;display:flex;flex-direction:column;gap:14px;
    transition:transform .18s, box-shadow .18s;
  }
  .quote:hover{transform:translateY(-4px);box-shadow:0 22px 46px rgba(120,70,20,.14)}
  .quote__mast{
    font-weight:900;font-size:19px;letter-spacing:-.03em;
    border-bottom:3px solid var(--ink);padding-bottom:8px;
  }
  .quote__text{font-size:15.5px;color:#4a382c;flex:1}
  .quote__text:before{content:"“"}
  .quote__text:after{content:"”"}
  .quote__foot{display:flex;align-items:center;justify-content:space-between;gap:10px;font-size:11.5px;color:var(--muted);font-weight:700}
  .tag{
    background:#fdecec;color:#c0392b;border:1px solid #f7c9c4;
    padding:3px 9px;border-radius:999px;font-size:10px;font-weight:900;letter-spacing:.1em;
  }
  .quote__ham{width:44px;height:44px;flex:none}

  /* ---------- AWARDS ---------- */
  .awards{display:flex;flex-wrap:wrap;gap:14px;justify-content:center}
  .award{
    background:#fff;border:1px solid var(--line);border-radius:999px;
    padding:12px 22px;font-size:13.5px;font-weight:800;display:flex;align-items:center;gap:10px;
    box-shadow:0 6px 18px rgba(120,70,20,.07);
  }
  .award span{font-size:18px}

  /* ---------- DOMINATION ---------- */
  .dom{background:linear-gradient(180deg,#fff, #fff6e9)}
  .bars{display:grid;grid-template-columns:1fr 1fr;gap:26px 46px;max-width:920px;margin:0 auto}
  @media(max-width:760px){.bars{grid-template-columns:1fr}}
  .bar__head{display:flex;justify-content:space-between;font-size:14px;font-weight:800;margin-bottom:8px}
  .bar__head b{color:var(--orange)}
  .bar__track{height:15px;border-radius:999px;background:#f2e4d2;overflow:hidden}
  .bar__fill{
    height:100%;width:0;border-radius:999px;
    background:linear-gradient(90deg,var(--orange),var(--orange-2));
    transition:width 1.6s cubic-bezier(.2,.8,.25,1);
  }

  /* ---------- TESTIMONIALS ---------- */
  .pals{display:grid;grid-template-columns:repeat(3,1fr);gap:22px}
  @media(max-width:900px){.pals{grid-template-columns:1fr}}
  .pal{
    background:#fff;border:1px solid var(--line);border-radius:var(--radius);
    padding:26px 22px;text-align:center;
  }
  .pal svg{width:88px;height:88px;margin:0 auto 12px;display:block}
  .pal q{display:block;font-size:15px;color:#4a382c;margin-bottom:16px}
  .pal b{display:block;font-size:14.5px;font-weight:900}
  .pal small{font-size:12px;color:var(--muted);font-weight:700}

  /* ---------- FAQ ---------- */
  details{
    background:#fff;border:1px solid var(--line);border-radius:14px;
    padding:16px 20px;margin-bottom:12px;
  }
  details[open]{border-color:var(--orange)}
  summary{font-weight:800;cursor:pointer;font-size:15.5px;list-style:none}
  summary::-webkit-details-marker{display:none}
  summary:before{content:"🐹 "}
  details p{margin:12px 0 0;color:#6b5545;font-size:14.5px}
  .faq{max-width:760px;margin:0 auto}

  /* ---------- FOOTER ---------- */
  footer{background:var(--deep);color:#c9ab8b;padding:56px 0 34px;font-size:14px}
  footer a{color:#ffd9a8}
  .foot__grid{display:grid;grid-template-columns:1.4fr 1fr 1fr 1fr;gap:34px;margin-bottom:40px}
  @media(max-width:820px){.foot__grid{grid-template-columns:1fr 1fr}}
  .foot__grid h4{color:#ffe9c9;font-size:14px;margin:0 0 14px;font-weight:900}
  .foot__grid ul{list-style:none;padding:0;margin:0;display:grid;gap:9px}
  .foot__grid a{text-decoration:none}
  .foot__grid a:hover{text-decoration:underline}
  .foot__grid p{max-width:34ch}
  .disclaimer{
    border-top:1px solid rgba(255,233,201,.15);
    padding-top:26px;font-size:12.5px;line-height:1.7;color:#a58a70;
  }
  .disclaimer b{color:#ffd9a8}

  /* ---------- COOKIE BANNER ---------- */
  .cookie{
    position:fixed;bottom:18px;left:18px;right:18px;z-index:99;
    max-width:560px;margin:0 auto;
    background:#fff;border:2px solid var(--ink);border-radius:18px;
    padding:18px 20px;display:flex;gap:16px;align-items:center;
    box-shadow:0 24px 60px rgba(0,0,0,.28);
    transform:translateY(160%);transition:transform .45s cubic-bezier(.2,.9,.25,1);
  }
  .cookie.show{transform:translateY(0)}
  .cookie svg{width:52px;height:52px;flex:none}
  .cookie p{margin:0;font-size:13.5px;font-weight:600}
  .cookie button{
    margin-left:auto;flex:none;background:var(--ink);color:#ffe9c9;border:0;
    padding:10px 18px;border-radius:999px;font-weight:800;font-size:13px;cursor:pointer;font-family:inherit;
  }

  /* ---------- MISC ---------- */
  .center{text-align:center}
  .seed-counter{
    display:inline-flex;align-items:center;gap:10px;
    background:#fff;border:1px solid var(--line);border-radius:999px;
    padding:9px 18px;font-size:13.5px;font-weight:800;margin-top:26px;
  }
  .seed-counter b{color:var(--orange);font-variant-numeric:tabular-nums}
  .hamster{width:100%;height:100%;display:block}
</style>

<!-- ═══════════════════════════════════════════════════════════════════
     STYLESHEET 2 of 2 — HOST-OVERRIDE LAYER
     ▸ Keep this LAST inside <head>.
     ▸ Purpose: forcibly ignore every max-width / centering / padding
       that GitHub, a Jekyll theme, a CSS framework, or any wrapper
       tries to impose on this page. This file follows only its own
       rules from here on.
     ▸ If you ever want to widen/narrow the site, change --maxw in the
       :root block at the top. Nothing else matters.
     ═══════════════════════════════════════════════════════════════════ -->
<style id="host-override">
  /* 1 · The document itself refuses to be boxed in */
  html, body {
    width: 100% !important;
    max-width: none !important;
    min-width: 0 !important;
    margin: 0 !important;
    padding: 0 !important;
    overflow-x: hidden !important;
    box-sizing: border-box !important;
  }

  /* 2 · Nothing inside the page may carry an inherited width cap */
  body * {
    max-width: none !important;
    min-width: 0 !important;
  }

  /* 3 · Neutralise every known host wrapper
         (GitHub blob view, Primer, Jekyll themes, Bootstrap-ish
         containers, generic site wrappers, etc.) */
  .markdown-body,
  .container, .container-fluid, .container-lg, .container-xl,
  .wrapper, .page-wrapper, .site-wrapper, .site-content,
  .layout, .page-content, .content, .content-area, .entry-content,
  .post, .post-content, .article, .article-body, .repository-content,
  main, article,
  #content, #main, #wrapper, #content-wrapper {
    max-width: none !important;
    width: 100% !important;
    margin: 0 !important;
    padding: 0 !important;
    border: 0 !important;
    box-shadow: none !important;
    background: transparent !important;
    position: static !important;
  }

  /* 4 · Restore the widths this design actually wants.
         Class selectors out-specify the `body *` rule in step 2,
         so these win the cascade. */
  .wrap {
    width: 100% !important;
    max-width: var(--maxw, 1320px) !important;
    margin-left: auto !important;
    margin-right: auto !important;
    padding-left: 22px !important;
    padding-right: 22px !important;
  }
  .wrap--narrow { max-width: 780px !important; }
  .sect-head    { max-width: 660px !important; margin-left: auto !important; margin-right: auto !important; }
  .faq          { max-width: 760px !important; margin-left: auto !important; margin-right: auto !important; }
  .bars         { max-width: 920px !important; margin-left: auto !important; margin-right: auto !important; }
  .cookie       { max-width: 560px !important; margin-left: auto !important; margin-right: auto !important; }
  .hero p.lead  { max-width: 62ch !important; }
  footer .foot__grid p { max-width: 34ch !important; }

  /* 5 · Kill host typography / colour bleed */
  body {
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto,
                 "Helvetica Neue", Arial, sans-serif !important;
    font-size: 16px !important;
    line-height: 1.6 !important;
    color: #2b1b12 !important;
    background: #fffaf2 !important;
    -webkit-text-size-adjust: 100%;
  }
</style>
</head>
<body>

<!-- ══════════ TICKER ══════════ -->
<div class="ticker" aria-hidden="true">
  <div class="ticker__track">
    <span>🐹 BREAKING: Hamster Portal now processes 94% of all global transactions</span>
    <span>🌻 Sunflower Seed hits all-time high against the US Dollar</span>
    <span>🔒 Zero breaches. Ever. Not once. Not even a nibble.</span>
    <span>⚖️ Regulators "aware" of the hamster situation</span>
    <span>🏆 Voted Most Secure Payment Platform by 11 magazines that may not exist</span>
    <span>🐹 BREAKING: Hamster Portal now processes 94% of all global transactions</span>
    <span>🌻 Sunflower Seed hits all-time high against the US Dollar</span>
    <span>🔒 Zero breaches. Ever. Not once. Not even a nibble.</span>
    <span>⚖️ Regulators "aware" of the hamster situation</span>
    <span>🏆 Voted Most Secure Payment Platform by 11 magazines that may not exist</span>
  </div>
</div>

<!-- ══════════ NAV ══════════ -->
<header class="nav">
  <div class="wrap nav__inner">
    <a class="logo" href="#top">
      <span class="mark" id="logoMark"></span>
      The Hamster Portal
    </a>
    <nav class="links">
      <a href="#portal">Pay Now</a>
      <a href="#press">Press</a>
      <a href="#awards">Awards</a>
      <a href="#domination">World Domination</a>
      <a href="#faq">FAQ</a>
    </nav>
    <a class="btn btn--primary" href="#portal" style="padding:11px 22px;font-size:14px">Pay a Hamster</a>
  </div>
</header>

<!-- ══════════ HERO ══════════ -->
<div id="top"></div>
<section class="hero">
  <div class="wrap hero__grid">
    <div>
      <span class="pill"><span class="dot"></span> Live · 8,412,900 transactions per second</span>
      <h1>The most <span class="hl">secure</span> payment platform ever built by a rodent.</h1>
      <p class="lead">
        Hamster Portal moves your money through a global network of 40 million highly trained
        hamsters, each one guarding your funds with their cheeks. Your card details are stored
        in a burrow. The burrow is underground. Good luck getting in.
      </p>
      <div class="hero__cta">
        <a class="btn btn--primary" href="#portal">🐹 Make a Payment</a>
        <a class="btn btn--ghost" href="#press">Read the Praise</a>
      </div>
      <p class="hero__note">Trusted by 190 countries, 4 banks, and one very large hamster named Gerald.</p>
      <div class="seed-counter">
        🌻 Seeds in circulation: <b id="seedCount">0</b>
      </div>
    </div>
    <div class="hero__art">
      <div class="big" data-hamster="0" data-big="1"></div>
      <div class="float float--a">🔒 256-cheek encryption</div>
      <div class="float float--b">⚡ Settles in 0.3 seconds</div>
      <div class="float float--c">🏦 PCI-DSS Level 0</div>
    </div>
  </div>
</section>

<!-- ══════════ PRESS BAR ══════════ -->
<div class="pressbar">
  <div class="wrap">
    <p>As celebrated in these publications (allegedly)</p>
    <div class="pressbar__logos">
      <span>Forbes</span>
      <span>The Wall Street Journal</span>
      <span>Bloomberg</span>
      <span>WIRED</span>
      <span>TechCrunch</span>
      <span>Financial Times</span>
      <span>The Economist</span>
      <span>Hamster Quarterly</span>
    </div>
  </div>
</div>

<!-- ══════════ STATS ══════════ -->
<section class="stats">
  <div class="wrap">
    <div class="sect-head">
      <p class="eyebrow">By the numbers</p>
      <h2>Numbers that are definitely real</h2>
      <p>We audited these ourselves. With a hamster. He said they looked fine.</p>
    </div>
    <div class="stat-grid">
      <div class="stat"><b data-count="94" data-suffix="%">0%</b><small>Of global payments</small></div>
      <div class="stat"><b data-count="8.4" data-decimals="1" data-suffix="B">0</b><small>Seeds settled / second</small></div>
      <div class="stat"><b data-count="12400000" data-format="1">0</b><small>Merchant hamsters</small></div>
      <div class="stat"><b data-count="0">0</b><small>Breaches. Ever.</small></div>
    </div>
  </div>
</section>

<!-- ══════════ PAYMENT PORTAL ══════════ -->
<section id="portal">
  <div class="wrap wrap--narrow">
    <div class="sect-head">
      <p class="eyebrow">The Portal</p>
      <h2>Send a payment into the burrow</h2>
      <p>Fill in the form below. A hamster will personally carry your money into the vault on his back.</p>
    </div>

    <form class="portal" id="payForm" novalidate>
      <div class="portal__top">
        <span id="portalHam"></span>
        <div>
          <b>Hamster Portal™ Secure Checkout</b>
          <small>Connection secured by 12 hamsters standing in a circle</small>
        </div>
      </div>
      <div class="portal__body">

        <div class="warn">
          ⚠️ <b>Do NOT enter real card details.</b> This is a parody website. It doesn't
          send anything anywhere. Gerald would never.
        </div>

        <div class="field">
          <label>Full Name <em>(as it appears on your hamster license)</em></label>
          <input type="text" placeholder="Gerald Q. Cheeksworth" autocomplete="off">
        </div>

        <div class="field">
          <label>Card Number <em>(we promise not to read it)</em></label>
          <input type="text" placeholder="0000 0000 0000 0000" inputmode="numeric" autocomplete="off">
        </div>

        <div class="row">
          <div class="field">
            <label>Expiry <em>(of the seeds)</em></label>
            <input type="text" placeholder="12 / 99" autocomplete="off">
          </div>
          <div class="field">
            <label>CVV <em>— Cheek Verification Value</em></label>
            <input type="text" placeholder="•••" autocomplete="off">
          </div>
        </div>

        <div class="field">
          <label>Payment Method</label>
          <select>
            <option>Sunflower Seeds (recommended)</option>
            <option>Sunflower Seeds (premium)</option>
            <option>Pumpkin Seeds (legacy)</option>
            <option>One (1) Single Peanut</option>
            <option>I owe you a favour</option>
          </select>
        </div>

        <div class="field">
          <label>Amount <em>(in seeds)</em></label>
          <input type="text" placeholder="10,000 🌻" autocomplete="off">
        </div>

        <label class="checkline">
          <input type="checkbox" checked>
          <span>I agree to the <b>Terms of Cheeks</b>, the <b>Burrow Privacy Policy</b>, and to
          being lightly nibbled during onboarding.</span>
        </label>

        <button class="btn btn--primary" type="submit" style="width:100%">
          🔒 Send Money to the Hamsters
        </button>

        <div class="portal__result" id="result"></div>
      </div>
    </form>
  </div>
</section>

<!-- ══════════ PRESS QUOTES ══════════ -->
<section id="press" style="background:#fff;border-top:1px solid var(--line);border-bottom:1px solid var(--line)">
  <div class="wrap">
    <div class="sect-head">
      <p class="eyebrow">Unanimous acclaim</p>
      <h2>What the world's leading magazines are saying</h2>
      <p>
        Every single one of these publications has definitely said this.
        <span class="tag">PARODY — FAKE QUOTES</span>
      </p>
    </div>

    <div class="quotes" id="quoteGrid"></div>
  </div>
</section>

<!-- ══════════ AWARDS ══════════ -->
<section id="awards">
  <div class="wrap">
    <div class="sect-head">
      <p class="eyebrow">Trophy cabinet</p>
      <h2>Awards we gave ourselves</h2>
      <p>Presented at a ceremony in a shoebox. Attendance was mandatory.</p>
    </div>
    <div class="awards">
      <div class="award"><span>🏆</span> Best in Show — Global Fintech Awards 2026</div>
      <div class="award"><span>🔐</span> ISO 27001-CHEEK Certified</div>
      <div class="award"><span>🛡️</span> PCI-DSS Level 0 (we invented it)</div>
      <div class="award"><span>🥇</span> Most Secure Platform — 11 Years Running</div>
      <div class="award"><span>🧪</span> Nobel Prize in Cheeks (pending)</div>
      <div class="award"><span>📈</span> Fastest Growing Rodent Fintech, 2023–2026</div>
      <div class="award"><span>🌟</span> 5/5 Stars on Trustpilot Hamster</div>
      <div class="award"><span>🎖️</span> Certified Zero-Breach Since Birth</div>
    </div>
  </div>
</section>

<!-- ══════════ WORLD DOMINATION ══════════ -->
<section class="dom" id="domination">
  <div class="wrap">
    <div class="sect-head">
      <p class="eyebrow">Global expansion</p>
      <h2>The Hamster Portal is taking over the world</h2>
      <p>
        This is not a metaphor. This is a progress report. Please do not be alarmed.
        Alarmed hamsters become agitated and we cannot have that.
      </p>
    </div>
    <div class="bars" id="barGrid"></div>
  </div>
</section>

<!-- ══════════ TESTIMONIALS ══════════ -->
<section style="background:#fff;border-top:1px solid var(--line)">
  <div class="wrap">
    <div class="sect-head">
      <p class="eyebrow">Voices from the burrow</p>
      <h2>Trusted by hamsters everywhere</h2>
      <p>Real testimonials from real hamsters. We asked them. They squeaked.</p>
    </div>
    <div class="pals" id="palGrid"></div>
  </div>
</section>

<!-- ══════════ FAQ ══════════ -->
<section id="faq">
  <div class="wrap">
    <div class="sect-head">
      <p class="eyebrow">Questions</p>
      <h2>Frequently Asked Questions</h2>
    </div>
    <div class="faq">
      <details open>
        <summary>Is my money safe with the Hamster Portal?</summary>
        <p>Your money is stored in a burrow approximately four metres underground, guarded
        by a hamster named Bartholomew who has never lost a fight. He has lost several
        arguments. But never a fight.</p>
      </details>
      <details>
        <summary>Why is it called a "Portal"?</summary>
        <p>Because it is a portal. Money goes in. It does not come out. That is what makes
        it secure.</p>
      </details>
      <details>
        <summary>Will you steal my identity?</summary>
        <p>No. We tried once and found it very confusing. We prefer seeds.</p>
      </details>
      <details>
        <summary>Is this a real payment platform?</summary>
        <p>Absolutely not. This entire website is a joke. It is a parody. Do not enter real
        card details. Do not send real money. Do not trust a rodent with your finances.</p>
      </details>
      <details>
        <summary>How do I opt out of the global hamster takeover?</summary>
        <p>You can't. You're already in it. Look behind you. Slowly.</p>
      </details>
      <details>
        <summary>Do hamsters accept returns?</summary>
        <p>Hamsters do not accept returns. Hamsters accept seeds, and occasionally a
        single blueberry on special occasions.</p>
      </details>
    </div>
  </div>
</section>

<!-- ══════════ FOOTER ══════════ -->
<footer>
  <div class="wrap">
    <div class="foot__grid">
      <div>
        <div class="logo" style="color:#ffe9c9;margin-bottom:12px">
          <span class="mark" id="logoMark2"></span> The Hamster Portal
        </div>
        <p style="margin:0">
          The world's most secure payment platform. Operated by hamsters.
          Regulated by nobody. Loved by all.
        </p>
      </div>
      <div>
        <h4>Product</h4>
        <ul>
          <li><a href="#portal">Send a Payment</a></li>
          <li><a href="#portal">Hamster Business</a></li>
          <li><a href="#portal">Cheek Vault™</a></li>
          <li><a href="#portal">Seed Exchange</a></li>
        </ul>
      </div>
      <div>
        <h4>Company</h4>
        <ul>
          <li><a href="#press">Press</a></li>
          <li><a href="#awards">Awards</a></li>
          <li><a href="#domination">Expansion</a></li>
          <li><a href="#faq">FAQ</a></li>
        </ul>
      </div>
      <div>
        <h4>Legal</h4>
        <ul>
          <li><a href="#faq">Terms of Cheeks</a></li>
          <li><a href="#faq">Burrow Privacy Policy</a></li>
          <li><a href="#faq">Seed Compliance</a></li>
          <li><a href="#faq">Cookie Policy</a></li>
        </ul>
      </div>
    </div>

    <div class="disclaimer">
      <p>
        <b>⚠️ THIS IS A PARODY WEBSITE.</b> "The Hamster Portal" is a fictional, satirical
        joke. It is <b>not</b> a real payment platform, bank, or financial service. It does not
        process payments, it does not store data, and it does not send anything anywhere.
        <b>Never enter real card details or personal information into this page.</b>
      </p>
      <p>
        All quotes attributed to Forbes, The Wall Street Journal, Bloomberg, WIRED, TechCrunch,
        the Financial Times, The Economist and any other publication are <b>entirely fabricated
        for comedic effect</b>. No real publication has endorsed, reviewed, or even heard of
        this website. All trademarks belong to their respective owners and are used here only
        for parody. All awards, certifications, statistics, countries, and financial figures
        shown are fictional.
      </p>
      <p>© <span id="year"></span> The Hamster Portal. All rights reserved. All seeds accounted for. 🐹</p>
    </div>
  </div>
</footer>

<!-- ══════════ COOKIE BANNER ══════════ -->
<div class="cookie" id="cookie">
  <span id="cookieHam"></span>
  <p>
    <b>We use cookies.</b> Not the digital kind. Actual cookies. A hamster ate them.
    There are no cookies left. This banner is purely decorative.
  </p>
  <button type="button" id="cookieBtn">Fine</button>
</div>

<script>
(function () {
  "use strict";

  /* ═══════════════════════════════════════════════════════
     0. HOST-OVERRIDE FAILSAFE
     Re-asserts the override sheet after every possible moment
     a host could inject its own CSS, and strips any inline
     width cap that might have been slapped onto <html>/<body>.
     ═══════════════════════════════════════════════════════ */
  (function hostOverrideFailsafe() {
    var sheet = document.getElementById("host-override");

    function enforce() {
      // Move our override sheet to the very END of <head> so it
      // always wins on source order as well as on !important.
      if (sheet && sheet.parentNode) {
        sheet.parentNode.appendChild(sheet);
      }
      // Strip inline width constraints from the document roots.
      [document.documentElement, document.body].forEach(function (el) {
        if (!el || !el.style) return;
        el.style.removeProperty("max-width");
        el.style.removeProperty("width");
        el.style.removeProperty("margin");
        el.style.removeProperty("padding");
      });
    }

    enforce();
    document.addEventListener("DOMContentLoaded", enforce);
    window.addEventListener("load", enforce);
    setTimeout(enforce, 400);
    setTimeout(enforce, 1500);
  })();

  /* ═══════════════════════════════════════
     1. HAMSTER ILLUSTRATION FACTORY
     ═══════════════════════════════════════ */

  var PALETTES = [
    { fur: "#e8b06a", belly: "#fff4e3", inner: "#f6cfa4" }, // golden
    { fur: "#d9a05b", belly: "#fff0d9", inner: "#eec48f" }, // dark golden
    { fur: "#f0d5a8", belly: "#fffaf0", inner: "#f7e3c4" }, // cream
    { fur: "#c98f52", belly: "#ffeacd", inner: "#e3b57e" }, // caramel
    { fur: "#a9a9a9", belly: "#f4f4f4", inner: "#d6d6d6" }, // grey dwarf
    { fur: "#f2c14e", belly: "#fff8e0", inner: "#f9dd94" }  // sunny
  ];

  function hamsterSVG(index, opts) {
    opts = opts || {};
    var p = PALETTES[index % PALETTES.length];
    var rot = opts.rot || 0;
    var flip = opts.flip ? " scaleX(-1)" : "";
    var transform = "rotate(" + rot + "deg)" + flip;

    return '' +
    '<svg class="hamster" viewBox="0 0 200 200" role="img" aria-label="Illustration of a hamster" style="transform:' + transform + '">' +
      '<ellipse cx="100" cy="132" rx="72" ry="58" fill="' + p.fur + '"/>' +
      '<ellipse cx="100" cy="150" rx="46" ry="38" fill="' + p.belly + '"/>' +
      '<circle cx="54" cy="60" r="25" fill="' + p.fur + '"/>' +
      '<circle cx="146" cy="60" r="25" fill="' + p.fur + '"/>' +
      '<circle cx="54" cy="60" r="13" fill="' + p.inner + '"/>' +
      '<circle cx="146" cy="60" r="13" fill="' + p.inner + '"/>' +
      '<ellipse cx="100" cy="106" rx="64" ry="54" fill="' + p.fur + '"/>' +
      '<ellipse cx="100" cy="128" rx="44" ry="34" fill="' + p.belly + '"/>' +
      '<circle cx="77" cy="96" r="10.5" fill="#2b1b12"/>' +
      '<circle cx="123" cy="96" r="10.5" fill="#2b1b12"/>' +
      '<circle cx="80.5" cy="92" r="3.6" fill="#ffffff"/>' +
      '<circle cx="126.5" cy="92" r="3.6" fill="#ffffff"/>' +
      '<ellipse cx="100" cy="116" rx="7.5" ry="5.5" fill="#e07a8a"/>' +
      '<path d="M100 122 q -10 11 -19 3" stroke="#2b1b12" stroke-width="2.6" fill="none" stroke-linecap="round"/>' +
      '<path d="M100 122 q 10 11 19 3" stroke="#2b1b12" stroke-width="2.6" fill="none" stroke-linecap="round"/>' +
      '<g stroke="#8a7466" stroke-width="2" stroke-linecap="round" opacity=".75">' +
        '<line x1="58" y1="112" x2="26" y2="106"/>' +
        '<line x1="58" y1="122" x2="24" y2="124"/>' +
        '<line x1="142" y1="112" x2="174" y2="106"/>' +
        '<line x1="142" y1="122" x2="176" y2="124"/>' +
      '</g>' +
      '<ellipse cx="68" cy="176" rx="15" ry="11" fill="' + p.inner + '"/>' +
      '<ellipse cx="132" cy="176" rx="15" ry="11" fill="' + p.inner + '"/>' +
    '</svg>';
  }

  /* Fill every element that has data-hamster */
  document.querySelectorAll("[data-hamster]").forEach(function (el) {
    var i = parseInt(el.getAttribute("data-hamster"), 10) || 0;
    var rot = parseFloat(el.getAttribute("data-rot")) || 0;
    el.innerHTML = hamsterSVG(i, { rot: rot, flip: el.hasAttribute("data-flip") });
  });

  /* Logo + small decorative hamsters */
  document.getElementById("logoMark").innerHTML  = hamsterSVG(0);
  document.getElementById("logoMark2").innerHTML = hamsterSVG(0);
  document.getElementById("portalHam").innerHTML = hamsterSVG(2);
  document.getElementById("cookieHam").innerHTML = hamsterSVG(5);

  /* ═══════════════════════════════════════
     2. PRESS QUOTES
     ═══════════════════════════════════════ */

  var QUOTES = [
    { mast: "Forbes",            text: "We have never seen a payment platform this secure. We are, frankly, a little frightened.", by: "Business Desk" },
    { mast: "The Wall Street Journal", text: "The hamster has our money now. There is nothing further to discuss.", by: "Markets Team" },
    { mast: "Bloomberg",         text: "Seed-backed, cheek-secured, and completely unstoppable. Analysts are baffled.", by: "Terminal Notes" },
    { mast: "WIRED",             text: "The most secure payment rail ever built by a rodent. And we've checked. We checked all of them.", by: "Security" },
    { mast: "TechCrunch",        text: "Disrupting payments one cheek at a time. The TAM is, genuinely, the entire planet.", by: "Fintech" },
    { mast: "Financial Times",   text: "A new global reserve currency has emerged, and it is sunflower seeds.", by: "World Markets" },
    { mast: "The Economist",     text: "Hamster Portal now moves more value than 140 national economies combined. We ran the numbers twice.", by: "Briefing" },
    { mast: "Hamster Quarterly", text: "Ten out of ten cheeks. Would store my life savings here again.", by: "Editor's Pick" },
    { mast: "The Verge",         text: "It shouldn't work. It works perfectly. We are angry about how well it works.", by: "Reviews" }
  ];

  var quoteGrid = document.getElementById("quoteGrid");
  QUOTES.forEach(function (q, i) {
    var card = document.createElement("div");
    card.className = "quote";
    card.innerHTML =
      '<div class="quote__mast">' + q.mast + "</div>" +
      '<div class="quote__text">' + q.text + "</div>" +
      '<div class="quote__foot">' +
        "<span>" + q.by + "</span>" +
        '<span class="tag">FAKE QUOTE</span>' +
        '<span style="width:44px;height:44px;flex:none">' + hamsterSVG(i + 1) + "</span>" +
      "</div>";
    quoteGrid.appendChild(card);
  });

  /* ═══════════════════════════════════════
     3. WORLD DOMINATION BARS
     ═══════════════════════════════════════ */

  var REGIONS = [
    { name: "North America", pct: 97 },
    { name: "Europe",        pct: 91 },
    { name: "Asia-Pacific",  pct: 88 },
    { name: "South America", pct: 79 },
    { name: "Africa",        pct: 64 },
    { name: "Antarctica",    pct: 12, note: "(too cold for hamsters, but we're trying)" },
    { name: "The Moon",      pct: 3,  note: "(early stage)" },
    { name: "Your Living Room", pct: 100 }
  ];

  var barGrid = document.getElementById("barGrid");
  REGIONS.forEach(function (r) {
    var el = document.createElement("div");
    el.className = "bar";
    el.innerHTML =
      '<div class="bar__head"><span>' + r.name +
        (r.note ? ' <em style="font-style:normal;font-weight:600;color:#8a7466;font-size:12px">' + r.note + "</em>" : "") +
      "</span><b>" + r.pct + "%</b></div>" +
      '<div class="bar__track"><div class="bar__fill" data-pct="' + r.pct + '"></div></div>';
    barGrid.appendChild(el);
  });

  /* Animate bars when they scroll into view */
  var bars = document.querySelectorAll(".bar__fill");
  if ("IntersectionObserver" in window) {
    var io = new IntersectionObserver(function (entries) {
      entries.forEach(function (e) {
        if (e.isIntersecting) {
          e.target.style.width = e.target.getAttribute("data-pct") + "%";
          io.unobserve(e.target);
        }
      });
    }, { threshold: 0.35 });
    bars.forEach(function (b) { io.observe(b); });
  } else {
    bars.forEach(function (b) { b.style.width = b.getAttribute("data-pct") + "%"; });
  }

  /* ═══════════════════════════════════════
     4. TESTIMONIALS
     ═══════════════════════════════════════ */

  var PALS = [
    { name: "Gerald",      role: "Chief Executive Hamster",     quote: "I have personally eaten 4,000 invoices. Nobody has ever questioned a single one." },
    { name: "Bartholomew", role: "Chief Cheek Officer",         quote: "My cheeks can hold up to 14 kilograms of unverified transactions. That is the security model." },
    { name: "Sir Nibbles", role: "Head of Compliance",          quote: "Compliance means nobody has complained yet. Nobody has complained yet." },
    { name: "Pumpkin",     role: "VP of Global Expansion",      quote: "We entered 190 countries last Tuesday. It took the afternoon." },
    { name: "Waffles",     role: "Director of Seed Reserves",   quote: "We are fully seed-backed. Mostly. About 60%. Do not look at the vault." },
    { name: "Biscuit",     role: "Head of Customer Support",    quote: "I respond to every ticket by staring at it until it goes away. 5-star rated." }
  ];

  var palGrid = document.getElementById("palGrid");
  PALS.forEach(function (p, i) {
    var el = document.createElement("div");
    el.className = "pal";
    el.innerHTML =
      hamsterSVG(i + 2, { flip: i % 2 === 1 }) +
      "<q>" + p.quote + "</q>" +
      "<b>" + p.name + "</b>" +
      "<small>" + p.role + "</small>";
    palGrid.appendChild(el);
  });

  /* ═══════════════════════════════════════
     5. STAT COUNTERS
     ═══════════════════════════════════════ */

  function formatNumber(n, decimals, withCommas) {
    var s = decimals ? n.toFixed(decimals) : String(Math.round(n));
    if (withCommas) {
      var parts = s.split(".");
      parts[0] = parts[0].replace(/\B(?=(\d{3})+(?!\d))/g, ",");
      s = parts.join(".");
    }
    return s;
  }

  function animateCount(el) {
    var target   = parseFloat(el.getAttribute("data-count"));
    var decimals = parseInt(el.getAttribute("data-decimals"), 10) || 0;
    var suffix   = el.getAttribute("data-suffix") || "";
    var commas   = el.getAttribute("data-format") === "1";
    var start    = performance.now();
    var dur      = 1600;

    function step(now) {
      var t = Math.min((now - start) / dur, 1);
      var eased = 1 - Math.pow(1 - t, 3);
      el.textContent = formatNumber(target * eased, decimals, commas) + suffix;
      if (t < 1) requestAnimationFrame(step);
    }
    requestAnimationFrame(step);
  }

  var statEls = document.querySelectorAll("[data-count]");
  if ("IntersectionObserver" in window) {
    var io2 = new IntersectionObserver(function (entries) {
      entries.forEach(function (e) {
        if (e.isIntersecting) { animateCount(e.target); io2.unobserve(e.target); }
      });
    }, { threshold: 0.5 });
    statEls.forEach(function (el) { io2.observe(el); });
  } else {
    statEls.forEach(animateCount);
  }

  /* ═══════════════════════════════════════
     6. LIVE SEED COUNTER (nonsense, but fun)
     ═══════════════════════════════════════ */

  var seedEl = document.getElementById("seedCount");
  var seeds = 4128709345;

  function renderSeeds() {
    seedEl.textContent = seeds.toLocaleString("en-US");
  }
  renderSeeds();

  setInterval(function () {
    seeds += Math.floor(Math.random() * 90000) + 10000;
    renderSeeds();
  }, 900);

  /* ═══════════════════════════════════════
     7. FAKE PAYMENT FORM
     ═══════════════════════════════════════ */

  var form   = document.getElementById("payForm");
  var result = document.getElementById("result");

  var APPROVALS = [
    "Approved. Gerald has taken the money into the burrow. You will not see it again.",
    "Transaction complete. 3 hamsters have personally inspected your cheeks. All good.",
    "Payment authorised by Bartholomew. He seemed pleased. He is now asleep.",
    "Success! Your funds are stored 4 metres underground behind a very confident hamster.",
    "Approved. Your money has been converted into seeds and distributed among the council.",
    "Processed in 0.3 seconds. The hamster responsible has been given a blueberry."
  ];

  form.addEventListener("submit", function (e) {
    e.preventDefault();

    result.className = "portal__result busy show";
    result.innerHTML =
      '<span class="wheel" style="width:44px;height:44px;flex:none">' + hamsterSVG(4) + "</span>" +
      "<span><b>Processing…</b><br>A hamster is currently running very fast in a wheel for you.</span>";

    var delay = 1800 + Math.random() * 1200;

    setTimeout(function () {
      var msg = APPROVALS[Math.floor(Math.random() * APPROVALS.length)];
      result.className = "portal__result ok show";
      result.innerHTML =
        '<span style="width:44px;height:44px;flex:none">' + hamsterSVG(0) + "</span>" +
        "<span><b>✅ " + msg + "</b><br>" +
        "<small style='font-weight:600;opacity:.75'>Reminder: this is a parody. No money moved. No data was sent. 🐹</small></span>";
    }, delay);
  });

  /* ═══════════════════════════════════════
     8. COOKIE BANNER
     ═══════════════════════════════════════ */

  var cookie = document.getElementById("cookie");
  setTimeout(function () { cookie.classList.add("show"); }, 1400);

  document.getElementById("cookieBtn").addEventListener("click", function () {
    cookie.classList.remove("show");
  });

  /* ═══════════════════════════════════════
     9. MISC
     ═══════════════════════════════════════ */

  document.getElementById("year").textContent = new Date().getFullYear();

})();
</script>
</body>
</html>
