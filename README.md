# Tulhia, design system

Tulhia é um produto para o produtor rural: mostra quanto ele deve, quando cada parcela vence e em que mês o caixa da fazenda aperta, com um consultor responsável pela fazenda. O nome vem de tulha, o depósito onde a colheita é guardada, mais IA. Caixa e dívidas da fazenda, com consultor.

Este repositório reúne tudo o que uma pessoa (ou o Claude Design) precisa para desenhar a Tulhia: conceito, marca atual, tokens, tipografia, fotos, telas do app, a landing page no ar e a mensagem. O prompt pronto para o Claude Design está em `CLAUDE-DESIGN-PROMPT.md`.

Landing page no ar: https://tulhia.vercel.app (pré-lançamento, sem indexação).

## 1. O produto, em uma tela

- Promessa: "Quanto você deve, quando vence e em que mês o caixa aperta."
- Três provas: 12 meses de caixa à frente · 15 dias para ter tudo organizado · 1 página com tudo.
- O que o produtor recebe: calendário de dívidas; caixa dos próximos 12 meses; resumo do mês no WhatsApp; dois avisos antes do aperto.
- Como funciona (3 passos): manda a cédula (PDF) · autoriza o banco só para ver (Open Finance) · o consultor fecha o mês com ele.
- Confiança: acesso ao banco só para ver, sem digitar extrato, um consultor responsável pela fazenda.
- Para quem: produtor médio e grande (soja, milho, gado), que decide pelo WhatsApp e não quer planilha. Não é para quem quer fazer sozinho ou quer só um aplicativo de banco.
- Chamada à ação: WhatsApp ("Quero conhecer a Tulhia").

A mensagem completa está em `conteudo/mensagem.md` e o texto integral em `landing/index.html`.

## 2. Público e tom

Produtor rural próspero, 45 a 65 anos, fazenda estruturada (silos, frota, funcionários), decide rápido, por conversa, com quem confia. Odeia planilha e aplicativo que pede digitação. O consultor é a pessoa de confiança; o sistema é a ferramenta do consultor.

Tom: direto, adulto, sem jargão de fintech, sem promessa de "transformar". Sentence case nos títulos. Número antes de prosa. Nada de travessão, nada de emoji, nada de "revolucionar". Fala com "você".

## 3. Marca atual (versão 1, 05/10/2026)

Conceito: a tulha guarda a safra; a Tulhia guarda o caixa.

Símbolo: três silos que sobem da esquerda para a direita, lidos de uma vez como o gráfico de caixa dos próximos 12 meses (que é o que o produto mostra). O silo mais alto, em ocre, é o mês da safra, quando o dinheiro entra. Sobre fundo escuro, os silos ficam em papel e o acento em ocre claro.

Nome: "Tulhia" em Bricolage Grotesque 800, entreletras -0,03em, T maiúsculo e o resto minúsculo.

Arquivos em `marca/`: `tulhia-simbolo.svg` (cores fixas), `favicon.svg`, `icone-app-512.png`, `apple-touch-icon.png`, `avatar-whatsapp-1024.png`, `folha-da-marca.html` (abrir no navegador: assinaturas, cores, tipografia, regras). Em `marca/conceitos/` estão os quatro caminhos explorados (silos como gráfico, tulha como cofre, monograma T, selo); o primeiro foi o escolhido.

Esta marca é um ponto de partida, não uma amarra: quem redesenhar tem liberdade para propor outra, desde que o conceito (o caixa da fazenda guardado, visível mês a mês) continue reconhecível.

## 4. Tokens

`tokens/tokens.css` (como está na landing) e `tokens/tokens.json` (com o papel de cada cor).

Cores: papel #F3EEE4 (fundo) · terra #1B1914 (texto) · cinza #5B574E (secundário) · verde tulha #1F4A3A (principal) · verde escuro #12332A · verde claro #2C6A51 · verde fundo #E3EBE4 (faixas) · areia #DED3BF e linha #D8CDB8 (separação) · ocre safra #C47A2C (um acento por tela) · ocre claro #E9B86B (acento sobre escuro) · vermelho #A8392D e fundo #F7E6E2 (alerta).

Regra de cor: um acento vibrante por tela; o ocre nunca cobre área grande; verde escuro é o único fundo escuro além do terra.

Tipografia: Bricolage Grotesque (500 a 800) para nome, títulos e números grandes; Hanken Grotesk (400 a 700) para texto, botões e telas. Escala em px: 14, 16, 18, 20, 24, 32, 40, 52. Corpo nunca abaixo de 16 px no celular. Arquivos em `fontes/`.

Espaço e forma: grade de 4/8 px, gutter 20 px, largura máxima 1180 px, 48 a 96 px entre seções; cartão com raio 14 px, botão 12 px; sem sombra pesada, separação por fundo e linha. Movimento de 150 a 300 ms, respeitando `prefers-reduced-motion`.

## 5. Componentes da landing atual

Cabeçalho fixo (símbolo + nome + botão) · hero com foto (4:3 no celular) e lista de confiança · faixa de três números · citações do produtor (blockquote) com foto · cartões "O que você recebe" · seção escura de dívidas com tela do app e dois cartões · seção de caixa com a tela dos 12 meses e alerta · três passos numerados com ícones (Lucide) · seção do consultor com foto e tela do resumo no WhatsApp · seção escura de segurança (lista com ícones) · "É para quem / Não é para quem" · FAQ com `details` · chamada final sobre foto com véu · barra fixa de CTA no celular · rodapé com LGPD e "Produto em pré-lançamento".

## 6. Fotos e telas

`fotos/`: sete fotos documentais (produtor próspero, silos, varanda, mesa de escritório, pôr do sol), geradas para a marca, sem direitos de terceiros. Regra: gente de verdade no enquadramento, luz natural, nada com cara de banco de imagem. Rejeitado no caminho: página "com cara de IA", sem humano; foto de produtor "pé-rapado"; stock genérico.

`telas-app/`: quatro telas reais do app (resumo de dívidas, caixa de 12 meses, cronograma lido da cédula, resumo no WhatsApp). São o produto; podem ser redesenhadas junto com o sistema, mas o conteúdo delas é real.

## 7. Como usar no Claude Design

1. Abra o Claude Design e cole o conteúdo de `CLAUDE-DESIGN-PROMPT.md`.
2. Aponte este repositório (ou anexe `README.md`, `tokens/`, `marca/`, `fotos/` e `landing/index.html`).
3. Peça primeiro as direções de identidade; escolha uma; só então peça a landing completa dentro do design system.

## 8. Mapa de arquivos

- `CLAUDE-DESIGN-PROMPT.md`: prompt pronto.
- `tokens/`: tokens em CSS e JSON.
- `marca/`: símbolo, ícones, avatar, folha da marca e os quatro conceitos.
- `fontes/`: Bricolage e Hanken (OFL) com licenças.
- `fotos/` e `telas-app/`: imagens prontas para uso.
- `landing/`: a landing page no ar, íntegra (abrir `index.html`).
- `conteudo/mensagem.md`: títulos, frases, FAQ e botões da landing.
