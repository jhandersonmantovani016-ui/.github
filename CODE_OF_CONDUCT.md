<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Próximo Nível</title>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
}

html{
    scroll-behavior:smooth;
}

body{
    font-family:Arial, sans-serif;
    background:#050a14;
    color:#fff;
    line-height:1.5;
}

button,
input,
select{
    font:inherit;
}

button,
a{
    -webkit-tap-highlight-color:transparent;
}

header{
    position:fixed;
    top:0;
    left:0;
    width:100%;
    z-index:1000;
    background:rgba(5,10,20,.96);
    border-bottom:1px solid #14243a;
    backdrop-filter:blur(12px);
}

.navbar{
    max-width:1200px;
    height:72px;
    margin:auto;
    padding:0 20px;
    display:flex;
    align-items:center;
    justify-content:space-between;
}

.logo{
    font-size:23px;
    font-weight:900;
    letter-spacing:-1px;
}

.logo span{
    color:#1984ff;
}

.menu-btn{
    width:48px;
    height:48px;
    border:1px solid #23476e;
    border-radius:12px;
    background:#091525;
    color:#fff;
    cursor:pointer;
    font-size:28px;
}

.menu{
    position:fixed;
    top:72px;
    right:-100%;
    width:100%;
    max-width:450px;
    height:calc(100vh - 72px);
    padding:24px;
    background:#07101e;
    border-left:1px solid #23476e;
    z-index:999;
    transition:.35s ease;
    overflow-y:auto;
}

.menu.open{
    right:0;
}

.menu-top{
    display:flex;
    align-items:center;
    justify-content:space-between;
    margin-bottom:20px;
}

.close-btn{
    width:45px;
    height:45px;
    border:0;
    background:none;
    color:#fff;
    font-size:32px;
    cursor:pointer;
}

.menu-list{
    list-style:none;
    border:1px solid #23476e;
    border-radius:14px;
    overflow:hidden;
}

.menu-list li{
    border-bottom:1px solid #193653;
}

.menu-list li:last-child{
    border-bottom:0;
}

.menu-list a{
    display:block;
    padding:18px;
    color:#fff;
    text-decoration:none;
}

.menu-list a:hover{
    background:#0d2847;
}

.hero{
    min-height:100vh;
    padding:130px 20px 70px;
    display:flex;
    align-items:center;
    justify-content:center;
    text-align:center;
    background:
    radial-gradient(circle at center,
    rgba(25,132,255,.20),
    transparent 55%);
}

.hero-content{
    max-width:850px;
}

.badge{
    display:inline-block;
    padding:8px 15px;
    border:1px solid #1d5ca4;
    border-radius:50px;
    color:#62aaff;
    font-size:13px;
    margin-bottom:22px;
}

.hero h1{
    font-size:clamp(45px,8vw,82px);
    line-height:1;
    letter-spacing:-4px;
}

.hero h1 span{
    display:block;
    color:#1984ff;
}

.hero p{
    max-width:650px;
    margin:25px auto;
    color:#9ba9bc;
    font-size:18px;
}

.buttons{
    display:flex;
    justify-content:center;
    gap:12px;
    flex-wrap:wrap;
}

.btn{
    border:0;
    padding:15px 22px;
    border-radius:11px;
    background:#1984ff;
    color:#fff;
    text-decoration:none;
    font-weight:800;
    cursor:pointer;
}

.btn:hover{
    transform:translateY(-2px);
    box-shadow:0 10px 30px rgba(25,132,255,.25);
}

.btn-outline{
    padding:14px 22px;
    border:1px solid #1984ff;
    border-radius:11px;
    color:#fff;
    text-decoration:none;
    font-weight:700;
}

section{
    padding:80px 20px;
}

.container{
    max-width:1100px;
    margin:auto;
}

.title{
    margin-bottom:35px;
}

.title small{
    color:#1984ff;
    font-weight:900;
}

.title h2{
    margin-top:7px;
    font-size:38px;
}

.title p{
    margin-top:8px;
    color:#8997aa;
}

.cards{
    display:grid;
    grid-template-columns:repeat(4,1fr);
    gap:16px;
}

.card{
    padding:25px;
    background:#071426;
    border:1px solid #153a61;
    border-radius:16px;
}

.card:hover{
    border-color:#1984ff;
}

.icon{
    font-size:38px;
    margin-bottom:15px;
}

.card p{
    color:#9aa8ba;
    margin-top:8px;
}

.dashboard{
    display:grid;
    grid-template-columns:1fr 1fr;
    gap:18px;
}

