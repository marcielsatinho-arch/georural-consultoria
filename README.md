@import url('https://fonts.googleapis.com/css2?family=DM+Sans:wght@400;500;600;700&family=Libre+Caslon+Display&display=swap');

:root {
    --verde-950: #10281a;
    --verde-900: #173322;
    --verde-800: #23462f;
    --verde-700: #315d3e;
    --verde-500: #7a9e68;
    --verde-200: #c9dac1;
    --verde-100: #eaf1e6;
    --areia: #f5f0e5;
    --areia-clara: #fbf9f3;
    --branco: #ffffff;
    --texto: #202820;
    --cinza: #667067;
    --linha: #dce4d9;
    --dourado: #cda969;
    --container: 1200px;
    --raio: 28px;
    --sombra: 0 30px 80px rgba(14, 40, 25, 0.14);
}

* {
    box-sizing: border-box;
}

html {
    scroll-behavior: smooth;
}

body {
    margin: 0;
    color: var(--texto);
    background: var(--areia-clara);
    font-family: "DM Sans", Arial, sans-serif;
    line-height: 1.6;
}

body.menu-aberto {
    overflow: hidden;
}

img {
    display: block;
    max-width: 100%;
}

a {
    color: inherit;
    text-decoration: none;
}

button,
input,
textarea,
select {
    font: inherit;
}

.container {
    width: min(calc(100% - 40px), var(--container));
    margin-inline: auto;
}

.cursor-luz {
    position: fixed;
    width: 320px;
    height: 320px;
    border-radius: 50%;
    pointer-events: none;
    z-index: 0;
    background: radial-gradient(circle, rgba(205, 169, 105, 0.11), transparent 68%);
    transform: translate(-50%, -50%);
    opacity: 0;
    transition: opacity .3s ease;
}

/* Cabeçalho */
.cabecalho {
    position: fixed;
    inset: 0 0 auto;
    z-index: 100;
    border-bottom: 1px solid rgba(255,255,255,.12);
    background: rgba(16, 40, 26, .78);
    backdrop-filter: blur(18px);
}

.barra {
    min-height: 82px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 30px;
}

.identidade {
    display: flex;
    align-items: center;
    gap: 13px;
    color: var(--branco);
}

.identidade img {
    width: 54px;
    height: 54px;
    border-radius: 15px;
    object-fit: cover;
    border: 1px solid rgba(255,255,255,.16);
}

.identidade span {
    display: grid;
    line-height: 1.05;
}

.identidade strong {
    font-family: "Libre Caslon Display", Georgia, serif;
    font-size: 1.35rem;
    letter-spacing: .02em;
}

.identidade small {
    margin-top: 6px;
    color: #c5d4c0;
    font-size: .67rem;
    font-weight: 700;
    letter-spacing: .2em;
    text-transform: uppercase;
}

.menu-principal {
    display: flex;
    align-items: center;
    gap: 28px;
    color: #dce8d8;
    font-size: .91rem;
    font-weight: 600;
}

.menu-principal a {
    transition: color .2s ease;
}

.menu-principal a:hover {
    color: var(--branco);
}

.link-destaque {
    padding: 11px 18px;
    border: 1px solid rgba(255,255,255,.3);
    border-radius: 999px;
}

.menu-mobile {
    display: none;
    width: 46px;
    height: 46px;
    padding: 13px;
    border: 1px solid rgba(255,255,255,.18);
    border-radius: 14px;
    background: rgba(255,255,255,.08);
}

.menu-mobile span {
    display: block;
    width: 100%;
    height: 2px;
    margin: 5px 0;
    background: var(--branco);
    transition: .25s ease;
}

/* Hero */
.hero {
    position: relative;
    overflow: hidden;
    min-height: 820px;
    display: flex;
    align-items: center;
    padding: 150px 0 90px;
    color: var(--branco);
    background:
        linear-gradient(115deg, rgba(7, 28, 15, .95), rgba(23, 51, 34, .87)),
        repeating-linear-gradient(45deg, rgba(255,255,255,.025) 0 1px, transparent 1px 14px);
}

.hero::before {
    content: "";
    position: absolute;
    inset: 0;
    opacity: .5;
    background:
        radial-gradient(circle at 77% 40%, rgba(122, 158, 104, .32), transparent 30%),
        radial-gradient(circle at 25% 85%, rgba(205, 169, 105, .18), transparent 24%);
}

