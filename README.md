<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1.0">
<title>Rotas Extra — Apresentação</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&display=swap');

  *{box-sizing:border-box;margin:0;padding:0}

  :root{
    --yellow:#FFE600;
    --yellow-dark:#CCBA00;
    --blue:#3483FA;
    --blue-dark:#2968C8;
    --black:#1A1A1A;
    --gray:#666;
    --light:#F7F7F7;
    --white:#fff;
    --green:#00A650;
    --amber:#F59E0B;
    --red:#E02020;
  }

  body{
    font-family:'Inter',system-ui,sans-serif;
    background:var(--black);
    color:var(--white);
    font-size:15px;
    line-height:1.6;
  }

  /* ── HERO ── */
  .hero{
    background:var(--yellow);
    color:var(--black);
    padding:60px 24px 50px;
    text-align:center;
    position:relative;
    overflow:hidden;
  }
  .hero::before{
    content:'';
    position:absolute;
    inset:0;
    background:repeating-linear-gradient(
      -45deg,
      transparent,
      transparent 20px,
      rgba(0,0,0,.04) 20px,
      rgba(0,0,0,.04) 21px
    );
  }
  .hero-inner{position:relative;max-width:680px;margin:0 auto}
  .hero-badge{
    display:inline-flex;align-items:center;gap:8px;
    background:var(--black);color:var(--yellow);
    font-size:11px;font-weight:700;letter-spacing:.08em;text-transform:uppercase;
    padding:5px 14px;border-radius:99px;margin-bottom:24px;
  }
  .hero h1{
    font-size:clamp(32px,6vw,52px);
    font-weight:800;
    line-height:1.1;
    letter-spacing:-.02em;
    margin-bottom:16px;
  }
  .hero h1 span{color:var(--blue)}
  .hero p{
    font-size:17px;color:#444;
    max-width:520px;margin:0 auto 32px;
    font-weight:500;
  }
  .hero-cta{
    display:inline-flex;align-items:center;gap:8px;
    background:var(--blue);color:var(--white);
    font-size:15px;font-weight:700;
    padding:14px 28px;border-radius:10px;
    text-decoration:none;
    transition:background .15s;
  }
  .hero-cta:hover{background:var(--blue-dark)}
  .arrow{font-size:18px}

  /* ── SEÇÕES ── */
  section{padding:64px 24px}
  .container{max-width:900px;margin:0 auto}

  .section-label{
    font-size:11px;font-weight:700;letter-spacing:.1em;text-transform:uppercase;
    color:var(--yellow);margin-bottom:12px;
  }
  h2{
    font-size:clamp(24px,4vw,36px);
    font-weight:800;line-height:1.2;letter-spacing:-.02em;
    margin-bottom:12px;
  }
  .subtitle{font-size:16px;color:#999;margin-bottom:48px}

  /* ── COMO FUNCIONA ── */
  .steps{display:grid;grid-template-columns:repeat(auto-fit,minmax(240px,1fr));gap:20px}
  .step{
    background:#242424;
    border:1px solid #333;
    border-radius:16px;
    padding:28px 24px;
    position:relative;
  }
  .step-num{
    font-size:11px;font-weight:800;letter-spacing:.08em;
    color:var(--yellow);text-transform:uppercase;margin-bottom:16px;
    display:block;
  }
  .step-icon{
    font-size:32px;margin-bottom:12px;display:block;
  }
  .step h3{font-size:17px;font-weight:700;margin-bottom:8px}
  .step p{font-size:14px;color:#999;line-height:1.6}

  /* ── FEATURES ── */
  .features-section{background:#111}
  .features{display:grid;grid-template-columns:repeat(auto-fit,minmax(260px,1fr));gap:16px}
  .feature{
    background:#1A1A1A;
    border:1px solid #2A2A2A;
    border-radius:14px;
    padding:24px;
    display:flex;gap:16px;align-items:flex-start;
  }
  .feature-icon{
    width:44px;height:44px;border-radius:10px;
    display:flex;align-items:center;justify-content:center;
    font-size:20px;flex-shrink:0;
  }
  .fi-yellow{background:rgba(255,230,0,.12);color:var(--yellow)}
  .fi-blue{background:rgba(52,131,250,.12);color:var(--blue)}
  .fi-green{background:rgba(0,166,80,.12);color:var(--green)}
  .fi-amber{background:rgba(245,158,11,.12);color:var(--amber)}
  .feature h3{font-size:15px;font-weight:700;margin-bottom:4px}
  .feature p{font-size:13px;color:#888;line-height:1.5}

  /* ── SEMÁFORO ── */
  .semaforo-section{background:#0D0D0D}
  .sema-cards{display:flex;flex-direction:column;gap:12px;max-width:560px}
  .sema-card{
    display:flex;align-items:center;gap:16px;
    background:#1A1A1A;border:1px solid #2A2A2A;border-radius:12px;
    padding:16px 20px;
  }
  .sema-dot{width:16px;height:16px;border-radius:50%;flex-shrink:0}
  .sema-dot.verde{background:var(--green);box-shadow:0 0 10px rgba(0,166,80,.5)}
  .sema-dot.amarelo{background:var(--amber);box-shadow:0 0 10px rgba(245,158,11,.5)}
  .sema-dot.vermelho{background:var(--red);box-shadow:0 0 10px rgba(224,32,32,.5)}
  .sema-dot.cinza{background:#555}
  .sema-card h4{font-size:14px;font-weight:700;margin-bottom:2px}
  .sema-card p{font-size:13px;color:#888}

  .sema-layout{display:grid;grid-template-columns:1fr 1fr;gap:48px;align-items:center}
  @media(max-width:640px){.sema-layout{grid-template-columns:1fr}}

  .sema-explain h3{font-size:22px;font-weight:700;margin-bottom:12px;line-height:1.3}
  .sema-explain p{font-size:14px;color:#888;line-height:1.7}

  /* ── TURNOS ── */
  .turnos-section{background:#111}
  .turnos{display:grid;grid-template-columns:repeat(auto-fit,minmax(200px,1fr));gap:16px}
  .turno-card{
    border-radius:14px;padding:24px;text-align:center;
    border:1px solid #2A2A2A;
  }
  .turno-card.t1{background:rgba(52,131,250,.08);border-color:rgba(52,131,250,.2)}
  .turno-card.t2{background:rgba(245,158,11,.08);border-color:rgba(245,158,11,.2)}
  .turno-card.t3{background:rgba(100,100,100,.08);border-color:rgba(100,100,100,.2)}
  .turno-card.tc{background:rgba(0,166,80,.08);border-color:rgba(0,166,80,.2)}
  .turno-hora{font-size:22px;font-weight:800;margin-bottom:4px}
  .turno-hora.blue{color:var(--blue)}
  .turno-hora.amber{color:var(--amber)}
  .turno-hora.gray{color:#888}
  .turno-hora.green{color:var(--green)}
  .turno-label{font-size:13px;color:#666;margin-bottom:10px}
  .turno-badge{
    display:inline-block;font-size:11px;font-weight:700;
    padding:3px 10px;border-radius:99px;
  }
  .turno-badge.blue{background:rgba(52,131,250,.15);color:var(--blue)}
  .turno-badge.amber{background:rgba(245,158,11,.15);color:var(--amber)}
  .turno-badge.gray{background:rgba(100,100,100,.15);color:#888}
  .turno-badge.green{background:rgba(0,166,80,.15);color:var(--green)}

  /* ── ALERTAS ── */
  .alertas-section{background:#0D0D0D}
  .alertas{display:grid;grid-template-columns:repeat(auto-fit,minmax(240px,1fr));gap:16px}
  .alerta{border-radius:12px;padding:20px 24px;border-left:4px solid}
  .alerta.fiel{background:#1A1A00;border-color:var(--yellow);color:var(--yellow)}
  .alerta.fiel p{color:#cc9900}
  .alerta.express{background:#1A0F00;border-color:var(--amber)}
  .alerta.express h4{color:var(--amber)}
  .alerta.express p{color:#cc8800}
  .alerta.restricao{background:#0A0A0A;border-color:#444}
  .alerta.restricao h4{color:#ccc}
  .alerta.restricao p{color:#666}
  .alerta h4{font-size:14px;font-weight:700;margin-bottom:6px}
  .alerta p{font-size:13px;line-height:1.5}

  /* ── CTA FINAL ── */
  .cta-section{
    background:var(--yellow);
    color:var(--black);
    text-align:center;
    padding:72px 24px;
  }
  .cta-section h2{color:var(--black);margin-bottom:12px}
  .cta-section p{color:#555;margin-bottom:32px;font-size:16px}
  .cta-btn{
    display:inline-flex;align-items:center;gap:8px;
    background:var(--black);color:var(--yellow);
    font-size:16px;font-weight:700;
    padding:16px 32px;border-radius:12px;
    text-decoration:none;
    transition:opacity .15s;
  }
  .cta-btn:hover{opacity:.85}

  /* ── FOOTER ── */
  footer{
    background:#0A0A0A;border-top:1px solid #1A1A1A;
    padding:24px;text-align:center;
    font-size:12px;color:#444;
  }

  @media(max-width:600px){
    .hero{padding:48px 20px 40px}
    section{padding:48px 20px}
  }
</style>
</head>
<body>

<!-- HERO -->
<div class="hero">
  <div class="hero-inner">
    <div class="hero-badge">🛒 Mercado Livre Transportes</div>
    <h1>Rotas Extra<br><span>na palma da mão</span></h1>
    <p>Consulte transportadoras, veja propensão de aceite e acione o contato certo no turno certo — tudo em segundos.</p>
    <a class="hero-cta" href="https://danilowagner-web.github.io/rotas-meli" target="_blank">
      Acessar a ferramenta <span class="arrow">↗</span>
    </a>
  </div>
</div>

<!-- COMO FUNCIONA -->
<section>
  <div class="container">
    <div class="section-label">Como funciona</div>
    <h2>Três passos para acionar uma rota extra</h2>
    <p class="subtitle">Simples, rápido e sem precisar instalar nada.</p>
    <div class="steps">
      <div class="step">
        <span class="step-num">Passo 01</span>
        <span class="step-icon">🔍</span>
        <h3>Selecione origem e destino</h3>
        <p>Digite o ID da operação (ex: BRXSP10) ou o nome. A busca filtra em tempo real entre todas as operações cadastradas.</p>
      </div>
      <div class="step">
        <span class="step-num">Passo 02</span>
        <span class="step-icon">🚛</span>
        <h3>Escolha o tipo de veículo</h3>
        <p>Carreta, Bi-trem, Truck, Toco, VUC e mais. A ferramenta valida automaticamente se o veículo é compatível com a rota.</p>
      </div>
      <div class="step">
        <span class="step-num">Passo 03</span>
        <span class="step-icon">📲</span>
        <h3>Acione a transportadora</h3>
        <p>Veja quem está no turno agora com maior propensão de aceite e abra o WhatsApp direto com um toque.</p>
      </div>
    </div>
  </div>
</section>

<!-- FEATURES -->
<section class="features-section">
  <div class="container">
    <div class="section-label">Funcionalidades</div>
    <h2>Tudo que você precisa em um só lugar</h2>
    <p class="subtitle">Desenvolvido especificamente para o time de Transportes MLP.</p>
    <div class="features">
      <div class="feature">
        <div class="feature-icon fi-yellow">🗺️</div>
        <div>
          <h3>Busca inteligente</h3>
          <p>88 origens XD/Full e 140 Service Centers. Busque por ID ou nome da operação.</p>
        </div>
      </div>
      <div class="feature">
        <div class="feature-icon fi-green">🟢</div>
        <div>
          <h3>Semáforo de aceite</h3>
          <p>Ranking baseado no histórico real de viagens. Saiba quem tem mais chance de aceitar antes de ligar.</p>
        </div>
      </div>
      <div class="feature">
        <div class="feature-icon fi-blue">📞</div>
        <div>
          <h3>Contatos por turno</h3>
          <p>Detecta o turno atual automaticamente e destaca quem está trabalhando agora na transportadora.</p>
        </div>
      </div>
      <div class="feature">
        <div class="feature-icon fi-yellow">⭐</div>
        <div>
          <h3>Fiel Depositário</h3>
          <p>Alerta automático para UFs que exigem habilitação. Filtra só as transportadoras aptas.</p>
        </div>
      </div>
      <div class="feature">
        <div class="feature-icon fi-amber">⚠️</div>
        <div>
          <h3>Alertas de rota</h3>
          <p>Rota expressa acima de 11h30, restrição de veículo no destino e perfil exigido — tudo automático.</p>
        </div>
      </div>
      <div class="feature">
        <div class="feature-icon fi-blue">📋</div>
        <div>
          <h3>Diretório de transportadores</h3>
          <p>Lista completa de MLPs com filtro por regional e botão de WhatsApp direto para cada um.</p>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- SEMÁFORO -->
<section class="semaforo-section">
  <div class="container">
    <div class="sema-layout">
      <div class="sema-explain">
        <div class="section-label">Propensão de aceite</div>
        <h3>Saiba antes de ligar quem tem mais chance de aceitar</h3>
        <p>O semáforo é calculado com base no histórico real de viagens de cada transportadora para o destino escolhido. Quem fez mais vezes aquela rota tende a aceitar mais rápido.</p>
      </div>
      <div class="sema-cards">
        <div class="sema-card">
          <div class="sema-dot verde"></div>
          <div>
            <h4>Alta propensão</h4>
            <p>50% ou mais do volume do líder naquela rota</p>
          </div>
        </div>
        <div class="sema-card">
          <div class="sema-dot amarelo"></div>
          <div>
            <h4>Média propensão</h4>
            <p>Entre 20% e 49% do volume do líder</p>
          </div>
        </div>
        <div class="sema-card">
          <div class="sema-dot vermelho"></div>
          <div>
            <h4>Baixa propensão</h4>
            <p>Menos de 20% do volume do líder</p>
          </div>
        </div>
        <div class="sema-card">
          <div class="sema-dot cinza"></div>
          <div>
            <h4>Sem histórico</h4>
            <p>Nenhuma viagem registrada para esse destino</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- TURNOS -->
<section class="turnos-section">
  <div class="container">
    <div class="section-label">Contatos por turno</div>
    <h2>Fala com quem está trabalhando agora</h2>
    <p class="subtitle">A ferramenta detecta o horário atual e destaca automaticamente os contatos do turno ativo.</p>
    <div class="turnos">
      <div class="turno-card t1">
        <div class="turno-hora blue">06h — 14h</div>
        <div class="turno-label">1° Turno</div>
        <span class="turno-badge blue">Manhã</span>
      </div>
      <div class="turno-card t2">
        <div class="turno-hora amber">14h — 22h</div>
        <div class="turno-label">2° Turno</div>
        <span class="turno-badge amber">Tarde</span>
      </div>
      <div class="turno-card t3">
        <div class="turno-hora gray">22h — 06h</div>
        <div class="turno-label">3° Turno</div>
        <span class="turno-badge gray">Noite</span>
      </div>
      <div class="turno-card tc">
        <div class="turno-hora green">08h — 18h</div>
        <div class="turno-label">Horário Comercial</div>
        <span class="turno-badge green">Adm</span>
      </div>
    </div>
  </div>
</section>

<!-- ALERTAS -->
<section class="alertas-section">
  <div class="container">
    <div class="section-label">Alertas automáticos</div>
    <h2>Nenhuma informação crítica passa em branco</h2>
    <p class="subtitle">A ferramenta avalia a rota e dispara avisos antes mesmo de você buscar as transportadoras.</p>
    <div class="alertas">
      <div class="alerta fiel">
        <h4>⭐ Fiel Depositário obrigatório</h4>
        <p>Quando o destino está em UF que exige habilitação, apenas as transportadoras aptas aparecem na lista.</p>
      </div>
      <div class="alerta express">
        <h4>⚠️ Rota expressa &gt; 11h30</h4>
        <p>Veículos pequenos como VUC e Toco são bloqueados automaticamente. Só carreta, bi-trem e truck são exibidos.</p>
      </div>
      <div class="alerta restricao">
        <h4>🚫 Restrição de veículo no destino</h4>
        <p>Se a operação de destino não comporta determinado tipo de veículo, o alerta aparece antes da busca.</p>
      </div>
    </div>
  </div>
</section>

<!-- CTA FINAL -->
<div class="cta-section">
  <div class="container">
    <div class="section-label" style="color:#888">Pronto para usar</div>
    <h2>Sem login. Sem instalação.<br>Abre no celular e no computador.</h2>
    <p>Acesse direto pelo link, compartilha com o time e começa a usar agora.</p>
    <a class="cta-btn" href="https://danilowagner-web.github.io/rotas-meli" target="_blank">
      🚀 Acessar Rotas Extra
    </a>
  </div>
</div>

<footer>
  Mercado Livre Transportes — Rotas Extra &nbsp;|&nbsp; Desenvolvido por Danilo Wagner
</footer>

</body>
</html>