.panel{
    background:#071426;
    border:1px solid #153a61;
    border-radius:16px;
    padding:25px;
}

.panel h3{
    margin-bottom:15px;
}

.big-number{
    font-size:42px;
    font-weight:900;
    color:#1984ff;
}

.muted{
    color:#8f9db0;
}

.progress{
    height:11px;
    background:#172337;
    border-radius:20px;
    overflow:hidden;
    margin-top:10px;
}

.progress-fill{
    height:100%;
    background:#1984ff;
    border-radius:20px;
    transition:.5s;
}

.progress-row{
    margin-bottom:20px;
}

.progress-head{
    display:flex;
    justify-content:space-between;
}

.goal-grid{
    display:grid;
    grid-template-columns:repeat(2,1fr);
    gap:18px;
}

.goal-card{
    background:#071426;
    border:1px solid #153a61;
    border-radius:17px;
    padding:23px;
    position:relative;
}

.goal-card h3{
    margin-bottom:6px;
}

.goal-type{
    color:#1984ff;
    font-size:12px;
    font-weight:900;
    text-transform:uppercase;
}

.goal-status{
    display:inline-flex;
    align-items:center;
    gap:6px;
    padding:7px 10px;
    border-radius:20px;
    background:#101d2e;
    margin:12px 0;
    font-size:13px;
}

.goal-status.done{
    color:#6ee7a0;
}

.goal-status.pending{
    color:#ffd166;
}

.goal-status.late{
    color:#ff8b8b;
}

.goal-actions{
    display:flex;
    gap:8px;
    flex-wrap:wrap;
    margin-top:18px;
}

.small-btn{
    border:1px solid #275276;
    background:#0a192b;
    color:#fff;
    border-radius:9px;
    padding:9px 12px;
    cursor:pointer;
}

.small-btn.primary{
    background:#1984ff;
    border-color:#1984ff;
}

.small-btn.danger{
    border-color:#703737;
}

.form-box{
    background:#071426;
    border:1px solid #153a61;
    border-radius:17px;
    padding:25px;
    margin-bottom:20px;
}

.form-grid{
    display:grid;
    grid-template-columns:repeat(2,1fr);
    gap:13px;
}

.field{
    display:flex;
    flex-direction:column;
    gap:7px;
}

.field label{
    color:#aeb9c9;
    font-size:14px;
}

.field input,
.field select{
    width:100%;
    padding:13px;
    border:1px solid #284b70;
    border-radius:10px;
    background:#0a1829;
    color:#fff;
    outline:none;
}

.field input:focus,
.field select:focus{
    border-color:#1984ff;
}

.form-actions{
    margin-top:18px;
    display:flex;
    gap:10px;
    flex-wrap:wrap;
}

.articles{
    display:grid;
    grid-template-columns:repeat(4,1fr);
    gap:16px;
}

.article{
    overflow:hidden;
    background:#071426;
    border:1px solid #153a61;
    border-radius:15px;
}

.article img{
    width:100%;
    height:145px;
    object-fit:cover;
}

.article-content{
    padding:18px;
}

.category{
    color:#1984ff;
    font-size:11px;
    font-weight:900;
}

.article h3{
    margin:8px 0 12px;
}

.challenge{
    background:#071426;
    border:1px solid #153a61;
    border-radius:17px;
    padding:25px;
}

.challenge-days{
    display:grid;
    grid-template-columns:repeat(7,1fr);
    gap:10px;
    margin-top:20px;
}

.day{
    min-height:65px;
    display:flex;
    align-items:center;
    justify-content:center;
    text-align:center;
    background:#0a1829;
    border:1px solid #284b70;
    border-radius:11px;
    cursor:pointer;
}

.day.done{
    background:#0f4f36;
    border-color:#3cbb7a;
}

.empty{
    text-align:center;
    padding:35px 20px;
    color:#8290a3;
    border:1px dashed #284b70;
    border-radius:14px;
}

.modal{
    display:none;
    position:fixed;
    inset:0;
    z-index:3000;
    background:rgba(0,0,0,.78);
    padding:20px;
    align-items:center;
    justify-content:center;
}

.modal.show{
    display:flex;
}

.modal-box{
    width:100%;
    max-width:560px;
    max-height:90vh;
    overflow:auto;
    padding:28px;
    background:#071426;
    border:1px solid #24527c;
    border-radius:18px;
}

.modal-top{
    display:flex;
    justify-content:space-between;
    align-items:center;
    gap:20px;
}

.modal-close{
    border:0;
    background:none;
    color:#fff;
    font-size:30px;
    cursor:pointer;
}

