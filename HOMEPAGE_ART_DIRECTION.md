# SolveIT — Homepage: Direção Visual + UX (Phase 4, pré-implementação)

> Sessão de direção visual e UX, conduzida com `frontend-design` (composição/identidade própria) + `ui-ux-pro-max` (validação de estrutura B2B/conversão/acessibilidade). Sem código. Depois de escolhida uma direção, avançamos para implementação.

---

## 0. Ponto de partida

**Fonte de verdade absoluta:** `DESIGN_SYSTEM.md` (tokens, componentes, símbolo). Nenhuma das três direções abaixo introduz cor, fonte, radius ou geometria nova — todas usam exatamente: Grafite `#1E2124`, Âmbar `#D98C2B`, Secondary `#8C8577`, Background `#F5F4F2`, Manrope/Inter, e o símbolo aprovado (arco em grafite + segmento em âmbar).

**O que varia entre as três direções não é conteúdo, é composição.** O inventário de copy aprovado em `HOMEPAGE_STRATEGY.md` (hero, "Alguma vez isto lhe soou familiar?", "Os dois caminhos", os 6 serviços, "Como trabalhamos", "Porque a SolveIT", FAQ, CTA final) mantém-se — nada de novo é inventado. O que muda é **como esse conteúdo é sequenciado, agrupado e composto no espaço**.

**Validação cruzada com `ui-ux-pro-max`:** consultei o dataset de padrões B2B (`--domain landing`, `--domain product`, `--domain ux`). Os três padrões "de fábrica" para B2B services são *Trust & Authority + Conversion* (logos/certificações/casos de estudo — não temos nenhum), *Hero + Testimonials + CTA* (não temos testemunhos, já decidido em `PROJECT_PLAN.md`) e *Funnel 3-Step*. Nenhuma das três direções abaixo segue algum destes literalmente — confirma que evitar o "hero → 3 cards → números → testemunhos → CTA" não é só preferência estética, é a escolha certa dado que não temos prova social real para preencher esse molde.

---

## DIREÇÃO 1 — "A Linha"

### 1. Nome
A Linha.

### 2. Ideia central
O símbolo aprovado é, na sua essência, **uma linha que carrega tensão e a liberta**. Em vez de tratar o símbolo como um ícone decorativo colado ao header, a Direção 1 transforma essa lógica numa **estrutura real da página**: uma linha vertical fina, em grafite, corre ao longo da margem esquerda do conteúdo — como a lombada de um documento editorial — e **parte-se para âmbar exatamente nos dois ou três momentos em que o discurso passa de "problema" para "resolução"**. A linha não é decoração; é o esqueleto de leitura da página.

### 3. Thesis do hero
"Esta página não vai gritar consigo — vai mostrar-lhe, com precisão, onde está o problema e onde está a saída." O hero é editorial, não centrado: título grande, alinhado à esquerda, ladeado pela linha-espinha, texto a ocupar um bloco de leitura deliberado, não um cartaz.

### 4. Estrutura completa
1. Header fino, sem sombra, só uma linha de 1px a separar do conteúdo.
2. Hero editorial (headline + subheadline + 2 CTAs), linha-espinha grafite ao lado.
3. "Alguma vez isto lhe soou familiar?" — lista corrida, não bullets com ícone; a linha-espinha continua.
4. **Quebra 1**: a linha muda de grafite para âmbar exatamente aqui — ponto de viragem do discurso.
5. "Os dois caminhos" — dois blocos lado a lado, não "cards" com sombra; divididos pela própria linha-espinha que aqui se bifurca visualmente.
6. Serviços — apresentados como **lista/índice editorial** (nome + 1 frase + seta), não grid de 6 cards idênticos.
7. "Como trabalhamos" — os 3-4 passos como uma sequência tipográfica simples (números pequenos, não ícones).
8. "Porque a SolveIT" — citações isoladas (pull-quotes), não lista com check icons.
9. FAQ — accordion nativo, sem alterações ao componente já construído.
10. **Quebra 2**: a linha volta a acentuar-se em âmbar mesmo antes do CTA final.
11. CTA final — banda grafite, linha desaparece (resolvida).
12. Footer.

