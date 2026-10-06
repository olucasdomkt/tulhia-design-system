# Tulhia, design system

> **Nome provisório.** Tulhia é um nome de trabalho, usado para visualizar a marca. O nome definitivo e a identidade ainda serão decididos com os sócios.

**Tulhia = tulha + IA.** A tulha guarda a safra, a Tulhia guarda o caixa.

Tulhia é um produto para o produtor rural: mostra quanto ele deve, quando cada parcela vence e em que mês o caixa da fazenda aperta, com um consultor responsável pela fazenda. Caixa e dívidas da fazenda, com consultor.

O IA do nome está no aplicativo. Na conciliação do extrato, ele sugere a categoria de cada movimentação: primeiro pelas regras, que aprendem com o que já foi conferido, e depois pela IA, para o que as regras não resolveram. Na leitura da cédula em PDF, quando o texto não basta (cédula escaneada, por exemplo), é a IA que lê e monta o cronograma das parcelas. A sugestão só vale depois que o consultor confere, e só ele fecha o mês.

Este repositório reúne o que uma pessoa (ou o Claude Design) precisa para desenhar a Tulhia na marca atual, a **1b Livro-caixa**, escolhida em 05/10/2026: conceito, símbolo, tokens, tipografia, componentes, kit de marca, fotos, telas do app, a landing page no ar e a mensagem. A folha completa do design system está em `design-system.html` (abra no navegador).

- Landing page no ar: https://tulhia.vercel.app (pré-lançamento, sem indexação).
- Projeto no Claude Design: https://claude.ai/design/p/827ef3a2-3008-4b77-90d0-0403a5b31f52
- A marca anterior (v1, três silos) foi superada e está em `legado/`.

## 1. O produto, em uma tela

- Promessa: "Quanto você deve, quando vence e em que mês o caixa aperta."
- Três números: 12 meses de projeção do caixa, com cada parcela dentro · 15 dias antes do vencimento, a parcela entra no aviso do consultor · 1 página de relatório por mês, para imprimir ou mandar ao contador.
- O que o produtor recebe: calendário de dívidas; caixa dos próximos 12 meses; resumo do mês no WhatsApp; dois avisos antes do aperto.
- Como começa (3 passos): você manda as cédulas · você autoriza os bancos, só para ver (Open Finance) · o consultor acompanha todo mês.
- Confiança: acesso ao banco só para ver · sem digitar extrato · um consultor responsável pela sua fazenda.
- Para quem: quem toca a fazenda com crédito rural (custeio, investimento, CPR, renegociação), tem conta em mais de um banco ou em mais de um nome da família e quer saber o mês que aperta antes de ele chegar, sem lançar extrato. Não é para quem só quer anotar gasto, procura sistema de lavoura, estoque, nota fiscal ou imposto, procura empréstimo ou quer só o aplicativo.
- Chamada à ação: WhatsApp. O botão diz "Falar com um consultor" e a mensagem pronta é "Quero conhecer a Tulhia".

A mensagem completa está em `conteudo/mensagem.md` e o texto integral em `landing/index.html`.

## 2. Público e tom

Produtor rural próspero, 45 a 65 anos, fazenda estruturada (silos, frota, funcionários), decide rápido, por conversa, com quem confia. Odeia planilha e aplicativo que pede digitação. O consultor é a pessoa de confiança; o sistema é a ferramenta do consultor.

Tom: direto, adulto, sem jargão de fintech, sem promessa de "transformar". Sentence case nos títulos. Número antes de prosa. Nada de travessão, nada de emoji, nada de "revolucionar". Fala com "você".

## 3. Marca: 1b Livro-caixa

A Tulhia funciona como o livro-caixa da fazenda, que alguém de confiança mantém em dia. Os números vêm antes do texto e ficam em coluna, separados por linhas de pauta. O amarelo do marca-texto aparece uma vez por tela, no mês que aperta ou no número que importa.

