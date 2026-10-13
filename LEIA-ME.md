# Formulários CRAS (PWA único)

Reúne os 8 formulários em um só aplicativo: menu lateral (gaveta no celular), cor própria de cada formulário e modo noturno geral.

- `index.html`: tela principal (menu, início, tema). Cada formulário abre em `forms/<nome>.html`.
- **Tema:** botão no topo alterna automático / escuro / claro e vale para todos os formulários (guardado em `localStorage`, chave `tema`).
- **Cores:** cada formulário mantém a cor original; a barra do topo muda para a cor do formulário aberto.
- Os formulários ficam abertos em segundo plano: trocar de menu não apaga o que foi digitado (fechar a página apaga).
- Nada é enviado a servidores.

## Publicar
Precisa de HTTPS (Netlify Drop, GitHub Pages, Cloudflare Pages): envie a pasta inteira. Teste local: `python3 -m http.server 8000`.
Ao atualizar, aumente `VERSION` em `sw.js`.