### 5. Hierarquia visual
Tipografia e a linha-espinha fazem todo o trabalho de hierarquia — quase nenhuma cor fora do grafite/âmbar da linha e dos CTAs. Tamanho, peso e posição no eixo horizontal (tudo alinhado à mesma margem esquerda) substituem cor como sinal de importância.

### 6. Papel do logo/símbolo
No header, o lockup normal (símbolo + wordmark), pequeno, sem protagonismo. O verdadeiro "símbolo" da página é a linha-espinha — uma extensão conceptual do próprio arco/segmento aprovado, nunca uma cópia ampliada dele.

### 7. Uso do âmbar
Racionado ao extremo: só nos 2-3 pontos de quebra da linha + CTAs. Em toda a leitura corrida, zero âmbar. Isto torna o âmbar **informativo** (marca uma transição real) em vez de decorativo.

### 8. Movimento
Um único momento: ao entrar em viewport, a secção onde a linha muda de cor para âmbar tem uma transição suave de cor (não um efeito de scroll genérico) — 1 movimento com significado, não motion espalhado pela página. Respeita `prefers-reduced-motion` (já implementado no Design System).

### 9. Desktop (1440px)
Coluna de leitura com largura controlada (~68ch, o token `--container-prose` já existe), margem esquerda generosa para a linha-espinha, muito espaço em branco à direita em ecrãs largos — a página não estica o texto para preencher o ecrã, mantém a proporção editorial.

### 10. Mobile (375px)
A linha-espinha encolhe para uma barra fina no topo de cada bloco de secção (não desce a página inteira — em mobile isso competiria com o polegar/scroll). As quebras de cor mantêm-se nos mesmos pontos narrativos.

```
Desktop (≈1440px)                                    Mobile (375px)
┌──────────────────────────────────────────┐         ┌──────────────┐
│ SolveIT      Serviços Soluções Sobre  ●   │         │ SolveIT   ≡  │
├──────────────────────────────────────────┤         ├──────────────┤
│ │ 01                                      │         │▔▔▔▔▔▔▔▔▔▔▔▔▔│
│ │ Tenha um departamento de IT.            │         │ Tenha um     │
│ │ Sem ter de o contratar.                 │         │ departamento │
│ ┃                                         │         │ de IT. Sem   │
│ │ A SolveIT acompanha, mantém e protege...│         │ ter de o     │
│ │                                         │         │ contratar.   │
│ │ [Marcar uma conversa →] [Ver a avença]  │         │              │
│ │                                         │         │ [Marcar]     │
│ │ ─────────────────────────────────────   │         │ [Ver avença] │
│ │ Alguma vez isto lhe soou familiar?      │         │▔▔▔▔▔▔▔▔▔▔▔▔▔│
│ │  — computador trava no pior momento     │         │ Familiar?    │
│ │  — ninguém sabe onde estão os backups   │         │  — ...       │
│ ┃═══ (linha muda p/ âmbar aqui) ══════    │         │▁▁▁▁▁▁(âmbar)▁│
│ │ Os dois caminhos                        │         │ Os dois      │
│ │  Ajuda agora   │   Avença (recomendado) │         │ caminhos     │
│ │                                         │         │  ▸ Ajuda     │
│ │ Serviços                                │         │  ▸ Avença    │
│ │  Suporte IT ───────────────────────→    │         │              │
│ │  Segurança ────────────────────────→    │         │ Serviços     │
│ │  Backups ───────────────────────────→   │         │  Suporte →   │
│ │  ... (lista, não grid)                  │         │  Segur. →    │
│ │                                         │         │  ...         │
│ ┃═══ (2ª quebra âmbar, antes do CTA) ═══  │         │▁▁▁▁▁▁▁▁▁▁▁▁▁│
├──────────────────────────────────────────┤         ├──────────────┤
│ ██████ CTA final (grafite) ██████████████│         │██ CTA ██████│
├──────────────────────────────────────────┤         ├──────────────┤
│ Footer                                    │         │ Footer       │
└──────────────────────────────────────────┘         └──────────────┘
```

### 11. Porque é adequada à SolveIT
A marca vende clareza sobre caos. Uma página que se comporta como um documento bem editado — precisa, sequencial, sem ruído — é a prova viva dessa promessa antes mesmo de o texto a fazer.