**Símbolo: o T de livro-caixa.** Pauta de 64 unidades. A linha do cabeçalho e a da coluna formam o T, e a casa amarela é o mês marcado. A casa fica na coluna dos valores, embaixo e à direita, onde está o último número da conta. Desenho: caixa de 64 × 64; cabeçalho em x 10, y 14, com 44 × 6; coluna em x 23, y 20, com 6 × 34; casa em x 35, y 38, com 17 × 12.

- `marca/tulhia-simbolo.svg`: a versão principal. Caixa em tinta, T em almaço, casa em marca-texto. Vai sobre almaço e folha.
- `marca/tulhia-simbolo-claro.svg`: caixa em almaço, T em tinta, casa em marca-texto. Vai sobre tinta (seção escura e rodapé).

**Nome:** "Tulhia" em Schibsted Grotesk 800, entreletra −4,5%, ao lado do símbolo, com 10 px entre os dois (no cabeçalho, símbolo de 30 px e nome de 26 px). Assinatura: caixa e dívidas da fazenda, com consultor.

**Uso:** tamanho mínimo de 16 px o símbolo e 72 px o conjunto. Respiro de 1/4 do lado do símbolo em volta. Não fazer: girar, arredondar, trocar a cor da casa, pôr sobre foto sem a caixa sólida.

**Kit de marca, em `marca/`:**
- `icone-app-1024.png` e `icone-app-180.png` (apple-touch-icon): o desenho fica na área segura de 80%, porque o sistema arredonda os cantos.
- `favicon.svg` e `favicon-32.png`.
- `avatar-whatsapp-640.png`: o WhatsApp corta em círculo. O símbolo fica dentro do círculo e sem a caixa, para não ter quadrado dentro de círculo.
- `og-1200x630.png`: a imagem de compartilhamento da landing no ar. Título da página, os dois lançamentos do hero e a foto do hero, para o link no WhatsApp e a página parecerem a mesma coisa. É gerada por `landing/og.html`.

## 4. Cor

Tinta e almaço fazem quase tudo. Os tokens estão em `tokens/tokens.css` (com os nomes usados na landing no ar) e em `tokens/tokens.json` (com o papel de cada cor). Entre parênteses, o nome no design system quando ele muda.

| Token | Valor | Papel |
|---|---|---|
| `--almaco` | #F5F6F2 | Fundo da página, texto sobre tinta, botão claro. |
| `--almaco-2` | #ECEEE8 | Seção alternada clara. |
| `--folha` | #FFFFFF | Cartão, moldura de tela, aviso. |
| `--pauta` | #D9DDE3 | Linha de 1 px entre linhas da conta. |
| `--pauta-2` | #C4CAD3 | Pauta forte, sobre almaço-2. |
| `--tinta` | #172238 | Texto principal, botão primário, seções escuras, regras de 2 px. |
| `--tinta-2` (tinta-hover) | #2A3A5C | Hover do botão primário. |
| `--tinta-3` (tinta-cartão) | #1F2C47 | Fundo de cartão dentro da seção escura. |
| `--tinta-linha` | #2E3D5C | Borda e linha dentro da seção escura. |
| `--tinta-fundo` | #0F1729 | Rodapé. |
| `--texto-2` (grafite-texto) | #3B4352 | Parágrafo de apoio (lead, descrição). 9,9:1 sobre almaço. |
| `--grafite` | #565E6B | Rótulos, legendas, notas. 6,2:1 sobre almaço. |
| `--claro-2` (névoa) | #B8C0CC | Texto de apoio sobre tinta. 8,9:1. |
| `--claro-3` | #D5DAE2 | Texto claro sobre tinta: linha de pré-lançamento do rodapé, rótulo e nota da chamada final. |
| `--marca-texto` | #F2D43D | O acento. Uma vez por tela, atrás do mês que aperta ou do número que importa. Também é o anel de foco. |
| `--vermelho` | #B3261E | Caixa negativo e aviso, sempre com texto. Não é cor de botão. |

Regras de cor:
- Marca-texto uma vez por tela, só no mês em que o caixa aperta ou no número mais crítico. Texto sobre ele sempre em tinta, nunca branco. Se dois números disputam, a tela tem informação demais.
- O vermelho só marca caixa negativo e sempre vem com texto ou sinal de menos ao lado, porque a cor sozinha não basta.
- Não há verde na paleta: valor positivo fica em tinta.
- Seção escura: no máximo duas por página, nunca seguidas.

