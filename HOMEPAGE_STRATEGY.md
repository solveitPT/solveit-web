# SolveIT — Homepage: UX & Content Strategy

> Documento de estratégia. Sem código, sem componentes, sem decisões visuais (cor/logo/tipografia ficam para depois desta direção verbal estar fechada).

---

## 1. Estratégia da homepage

**Objetivo único:** converter um visitante de PME portuguesa numa lead, em poucos segundos de leitura.

O visitante-tipo não procura "tecnologia" — procura alívio de um incómodo (o computador avariou, o backup falhou, ninguém trata disto) ou alívio de uma preocupação recorrente ("não tenho ninguém de confiança para isto"). A homepage tem de servir os dois em simultâneo, sem obrigar nenhum dos dois a ler a página toda.

**Jornada do visitante:**

```
Chega (pesquisa Google / referência)
   ↓
Hero → "isto é para empresas como a minha, e resolve o que eu preciso"
   ↓
Problemas → identificação ("sim, é isto que me acontece")
   ↓
Os dois caminhos → percebe que pode pedir ajuda pontual OU ter um parceiro contínuo
   ↓
Serviços → confirma que cobre a área técnica que precisa
   ↓
Como trabalhamos → reduz incerteza sobre "o que acontece se eu contactar"
   ↓
Porque a SolveIT → reforça confiança face a alternativas (freelancer, loja de informática, "sobrinho que percebe de computadores")
   ↓
FAQ → resolve últimas objeções (preço, compromisso, disponibilidade)
   ↓
CTA final → converte
```

Há duas "rampas de saída" ao longo da página — não é preciso chegar ao fim para converter:
- **Visitante urgente** (tem um problema agora): pode converter logo no hero ou na secção "Os dois caminhos".
- **Visitante em avaliação** (está a decidir se vale a pena ter um parceiro de IT): é nutrido até ao CTA final.

---

## 2. Três alternativas de posicionamento

Cada uma é uma direção de marca coerente, não só uma frase diferente — mudam o ângulo de venda.

### Direção A — "Parceiro de confiança"
Tom: calmo, próximo, relação continuada. É a direção que mais naturalmente conduz à avença.

| | |
|---|---|
| **Headline** | "A sua empresa cresce. A sua informática não devia ser uma preocupação." |
| **Subheadline** | "A SolveIT é o parceiro de tecnologia das pequenas e médias empresas em Portugal. Tratamos do suporte, da segurança e dos backups — para a sua equipa nunca ter de pensar nisso." |
| **CTA principal** | "Fale connosco" |
| **CTA secundário** | "Conhecer os serviços" |

**Prós:** tom mais alinhado com "confiança, proximidade, prevenção"; fácil de sustentar visualmente sem parecer loja de informática.
**Contras:** menos "pesquisável" — não usa linguagem de quem está a googlar um problema concreto agora.

### Direção B — "Alívio imediato"
Tom: direto, prático, fala com quem tem uma dor concreta neste momento.

| | |
|---|---|
| **Headline** | "Problemas de informática a atrasar o seu negócio? Nós resolvemos." |
| **Subheadline** | "Suporte técnico rápido quando precisa, e um plano de manutenção contínua para deixar de ter surpresas. Assistência remota em todo o país, presencial na Grande Lisboa e Margem Sul do Tejo." |
| **CTA principal** | "Peça uma avaliação gratuita" |
| **CTA secundário** | "Tenho um problema agora" |

**Prós:** casa muito bem com pesquisas de intenção imediata ("suporte informático empresas", "assistência informática urgente").
**Contras:** lidera com o modelo avulso (reativo) — contradiz o objetivo estratégico de vender a avença como produto principal; corre o risco de fixar a SolveIT como "quem eu chamo quando avaria", não como parceiro.

### Direção C — "Departamento de IT sem o overhead"
Tom: proposta de valor de negócio, orientada a quem já pensa em ter *alguém responsável* pela IT, não só um "reparador".

| | |
|---|---|
| **Headline** | "Tenha um departamento de IT. Sem ter de o contratar." |
| **Subheadline** | "A SolveIT acompanha, mantém e protege a tecnologia da sua empresa como um parceiro externo — para se focar no que importa: o negócio." |
| **CTA principal** | "Marcar uma conversa" |
| **CTA secundário** | "Ver como funciona a avença" |