.modal-box p{
    color:#a3afbf;
    margin:15px 0;
}

footer{
    padding:40px 20px;
    text-align:center;
    color:#66758a;
    border-top:1px solid #14243a;
}

@media(max-width:850px){

    .cards,
    .articles{
        grid-template-columns:repeat(2,1fr);
    }

    .dashboard,
    .goal-grid{
        grid-template-columns:1fr;
    }
}

@media(max-width:600px){

    .cards,
    .articles,
    .form-grid{
        grid-template-columns:1fr;
    }

    .hero h1{
        font-size:49px;
    }

    .title h2{
        font-size:32px;
    }

    .challenge-days{
        grid-template-columns:repeat(4,1fr);
    }
}
</style>
</head>

<body>

<header>

<div class="navbar">

<div class="logo">
PRÓXIMO<span>NÍVEL</span>
</div>

<button
class="menu-btn"
id="menuBtn"
aria-label="Abrir menu"
>
☰
</button>

</div>

</header>


<nav class="menu" id="menu" aria-label="Menu principal">

<div class="menu-top">

<h2>Menu</h2>

<button
class="close-btn"
id="closeBtn"
aria-label="Fechar menu"
>
×
</button>

</div>

<ul class="menu-list">

<li><a href="#inicio">🏠 Início</a></li>
<li><a href="#areas">📚 Áreas</a></li>
<li><a href="#conteudos">▶️ Conteúdos</a></li>
<li><a href="#metas">🎯 Metas</a></li>
<li><a href="#progresso">📈 Progresso</a></li>
<li><a href="#desafio">🔥 Desafio</a></li>

</ul>

</nav>


<section class="hero" id="inicio">

<div class="hero-content">

<div class="badge">
🚀 EVOLUA UM DIA DE CADA VEZ
</div>

<h1>
Sua próxima versão
<span>começa hoje.</span>
</h1>

<p>
Conhecimento, disciplina e atitude para
construir uma vida melhor, um passo de cada vez.
</p>

<div class="buttons">

<a href="#metas" class="btn">
COMEÇAR AGORA →
</a>

<a href="#conteudos" class="btn-outline">
EXPLORAR CONTEÚDOS
</a>

</div>

</div>

</section>


<section id="areas">

<div class="container">

<div class="title">

<small>EXPLORE</small>

<h2>Escolha uma área</h2>

<p>
Organize diferentes partes da sua vida em um só lugar.
</p>

</div>

<div class="cards">

<div class="card">
<div class="icon">💰</div>
<h3>Finanças</h3>
<p>Metas de dinheiro, contas e planejamento.</p>
</div>

<div class="card">
<div class="icon">🏋️</div>
<h3>Academia</h3>
<p>Treinos, exercícios e evolução.</p>
</div>

<div class="card">
<div class="icon">📚</div>
<h3>Estudos</h3>
<p>Matérias, tarefas e progresso.</p>
</div>

<div class="card">
<div class="icon">🧠</div>
<h3>Hábitos</h3>
<p>Construa uma rotina melhor.</p>
</div>

</div>

</div>

</section>


<section id="metas">

<div class="container">

<div class="title">

<small>PERSONALIZE</small>

<h2>🎯 Minhas Metas</h2>

<p>
Crie uma meta e deixe o sistema acompanhar sua evolução.
</p>

</div>


<div class="form-box">

<h3>Nova meta</h3>

<div class="form-grid">

<div class="field">

<label for="goalName">
O que você quer alcançar?
</label>

<input
id="goalName"
type="text"
placeholder="Ex: Guardar dinheiro"
>

</div>


<div class="field">

<label for="goalType">
Tipo
</label>

<select id="goalType">

<option value="financeiro">
💰 Financeiro
</option>

<option value="academia">
🏋️ Academia
</option>

<option value="estudos">
📚 Estudos
</option>

<option value="habitos">
🧠 Hábitos
</option>

<option value="outro">
🎯 Outro
</option>

</select>

</div>


<div class="field">

<label for="goalTarget">
Meta total
</label>

<input
id="goalTarget"
type="number"
min="0"
step="0.01"
placeholder="Ex: 1000"
>

</div>


<div class="field">

<label for="goalCurrent">
Quanto já foi realizado?
</label>

<input
id="goalCurrent"
type="number"
min="0"
step="0.01"
placeholder="Ex: 250"
>

</div>

</div>


<div class="form-actions">

<button
class="btn"
onclick="criarMeta()"
>
＋ Criar Meta
</button>

<button
class="small-btn"
onclick="limparFormulario()"
>
Limpar
</button>