## 5. Tipografia

Uma letra para ler, uma para contar.

- **Schibsted Grotesk**, 400 a 800: títulos, texto e botões. É uma letra de jornal, clara no celular, e pouca gente usa.
- **Spline Sans Mono**, 400 a 600: valores, datas, rótulos e números de seção. Os algarismos têm a mesma largura e alinham em coluna.

| Estilo | Tamanho / altura de linha | Peso · entreletra |
|---|---|---|
| display | 37 → 66 px / 1,03 | 800 · −3,5% |
| h2 | 30 → 46 px / 1,08 | 800 · −3% |
| h3 | 21 → 22 px / 1,25 | 700 · −1,5% |
| citação | 19 → 23 px / 1,35 | 600 |
| lead | 18 → 21 px / 1,5 | 400 |
| corpo | 17 a 18 px / 1,55 | 400 · mínimo 16 |
| valor | 21 px / 1 | mono 600 |
| rótulo | 12 a 13 px | mono 500 |

Rótulos em mono de 12 a 13 px servem só para nomear coisas. Texto que precisa ser lido nunca fica abaixo de 16 px (a landing no ar usa 16 px também nos rótulos). As fontes ficam no próprio site, sem pedir nada a servidor de fora: os arquivos estão em `fontes/`, com as licenças (OFL).

## 6. Espaço, forma e linhas

- Espaço: 4 · 8 · 12 · 16 · 20 (margem no celular) · 24 · 32 · 48 (margem no desktop) · 80 (entre colunas). Entre seções, 56 a 112 px.
- Largura máxima de 1200 px. Margem lateral clamp(20px, 4vw, 48px). Texto corrido com até 32 em de largura.
- Raio: 0 em fotos, seções e símbolo · 2 px em cartões e molduras · 4 px em botões.
- Linhas: a regra-forte, de 2 px em tinta, abre seção e fecha a conta; a pauta, de 1 px, separa linhas. Linhas e colunas fazem o trabalho que sombra e arredondado fariam.
- Sombra: só na moldura de tela do app (0 28px 50px −30px, tinta a 50%).
- Movimento: na landing, só a cor dos botões muda com transição (0,2 s) e a rolagem até as âncoras é suave; com prefers-reduced-motion, as duas desligam.

## 7. Componentes

Todos estão desenhados em `design-system.html`, com as medidas.

1. **Cabeçalho**: fixo no topo, 64 px, regra-forte embaixo. No celular o botão vira só o ícone, com 44 × 44.
2. **Botões**: todos abrem o WhatsApp e têm o ícone dele. Primário em tinta, com 54 px de altura; secundário com borda, com 46; claro (almaço) sobre tinta. Foco com anel de 3 px em marca-texto (a landing no ar usa o anel em tinta sobre fundo claro e em marca-texto nas seções escuras). Embaixo de todo botão vem a mesma linha: "Abre o WhatsApp. A conversa não obriga a nada."
3. **Lista de confiança**: caixa de conferência marcada, como no livro. Até três itens.
4. **Lançamento**: a ideia da marca em forma de componente. Rótulo à esquerda, valor em mono à direita, marca-texto só na linha que importa e "Dados de demonstração" embaixo.
5. **Faixa de números**: fundo tinta, número em 800, explicação em névoa. Três colunas no desktop e uma pilha no celular.
6. **Citação**: fala do produtor, aspas em mono, entre linhas de pauta. Sem barra lateral.
7. **Abertura de seção**: regra-forte, número da folha e nome da seção. Depois, o h2.
8. **Cartão de entrega**: duas formas, a coluna do livro, para listar o que você recebe, e o cartão, para detalhar uma entrega. Nunca três cartões iguais em fila. O aviso de caixa negativo é a variante com borda vermelha.
9. **Seção escura**: fundo tinta, texto em almaço e névoa, cartões em tinta-cartão. No máximo duas por página, nunca seguidas.
10. **Moldura de tela do app**: folha com borda tinta e faixa de topo com o nome da tela e a etiqueta "Dados de demonstração". A captura entra como veio, sem mexer nos dados.
11. **Passo numerado**: número grande em 800 numa coluna de 64 px, regra-forte em cima, sem cartão.
12. **Perguntas**: linhas de 60 px no mínimo, sinal de mais em mono, abre no toque.
13. **Chamada final**: foto dos silos com véu de tinta (62% a 90%), três linhas numeradas e botão claro.
14. **Barra fixa de CTA**: só no celular, abaixo de 900 px. Fica presa embaixo e respeita a área segura da tela.
15. **Rodapé**: tinta-fundo. As linhas de LGPD e de pré-lançamento são obrigatórias.
16. **Fotografia**: na seção 9.