### 12. Risco / problema possível
Pode sentir-se **demasiado contida/silenciosa** para quem espera uma homepage de serviços mais "vendedora" — precisa de CTAs muito bem posicionados e visíveis para não perder conversão à precisão. A lista editorial de serviços (em vez de grid) também é menos "escaneável" à primeira vista do que cards — mitigável com boa tipografia e a seta como affordance clara.

### 13. Diferença face a uma landing B2B genérica
Não há grid de 3 ícones no hero, não há cards com sombra por todo o lado, não há números inventados. A hierarquia vem de tipografia e de uma linha estrutural própria da marca — não de decoração importada de um template.

---

## DIREÇÃO 2 — "A Ficha" (clareza como prova, não só como promessa)

### 1. Nome
A Ficha.

### 2. Ideia central
Se a SolveIT promete "transformar complexidade em algo simples, estável e compreensível", a homepage devia **demonstrar isso na primeira dobra**, não só prometer. Em vez de um hero inspiracional genérico (headline + parágrafo vago), o hero funciona como uma **ficha objetiva**: título grande à esquerda, e à direita um pequeno painel estruturado, tipo etiqueta técnica precisa (não um dashboard, não uma UI de produto) — "Modelo · Área de atuação · Como começa" — que responde de imediato às perguntas implícitas do visitante, com a precisão de quem já tem tudo organizado.

### 3. Thesis do hero
"Não lhe vou pedir para acreditar que somos organizados — vou mostrar-lhe uma página organizada, agora, nos primeiros 3 segundos."

### 4. Estrutura completa
1. Header.
2. Hero em duas colunas: título+subheadline+CTAs à esquerda; painel-ficha à direita (3 linhas rótulo/valor: "Modelo → Avença ou pontual", "Área → Nacional remoto · Grande Lisboa e Margem Sul presencial", "Como começa → Uma conversa, sem compromisso").
3. "Alguma vez isto lhe soou familiar?" — cada item como uma linha de "ficha" (rótulo implícito + descrição), reforçando a linguagem visual do hero.
4. "Os dois caminhos" — dois blocos com a mesma lógica de rótulo/valor do hero (cria eco estrutural, não visual repetitivo).
5. Serviços — aqui sim, grid (usa o `ServiceCard` já construído) — é o único momento da página com "cards", precisamente porque aqui a comparação lado a lado é genuinamente útil (não por hábito de template).
6. "Como trabalhamos" — passos numerados curtos, alinhados à grelha da ficha.
7. "Porque a SolveIT" — lista curta, com o símbolo em miniatura (não um ícone genérico) a marcar cada item, reforçando a marca sem decoração.
8. FAQ.
9. CTA final.
10. Footer.

### 5. Hierarquia visual
Alinhamento rígido a uma grelha (rótulo/valor) é o motor de hierarquia — tudo o resto (peso, tamanho) reforça essa grelha em vez de a substituir. É a direção mais "regrada" das três.

### 6. Papel do logo/símbolo
O símbolo aparece pequeno e repetido como marca de precisão — por exemplo, ao lado de cada rótulo do painel-ficha do hero, do tamanho de um carácter, nunca ampliado como ilustração. Reforça "isto tem a marca da SolveIT em cada detalhe", sem nunca virar decoração.

### 7. Uso do âmbar
Reservado à coluna de "valor" da ficha (os dados concretos) e aos CTAs — o grafite fica para os "rótulos"/perguntas, o âmbar para as "respostas". Cria uma associação consistente: âmbar = resposta/resolução, em qualquer parte da página.

### 8. Movimento
Micro-interação discreta: ao passar o rato/focar num item de rótulo/valor, o valor (âmbar) desliza 2-3px — feedback ínfimo, não uma animação de entrada. Sem animação de scroll ostentosa.

### 9. Desktop (1440px)
Grelha de 12 colunas visível na estrutura (hero 7/5, ficha, etc.) — a régua/grelha é sentida mesmo sem estar desenhada literalmente.

### 10. Mobile (375px)
O painel-ficha do hero empilha por baixo do título, mantendo o formato rótulo/valor (não vira uma lista genérica) — é o elemento que menos se perde na transição para mobile porque já é uma lista vertical de rótulo/valor por natureza.

