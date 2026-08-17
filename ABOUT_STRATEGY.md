# SolveIT — Página /sobre: Estratégia e Copy

> Mesmo processo das páginas anteriores.
>
> **Estado: aprovado e implementado.** Decisões finais: H1 alterado para "A informática devia ajudar a sua empresa a trabalhar melhor — não ser mais uma dor de cabeça"; imagem do hero (mãos no teclado) gerada e usada como `src/assets/images/office/hands-laptop-detail.jpg`; imagem do café usada no CTA final (`two-coffee-cups-desk.jpg`), em layout a duas colunas específico desta página; sem menção a background da equipa/fundadores.

---

## 1. Estratégia da página

**/sobre não responde "o que fazemos" nem "como comprar"** — isso já está em `/servicos` e `/solucoes`. Responde a uma pergunta diferente: **"porque é que a SolveIT existe, e para quem é que isto faz sentido?"**

Não é biografia corporativa. Não há "somos líderes", "apaixonados por tecnologia", "inovadores". A página existe para dar contexto humano às páginas de produto — o porquê por trás do "o quê".

**Regra seguida em toda a página:** zero factos não confirmados. Sem história da empresa inventada, sem número de pessoas, sem anos de experiência publicados, sem clientes, sem certificações. Onde o texto beneficiaria de um facto concreto (fundação, equipa, experiência), a opção por omissão é deliberada — ver secção "Decisions required".

---

## 2. Estrutura de secções

### 1. Hero
**Eyebrow:** "Sobre a SolveIT"
**H1:** "A informática devia ajudar a sua empresa a trabalhar melhor — não ser mais uma coisa para gerir."
**Subheadline:** "Ajudamos pequenas e médias empresas que não têm — nem precisam de ter — um departamento de IT interno, mas precisam de alguém de confiança a quem recorrer."

*Nota de posicionamento:* não repete literalmente o H1 da homepage ("Tenha um departamento de IT...") — essa promessa fica reservada para a secção 7, onde se liga explicitamente à marca. Aqui o hero fala do porquê, não da oferta.

### 2. Porque existimos
**Headline:** "Porque existimos."
**Copy:** "A generalidade das pequenas e médias empresas depende da tecnologia para trabalhar — computadores, email, ficheiros, ligação à internet — mas não tem dimensão nem necessidade para manter um departamento de IT interno. O resultado, muitas vezes, é alguém dentro da empresa a acumular esse papel informalmente, para além das suas funções reais — ou a empresa a lidar com os problemas apenas quando já a estão a atrapalhar. A SolveIT existe para ocupar esse espaço: o de um parceiro de tecnologia acessível, sem ser preciso construir uma equipa própria para isso."

### 3. O que queremos resolver
**Headline:** "O que queremos resolver."
**Copy:** "Não queremos ser apenas quem aparece quando um computador avaria. Queremos retirar à sua empresa o peso de ter de perceber, decidir e gerir a parte técnica da tecnologia — para que possa concentrar-se no negócio, não na informática."

### 4. Como trabalhamos
**Headline:** "Como trabalhamos."
Lista curta, cada item com uma linha de contexto (reaproveita literalmente os princípios que já definiste):
- **Falamos de forma clara.** Sem jargão técnico a mais, sem complicar o que é simples.
- **Resolvemos remotamente sempre que possível.** É mais rápido para si e reduz o tempo parado.
- **Estamos presentes quando é necessário.** Nem tudo se resolve à distância.
- **Explicamos antes de complicar.** Percebe sempre o que está a ser feito e porquê.
- **Recomendamos o que faz sentido para a sua empresa** — não o que é mais caro ou mais complexo.

### 5. Para quem somos
**Headline:** "Para quem somos."
**Copy:** "Pequenas e médias empresas — sobretudo negócios locais que precisam de um parceiro tecnológico acessível, sem a estrutura (nem o custo) de um departamento de IT interno." + link: "Veja em detalhe [para quem faz sentido a avença](/solucoes#para-quem-faz-sentido)."

*Nota:* deliberadamente curta — a lista detalhada de perfis já existe em `/solucoes` ("Para quem faz sentido"). Repeti-la aqui arriscaria ficar desatualizada nas duas páginas ao mesmo tempo; prefiro uma frase + link.

### 6. Onde estamos
**Headline:** "Onde estamos."
**Copy:** "Suporte remoto em todo o país. Assistência presencial na Grande Lisboa e Margem Sul do Tejo." *(linguagem literal já usada nas restantes páginas — sem alteração)*

### 7. A nossa ideia de IT
**Headline:** "A nossa ideia de IT."
**Copy:** "We Solve IT não é só um nome — é como pensamos a tecnologia: a resolver problemas reais, sem complicar o que não precisa de ser complicado. É a mesma ideia por trás de **'Tenha um departamento de IT. Sem ter de o contratar.'** — ter alguém responsável pela sua informática, sem ter de construir uma equipa própria para isso."

*(único ponto da página que liga explicitamente ao nome da marca e à promessa da homepage — final natural antes do CTA)*

