!doctype html>
<html lang="pt-BR">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Parabéns, Evellyn!</title>

  <!-- Fontes -->
  <link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@400;700&family=Montserrat:wght@300;600&display=swap" rel="stylesheet">

  <style>
    /* ---------- Variáveis default (serão sobrescritas por casa) ---------- */
    :root{
      --bg: #0b0b0b;
      --card-bg: linear-gradient(180deg, rgba(255,255,255,0.03), rgba(255,255,255,0.01));
      --primary: #7f0909;   /* cor principal (ex: Gryffindor) */
      --accent: #d4af37;    /* cor de destaque (ex: dourado) */
      --muted: rgba(255,255,255,0.85);
      --text-shadow: 0 2px 8px rgba(0,0,0,0.6);
      --paper: linear-gradient(180deg, #f8f1dc, #f0e6c9);
    }

    /* ---------- Cores por casa (troque data-house no <body>) ---------- */
    body[data-house="gryffindor"]{
      --primary: #7f0909;  /* vermelho escuro */
      --accent: #dbb02c;   /* dourado */
      --bg: radial-gradient(ellipse at top left, #2b0b0b 0%, #0b0710 60%);
      --paper: linear-gradient(180deg, #f7ecd6, #efe3c2);
    }
    body[data-house="slytherin"]{
      --primary: #0b6b3a;  /* verde */
      --accent: #bfbf9a;   /* prata/creme */
      --bg: radial-gradient(ellipse at top left, #082616 0%, #03100a 60%);
      --paper: linear-gradient(180deg, #eaf0e8, #d8e2d3);
    }
    body[data-house="ravenclaw"]{
      --primary: #0f3b6b;  /* azul escuro */
      --accent: #9ea8c3;   /* bronze/acinzentado */
      --bg: radial-gradient(ellipse at top left, #081631 0%, #030713 60%);
      --paper: linear-gradient(180deg, #eef3fb, #dde9f3);
    }
    body[data-house="hufflepuff"]{
      --primary: #a67e00;  /* amarelo queimado */
      --accent: #3b2b1f;   /* marrom escuro */
      --bg: radial-gradient(ellipse at top left, #2b1a00 0%, #0c0600 60%);
      --paper: linear-gradient(180deg, #fbf1d7, #f0e3c0);
    }

    /* ---------- Reset e layout ---------- */
    *{box-sizing:border-box;margin:0;padding:0}
    html,body{height:100%}
    body{
      font-family: "Montserrat", system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
      background: var(--bg);
      color: var(--muted);
      display:flex;
      align-items:center;
      justify-content:center;
      padding:32px;
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
    }

    .container{
      width:100%;
      max-width:980px;
      background: linear-gradient(180deg, rgba(0,0,0,0.25), rgba(255,255,255,0.02));
      border-radius:18px;
      padding:28px;
      box-shadow: 0 10px 40px rgba(0,0,0,0.6), inset 0 1px 0 rgba(255,255,255,0.02);
      position:relative;
      overflow:hidden;
      border: 1px solid rgba(255,255,255,0.03);
    }

    /* ---------- Header estilo "Hogwarts" ---------- */
    header{
      display:flex;
      gap:20px;
      align-items:center;
      margin-bottom:18px;
    }

    /* placeholder simples para brasão — altere texto se quiser */
    .crest small{display:block;font-size:12px;color:var(--accent);font-weight:700}

    h1{
      font-family: "Cinzel", serif;
      font-size:44px;
      line-height:1;
      color:var(--accent);
      text-shadow: 0 2px 0 rgba(0,0,0,0.6), 0 6px 18px rgba(0,0,0,0.55);
    }
    .subtitle{
      color:rgba(255,255,255,0.85);
      font-weight:600;
      margin-top:6px;
      font-size:16px;
    }

    /* ---------- Cartão de mensagem (papel antigo) ---------- */
    .card{
      margin-top:18px;
      background: var(--paper);
      border-radius:12px;
      padding:28px;
      color:#111;
      box-shadow: 0 15px 40px rgba(0,0,0,0.45);
      border: 1px solid rgba(0,0,0,0.06);
      font-size:18px;
      line-height:1.5;
    }
    .card h2{
      margin-bottom:8px;
      font-family: "Cinzel", serif;
      color: var(--primary);
      font-size:28px;
    }

    /* ---------- Confetes mágicos (simples) ---------- */
    .confetti {
      pointer-events:none;
      position:absolute;
      inset:0;
      overflow:hidden;
    }
    .confetti i{
      position:absolute;
      width:10px;height:16px;
      opacity:0.95;
      transform-origin:center;
      top:-10%;
      animation:fall linear infinite;
      border-radius:2px;
      box-shadow: 0 2px 4px rgba(0,0,0,0.25);
    }
    @keyframes fall{
      0%{transform:translateY(-10vh) rotate(0) translateX(0); opacity:1}
      100%{transform:translateY(120vh) rotate(720deg) translateX(120px); opacity:0.95}
    }

    /* Weave subtle "parchment" line behind */
    .parchment {
      position:absolute; inset:0; pointer-events:none;
      background-image:
        linear-gradient(transparent 0, rgba(0,0,0,0.02) 2px, transparent 3px);
      opacity:0.18;
      mix-blend-mode:overlay;
    }

    /* ---------- Footer controls ---------- */
    .controls{
      margin-top:14px;
      display:flex;
      gap:10px;
      align-items:center;
      justify-content:flex-end;
    }
    .btn{
      background:transparent;
      color:var(--accent);
      border:1px solid rgba(255,255,255,0.06);
      padding:8px 12px;
      border-radius:8px;
      cursor:pointer;
      font-weight:700;
      font-size:14px;
      transition: all .18s ease;
    }
    .btn:hover{transform:translateY(-3px); box-shadow: 0 6px 18px rgba(0,0,0,0.45)}
    .house-label{
      color:rgba(255,255,255,0.75);
      font-size:13px;
      margin-right:auto;
      font-weight:600;
    }

    /* Responsividade */
    @media (max-width:640px){
      header{flex-direction:row; gap:12px}
      .crest{width:84px;height:84px;font-size:28px}
      h1{font-size:28px}
      .card{padding:18px;font-size:16px}
    }
  </style>
</head>
<body data-house="gryffindor">
  <div class="container" role="main" aria-labelledby="main-title">
    <header>
      <div class="crest" aria-hidden="true">
        EVY
        <small>Grifinória</small>
      </div>

      <div>
        <h1 id="main-title">Parabéns, Evyyy!</h1>
        <div class="subtitle">Do seu irmãozinho Sonserino que te ama muito </div>
      </div>
    </header>

    <section class="card" aria-label="Mensagem de parabéns">
      <h2>13/11/1997</h2>
      <p>
        Querida <strong>Evellyn</strong>, Você sabe o quão importante você é para mim. Tudo que sou hoje, é graças a você. Receba esse sitezinho mequetrefe como 1% do amor que sinto por você
      </p>

      <p style="margin-top:10px;font-weight:600;">
        Com carinho, <br>
        <span style="font-style:italic">seu fã e irmão Kayo.</span>
      </p>

      <div class="controls" aria-hidden="false">
        <span class="house-label">:</span>
        <button class="btn" data-house="gryffindor">Grifinória</button>
        <button class="btn" data-house="slytherin">Sonserina</button>
        <button class="btn" data-house="ravenclaw">Corvinal</button>
        <button class="btn" data-house="hufflepuff">Lufa Lufa</button>
      </div>
    </section>

    <!-- confetti container (será preenchido por JS) -->
    <div class="confetti" aria-hidden="true"></div>
    <div class="parchment" aria-hidden="true"></div>
  </div>

  <script>
    // ---------- Troca visual da casa (altera data-house no body) ----------
    document.querySelectorAll('.btn[data-house]').forEach(btn=>{
      btn.addEventListener('click', e=>{
        const house = e.currentTarget.getAttribute('data-house');
        document.body.setAttribute('data-house', house);

        // atualiza o texto do brasão para ficar coerente
        const small = document.querySelector('.crest small');
        small.textContent = house.charAt(0).toUpperCase() + house.slice(1);
      });
    });

    // ---------- Gera confete colorido de acordo com a casa ----------
    const confettiContainer = document.querySelector('.confetti');

    function random(min,max){ return Math.random()*(max-min)+min }

    function createConfettiPiece(houseColors){
      const el = document.createElement('i');
      const size = Math.floor(random(8,18));
      el.style.width = size + 'px';
      el.style.height = Math.floor(size*1.4) + 'px';
      el.style.left = Math.floor(random(2,98)) + '%';
      el.style.background = houseColors[Math.floor(Math.random()*houseColors.length)];
      el.style.top = (-Math.random()*10) + '%';
      el.style.opacity = random(0.8,1);
      el.style.animationDuration = `${random(3.5,7.5)}s`;
      el.style.animationDelay = `${random(0,2)}s`;
      el.style.transform = `rotate(${Math.floor(random(0,360))}deg)`;
      confettiContainer.appendChild(el);

      // remove após a animação
      setTimeout(()=> el.remove(), 9000);
    }

    function getColorsForHouse(){
      const house = document.body.getAttribute('data-house') || 'gryffindor';
      if(house === 'gryffindor') return ['#7f0909','#dbb02c','#a71d2a','#6b0404'];
      if(house === 'slytherin') return ['#0b6b3a','#bfbf9a','#7da88a','#0a4f2f'];
      if(house === 'ravenclaw') return ['#0f3b6b','#9ea8c3','#2b5a8a','#25456d'];
      if(house === 'hufflepuff') return ['#a67e00','#3b2b1f','#e6c04a','#8a5f1b'];
      return ['#ffffff'];
    }

    // cria rajadas de confete periodicamente
    setInterval(()=>{
      const colors = getColorsForHouse();
      const count = Math.floor(random(8,16));
      for(let i=0;i<count;i++) createConfettiPiece(colors);
    }, 900);

    // atualiza crest label quando trocar casa via JS (inicial)
    const initial = document.body.getAttribute('data-house') || 'gryffindor';
    document.querySelector('.crest small').textContent = initial.charAt(0).toUpperCase() + initial.slice(1);
  </script>
</body>
</html>