```
Desktop (≈1440px)                                    Mobile (375px)
┌──────────────────────────────────────────┐         ┌──────────────┐
│ SolveIT      Serviços Soluções Sobre  ●   │         │ SolveIT   ≡  │
├──────────────────────────────────────────┤         ├──────────────┤
│ Tenha um departamento     │ MODELO         │        │ Tenha um     │
│ de IT. Sem ter de o       │  Avença/pontual│        │ departamento │
│ contratar.                │ ÁREA           │        │ de IT...     │
│                           │  Nacional·GL/MS│        │              │
│ A SolveIT acompanha...    │ COMEÇA         │        │ MODELO       │
│                           │  Uma conversa  │        │  Avença/pont.│
│ [Marcar conversa→][Avença]│                │        │ ÁREA          │
├──────────────────────────────────────────┤         │  Nacional·... │
│ Alguma vez isto lhe soou familiar?        │         │ COMEÇA        │
│  computador trava   ninguém sabe backups  │         │  Uma conversa│
├──────────────────────────────────────────┤         │ [Marcar→]    │
│ Os dois caminhos (rótulo/valor)           │         ├──────────────┤
│  Ajuda agora →    │  Avença (recomendado)→│         │ Familiar?    │
├──────────────────────────────────────────┤         │  ...          │
│ Serviços (grid — único momento com cards) │         ├──────────────┤
│  [Suporte][Segurança][Backups]            │         │ Dois caminhos │
│  [Cloud]  [Redes]    [Consultoria]        │         │  Ajuda →      │
├──────────────────────────────────────────┤         │  Avença →     │
│ Como trabalhamos · Porque a SolveIT       │         │ Serviços      │
├──────────────────────────────────────────┤         │  (2 colunas)  │
│ ██████ CTA final ██████████████████████  │         │ ...           │
├──────────────────────────────────────────┤         │██ CTA ██████│
│ Footer                                    │         │ Footer        │
└──────────────────────────────────────────┘         └──────────────┘
```

### 11. Porque é adequada à SolveIT
Responde diretamente ao maior medo do comprador-alvo (dono de PME sem IT interno): "não sei em que é que me estou a meter". A ficha resolve isso literalmente no primeiro ecrã, sem esperar por FAQ.

### 12. Risco / problema possível
É a direção mais próxima de "consultora enterprise" — precisa de tipografia calorosa (Manrope grande, boa entrelinha) e copy humana para não escorregar para "frio/corporativo", que é exatamente o que a marca quer evitar. Requer disciplina para não parecer um dashboard de produto.

### 13. Diferença face a uma landing B2B genérica
O hero não é "headline + imagem genérica" — é headline + prova de organização real. É a única das três a usar grid de cards, e fá-lo só onde faz sentido (comparação de serviços), não como reflexo.

---

## DIREÇÃO 3 — "A Travessia" (a tensão e a resolução acontecem na própria frase)

### 1. Nome
A Travessia.

### 2. Ideia central
Em vez de ilustrar "problema → solução" com ícones, layout dividido ou imagens, a Direção 3 faz a **própria headline do hero performar essa transformação tipograficamente**: o início da frase está mais denso — tracking apertado, peso mais forte, cor grafite — e a leitura vai-se "abrindo" à medida que avança, terminando na última palavra/frase em âmbar, maior, com mais espaço à volta. A travessia (do aperto ao alívio) é literalmente vivida ao ler a frase — a mesma lógica do símbolo (arco apertado que se liberta numa linha aberta), mas expressa em tipografia, não em forma.

### 3. Thesis do hero
"Não lhe vou mostrar um símbolo de transformação — vou fazer a sua leitura sentir uma."

### 4. Estrutura completa
1. Header.
2. Hero: a frase-travessia como headline central (única secção da página que é centrada — todas as outras seguem alinhamento à esquerda, criando contraste deliberado). Subheadline e CTAs por baixo, normais.
3. "Alguma vez isto lhe soou familiar?" — volta ao alinhamento à esquerda, tom mais contido/normal (a "travessia" já aconteceu no hero, não se repete constantemente).
4. "Os dois caminhos" — eco discreto: o texto do cartão "avença" usa o mesmo princípio (mais espaçado/aberto) do que o cartão "ajuda pontual" (mais compacto) — sem re-explicar o efeito, só ecoando-o visualmente.
5. Serviços — grid normal com `ServiceCard`, sem tratamento especial (aqui a página fica deliberadamente "quieta").
6. "Como trabalhamos".
7. "Porque a SolveIT".
8. FAQ.
9. CTA final — pode repetir, em pequena escala, o efeito de travessia numa frase curta ("Vamos resolver a sua informática." → "resolver" em âmbar/aberto).
10. Footer.