### 8. CTA final
**Headline:** "Conte-nos o que precisa."
**Subheadline:** "Sem compromisso, sem discurso de vendas — só uma conversa para perceber a sua situação."
**Conteúdo:** formulário de contacto reutilizado (mesmo padrão das outras páginas), desta vez acompanhado da imagem das duas chávenas de café (ver secção 4b) — a única secção da página com layout a duas colunas, para reforçar visualmente o tom de "conversa", não "formulário a preencher".

---

## 3. Sem FAQ

Ao contrário de `/solucoes`, esta página não tem secção de FAQ — não é uma página de decisão de compra, é uma página de contexto. Perguntas comerciais (preço, contrato, o que está incluído) já têm o lugar certo em `/solucoes`.

---

## 4. Design

Sem Travessia (igual às restantes páginas, exceto homepage). Página deliberadamente mais curta e com mais espaço em branco do que `/solucoes` — texto corrido em vez de grids/cards, sem `ServiceCard`. Estrutura: hero simples (sem imagem) → blocos de texto curto → CTA final com imagem.

**Diferença estrutural face às outras páginas:** a única imagem convencional é a do CTA final (ver 4b), não no hero. Isto separa visualmente `/sobre` das páginas de produto (que abrem sempre com imagem no hero) e reforça que esta página é sobre pessoas/propósito, não sobre um serviço a apresentar.

## 4b. Imagens — propostas

**Imagem 1 — CTA final (já processada, pronta a usar):**
`src/assets/images/office/two-coffee-cups-desk.jpg` — duas chávenas de café numa secretária, sem pessoas. Encaixa bem no tom "conte-nos o que precisa": evoca uma conversa informal, não uma venda. Reservada para esta secção, como combinado.

**Imagem 2 — hero (nova, prompt a gerar):**

Pediste uma imagem "editorial humana/profissional". Para manter coerência com o resto do site (nenhuma imagem existente mostra rostos — segue sempre o padrão "sem pessoas" ou "detalhe"), proponho um plano de detalhe com presença humana implícita (mãos), não um retrato:

> Editorial photograph, candid documentary style: close side-angle view of a person's hands typing calmly on a laptop keyboard at a clean, organized desk. No face visible, no eye contact with camera. Natural daylight from a window, muted warm-neutral color grading, slightly desaturated, calm and unhurried mood, generous negative space around the subject. Vertical portrait orientation, aspect ratio 4:5.
> **Avoid:** visible face, stock photography of people smiling at the camera, corporate headshot poses, servers, padlocks, shields, cybersecurity imagery, multiple monitors, blue color cast, neon, clutter.

**Ficheiro sugerido:** `src/assets/images/office/hands-laptop-detail.jpg`

**Alternativa (mais arriscada, menos consistente com o resto do site):** um plano mais largo, duas pessoas em conversa junto a uma secretária, vistas de lado/costas, sem rosto visível — mais literalmente "humano", mas mais perto do cliché "duas pessoas a colaborar" que temos evitado. Não é a minha recomendação, mas fica como opção — ver decisão abaixo.

---

## 5. SEO

**Title:** "Sobre a SolveIT"
**Meta description:** "Conheça a SolveIT — o parceiro de tecnologia para pequenas e médias empresas que não têm, nem precisam de ter, um departamento de IT interno."
**H1:** "A informática devia ajudar a sua empresa a trabalhar melhor — não ser mais uma coisa para gerir."
**H2:** "Porque existimos." / "O que queremos resolver." / "Como trabalhamos." / "Para quem somos." / "Onde estamos." / "A nossa ideia de IT." / "Conte-nos o que precisa."
**Intenções de pesquisa:** "sobre a SolveIT", "empresa de IT para PME Lisboa", "parceiro de tecnologia PME", "quem é a SolveIT".

---

## Decisions required

1. **Background da equipa** — não incluí qualquer menção a fundadores, número de pessoas ou anos de experiência. É uma opção deliberada (evita números que depois têm de ser mantidos atualizados, e mantém o foco no cliente, não na empresa). Se preferires uma frase muito genérica e sem números — ex.: *"Somos uma equipa pequena, com larga experiência em tecnologia, focada em manter a informática das PME simples e sob controlo."* — digo-me e insiro-a na secção 2 ou 7. **[CONFIRMAR]**

2. **Imagem do hero** — recomendo o plano de detalhe (mãos no teclado, sem rosto), consistente com o resto do site. A alternativa (duas pessoas em conversa) fica disponível mas não é a recomendação. **[CONFIRMAR qual das duas prompts usar]**

3. **Layout do CTA final com imagem** — nenhuma outra página tem imagem dentro da secção de CTA/formulário; seria um padrão novo (grid a duas colunas: formulário + imagem), implementado apenas nesta página, sem alterar o componente partilhado `CtaSection.astro`. Confirmas que este layout novo, específico desta página, está aprovado? **[CONFIRMAR]**

4. **H1 do hero** — proposta: *"A informática devia ajudar a sua empresa a trabalhar melhor — não ser mais uma coisa para gerir."* Alternativa mais curta, se preferires algo mais direto: *"Existimos para que a sua empresa deixe de se preocupar com informática."* **[CONFIRMAR]**
