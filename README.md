<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>ResidênciaFix — Serviços Domiciliares Profissionais</title>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@400;600;700&family=Outfit:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
:root {
  --navy: #0a1628;
  --navy2: #142238;
  --gold: #b8963e;
  --gold-lt: #d4af6a;
  --cream: #f7f3ec;
  --offwhite: #fdfaf5;
  --gray: #64748b;
  --light: #eee9df;
  --text: #1e293b;
}

*, *::before, *::after { margin:0; padding:0; box-sizing:border-box; }
html { scroll-behavior: smooth; }

body {
  font-family: 'Outfit', sans-serif;
  background: var(--offwhite);
  color: var(--text);
  overflow-x: hidden;
}

/* ── NAVBAR ── */
nav {
  position: fixed; top:0; left:0; right:0; z-index:200;
  height: 68px;
  background: rgba(10,22,40,0.96);
  backdrop-filter: blur(12px);
  display: flex; align-items: center; justify-content: space-between;
  padding: 0 6%;
  border-bottom: 1px solid rgba(184,150,62,0.18);
}

.logo {
  font-family: 'Cormorant Garamond', serif;
  font-size: 1.55rem; font-weight: 700;
  color: #fff; letter-spacing: 0.3px;
}
.logo span { color: var(--gold); }

.nav-links { display:flex; gap:2.2rem; list-style:none; }
.nav-links a {
  color: rgba(255,255,255,0.68);
  text-decoration: none; font-size: 0.82rem;
  font-weight: 500; letter-spacing: 0.8px;
  text-transform: uppercase;
  transition: color .2s;
}
.nav-links a:hover { color: var(--gold); }

.nav-cta {
  background: var(--gold);
  color: var(--navy) !important;
  padding: 0.5rem 1.3rem !important;
  border-radius: 4px;
  font-weight: 700 !important;
  letter-spacing: 0.4px !important;
  transition: background .2s, transform .2s !important;
}
.nav-cta:hover { background: var(--gold-lt) !important; transform: translateY(-1px); }

/* ── HERO ── */
.hero {
  min-height: 100vh;
  background: var(--navy);
  display: flex; flex-direction: column; justify-content: center;
  padding: 68px 6% 0;
  position: relative; overflow: hidden;
}

.hero-bg {
  position: absolute; inset:0;
  background:
    radial-gradient(ellipse 70% 60% at 90% 50%, rgba(184,150,62,0.07) 0%, transparent 60%),
    radial-gradient(ellipse 50% 80% at -10% 60%, rgba(184,150,62,0.04) 0%, transparent 50%);
}

.hero-lines {
  position: absolute; inset:0;
  background-image:
    linear-gradient(rgba(184,150,62,0.04) 1px, transparent 1px),
    linear-gradient(90deg, rgba(184,150,62,0.04) 1px, transparent 1px);
  background-size: 72px 72px;
}

.hero-inner {
  position: relative; z-index:2;
  display: grid; grid-template-columns: 1fr 420px;
  gap: 4rem; align-items: center;
  padding-bottom: 5rem;
}

.hero-eyebrow {
  display: inline-flex; align-items: center; gap:.5rem;
  background: rgba(184,150,62,0.1);
  border: 1px solid rgba(184,150,62,0.28);
  color: var(--gold);
  padding: .38rem 1rem;
  border-radius: 50px;
  font-size: .75rem; font-weight: 600;
  letter-spacing: 1.2px; text-transform: uppercase;
  margin-bottom: 1.6rem;
  animation: rise .7s ease both;
}

.hero-eyebrow::before {
  content:''; width:6px; height:6px;
  background: var(--gold); border-radius:50%;
  animation: blink 2s infinite;
}
@keyframes blink { 0%,100%{opacity:1} 50%{opacity:.2} }