### 5. Hierarquia visual
Nasce do contraste ENTRE o hero (centrado, expressivo, único momento "performático" da página) e o resto (alinhado à esquerda, disciplinado, "resolvido"). A composição do resto da página é deliberadamente calma — a confirmar, estruturalmente, que "o problema já foi tratado" logo após o hero.

### 6. Papel do logo/símbolo
Discreto no header. Não precisa de aparecer ampliado em mais lado nenhum — o conceito do símbolo já foi traduzido para tipografia no hero, repeti-lo visualmente seria redundante.

### 7. Uso do âmbar
Concentrado quase por completo na(s) palavra(s) finais da(s) frase(s)-travessia (hero + eco no CTA final) — o uso mais restrito e mais "cinematográfico" das três direções.

### 8. Movimento
Um único momento de entrada, uma vez, na primeira vista do hero: o tracking/peso da parte final da frase relaxa suavemente (~500ms, easing standard já definido no Design System) até à posição de repouso. Não se repete no scroll. Totalmente desligado sob `prefers-reduced-motion` (mostra o estado final direto, sem perda de conteúdo).

### 9. Desktop (1440px)
O hero centrado precisa de uma largura de linha controlada (não esticar a frase pela largura toda do ecrã) — usa o mesmo `--container-prose` para a headline, mesmo sendo H1.

### 10. Mobile (375px)
O efeito de tracking/abertura é subtil a este tamanho — mantém-se, mas a diferença de peso importa mais do que o espaçamento (que tem menos margem para variar em ecrãs estreitos sem quebrar a linha de forma estranha).

```
Desktop (≈1440px)                                    Mobile (375px)
┌──────────────────────────────────────────┐         ┌──────────────┐
│ SolveIT      Serviços Soluções Sobre  ●   │         │ SolveIT   ≡  │
├──────────────────────────────────────────┤         ├──────────────┤
│         Tenha um departamento de IT.      │         │  Tenha um    │
│              Sem ter de   O  C O N T R A T A R.     │  departamento│
│                    (denso)  (âmbar, aberto)│         │  de IT. Sem  │
│                                            │         │  ter de o    │
│   A SolveIT acompanha, mantém e protege...│         │  C O N T R A T A R.│
│                                            │         │              │
│      [Marcar uma conversa]  [Ver avença]  │         │ A SolveIT... │
├──────────────────────────────────────────┤         │ [Marcar]     │
│ (volta ao alinhamento à esquerda, quieto) │         │ [Avença]     │
│ Alguma vez isto lhe soou familiar?        │         ├──────────────┤
│  — computador trava no pior momento       │         │ Familiar?    │
├──────────────────────────────────────────┤         │  ...         │
│ Os dois caminhos                          │         ├──────────────┤
│  [compacto] Ajuda  │ [aberto] Avença ★     │         │ Dois caminhos│
├──────────────────────────────────────────┤         │  Ajuda       │
│ Serviços (grid normal, sem efeito)        │         │  Avença ★    │
│  [Suporte][Segurança][Backups]            │         ├──────────────┤
│  [Cloud]  [Redes]    [Consultoria]        │         │ Serviços     │
├──────────────────────────────────────────┤         │  (grid 2col) │
│ Como trabalhamos · Porque a SolveIT · FAQ │         ├──────────────┤
├──────────────────────────────────────────┤         │ ...          │
│ ██ Vamos R E S O L V E R a sua IT. ██████│         │██ CTA ██████│
├──────────────────────────────────────────┤         ├──────────────┤
│ Footer                                    │         │ Footer       │
└──────────────────────────────────────────┘         └──────────────┘
```