**Prós:** é a única das três que já comunica o produto estratégico (avença) diretamente no hero, sem esperar por secções mais abaixo.
**Contras:** ligeiramente mais abstrato para quem não está ainda a pensar em "ter um departamento de IT" — pode não ressoar com quem só quer o computador a funcionar.

*(As frases "It's broken? We Solve IT." e "We solve IT before it breaks." foram avaliadas e não avançam como headline: a primeira é reativa e contraria o posicionamento de parceiro proativo; a segunda funciona melhor como reforço secundário — ver secção 4, "Como trabalhamos".)*

---

## 3. Estrutura recomendada da homepage

9 secções, deliberadamente curtas — nenhuma delas deve exigir scroll interno nem parecer uma página de serviço completa.

| # | Secção | Só homepage / encaminha |
|---|---|---|
| 1 | Hero | Só homepage |
| 2 | Problemas que reconhece | Só homepage |
| 3 | Os dois caminhos (avulso vs avença) | Encaminha para `/servicos/suporte-it` e `/solucoes` |
| 4 | Serviços (grid) | Encaminha para as 6 páginas-pilar |
| 5 | Como trabalhamos | Só homepage |
| 6 | Porque a SolveIT | Só homepage |
| 7 | FAQ (curada, ~5 perguntas) | Homepage tem só as perguntas mais gerais; FAQ completa e específica fica em cada página de serviço |
| 8 | CTA final | Só homepage (mas o formulário é o mesmo componente usado em `/contactos`) |
| 9 | Footer | Global |

Nota sobre a secção 3 ("Os dois caminhos"): é uma secção **nova** face à estrutura originalmente aprovada no `PROJECT_PLAN.md` — nasce diretamente da exigência de que o visitante perceba, de forma explícita, que existem duas formas de trabalhar com a SolveIT (objetivos 4 e 5 do briefing). Substitui a necessidade de uma secção de avenças mais longa a meio da página.

---

## 4. Copy proposta, secção a secção

*(usa a Direção recomendada — ver secção 7. Onde relevante, indico alternativas.)*

### 1. Hero
**Objetivo:** comunicar em menos de 5 segundos o quê + para quem + próxima ação.
**Conteúdo:**
- Headline + subheadline (ver Direção recomendada, secção 7)
- CTA principal + CTA secundário
- Linha de contexto/confiança, pequena, por baixo dos CTAs: *"Suporte remoto em todo o país · Assistência presencial na Grande Lisboa e Margem Sul do Tejo"*

**Razão estratégica:** a linha de área de atuação faz dupla função — gera confiança imediata (não é uma promessa vaga) e reforça sinais de SEO local sem parecer uma palavra-chave forçada.

### 2. Problemas que reconhece
**Headline:** "Alguma vez isto lhe soou familiar?"
**Conteúdo (4 bullets, sem exagero/alarmismo — atualizado após aprovação do cliente):**
- "O computador trava, "o sistema está lento"."
- "Ninguém sabe ao certo onde estão os backups — ou se existem."
- "Um colaborador saiu da empresa e ainda tem acesso a tudo."
- "Sempre que há um problema, é preciso descobrir alguém que perceba disto."

**Linha de fecho:** "Não precisa de resolver isto sozinho."
**CTA:** nenhum (secção de identificação, não de conversão).
**Razão estratégica:** ativa reconhecimento antes de apresentar a solução — sem soar a "medo vendido", só factos do dia a dia de quem não tem IT interno.

### 3. Os dois caminhos
**Headline:** "Duas formas de trabalhar com a SolveIT."
**Conteúdo:** dois cartões lado a lado.

- **Cartão 1 — "Preciso de ajuda agora"**
  "Tem um problema concreto? Resolvemos pontualmente, sem compromisso."
  CTA: "Pedir ajuda pontual" → `/servicos/suporte-it`

- **Cartão 2 — destacado (ex. badge "Recomendado")— "Quero deixar de me preocupar com isto"**
  "Um parceiro que acompanha, previne e mantém a sua informática todos os meses — sem surpresas."
  CTA: "Conhecer a avença" → `/solucoes`

