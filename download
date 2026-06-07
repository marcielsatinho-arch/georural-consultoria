const botaoMenu = document.querySelector(".menu-mobile");
const menu = document.querySelector(".menu-principal");
const links = document.querySelectorAll(".menu-principal a");
const cursorLuz = document.querySelector(".cursor-luz");

function fecharMenu() {
    botaoMenu?.classList.remove("ativo");
    menu?.classList.remove("ativo");
    botaoMenu?.setAttribute("aria-expanded", "false");
    botaoMenu?.setAttribute("aria-label", "Abrir menu");
    document.body.classList.remove("menu-aberto");
}

botaoMenu?.addEventListener("click", () => {
    const aberto = menu.classList.toggle("ativo");
    botaoMenu.classList.toggle("ativo", aberto);
    botaoMenu.setAttribute("aria-expanded", String(aberto));
    botaoMenu.setAttribute("aria-label", aberto ? "Fechar menu" : "Abrir menu");
    document.body.classList.toggle("menu-aberto", aberto);
});

links.forEach(link => link.addEventListener("click", fecharMenu));
window.addEventListener("resize", () => {
    if (window.innerWidth > 1000) fecharMenu();
});

const observador = new IntersectionObserver((entradas) => {
    entradas.forEach((entrada) => {
        if (entrada.isIntersecting) {
            entrada.target.classList.add("visivel");
            observador.unobserve(entrada.target);
        }
    });
}, { threshold: 0.12 });

document.querySelectorAll(".revelar").forEach((elemento, indice) => {
    elemento.style.transitionDelay = `${Math.min(indice % 4, 3) * 70}ms`;
    observador.observe(elemento);
});

if (window.matchMedia("(pointer: fine)").matches && cursorLuz) {
    window.addEventListener("mousemove", (evento) => {
        cursorLuz.style.left = `${evento.clientX}px`;
        cursorLuz.style.top = `${evento.clientY}px`;
        cursorLuz.style.opacity = "1";
    });
    window.addEventListener("mouseleave", () => {
        cursorLuz.style.opacity = "0";
    });
}

// Digite o número oficial com código do país e DDD, somente números.
// Exemplo: 5575999999999
const numeroWhatsApp = "";
const formulario = document.querySelector("#formulario-contato");
const retorno = document.querySelector("#retorno-formulario");

formulario?.addEventListener("submit", async (evento) => {
    evento.preventDefault();

    if (!formulario.checkValidity()) {
        formulario.reportValidity();
        retorno.textContent = "Preencha os campos obrigatórios antes de continuar.";
        retorno.className = "retorno-formulario erro";
        return;
    }

    const dados = new FormData(formulario);
    const texto = [
        "Olá! Gostaria de solicitar atendimento da GeoRural Consultoria.",
        "",
        `Nome: ${dados.get("nome")}`,
        `Telefone: ${dados.get("telefone")}`,
        `E-mail: ${dados.get("email") || "Não informado"}`,
        `Serviço: ${dados.get("servico")}`,
        "",
        `Mensagem: ${dados.get("mensagem")}`
    ].join("\n");

    try {
        await navigator.clipboard.writeText(texto);
    } catch (_) {
        // Alguns navegadores bloqueiam a cópia automática; o WhatsApp ainda pode abrir.
    }

    if (numeroWhatsApp) {
        const link = `https://wa.me/${numeroWhatsApp}?text=${encodeURIComponent(texto)}`;
        window.open(link, "_blank", "noopener,noreferrer");
        retorno.textContent = "Mensagem preparada. O WhatsApp foi aberto em uma nova aba.";
    } else {
        retorno.textContent = "Mensagem copiada. Para abrir o WhatsApp automaticamente, adicione o número oficial no arquivo script.js.";
    }

    retorno.className = "retorno-formulario sucesso";
});