h1 {
  font-family: 'Cormorant Garamond', serif;
  font-size: clamp(2.8rem, 4.5vw, 4.2rem);
  color: #fff; line-height: 1.12;
  font-weight: 700; margin-bottom: 1.4rem;
  animation: rise .7s .15s ease both;
}

h1 em { font-style: italic; color: var(--gold); }

.hero-p {
  color: rgba(255,255,255,0.58);
  font-size: 1.05rem; line-height: 1.75;
  font-weight: 300; max-width: 500px;
  margin-bottom: 2.4rem;
  animation: rise .7s .3s ease both;
}

.hero-btns {
  display: flex; gap: 1rem;
  animation: rise .7s .45s ease both;
}

.btn-gold {
  background: var(--gold); color: var(--navy);
  padding: .85rem 2rem; border-radius: 5px;
  font-weight: 700; font-size: .95rem;
  text-decoration: none; border: none; cursor: pointer;
  transition: all .25s; letter-spacing:.2px;
  font-family: 'Outfit', sans-serif;
}
.btn-gold:hover {
  background: var(--gold-lt);
  transform: translateY(-2px);
  box-shadow: 0 8px 28px rgba(184,150,62,.35);
}

.btn-ghost {
  background: transparent; color: rgba(255,255,255,.8);
  padding: .85rem 2rem; border-radius: 5px;
  font-weight: 500; font-size: .95rem;
  text-decoration: none; cursor: pointer;
  border: 1.5px solid rgba(255,255,255,.2);
  transition: all .25s; font-family: 'Outfit', sans-serif;
}
.btn-ghost:hover { border-color: var(--gold); color: var(--gold); }

/* Hero card */
.hero-card {
  background: rgba(255,255,255,0.04);
  border: 1px solid rgba(184,150,62,0.2);
  border-radius: 16px; padding: 2rem;
  animation: rise .7s .55s ease both;
}

.hero-card-title {
  font-family: 'Cormorant Garamond', serif;
  color: rgba(255,255,255,.85); font-size: 1.1rem;
  font-weight: 600; margin-bottom: 1.2rem;
  padding-bottom: .8rem;
  border-bottom: 1px solid rgba(184,150,62,.15);
}

.hero-feat {
  display: flex; align-items: center; gap:.85rem;
  padding: .7rem 0;
  border-bottom: 1px solid rgba(255,255,255,.05);
  color: rgba(255,255,255,.6); font-size: .88rem;
}
.hero-feat:last-child { border-bottom:none; }

.hero-feat-icon {
  width:36px; height:36px; flex-shrink:0;
  background: rgba(184,150,62,.1);
  border-radius: 8px;
  display:flex; align-items:center; justify-content:center;
  font-size:1.1rem;
}

.hero-stats {
  display: flex; gap: 2.5rem;
  margin-top: 2rem; padding-top: 1.5rem;
  border-top: 1px solid rgba(184,150,62,.15);
}

.stat-n {
  font-family: 'Cormorant Garamond', serif;
  font-size: 2rem; font-weight: 700; color: var(--gold);
  display: block; line-height:1;
}
.stat-l {
  font-size:.72rem; color:rgba(255,255,255,.4);
  text-transform:uppercase; letter-spacing:.8px;
  margin-top:.2rem; display:block;
}

@keyframes rise {
  from { opacity:0; transform:translateY(24px); }
  to   { opacity:1; transform:translateY(0); }
}

/* ── SECTIONS ── */
section { padding: 100px 6%; }

.tag {
  font-size:.72rem; text-transform:uppercase;
  letter-spacing:2px; color:var(--gold);
  font-weight:600; margin-bottom:.6rem;
}

.sec-title {
  font-family: 'Cormorant Garamond', serif;
  font-size: clamp(1.9rem, 3vw, 2.8rem);
  color: var(--navy); line-height:1.2; margin-bottom:.75rem;
}

.bar {
  width:44px; height:3px; background:var(--gold);
  border-radius:2px; margin: .9rem 0 1.5rem;
}