## 8. Regras de escrita e montagem

1. Primeiro o número, depois a explicação: "15 dias antes do vencimento".
2. Marca-texto uma vez por tela. Se dois números disputam, a tela tem informação demais.
3. Todo número de exemplo leva a etiqueta "Dados de demonstração".
4. Títulos com só a primeira letra maiúscula. Sem travessão, sem emoji, sem "transformar" ou "revolucionar".
5. Texto alinhado à esquerda. Linhas e colunas fazem o trabalho que sombra e arredondado fariam.
6. Toque mínimo de 44 px e corpo mínimo de 16 px. Página sem rolagem horizontal em 360 px.

## 9. Fotos e telas

`fotos/`: sete fotos documentais (produtor próspero, silos, varanda, mesa de escritório, pôr do sol), geradas para a marca, sem direitos de terceiros. Regra: documental, luz natural, o produtor com a fazenda dele em volta. Cantos retos e proporções 4:5 ou 3:2. Sem filtro e sem texto em cima, a não ser na chamada final. Rejeitado no caminho: página "com cara de IA", sem humano; foto de produtor "pé-rapado"; stock genérico.

`telas-app/`: quatro telas reais do app (resumo de dívidas, caixa de 12 meses, cronograma lido da cédula, resumo no WhatsApp), com dados de demonstração. São o produto e entram na moldura como vieram. Estas capturas são de antes de o app passar para a 1b (o gráfico ainda é verde): o conteúdo vale, o visual muda quando as telas forem capturadas de novo.

## 10. Como usar no Claude Design

A direção já foi escolhida: a 1b Livro-caixa, em 05/10/2026, no projeto https://claude.ai/design/p/827ef3a2-3008-4b77-90d0-0403a5b31f52. O mesmo projeto tem o design system (etapa 2), a landing (etapa 3) e o kit de marca (etapa 4).

1. Para uma peça nova, abra o projeto ou aponte este repositório (`README.md`, `design-system.html`, `tokens/`, `marca/`, `fotos/` e `telas-app/`).
2. Peça a peça dentro do design system 1b.
3. `CLAUDE-DESIGN-PROMPT.md` é o prompt que gerou as três direções da etapa 1. Fica como registro.

## 11. Mapa de arquivos

- `design-system.html`: a folha do design system 1b (marca, cor, tipografia, espaço, componentes e regras), versão estática do arquivo exportado do Claude Design.
- `tokens/`: tokens em CSS e JSON.
- `marca/`: símbolo nas duas versões, favicon, ícones de app, avatar de WhatsApp e imagem de compartilhamento.
- `fontes/`: Schibsted Grotesk e Spline Sans Mono (OFL), com as licenças.
- `fotos/` e `telas-app/`: imagens prontas para uso.
- `landing/`: a landing page no ar, íntegra (abrir `index.html`; `og.html` gera o `og.png`).
- `conteudo/mensagem.md`: títulos, frases, FAQ e botões da landing.
- `CLAUDE-DESIGN-PROMPT.md`: o prompt usado no Claude Design, com a direção escolhida no topo.
- `legado/`: a marca v1 dos silos, superada em 05/10/2026, com marca, fontes, tokens e landing como estavam.