.hero-forma {
    position: absolute;
    border: 1px solid rgba(255,255,255,.1);
    border-radius: 50%;
}

.hero-forma-1 {
    width: 620px;
    height: 620px;
    top: 100px;
    right: -210px;
}

.hero-forma-2 {
    width: 380px;
    height: 380px;
    left: -200px;
    bottom: -90px;
}

.hero-grid {
    position: relative;
    z-index: 2;
    display: grid;
    grid-template-columns: 1.13fr .87fr;
    align-items: center;
    gap: 90px;
}

.sobrelinha {
    margin: 0 0 18px;
    color: #d2dfcd;
    font-size: .75rem;
    font-weight: 700;
    letter-spacing: .2em;
    text-transform: uppercase;
}

.sobrelinha.escura {
    color: var(--verde-700);
}

h1,
h2 {
    margin: 0;
    font-family: "Libre Caslon Display", Georgia, serif;
    font-weight: 400;
    letter-spacing: -.03em;
    line-height: 1.04;
}

h1 {
    max-width: 770px;
    font-size: clamp(3.5rem, 6.8vw, 7.4rem);
}

.hero-descricao {
    max-width: 680px;
    margin: 30px 0 0;
    color: #c7d4c3;
    font-size: 1.12rem;
}

.hero-botoes {
    display: flex;
    flex-wrap: wrap;
    gap: 14px;
    margin-top: 38px;
}

.botao {
    min-height: 52px;
    display: inline-flex;
    align-items: center;
    justify-content: center;
    padding: 0 24px;
    border: 1px solid transparent;
    border-radius: 999px;
    font-weight: 700;
    cursor: pointer;
    transition: transform .2s ease, box-shadow .2s ease, background .2s ease;
}

.botao:hover {
    transform: translateY(-3px);
}

.botao-claro {
    background: var(--branco);
    color: var(--verde-950);
    box-shadow: 0 14px 36px rgba(0,0,0,.18);
}

.botao-transparente {
    border-color: rgba(255,255,255,.25);
    color: var(--branco);
    background: rgba(255,255,255,.05);
}

.botao-escuro {
    background: var(--verde-900);
    color: var(--branco);
}

.hero-numeros {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
    margin-top: 54px;
    padding-top: 28px;
    border-top: 1px solid rgba(255,255,255,.14);
}

.hero-numeros article {
    display: grid;
    gap: 4px;
}

.hero-numeros strong {
    font-size: .9rem;
}

.hero-numeros span {
    color: #aebdaa;
    font-size: .78rem;
    line-height: 1.45;
}

.hero-visual {
    position: relative;
    min-height: 550px;
    display: grid;
    place-items: center;
}

.quadro-logo {
    width: min(100%, 470px);
    border-radius: 34px;
    overflow: hidden;
    transform: rotate(2.5deg);
    box-shadow: 0 40px 100px rgba(0,0,0,.35);
    border: 10px solid rgba(255,255,255,.1);
}

.quadro-logo img {
    width: 100%;
}

.selo {
    position: absolute;
    z-index: 3;
    left: -30px;
    top: 36px;
    width: 170px;
    height: 170px;
    display: grid;
    place-content: center;
    padding: 28px;
    border-radius: 50%;
    color: var(--verde-950);
    background: var(--dourado);
    transform: rotate(-9deg);
    box-shadow: var(--sombra);
}

.selo span {
    font-size: .73rem;
    line-height: 1.3;
}

.selo strong {
    margin-top: 3px;
    font-family: "Libre Caslon Display", Georgia, serif;
    font-size: 1.28rem;
    line-height: 1.06;
}

.cartao-flutuante {
    position: absolute;
    z-index: 3;
    right: -20px;
    bottom: 55px;
    display: flex;
    align-items: center;
    gap: 13px;
    min-width: 250px;
    padding: 17px 20px;
    border: 1px solid rgba(255,255,255,.18);
    border-radius: 18px;
    background: rgba(255,255,255,.09);
    backdrop-filter: blur(18px);
    box-shadow: var(--sombra);
}

