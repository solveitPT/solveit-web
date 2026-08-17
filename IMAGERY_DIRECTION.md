# SolveIT — Homepage Imagery: Proposta (Phase 4, refinamento)

> Proposta de exploração fotográfica sobre a homepage já aprovada (Direção 3 — "A Travessia"). Sem código, sem imagens escolhidas ainda. Estrutura/direção apenas — a implementação só avança depois de aprovada.

---

## Avaliação dos 4 locais candidatos

### 1. Hero — **não recomendado**

Avaliei explicitamente, como pedido. A recomendação é **não colocar imagem no hero**, por uma razão estrutural, não estética: o poder da Travessia vem de a tipografia ser o único ponto focal no momento mais importante da página — a frase que passa de tensão (peso 800, compacta) a abertura (peso 600, maior, o "contratar." a resolver para âmbar). Qualquer imagem, mesmo pequena e assimétrica, introduz um segundo ponto focal exatamente onde a composição precisa de um só. Testei mentalmente uma coluna fotográfica estreita (20-25%) a sangrar pela margem direita — resultado: compete com a leitura da headline em vez de a reforçar, e obriga a decisões de recorte diferentes em mobile que alteram o ritmo vertical que já está afinado. Não cumpre "se enfraquecer a Travessia, não colocar".

### 2. "Alguma vez isto lhe soou familiar?" — **recomendado, prioridade 1**

**Objetivo:** ancorar a lista de problemas (hoje só texto) num espaço real e reconhecível — o oposto de imagética de "desastre informático".
**Tipo de fotografia:** um pequeno escritório real — secretária com portátil, luz natural de janela, talvez um router/switch discreto no enquadramento. Sem pessoa em pânico; se houver presença humana, deve ser parcial/candid (mãos, alguém desfocado ao fundo), nunca posada a olhar para a câmara.
**Composição:** quebra deliberada do padrão de coluna única desta secção — texto à esquerda (título + lista + linha de fecho), fotografia à direita, sem moldura pesada (sem card, sem sombra — só a foto, como um recorte editorial real).
**Proporção:** retrato ~4:5 em desktop (ocupando ~40% da largura), paisagem ~3:2 em mobile, empilhada acima ou abaixo do texto.
**Porque funciona:** é exatamente a secção que pede reconhecimento — uma fotografia calma de um espaço real faz o "isto sou eu" acontecer visualmente, sem precisar de uma pessoa a demonstrar pânico.

### 3. Serviços / transição para "Como trabalhamos" — **recomendado, prioridade 2**

**Objetivo:** dar à página uma pausa/respiração tátil entre o índice editorial de serviços (só texto, deliberadamente) e os passos do processo — não ilustrar nenhum serviço específico (evita a leitura errada de "esta foto = este serviço").
**Tipo de fotografia:** detalhe técnico discreto — teclado de portátil em luz natural, um pequeno switch de rede bem arrumado, cabos organizados — sinaliza "trabalho técnico feito com cuidado", não uma sala de servidores dramática.
**Composição:** faixa horizontal contida (não full-bleed), com bastante espaço em branco à volta — funciona como uma pausa no ritmo de leitura, não como uma "feature".
**Proporção:** paisagem ampla, ~16:9 a 21:9, altura moderada.
**Porque funciona:** a secção de Serviços é deliberadamente só texto (índice editorial, não catálogo de cards) — colocar a foto FORA da lista, como transição, dá o toque humano pedido sem quebrar a disciplina que já foi decidida para essa secção.

### 4. CTA final — **não recomendado para já**

Avaliei como pedido. Uma fotografia humana pequena arrisca dois problemas reais: (1) o fundo grafite exige tratamento tonal cuidadoso para a foto não destoar, e (2) o único trabalho desta secção é o formulário — qualquer elemento adicional, mesmo pequeno, compete por atenção exatamente no momento de conversão. A recomendação é deixar esta secção como está. Podemos reconsiderar depois de vermos as duas fotografias principais implementadas e a funcionar bem.

**Resultado: 2 locais firmes, alinhado com "prefiro 2 imagens excelentes a 6 medianas".**

---

## Direção de produção fotográfica (para as 2 imagens)

- Luz natural, nunca luz de estúdio dura.
- White balance neutro/quente — evitar o azul frio típico de stock "tech" (explicitamente na lista a evitar).
- Grading levemente dessaturado, sombras não esmagadas — tom consistente com grafite/âmbar/background da marca, não uma foto vibrante isolada da paleta.
- Grão/tratamento editorial, não "polido de anúncio".
- Nenhuma pessoa a olhar/sorrir para a câmara; nenhum logótipo de terceiros visível; nenhum ecrã com conteúdo genérico de "hacker"/código.

---

## Estrutura de assets

Proposta técnica com uma nota importante: sugiro `src/assets/images/` em vez de `public/images/` — mantém exatamente a mesma organização por pastas que propuseste, mas permite que o Astro otimize as imagens automaticamente no build (WebP/AVIF, tamanhos responsivos, lazy loading), consistente com a prioridade de performance já definida no `DESIGN_SYSTEM.md`. Ficheiros em `public/` são servidos tal como estão, sem essa otimização. Se preferires manter `public/images/`, também funciona — só significa termos de exportar os ficheiros já otimizados manualmente antes de os lá colocar. Digo-me qual preferes.