</div>

</div>


<div id="goalList" class="goal-grid"></div>

</div>

</section>


<section id="progresso">

<div class="container">

<div class="title">

<small>VISÃO GERAL</small>

<h2>📈 Seu Progresso</h2>

<p>
Veja o que já foi feito e o que ainda falta.
</p>

</div>


<div class="dashboard">

<div class="panel">

<h3>Metas concluídas</h3>

<div
class="big-number"
id="completedCount"
>
0
</div>

<span class="muted">
metas finalizadas
</span>

</div>


<div class="panel">

<h3>Progresso geral</h3>

<div
class="big-number"
id="generalPercent"
>
0%
</div>

<div class="progress">

<div
class="progress-fill"
id="generalBar"
style="width:0%"
></div>

</div>

</div>

</div>

<br>

<div class="panel">

<div class="progress-row">

<div class="progress-head">
<span>💰 Finanças</span>
<strong id="financeProgress">0%</strong>
</div>

<div class="progress">
<div
class="progress-fill"
id="financeBar"
style="width:0%"
></div>
</div>

</div>


<div class="progress-row">

<div class="progress-head">
<span>🏋️ Academia</span>
<strong id="gymProgress">0%</strong>
</div>

<div class="progress">
<div
class="progress-fill"
id="gymBar"
style="width:0%"
></div>
</div>

</div>


<div class="progress-row">

<div class="progress-head">
<span>📚 Estudos</span>
<strong id="studyProgress">0%</strong>
</div>

<div class="progress">
<div
class="progress-fill"
id="studyBar"
style="width:0%"
></div>
</div>

</div>


<div class="progress-row">

<div class="progress-head">
<span>🧠 Hábitos</span>
<strong id="habitProgress">0%</strong>
</div>

<div class="progress">
<div
class="progress-fill"
id="habitBar"
style="width:0%"
></div>
</div>

</div>

</div>

</div>

</section>


<section id="conteudos">

<div class="container">

<div class="title">

<small>APRENDA</small>

<h2>📚 Conteúdos</h2>

<p>
Conhecimento para ajudar na sua evolução.
</p>

</div>


<div class="articles">

<div class="article">

<img
src="https://images.unsplash.com/photo-1554224155-6726b3ff858f?auto=format&fit=crop&w=600&q=80"
alt=""
>

<div class="article-content">

<div class="category">
FINANÇAS
</div>

<h3>
Como organizar seu primeiro salário
</h3>

<button
class="small-btn primary"
onclick="abrirConteudo(
'Como organizar seu primeiro salário',
'Comece entendendo quanto entra, quanto sai e quais são suas prioridades. Separe despesas essenciais, objetivos e uma margem para imprevistos. O mais importante é acompanhar o dinheiro regularmente.'
)"
>
Ler conteúdo →
</button>

</div>

</div>


<div class="article">

<img
src="https://images.unsplash.com/photo-1517836357463-d25dfeac3438?auto=format&fit=crop&w=600&q=80"
alt=""
>

<div class="article-content">

<div class="category">
ACADEMIA
</div>

<h3>
Como manter consistência nos treinos
</h3>

<button
class="small-btn primary"
onclick="abrirConteudo(
'Como manter consistência nos treinos',
'Escolha uma rotina que caiba na sua realidade. Registre os exercícios, mantenha uma progressão gradual e dê atenção à recuperação. Consistência ao longo do tempo é mais importante do que tentar fazer tudo de uma vez.'
)"
>
Ler conteúdo →
</button>

</div>

</div>


<div class="article">

<img
src="https://images.unsplash.com/photo-1497366811353-6870744d04b2?auto=format&fit=crop&w=600&q=80"
alt=""
>

<div class="article-content">

<div class="category">
CARREIRA
</div>

<h3>
Como desenvolver sua carreira
</h3>

<button
class="small-btn primary"
onclick="abrirConteudo(
'Como desenvolver sua carreira',
'Identifique as habilidades que você já possui e as que precisa desenvolver. Faça cursos, pratique e registre suas conquistas. Ter clareza sobre seu próximo passo ajuda a transformar aprendizado em ação.'
)"
>
Ler conteúdo →
</button>

</div>

</div>


<div class="article">

<img
src="https://images.unsplash.com/photo-1477959858617-67f85cf4f1df?auto=format&fit=crop&w=600&q=80"
alt=""
>

<div class="article-content">

<div class="category">
VIDA
</div>

<h3>
Construindo uma rotina melhor
</h3>