.sec-sub {
  color:var(--gray); font-size:.97rem;
  line-height:1.75; max-width:500px;
}

/* ── SERVICES ── */
#servicos { background: var(--offwhite); }

.services-grid {
  display:grid;
  grid-template-columns: repeat(auto-fill, minmax(275px, 1fr));
  gap:1.4rem; margin-top:3.5rem;
}

.svc-card {
  background: var(--cream);
  border:1px solid rgba(10,22,40,.07);
  border-radius:12px; padding:1.8rem;
  transition: all .3s; position:relative; overflow:hidden;
}
.svc-card::before {
  content:'';
  position:absolute; left:0; top:0; bottom:0; width:3px;
  background: var(--gold); transform:scaleY(0);
  transform-origin:bottom; transition:transform .3s;
  border-radius:0 2px 2px 0;
}
.svc-card:hover { transform:translateY(-5px); box-shadow:0 18px 44px rgba(10,22,40,.1); border-color:rgba(184,150,62,.25); }
.svc-card:hover::before { transform:scaleY(1); }

.svc-icon {
  width:50px; height:50px; background:var(--navy);
  border-radius:10px; display:flex; align-items:center;
  justify-content:center; font-size:1.45rem;
  margin-bottom:1.1rem;
}

.svc-card h3 {
  font-family: 'Cormorant Garamond', serif;
  font-size:1.2rem; color:var(--navy);
  margin-bottom:.5rem; font-weight:700;
}

.svc-card p {
  color:var(--gray); font-size:.875rem;
  line-height:1.7; margin-bottom:1rem;
}

.svc-price {
  font-weight:600; color:var(--gold);
  font-size:.875rem;
}

/* ── TEAM ── */
#equipe { background:var(--cream); }

.team-grid {
  display:grid;
  grid-template-columns: repeat(5, 1fr);
  gap:1.2rem; margin-top:3.5rem;
}

.team-card {
  background:var(--offwhite);
  border:1px solid rgba(10,22,40,.07);
  border-radius:14px; padding:1.8rem 1.4rem;
  text-align:center; transition:all .3s;
}
.team-card:hover {
  transform:translateY(-5px);
  box-shadow:0 14px 36px rgba(10,22,40,.1);
  border-color:rgba(184,150,62,.3);
}

.avatar {
  width:72px; height:72px;
  background: linear-gradient(135deg, var(--navy), var(--navy2));
  border-radius:50%; margin:0 auto 1.1rem;
  display:flex; align-items:center; justify-content:center;
  font-family:'Cormorant Garamond',serif;
  font-size:1.6rem; font-weight:700; color:var(--gold);
  border:2.5px solid var(--gold);
}

.team-card h3 {
  font-family:'Cormorant Garamond',serif;
  font-size:1.05rem; color:var(--navy); margin-bottom:.25rem;
}

.team-role {
  color:var(--gold); font-size:.72rem;
  font-weight:600; text-transform:uppercase;
  letter-spacing:.7px; margin-bottom:1rem;
}

.skills { display:flex; flex-wrap:wrap; gap:.35rem; justify-content:center; }
.sk {
  background:var(--light); color:var(--navy);
  font-size:.7rem; padding:.22rem .6rem;
  border-radius:50px; font-weight:500;
}

/* ── WHY ── */
#vantagens { background:var(--offwhite); }

.why-grid {
  display:grid; grid-template-columns:repeat(3,1fr);
  gap:1.5rem; margin-top:3.5rem;
}

.why-card {
  padding:2rem 1.75rem;
  border-left:3px solid var(--gold);
  background:var(--cream); border-radius:0 12px 12px 0;
  transition:all .3s;
}
.why-card:hover { transform:translateX(4px); box-shadow:4px 8px 24px rgba(10,22,40,.08); }

.why-num {
  font-family:'Cormorant Garamond',serif;
  font-size:2.4rem; color:rgba(184,150,62,.2);
  font-weight:700; line-height:1; margin-bottom:.6rem;
}

