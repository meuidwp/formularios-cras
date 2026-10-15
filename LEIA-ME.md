# Formulários CRAS (PWA único)

Reúne os 9 formulários em um só aplicativo: menu lateral (gaveta no celular), cor própria de cada formulário e modo noturno geral.

- `index.html`: tela principal (menu, início, tema). Cada formulário abre em `forms/<nome>.html`.
- **Tema:** botão no topo alterna automático / escuro / claro e vale para todos os formulários (guardado em `localStorage`, chave `tema`).
- **Cores:** cada formulário mantém a cor original; a barra do topo muda para a cor do formulário aberto.
- Os formulários ficam abertos em segundo plano: trocar de menu não apaga o que foi digitado (fechar a página apaga).
- Nada é enviado a servidores.

## Publicar
Precisa de HTTPS (Netlify Drop, GitHub Pages, Cloudflare Pages): envie a pasta inteira. Teste local: `python3 -m http.server 8000`.
Ao atualizar, aumente `VERSION` em `sw.js`.

## Identificação Familiar
Formulário `forms/identificacao-familiar.html` (grupo **Atendimento**, cor verde). Gera a ficha de Identificação Familiar do CRAS em PDF (4 páginas, modelo da Prefeitura), tudo em caixa alta, pronta para imprimir e assinar. Preenche: atendimento e demanda, dados do responsável, programas sociais, renda e moradia, composição familiar (até 14 pessoas), rede de apoio, códigos de vulnerabilidade e técnico(a).
Enter passa para o próximo campo; máscaras automáticas para telefone, RG, CPF (avisa se o dígito verificador não bater), NIS, datas e valores.
Como os demais, ele fica embutido no `index.html` (variável `EMB`) e também existe solto em `forms/`. **Se editar `forms/identificacao-familiar.html`, o conteúdo embutido no `index.html` precisa ser regerado** para a mudança aparecer no app.