<button
class="small-btn primary"
onclick="abrirConteudo(
'Construindo uma rotina melhor',
'Escolha poucas mudanças de cada vez. Defina horários, organize suas tarefas e acompanhe o que conseguiu cumprir. Uma rotina sustentável é construída gradualmente.'
)"
>
Ler conteúdo →
</button>

</div>

</div>

</div>

</div>

</section>


<section id="desafio">

<div class="container">

<div class="title">

<small>CONSTÂNCIA</small>

<h2>🔥 Desafio de 7 dias</h2>

<p>
Complete um dia por vez.
</p>

</div>


<div class="challenge">

<h3>Seu desafio</h3>

<p class="muted">
Clique em um dia quando concluir sua atividade.
</p>

<div
class="challenge-days"
id="challengeDays"
></div>

</div>

</div>

</section>


<section>

<div class="container">

<div class="panel">

<h2>
🚀 Continue avançando
</h2>

<p class="muted" style="margin:12px 0 20px;">
Não precisa fazer tudo de uma vez.
Escolha uma pequena ação e continue.
</p>

<a href="#metas" class="btn">
CRIAR UMA META
</a>

</div>

</div>

</section>


<footer>

<div class="logo">
PRÓXIMO<span>NÍVEL</span>
</div>

<p>
Evolua. Aprenda. Construa.
</p>

<br>

<p>
© 2026 Próximo Nível
</p>

</footer>


<div
class="modal"
id="modal"
role="dialog"
aria-modal="true"
>

<div class="modal-box">

<div class="modal-top">

<h2 id="modalTitle"></h2>

<button
class="modal-close"
onclick="fecharConteudo()"
aria-label="Fechar"
>
×
</button>

</div>

<p id="modalText"></p>

<button
class="btn"
onclick="fecharConteudo()"
>
Entendi ✓
</button>

</div>

</div>


<script>

/* =========================
   MENU
========================= */

const menu =
document.getElementById("menu");

const menuBtn =
document.getElementById("menuBtn");

const closeBtn =
document.getElementById("closeBtn");

menuBtn.addEventListener("click", () => {

    menu.classList.add("open");

    menuBtn.setAttribute(
        "aria-label",
        "Fechar menu"
    );

    menuBtn.innerHTML = "×";

});

closeBtn.addEventListener("click", fecharMenu);

function fecharMenu(){

    menu.classList.remove("open");

    menuBtn.setAttribute(
        "aria-label",
        "Abrir menu"
    );

    menuBtn.innerHTML = "☰";

}

document.querySelectorAll(".menu a").forEach(link => {

    link.addEventListener(
        "click",
        fecharMenu
    );

});

document.addEventListener("keydown", event => {

    if(event.key === "Escape"){

        fecharMenu();

        fecharConteudo();

    }

});


/* =========================
   DADOS
========================= */

let metas =
JSON.parse(
    localStorage.getItem("pn_metas")
) || [];

let desafio =
JSON.parse(
    localStorage.getItem("pn_desafio")
) || [
    false,
    false,
    false,
    false,
    false,
    false,
    false
];


/* =========================
   CRIAR META
========================= */

function criarMeta(){

    const nome =
    document.getElementById("goalName")
    .value.trim();

    const tipo =
    document.getElementById("goalType")
    .value;

    const alvo =
    Number(
        document.getElementById("goalTarget")
        .value
    );

    const atual =
    Number(
        document.getElementById("goalCurrent")
        .value
    ) || 0;


    if(!nome){

        alert("Digite o nome da sua meta.");

        return;

    }

    if(alvo <= 0){

        alert("Digite um valor maior que zero para a meta.");

        return;

    }

    if(atual < 0 || atual > alvo){

        alert(
            "O progresso atual precisa estar entre 0 e a meta total."
        );

        return;

    }


    metas.push({

        id:Date.now(),

        nome:nome,

        tipo:tipo,

        alvo:alvo,

        atual:atual,

        criada:new Date().toLocaleDateString("pt-BR")

    });


    salvarMetas();

    limparFormulario();

    renderizarMetas();

}


/* =========================
   SALVAR
========================= */

function salvarMetas(){

    localStorage.setItem(
        "pn_metas",
        JSON.stringify(metas)
    );

}


/* =========================
   RENDERIZAR METAS
========================= */

function renderizarMetas(){

    const lista =
    document.getElementById("goalList");

    lista.innerHTML = "";


    if(metas.length === 0){

        lista.innerHTML = `
        <div class="empty">
            🎯 Você ainda não criou nenhuma meta.<br>
            Comece com uma pequena meta.
        </div>python3 -m http.server 8080
  