.why-card h3 {
  font-family:'Cormorant Garamond',serif;
  font-size:1.1rem; color:var(--navy);
  margin-bottom:.5rem; font-weight:700;
}

.why-card p { color:var(--gray); font-size:.875rem; line-height:1.7; }

/* ── SCHEDULE ── */
#agendamento {
  background: var(--navy);
  position:relative; overflow:hidden;
}
#agendamento::before {
  content:'';
  position:absolute; inset:0;
  background:
    radial-gradient(ellipse 60% 60% at 5% 50%, rgba(184,150,62,.05) 0%, transparent 60%),
    radial-gradient(ellipse 40% 80% at 95% 40%, rgba(184,150,62,.04) 0%, transparent 60%);
}

#agendamento .tag { position:relative; z-index:1; }
#agendamento .sec-title { color:#fff; position:relative; z-index:1; }
#agendamento .sec-sub { color:rgba(255,255,255,.45); position:relative; z-index:1; }
#agendamento .bar { position:relative; z-index:1; }

.sched-wrap {
  display:grid; grid-template-columns:1fr 1.1fr;
  gap:4rem; align-items:start;
  margin-top:3.5rem; position:relative; z-index:1;
}

.sched-info h3 {
  font-family:'Cormorant Garamond',serif;
  color:#fff; font-size:1.4rem; margin-bottom:1.5rem;
}

.step-list { list-style:none; }

.step {
  display:flex; gap:1rem; padding:1rem 0;
  border-bottom:1px solid rgba(255,255,255,.06);
  align-items:flex-start;
}
.step:last-child { border-bottom:none; }

.step-icon {
  width:38px; height:38px; flex-shrink:0;
  background:rgba(184,150,62,.1);
  border:1px solid rgba(184,150,62,.2);
  border-radius:8px; display:flex;
  align-items:center; justify-content:center; font-size:1rem;
}

.step-txt strong {
  display:block; color:#fff; font-size:.9rem;
  margin-bottom:.2rem; font-weight:600;
}
.step-txt span { color:rgba(255,255,255,.5); font-size:.83rem; line-height:1.6; }

.form-box {
  background:rgba(255,255,255,.04);
  border:1px solid rgba(184,150,62,.18);
  border-radius:16px; padding:2.4rem;
}

.form-box-title {
  font-family:'Cormorant Garamond',serif;
  color:#fff; font-size:1.35rem; font-weight:600;
  margin-bottom:1.75rem; padding-bottom:1rem;
  border-bottom:1px solid rgba(184,150,62,.18);
}

.f-row { display:grid; grid-template-columns:1fr 1fr; gap:1rem; }

.fg { margin-bottom:1.15rem; }

.fg label {
  display:block; color:rgba(255,255,255,.5);
  font-size:.75rem; text-transform:uppercase;
  letter-spacing:.6px; margin-bottom:.45rem; font-weight:500;
}