```
src/assets/images/
  hero/           (reservada — sem imagem na v1, por decisão acima)
  office/
    small-business-desk-daylight.jpg   → Local 2 ("Alguma vez... familiar?")
  services/
    laptop-keyboard-detail.jpg         → Local 3 (transição Serviços → Como trabalhamos)
  about/          (reservada — CTA final / futura página Sobre)
```

Nomes semânticos, uma imagem = um ficheiro = um local — trocar uma foto por outra é substituir o ficheiro, o layout (aspect-ratio fixo por container) não muda.

---

## Sobre Higgsfield e ImageKit

Consultei a documentação indicada (`imagekit.io/docs/build-with-ai`).

**ImageKit** — encaixa bem, mas para a camada errada do problema: é um serviço de alojamento/otimização/transformação de imagens (CDN, redimensionamento via URL, conversão automática de formato), não gera imagens. A instalação "build with AI" liga um MCP à tua conta via OAuth com uma chave API privada — as credenciais nunca ficam expostas a mim diretamente, é um token limitado. Só faz sentido se decidires alojar as imagens fora do repositório (útil se a equipa for atualizar imagens sem passar por deploy de código); para uma v1 com 2 imagens fixas, `src/assets/` local é mais simples e não introduz uma dependência externa nem custo recorrente.

**Higgsfield** — é uma ferramenta de geração de imagem/vídeo por IA, não de fotografia real. Antes de a usar, preciso que decidas algo importante: o briefing pede explicitamente "fotografias editoriais/profissionais, não stock photography óbvia" e insiste em autenticidade — imagens geradas por IA, por melhores que sejam, não são fotografias reais, e para uma marca que vende justamente "confiança" e "proximidade" com PME reais, isso é uma decisão de posicionamento, não só técnica. Não vou avançar com imagens geradas por IA sem confirmares que é essa a direção que queres.

---

## Decisões (confirmadas)

1. **Geração por IA** — aprovado. Isto ajusta a posição do `BRAND_IDENTITY.md`/briefing original de "só fotografia real" — nota registada aqui para não se perder.
2. **ImageKit — descartado para já.** É uma camada de alojamento/otimização (CDN + transformação por URL), não gera imagens. Só compensa quando há uma biblioteca de imagens que cresce com frequência ou uma equipa não-técnica a substituir imagens sem passar por deploy — nenhum dos dois é o caso agora, com 2 imagens fixas. O `src/assets/` do Astro já trata da otimização (WebP/AVIF, responsive) sem custo nem dependência externa. Fica como candidato futuro em `PROJECT_PLAN.md` (Phase 12) se a biblioteca de imagens crescer muito.
3. **`src/assets/images/`** — confirmado e já criado: `hero/` (reservada), `office/`, `services/`, `about/` (reservada).

## Nota importante sobre geração — sem ferramenta ligada nesta sessão

Verifiquei: não tenho o Higgsfield ligado como conector nesta sessão (não está no registo de MCPs disponíveis), nem a skill de geração de imagem por IA (`ai-artist`) está ativa neste projeto — só gero SVG (ícones/logótipo), não fotografia rasterizada. Não consigo gerar as imagens diretamente a partir daqui.

**Caminho prático:** geras as duas imagens tu, no Higgsfield (prompts prontos abaixo), e depois ou (a) colocas os ficheiros diretamente nas pastas já criadas, ou (b) partilhas os ficheiros aqui no chat e eu guardo-os no sítio certo.

### Prompt — `office/small-business-desk-daylight`

> Editorial photograph of a small modern office desk in Portugal/Southern Europe, mid-morning natural window light from the left, shallow depth of field. A laptop is open showing a blurred generic interface (no readable text or logos), a small desk organizer, a notebook, a coffee cup slightly out of focus. In the soft background, a small discreet network router/switch sits on a shelf, barely noticeable. No people in sharp focus — optionally a blurred hand or silhouette passing in the background, out of focus. Muted, warm-neutral color grading, slightly desaturated, soft shadows, documentary/editorial photography style. Vertical portrait orientation, aspect ratio 4:5.
> **Avoid:** dramatic server rooms, blue color cast, people smiling at camera, visible brand logos, generic "business team" imagery, neon, futuristic elements, stock-photo look.

### Prompt — `services/laptop-keyboard-detail`

> Close-up editorial detail photograph of a laptop keyboard and trackpad on a wooden desk, soft natural daylight from a window, shallow depth of field with the keys in sharp focus and background softly blurred. A neatly organized ethernet cable or small network switch partially visible at the edge of frame, tidy, not dramatic. Warm-neutral tones, slightly desaturated, editorial documentary photography style, no visible screen content, no logos, no hands or people. Wide horizontal composition, aspect ratio 16:9.
> **Avoid:** dramatic lighting, blue color cast, "hacker" aesthetic, glowing green code, futuristic server room, neon accents.

Assim que tiver os dois ficheiros, integro-os na homepage (secções "Alguma vez... familiar?" e a transição Serviços → Como trabalhamos) — nessa altura sim, há alteração de código.