.ponto {
    width: 12px;
    height: 12px;
    border-radius: 50%;
    background: #92c47b;
    box-shadow: 0 0 0 7px rgba(146,196,123,.12);
}

.cartao-flutuante div {
    display: grid;
}

.cartao-flutuante small {
    color: #aebfaa;
}

.cartao-flutuante strong {
    font-size: .9rem;
}

/* Faixa */
.faixa-informativa {
    background: var(--dourado);
    color: var(--verde-950);
}

.faixa-informativa .container {
    min-height: 88px;
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    align-items: center;
}

.faixa-informativa span {
    padding: 8px 18px;
    text-align: center;
    border-right: 1px solid rgba(16,40,26,.22);
    font-size: .84rem;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: .06em;
}

.faixa-informativa span:last-child {
    border-right: 0;
}

/* Seções */
.secao {
    position: relative;
    padding: 120px 0;
}

.titulo-secao h2,
.cabecalho-servicos h2,
.processo h2,
.chamada h2,
.contato h2 {
    font-size: clamp(2.7rem, 5vw, 5.2rem);
}

.empresa {
    background: var(--areia-clara);
}

.empresa-grid {
    display: grid;
    grid-template-columns: .9fr 1.1fr;
    gap: 100px;
    align-items: start;
}

.empresa-conteudo > p {
    margin: 0 0 20px;
    color: var(--cinza);
    font-size: 1.08rem;
}

.empresa-pilares {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 14px;
    margin-top: 40px;
}

.empresa-pilares div {
    min-height: 145px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    padding: 22px;
    border: 1px solid var(--linha);
    border-radius: 20px;
    background: var(--branco);
}

.empresa-pilares span {
    color: var(--verde-500);
    font-size: .76rem;
    font-weight: 700;
}

.empresa-pilares strong {
    color: var(--verde-900);
    line-height: 1.3;
}

/* Serviços */
.servicos {
    color: var(--branco);
    background: var(--verde-950);
}

.cabecalho-servicos {
    display: grid;
    grid-template-columns: 1fr .62fr;
    gap: 80px;
    align-items: end;
}

.cabecalho-servicos p:last-child {
    margin: 0 0 8px;
    color: #afbeaa;
}

.grade-servicos {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    margin-top: 70px;
    border-top: 1px solid rgba(255,255,255,.14);
}

.servico-card {
    position: relative;
    min-height: 230px;
    display: grid;
    grid-template-columns: auto 1fr auto;
    gap: 24px;
    padding: 34px 30px;
    border-bottom: 1px solid rgba(255,255,255,.14);
    transition: background .25s ease;
}

.servico-card:nth-child(odd) {
    border-right: 1px solid rgba(255,255,255,.14);
}

.servico-card:hover {
    background: rgba(255,255,255,.05);
}

.servico-numero {
    color: var(--dourado);
    font-size: .77rem;
    font-weight: 700;
}

.servico-card h3 {
    margin: -3px 0 12px;
    font-family: "Libre Caslon Display", Georgia, serif;
    font-size: 1.65rem;
    font-weight: 400;
}

.servico-card p {
    margin: 0;
    color: #aebdaa;
    font-size: .93rem;
}

.seta {
    color: var(--dourado);
    font-size: 1.35rem;
}

/* Processo */
.processo {
    background: var(--areia);
}

.processo-grid {
    display: grid;
    grid-template-columns: .78fr 1.22fr;
    gap: 100px;
}

.processo-intro {
    position: sticky;
    top: 130px;
    align-self: start;
}

.processo-intro > p:not(.sobrelinha) {
    max-width: 510px;
    margin: 26px 0 0;
    color: var(--cinza);
}

.texto-link {
    display: inline-flex;
    align-items: center;
    gap: 12px;
    margin-top: 30px;
    color: var(--verde-800);
    font-weight: 700;
}

.texto-link span {
    font-size: 1.35rem;
}

.lista-etapas {
    border-top: 1px solid #cfd9ca;
}

.etapa {
    display: grid;
    grid-template-columns: 80px 1fr;
    gap: 24px;
    padding: 34px 0;
    border-bottom: 1px solid #cfd9ca;
}

.etapa > span {
    color: var(--verde-500);
    font-size: .82rem;
    font-weight: 700;
}