.fg input, .fg select, .fg textarea {
  width:100%;
  background:rgba(255,255,255,.05);
  border:1px solid rgba(255,255,255,.1);
  color:#fff; padding:.72rem 1rem;
  border-radius:7px;
  font-family:'Outfit',sans-serif; font-size:.875rem;
  outline:none; transition:border .2s, background .2s;
  appearance:none;
}
.fg select option { background:#142238; }
.fg input:focus, .fg select:focus, .fg textarea:focus {
  border-color:var(--gold);
  background:rgba(184,150,62,.05);
}
.fg input::placeholder, .fg textarea::placeholder { color:rgba(255,255,255,.28); }
.fg textarea { resize:vertical; min-height:85px; }

.submit-btn {
  width:100%; background:var(--gold); color:var(--navy);
  border:none; padding:1rem;
  border-radius:7px; font-family:'Outfit',sans-serif;
  font-weight:700; font-size:1rem; cursor:pointer;
  transition:all .25s; margin-top:.4rem; letter-spacing:.2px;
}
.submit-btn:hover {
  background:var(--gold-lt);
  transform:translateY(-2px);
  box-shadow:0 8px 28px rgba(184,150,62,.32);
}

.success-box {
  display:none; margin-top:1rem;
  background:rgba(45,106,79,.15);
  border:1px solid rgba(45,106,79,.4);
  color:#86efac; padding:.9rem 1.1rem;
  border-radius:7px; font-size:.875rem;
  text-align:center; line-height:1.5;
}

/* ── FOOTER ── */
footer {
  background:var(--navy);
  border-top:1px solid rgba(184,150,62,.12);
  padding:2.5rem 6%;
  text-align:center;
  color:rgba(255,255,255,.4); font-size:.83rem;
}
.footer-logo {
  font-family:'Cormorant Garamond',serif;
  font-size:1.4rem; color:#fff; margin-bottom:.6rem;
}
.footer-logo span { color:var(--gold); }
footer p { margin:.3rem 0; }

/* ── RESPONSIVE ── */
@media(max-width:1100px) {
  .team-grid { grid-template-columns:repeat(3,1fr); }
}
@media(max-width:900px) {
  .hero-inner { grid-template-columns:1fr; }
  .hero-card { display:none; }
  .sched-wrap { grid-template-columns:1fr; }
  .why-grid { grid-template-columns:repeat(2,1fr); }
  .team-grid { grid-template-columns:repeat(2,1fr); }
  nav ul { display:none; }
}
@media(max-width:580px) {
  .why-grid, .team-grid { grid-template-columns:1fr; }
  .f-row { grid-template-columns:1fr; }
}
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="logo">Residência<span>Fix</span></div>
  <ul class="nav-links">
    <li><a href="#servicos">Serviços</a></li>
    <li><a href="#equipe">Equipe</a></li>
    <li><a href="#vantagens">Diferenciais</a></li>
    <li><a href="#agendamento" class="nav-cta">Agendar</a></li>
  </ul>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-bg"></div>
  <div class="hero-lines"></div>
  <div class="hero-inner">
    <div class="hero-left">
      <div class="hero-eyebrow">Serviços Domiciliares Profissionais</div>
      <h1>O seu lar merece cuidado de <em>verdade</em></h1>
      <p class="hero-p">
        Oferecemos serviços residenciais com profissionais qualificados,
        atendimento pontual, orçamento transparente e garantia em tudo que fazemos.
      </p>
      <div class="hero-btns">
        <a href="#agendamento" class="btn-gold">Agendar Visita</a>
        <a href="#servicos" class="btn-ghost">Ver Serviços</a>
      </div>
    </div>

    <div class="hero-card">
      <div class="hero-card-title">Por que escolher a ResidênciaFix?</div>
      <div class="hero-feat">
        <div class="hero-feat-icon">🛡️</div>
        <div>Garantia de 90 dias em todos os serviços realizados</div>
      </div>
      <div class="hero-feat">
        <div class="hero-feat-icon">⏱️</div>
        <div>Confirmação de agendamento em até 2 horas</div>
      </div>
      <div class="hero-feat">
        <div class="hero-feat-icon">📋</div>
        <div>Orçamento gratuito antes de qualquer execução</div>
      </div>
      <div class="hero-feat">
        <div class="hero-feat-icon">🏅</div>
        <div>Profissionais certificados e com experiência comprovada</div>
      </div>
      <div class="hero-feat">
        <div class="hero-feat-icon">💳</div>
        <div>Aceitamos cartão, PIX e pagamento parcelado</div>
      </div>
      <div class="hero-stats">
        <div class="stat">
          <span class="stat-n">500+</span>
          <span class="stat-l">Atendimentos</span>
        </div>
        <div class="stat">
          <span class="stat-n">5</span>
          <span class="stat-l">Especialistas</span>
        </div>
        <div class="stat">
          <span class="stat-n">98%</span>
          <span class="stat-l">Satisfação</span>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- SERVICES -->
<section id="servicos">
  <div class="tag">O que oferecemos</div>
  <h2 class="sec-title">Nossos Serviços</h2>
  <div class="bar"></div>
  <p class="sec-sub">Soluções completas para o dia a dia da sua residência, executadas com técnica, segurança e responsabilidade.</p>

  <div class="services-grid">
    <div class="svc-card">
      <div class="svc-icon">🚿</div>
      <h3>Troca de Chuveiro Elétrico</h3>
      <p>Instalação e substituição com adequação da fiação, teste de segurança e verificação da pressão da água.</p>
      <span class="svc-price">A partir de R$ 120,00</span>
    </div>
    <div class="svc-card">
      <div class="svc-icon">⚡</div>
      <h3>Reparo Elétrico Geral</h3>
      <p>Identificação de falhas, troca de tomadas, interruptores, disjuntores e revisão do quadro de distribuição.</p>
      <span class="svc-price">A partir de R$ 90,00</span>
    </div>
    <div class="svc-card">
      <div class="svc-icon">❄️</div>
      <h3>Instalação de Ar-Condicionado</h3>
      <p>Instalação, manutenção preventiva e higienização de aparelhos split e janela com garantia de funcionamento.</p>
      <span class="svc-price">A partir de R$ 250,00</span>
    </div>
    <div class="svc-card">
      <div class="svc-icon">🚰</div>
      <h3>Serviços Hidráulicos</h3>
      <p>Reparo de vazamentos, troca de torneiras, sifões, registros e instalação de aquecedores a gás ou elétrico.</p>
      <span class="svc-price">A partir de R$ 100,00</span>
    </div>
    <div class="svc-card">
      <div class="svc-icon">🪟</div>
      <h3>Instalação de Persianas</h3>
      <p>Medição, montagem e fixação de persianas, cortinas, rolôs e telas mosquiteiras com acabamento preciso.</p>
      <span class="svc-price">A partir de R$ 80,00</span>
    </div>
    <div class="svc-card">
      <div class="svc-icon">🔩</div>
      <h3>Montagem de Móveis</h3>
      <p>Montagem de móveis de todos os fabricantes: armários, estantes, camas, racks e escritórios completos.</p>
      <span class="svc-price">A partir de R$ 130,00</span>
    </div>
    <div class="svc-card">
      <div class="svc-icon">🎨</div>
      <h3>Pintura Residencial</h3>
      <p>Pintura interna e externa, massa corrida, textura, reparos de trincas e tratamento de infiltrações.</p>
      <span class="svc-price">A partir de R$ 200,00</span>
    </div>
    <div class="svc-card">
      <div class="svc-icon">🛁</div>
      <h3>Box e Acessórios de Banheiro</h3>
      <p>Instalação de box de vidro temperado, espelhos, prateleiras e acessórios com fixação nivelada e segura.</p>
      <span class="svc-price">A partir de R$ 150,00</span>
    </div>
    <div class="svc-card">
      <div class="svc-icon">📡</div>
      <h3>Câmeras e Sistema de Alarme</h3>
      <p>Instalação de câmeras de segurança, sensores de presença, centrais de alarme e interfones residenciais.</p>
      <span class="svc-price">A partir de R$ 180,00</span>
    </div>
  </div>
</section>

<!-- TEAM -->
<section id="equipe">
  <div class="tag">Quem executa</div>
  <h2 class="sec-title">Nossa Equipe</h2>
  <div class="bar"></div>
  <p class="sec-sub">Cinco profissionais especializados, selecionados e treinados para oferecer atendimento de alto padrão.</p>

  <div class="team-grid">
    <div class="team-card">
      <div class="avatar">1</div>
      <h3>Funcionário 1</h3>
      <div class="team-role">Especialista Elétrico</div>
      <div class="skills">
        <span class="sk">Instalações Elétricas</span>
   