**Razão estratégica:** cumpre diretamente os objetivos 4 e 5 do briefing, e orienta visualmente (via destaque) para a avença como opção recomendada, sem excluir quem só quer ajuda pontual.

### 4. Serviços
**Headline:** "O que tratamos por si."
**Conteúdo:** grid de 6 cartões (um por página-pilar), nome + 1 frase:
- **Suporte IT** — "Suporte remoto e presencial para o dia a dia da sua equipa."
- **Segurança** — "Proteção de equipamentos e redução do risco de incidentes."
- **Backups** — "Cópias de segurança automáticas e monitorizadas."
- **Cloud & Microsoft 365** — "Email empresarial, ficheiros e colaboração, sempre disponíveis."
- **Redes & Wi-Fi** — "Ligação estável e segura em todo o escritório."
- **Consultoria IT** — "Decisões tecnológicas certas, sem complicar."

**CTA por cartão:** "Saber mais" → página-pilar respetiva.
**Razão estratégica:** confirma abrangência técnica e introduz vocabulário próximo das keywords-alvo, sem detalhe técnico — o detalhe fica nas páginas internas.

### 5. Como trabalhamos
**Headline:** "Simples, sem burocracia."
**Conteúdo (3–4 passos):**
1. **Fala connosco** — conte-nos o que se passa, pontual ou contínuo.
2. **Avaliamos** — olhamos para a sua situação atual, sem custos escondidos.
3. **Propomos um plano** — pontual ou avença, à medida do negócio.
4. **Tratamos disto** — e continuamos por perto, antes de haver problema.

**CTA:** nenhum obrigatório (reforço leve opcional de "Fale connosco").
**Razão estratégica:** o medo de "vão-me vender algo que não percebo" é uma das maiores fricções de compra numa PME sem IT interno — mostrar o processo reduz essa ansiedade.

### 6. Porque a SolveIT
**Headline:** "Porque escolher a SolveIT."
**Conteúdo (diferenciadores — confirmados pelo cliente):**
- "Falamos a sua língua, não a de informático."
- "Prevenção antes do problema — não esperamos que avarie." *(liga à narrativa da avença)*
- "Resposta rápida." *(sem número específico — evita comprometer um SLA que ainda não está definido, mas confirma a promessa de rapidez)*

> **Removido (Phase 5, ao implementar `/solucoes`):** "Sem fidelização a contratos longos." — estava publicado aqui como diferenciador definitivo, mas as condições contratuais da avença ainda não estão fechadas. Removido para não contradizer `/solucoes`, que trata a duração de contrato como "definida caso a caso". Pode voltar a esta lista se/quando a política de fidelização for confirmada.

**Razão estratégica:** cumpre a instrução de nunca inventar números/garantias — "Resposta rápida" comunica o benefício sem fixar um SLA em horas que ainda não foi definido internamente.

### 7. FAQ (curada — 5 perguntas)
**Headline:** "Perguntas frequentes."
- "Preciso de mudar de fornecedor de informática para experimentar?"
- "Como funciona a avença mensal?"
- "Trabalham só remotamente ou também presencialmente?"
- "E se eu só precisar de ajuda uma vez?"
- `[placeholder até existir SLA definido]` "Quanto tempo demora a primeira resposta?"

**CTA:** "Ainda tem dúvidas? Fale connosco."
**Razão estratégica:** reduz fricção final e, em formato de pergunta natural, reforça keywords de forma orgânica (bom candidato a featured snippets no Google).

### 8. CTA final
**Headline:** "Vamos resolver a sua informática."
**Subheadline:** "Marque uma conversa sem compromisso — remoto em todo o país, presencial na Grande Lisboa e Margem Sul do Tejo."
**Conteúdo:** formulário curto (nome, empresa, email, telefone, mensagem) + contacto direto visível (telefone/email).
**CTA:** "Fale connosco" (botão de submissão).
**Razão estratégica:** fecha o funil com duas opções de fricção diferente — formulário (baixa fricção, assíncrono) e telefone (alta fricção, imediato) — para captar ambos os perfis de visitante.

### 9. Footer
**Conteúdo:** navegação secundária, contactos, linha de área de atuação repetida ("SolveIT — Suporte informático para empresas em Portugal. Remoto nacional, presencial na Grande Lisboa e Margem Sul do Tejo."), links legais (Política de Privacidade/Cookies), dados legais `[PLACEHOLDER: a confirmar]`.