.etapa h3 {
    margin: -4px 0 9px;
    color: var(--verde-900);
    font-family: "Libre Caslon Display", Georgia, serif;
    font-size: 1.8rem;
    font-weight: 400;
}

.etapa p {
    margin: 0;
    color: var(--cinza);
}

/* Chamada */
.chamada {
    padding: 56px 0;
    background: var(--areia);
}

.chamada-caixa {
    min-height: 340px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 60px;
    padding: 60px;
    border-radius: 34px;
    color: var(--branco);
    background:
        linear-gradient(110deg, rgba(16,40,26,.97), rgba(49,93,62,.86)),
        radial-gradient(circle at 80% 20%, rgba(205,169,105,.24), transparent 40%);
    box-shadow: var(--sombra);
}

.chamada-caixa h2 {
    max-width: 780px;
}

/* Contato */
.contato {
    background: var(--branco);
}

.contato-grid {
    display: grid;
    grid-template-columns: .83fr 1.17fr;
    gap: 100px;
    align-items: start;
}

.contato-texto > p:not(.sobrelinha) {
    max-width: 520px;
    margin: 24px 0 0;
    color: var(--cinza);
}

.dados-contato {
    display: grid;
    gap: 18px;
    margin-top: 38px;
}

.dados-contato article {
    display: grid;
    gap: 3px;
    padding-left: 18px;
    border-left: 3px solid var(--dourado);
}

.dados-contato span {
    color: var(--cinza);
    font-size: .8rem;
}

.dados-contato strong {
    color: var(--verde-900);
}

.formulario {
    display: grid;
    gap: 18px;
    padding: 36px;
    border: 1px solid var(--linha);
    border-radius: 28px;
    background: var(--areia-clara);
    box-shadow: var(--sombra);
}

.linha-formulario {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 16px;
}

.formulario label {
    display: grid;
    gap: 8px;
    color: var(--verde-900);
    font-size: .83rem;
    font-weight: 700;
}

.formulario input,
.formulario select,
.formulario textarea {
    width: 100%;
    border: 1px solid var(--linha);
    border-radius: 13px;
    outline: 0;
    background: var(--branco);
    color: var(--texto);
    transition: border-color .2s ease, box-shadow .2s ease;
}

.formulario input,
.formulario select {
    height: 52px;
    padding: 0 14px;
}

.formulario textarea {
    min-height: 140px;
    padding: 14px;
    resize: vertical;
}

.formulario input:focus,
.formulario select:focus,
.formulario textarea:focus {
    border-color: var(--verde-500);
    box-shadow: 0 0 0 4px rgba(122,158,104,.14);
}

.formulario .botao {
    width: fit-content;
    margin-top: 4px;
}

.formulario small {
    color: var(--cinza);
}

.alerta {
    padding: 14px 16px;
    border-radius: 12px;
    font-size: .9rem;
    font-weight: 600;
}

.alerta.sucesso {
    color: #245432;
    background: #e7f4e8;
    border: 1px solid #c6e3ca;
}

.alerta.erro {
    color: #7c2f28;
    background: #f9e8e5;
    border: 1px solid #edc9c4;
}

/* Rodapé */
.rodape {
    padding: 48px 0;
    color: var(--branco);
    background: #0a1c10;
}

.rodape-grid {
    display: grid;
    grid-template-columns: 1fr auto;
    gap: 30px;
    align-items: center;
}

.rodape-marca {
    display: flex;
    align-items: center;
    gap: 15px;
}

.rodape-marca img {
    width: 64px;
    height: 64px;
    object-fit: cover;
    border-radius: 16px;
}

.rodape-marca div {
    display: grid;
}

.rodape-marca strong {
    font-family: "Libre Caslon Display", Georgia, serif;
    font-size: 1.2rem;
}

.rodape-marca span {
    color: #9eae9a;
    font-size: .82rem;
}

.rodape-menu {
    display: flex;
    gap: 22px;
    color: #c8d4c4;
    font-size: .86rem;
    font-weight: 600;
}

.rodape-grid > p {
    grid-column: 1 / -1;
    margin: 10px 0 0;
    padding-top: 24px;
    border-top: 1px solid rgba(255,255,255,.1);
    color: #7f8e7c;
    font-size: .78rem;
    text-align: center;
}