### 11. Porque é adequada à SolveIT
É a direção mais diretamente derivada da lógica exata do símbolo aprovado (tensão que se abre) — não decorativamente, mas ao nível da própria linguagem. Nenhuma outra empresa de IT vai ter esta assinatura, porque nasce do símbolo específico da SolveIT, não de um recurso visual genérico de "transformação".

### 12. Risco / problema possível
É a mais difícil de executar bem tecnicamente (variação de tracking/peso tem de parecer intencional, não uma falha de carregamento de fonte) e a mais "conceptual" — corre o risco de o efeito passar despercebido para uma parte dos visitantes, especialmente em leitura rápida/mobile. Precisa de ser suficientemente subtil para não parecer um erro de layout, e suficientemente clara para ser notada.

### 13. Diferença face a uma landing B2B genérica
Não há nenhuma landing de serviços de IT que trate a própria tipografia do hero como uma narrativa. É a mais arriscada e a mais autoral das três.

---

## Autocrítica ("se removesse o logo e o nome, ainda reconhecia a SolveIT?")

| Direção | Reconhecível sem logo? | Demasiado SaaS? | Demasiado agência? | Demasiado startup? | "AI-generated"? | Cards a mais? | Rounded a mais? | Animação a mais? | Hierarquia sem cor? | 375px OK? | 1440px OK? | CTA claro? | Confiança antes do contacto? |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1 · A Linha | **Sim** — a linha-espinha é só nossa | Não | Ligeiramente (tom editorial) | Não | Não | Não (lista em vez de grid nos serviços) | Não | Não (1 transição de cor) | Sim (tipografia + posição) | Sim | Sim | Sim, mas precisa de destaque visual reforçado | Sim, pela precisão da leitura |
| 2 · A Ficha | Moderado — precisão é distintiva mas partilhável com outros géneros "precisos" | Não | Não | Não | Não | Só 1 secção (serviços) — justificado | Não | Micro-interação mínima | Sim (grelha rótulo/valor) | Sim, é a que melhor se adapta | Sim | Sim, muito claro | Sim — mostra organização antes de pedir confiança |
| 3 · A Travessia | **Sim, a mais** — deriva diretamente da geometria do símbolo | Não | Não | Não | Não | Não | Não | 1 momento único, orquestrado | Sim (contraste hero vs. resto) | Sim, com atenção ao efeito | Sim | Sim | Sim, de forma mais emocional/memorável |

Todas as três passam o teste central. Nenhuma usa gradientes, glassmorphism, blobs, neon, ilustração stock ou fotografia genérica — nenhuma decoração sem função foi introduzida em nenhuma direção.

---

## Recomendação

**Direção 3 — "A Travessia" — com a estrutura de secções da Direção 1 como espinha dorsal.**

Porquê: a Direção 3 é a que passa o teste de reconhecimento sem logo de forma mais convincente — não porque introduz um elemento gráfico novo, mas porque **traduz a lógica exata do símbolo aprovado** (uma tensão em grafite que se abre num segmento em âmbar) para o nível mais fundamental da página: a própria frase que o visitante lê primeiro. É também a que melhor cumpre o pedido explícito de não recorrer ao padrão genérico, e a mais difícil de confundir com qualquer outra empresa de IT.

A ressalva honesta: sozinha, a Direção 3 só resolve o hero — o resto da página (secções 3 a 10) fica "quieto" por desenho, o que é correto (não sobrecarregar o efeito), mas precisa de alguma disciplina estrutural para não cair de volta no genérico depois do hero. Por isso a recomendação final é **emprestar da Direção 1 a ideia de tratar os serviços como lista/índice editorial em vez de grid de 6 cards**, e o uso comedido/racionado do âmbar como sinal de transição (não decoração espalhada) — sem reintroduzir a linha-espinha como elemento literal, para não competir com o efeito do hero.

Se preferires a opção mais segura de executar tecnicamente, a **Direção 2 — "A Ficha"** é a alternativa mais forte: resolve diretamente a maior objeção do comprador-alvo (incerteza) e é a mais fácil de implementar com precisão, ao custo de ser a que mais se aproxima (sem nunca lá chegar) do tom "consultora enterprise" que a marca quer evitar.

**Não recomendo a Direção 1 isolada** como direção principal — é sólida e segura, mas das três é a que menos aproveita a oportunidade específica que o símbolo aprovado oferece.