---

## 5. Estratégia de conversão

**Mapa de CTAs ao longo da página:**

| Secção | CTA | Destino |
|---|---|---|
| Hero | "Fale connosco" / "Marcar uma conversa" (principal) | Scroll para CTA final / `/contactos` |
| Hero | CTA secundário (varia por direção) | Scroll para Serviços ou Solucoes |
| Os dois caminhos | "Pedir ajuda pontual" | `/servicos/suporte-it` |
| Os dois caminhos | "Conhecer a avença" | `/solucoes` |
| Serviços (cada cartão) | "Saber mais" | Página-pilar respetiva |
| FAQ | "Fale connosco" | Scroll para CTA final |
| CTA final | "Fale connosco" (submissão) | Formulário → email |

**Princípio:** nenhuma secção obriga o visitante a avançar linearmente — quem já está convencido no hero converte logo ali; quem precisa de mais confiança tem o caminho completo até ao CTA final.

---

## 6. Estratégia SEO da homepage

Nenhuma keyword é inserida de forma forçada — todas aparecem porque descrevem naturalmente o que está a ser dito sobre público, serviço ou geografia.

| Cluster de keywords | Onde aparece naturalmente |
|---|---|
| suporte informático para empresas / suporte IT | Hero (subheadline), Secção Serviços |
| assistência informática empresas | Secção "Os dois caminhos" (cartão de assistência pontual), FAQ |
| serviços IT para PME | Secção Serviços (introdução), meta description |
| informática para empresas | Footer, linha de contexto do hero |
| serviços informáticos Lisboa / suporte informático Portugal | Linha de área de atuação (hero + footer) — nunca como página dedicada de localização, só como afirmação honesta de cobertura |

Máximo de uma variante exata por secção; o resto é linguagem natural. `H1` único (o headline do hero); hierarquia de `H2` a acompanhar os títulos de cada secção listados acima.

---

## 7. RECOMMENDED HOMEPAGE DIRECTION

**Recomendo a Direção C — "Departamento de IT sem o overhead" — com um ajuste.**

Porquê: dos objetivos definidos no briefing, o mais estratégico é que a homepage conduza *naturalmente* para a ideia da avença, não que a apresente como uma opção entre outras a meio da página. A Direção C é a única das três que já comunica isso no hero, na primeira frase que o visitante lê — antes de qualquer secção. A Direção A é a mais "seguramente confortável" mas fica um passo atrás em clareza de proposta de valor; a Direção B lidera com o modelo errado (reativo/avulso) para o produto que a SolveIT quer vender como principal.

**Ajuste recomendado:** a Direção C, sozinha, pode não ressoar com quem chega com um problema urgente e concreto neste momento (intenção de pesquisa mais imediata). Por isso, a secção 3 ("Os dois caminhos") logo a seguir ao hero é o que resolve essa lacuna — capta esse visitante sem ter de o fazer no próprio hero.

**Hero final recomendado:**
- **Headline:** "Tenha um departamento de IT. Sem ter de o contratar."
- **Subheadline:** "A SolveIT acompanha, mantém e protege a tecnologia da sua empresa como um parceiro externo — para se focar no que importa: o negócio."
- **CTA principal:** "Marcar uma conversa"
- **CTA secundário:** "Ver como funciona a avença"
- **Linha de contexto:** "Suporte remoto em todo o país · Assistência presencial na Grande Lisboa e Margem Sul do Tejo"

**Nota de tonalidade:** evitei o uso repetido de "você" ao longo da copy (embora seja gramaticalmente PT-PT correto, tende a soar mais formal/distante em copy comercial atual) — preferi o padrão "a sua empresa" / segunda pessoa implícita, que costuma ler-se mais natural em PT-PT B2B contemporâneo. Se preferires manter "você" explícito (como no teu exemplo original), é uma alteração simples de fazer em todas as secções.

**Próximo passo depois de aprovares esta direção:** avançar para a identidade visual (logótipo + paleta), já que o Design System (Phase 3 do `PROJECT_PLAN.md`) depende diretamente desta direção verbal estar fechada.