/* Animações */
.revelar {
    opacity: 0;
    transform: translateY(28px);
    transition: opacity .7s ease, transform .7s ease;
}

.revelar.visivel {
    opacity: 1;
    transform: translateY(0);
}

/* Responsividade */
@media (max-width: 1000px) {
    .menu-mobile {
        display: block;
    }

    .menu-principal {
        position: fixed;
        inset: 82px 0 auto;
        display: grid;
        gap: 0;
        padding: 22px 24px 28px;
        background: var(--verde-950);
        border-bottom: 1px solid rgba(255,255,255,.14);
        transform: translateY(-130%);
        opacity: 0;
        pointer-events: none;
        transition: .25s ease;
    }

    .menu-principal.ativo {
        transform: translateY(0);
        opacity: 1;
        pointer-events: auto;
    }

    .menu-principal a {
        padding: 14px 4px;
    }

    .link-destaque {
        margin-top: 8px;
        text-align: center;
    }

    .menu-mobile.ativo span:first-child {
        transform: translateY(3.5px) rotate(45deg);
    }

    .menu-mobile.ativo span:last-child {
        transform: translateY(-3.5px) rotate(-45deg);
    }

    .hero-grid,
    .empresa-grid,
    .processo-grid,
    .contato-grid {
        grid-template-columns: 1fr;
        gap: 56px;
    }

    .hero-visual {
        min-height: 500px;
    }

    .selo {
        left: 0;
    }

    .cartao-flutuante {
        right: 0;
    }

    .empresa-grid,
    .processo-grid,
    .contato-grid {
        gap: 45px;
    }

    .processo-intro {
        position: static;
    }

    .cabecalho-servicos {
        grid-template-columns: 1fr;
        gap: 25px;
    }
}

@media (max-width: 720px) {
    .container {
        width: min(calc(100% - 28px), var(--container));
    }

    .hero {
        min-height: auto;
        padding-top: 132px;
    }

    h1 {
        font-size: clamp(3rem, 15vw, 4.6rem);
    }

    .hero-botoes {
        display: grid;
    }

    .hero-botoes .botao {
        width: 100%;
    }

    .hero-numeros,
    .empresa-pilares,
    .faixa-informativa .container,
    .grade-servicos,
    .linha-formulario {
        grid-template-columns: 1fr;
    }

    .hero-numeros {
        gap: 18px;
    }

    .hero-visual {
        min-height: 430px;
    }

    .quadro-logo {
        width: 86%;
    }

    .selo {
        width: 135px;
        height: 135px;
        padding: 20px;
    }

    .selo strong {
        font-size: 1.05rem;
    }

    .cartao-flutuante {
        min-width: auto;
        max-width: 225px;
    }

    .faixa-informativa {
        padding: 14px 0;
    }

    .faixa-informativa .container {
        min-height: auto;
    }

    .faixa-informativa span {
        padding: 11px 8px;
        border-right: 0;
        border-bottom: 1px solid rgba(16,40,26,.2);
    }

    .faixa-informativa span:last-child {
        border-bottom: 0;
    }

    .secao {
        padding: 84px 0;
    }

    .servico-card {
        min-height: auto;
        grid-template-columns: auto 1fr;
        padding: 28px 10px;
    }

    .servico-card:nth-child(odd) {
        border-right: 0;
    }

    .servico-card .seta {
        display: none;
    }

    .chamada {
        padding: 30px 0;
    }

    .chamada-caixa {
        min-height: 380px;
        align-items: flex-start;
        flex-direction: column;
        padding: 34px 26px;
    }

    .formulario {
        padding: 24px;
    }

    .formulario .botao {
        width: 100%;
    }

    .rodape-grid {
        grid-template-columns: 1fr;
    }

    .rodape-menu {
        flex-wrap: wrap;
    }
}

@media (prefers-reduced-motion: reduce) {
    html {
        scroll-behavior: auto;
    }

    *,
    *::before,
    *::after {
        transition-duration: .01ms !important;
        animation-duration: .01ms !important;
    }

    .revelar {
        opacity: 1;
        transform: none;
    }
}

.retorno-formulario {
    min-height: 24px;
    margin: 0;
    font-size: .88rem;
    font-weight: 600;
}

.retorno-formulario.sucesso { color: #245432; }
.retorno-formulario.erro { color: #7c2f28; }
