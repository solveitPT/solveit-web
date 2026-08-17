# SolveIT — Modelo Comercial Oficial

> **Estado: rascunho para validação. Nada aqui está aprovado nem deve ser publicado no site ou usado para cobrar clientes reais até seres tu a confirmar.**
>
> Este documento não altera `SOLUTIONS_STRATEGY.md` nem o site. É o passo anterior a isso.

---

## 0. Fontes usadas

- `PROJECT_PLAN.md`, `HOMEPAGE_STRATEGY.md`, `SOLUTIONS_STRATEGY.md`
- `SERVICE_SUPPORT_IT.md`, `SERVICE_BACKUPS.md`, `SERVICE_SECURITY.md`, `SERVICE_CLOUD.md`, `SERVICE_NETWORKS.md`, `SERVICE_CONSULTING.md`
- `MARKET_PRICING_BENCHMARK.md` (pesquisa de mercado, agosto de 2026 — guardado no projeto nesta mesma sessão)
- Copy já publicada em `src/pages/servicos/suporte-it.astro` e `src/pages/solucoes.astro` (para manter linguagem consistente com o que já está no ar)

**O que este documento explicitamente NÃO tem:** os custos reais da SolveIT (custo/hora do técnico, custo de ferramentas, tempo médio real por cliente). Isso não existe em nenhum documento do projeto. Todos os pontos que dependem disso estão marcados `[VALIDAR]` em vez de um número inventado — ver secção 8.

---

## 1. Princípios do modelo comercial

1. **A avença é o produto principal.** O pontual existe como porta de entrada e como opção legítima para quem não quer/precisa de acompanhamento contínuo — não é um produto "inferior" nem é desincentivado na comunicação.
2. **Sem pacotes de horas pré-pagas.** Nada de packs de 5h/10h/20h, créditos ou "bolsas de horas". Só duas arquiteturas: pontual (paga quando precisa) e avença (paga para ter acompanhamento contínuo).
3. **A avença vende responsabilidade e prevenção, não horas.** A diferença entre tiers é o âmbito do que a SolveIT passa a gerir por si, não um multiplicador de horas incluídas.
4. **Funil comercial:** problema → intervenção pontual → confiança → acompanhamento → avença. Nunca: comprar horas → gastar horas → comprar mais horas.
5. **Transparência de preço com IVA incluído na comunicação ao cliente**, sempre que se apresenta um valor final.
6. **Coerência com o posicionamento já publicado:** "Tenha um departamento de IT. Sem ter de o contratar." — a SolveIT não compete em preço mais baixo, compete em ser um parceiro externo com responsabilidade real pela informática do cliente.

---

## 2. Intervenções pontuais

### 2.1 Tabela comercial

| | Remoto | Presencial |
|---|---|---|
| **Preço base** | €60/h + IVA | €85/h + IVA |
| **Unidade mínima faturável** | 1 hora | 1 hora |
| **Blocos seguintes** | 30 min (€30 + IVA) | 30 min (€42,50 + IVA) |
| **Deslocação — Grande Lisboa / Margem Sul do Tejo** | n/a | Incluída no preço |
| **Deslocação fora da área habitual** | n/a | Avaliada caso a caso |

`[VALIDAR]` — estes valores seguem a faixa que o benchmark de mercado considera defensável para o posicionamento da SolveIT (€55–€65/h remoto, €75–€90/h presencial), mas **não foram confirmados contra os custos reais da SolveIT** (ver secção 8). Escolhi o ponto médio-alto de cada faixa porque o benchmark é explícito: a SolveIT não deve competir no segmento low-cost.

**Porque 1 hora como mínimo, e não 30 min:** simplifica a tabela (pedido explícito: "evita criar uma tabela excessivamente complicada") e evita o problema comercial de cobrar quase o mesmo por uma intervenção de 10 minutos e uma de 25 — quem faz intervenções muito curtas tende a ser precisamente o segmento low-cost que o benchmark recomenda evitar.

**Porque a deslocação dentro da Grande Lisboa/Margem Sul fica incluída:** essa já é a área de atuação presencial declarada em todo o site ("presencial na Grande Lisboa e Margem Sul do Tejo") — cobrar deslocação extra dentro da própria área de cobertura contradiria essa promessa já publicada.

### 2.2 Comunicação de preço (obrigatório mostrar o total com IVA)

Exemplo — intervenção presencial de 1 hora:

```
Base:              €85,00
IVA (23%):         €19,55
────────────────────────
Total a pagar:     €104,55
```

Nunca comunicar isoladamente "€85" sem o total. Esta regra aplica-se a toda a comunicação de preço do site e de propostas — pontual e avença.

### 2.3 Fora da área de atuação presencial

Reutilizar a formulação já publicada em `suporte-it.astro`, para não criar uma segunda promessa a party: *"Fora dessa área, avaliamos caso a caso — se a deslocação se justificar, não está excluída."*

---

## 3. Avença mensal — arquitetura geral

Três tiers. Nomes propostos (não obrigatórios, mas recomendados por ligarem diretamente à promessa da marca):

| Tier | Nome | Frase-resumo |
|---|---|---|
| 1 | **Essencial** | "Tem alguém a quem recorrer." |
| 2 | **Profissional** | "Temos alguém a acompanhar a sua informática." |
| 3 | **Departamento IT** | "A SolveIT funciona como o seu departamento de IT externo." |

O nome do Tier 3 ("Departamento IT") é uma escolha deliberada — torna literal a promessa já publicada na homepage ("Tenha um departamento de IT. Sem ter de o contratar."), reservando essa palavra exata para o nível que mais se aproxima de a cumprir.

---

## 4. Tier 1 — Essencial

**Preço:** €179/mês + IVA → **€220,17/mês com IVA** `[VALIDAR — hipótese dentro da faixa €149–€199 do benchmark; falta confirmar contra custos reais]`

**Para quem:** micro/pequenas empresas (tipicamente até 5–8 postos) que não têm ninguém internamente responsável pela informática, mas que ainda não sentem necessidade de um acompanhamento mais próximo — querem sobretudo deixar de estar sozinhas quando algo corre mal.

**Objetivo:** ser o primeiro passo real de "ter um parceiro", sem ainda ser gestão contínua de todas as áreas.

**Inclui:**
- Suporte remoto para pedidos do dia a dia (sem número fixo de pedidos definido — ver secção 9.1 do `SOLUTIONS_STRATEGY.md`, que já estabelece esta política)
- 1 intervenção presencial completa incluída a cada 2 meses, até 1 hora — **ver secção 6 para a decisão detalhada sobre esta formulação**
- Verificação periódica leve do estado dos equipamentos (não é gestão contínua de segurança/backups — é uma primeira camada de prevenção)

**Não inclui:**
- Gestão contínua de segurança, backups geridos, ou Microsoft 365 gerido (ver `SERVICE_SECURITY.md`, `SERVICE_BACKUPS.md`, `SERVICE_CLOUD.md`) — podem ser pedidos como intervenção pontual, ou o cliente pode subir de tier
- Redes & Wi-Fi geridos, consultoria contínua

**Nível de acompanhamento:** reativo com prevenção leve.

**Intervenções presenciais adicionais:** preço preferencial de €65/h + IVA (vs. €85/h + IVA pontual) `[VALIDAR percentagem/valor exato — depende da margem]`.

---

## 5. Tier 2 — Profissional

**Preço:** €299/mês + IVA → **€367,77/mês com IVA** `[VALIDAR — hipótese dentro da faixa €249–€349 do benchmark]`

**Para quem:** empresas que já dependem fortemente da informática para trabalhar (Microsoft 365, computadores, ligação à internet como ferramentas de trabalho diário) e querem parar de reagir a problemas.

**Objetivo:** acompanhamento próximo e contínuo — a SolveIT passa a gerir ativamente, não só a responder.

**Inclui tudo do Tier 1, mais:**
- Suporte remoto prioritário (atendido antes dos pedidos pontuais e do Tier 1 — sem prometer um tempo fixo de resposta, ver secção 7)
- 1 intervenção presencial incluída por mês, até 2 horas `[VALIDAR duração]`
- Gestão contínua de segurança (ver `SERVICE_SECURITY.md`)
- Backup, monitorização e verificação contínuos (ver `SERVICE_BACKUPS.md`)
- Gestão contínua de Microsoft 365 (ver `SERVICE_CLOUD.md`)
- Revisão periódica agendada `[VALIDAR cadência — ex. trimestral]`

**Não inclui:** gestão de redes/Wi-Fi como serviço contínuo, consultoria estratégica contínua (disponíveis à parte ou no Tier 3).

**Nível de acompanhamento:** preventivo e contínuo nas áreas incluídas.

**Intervenções presenciais adicionais:** preço preferencial de €60/h + IVA `[VALIDAR]`.

---

## 6. Tier 3 — Departamento IT

**Preço:** desde €549/mês + IVA → **desde €675,27/mês com IVA**, ajustado ao número de postos/dispositivos e à complexidade `[VALIDAR — hipótese dentro da faixa €449–€649+ do benchmark; o próprio benchmark já assume que este tier não pode ter preço fixo único]`

**Para quem:** empresas que querem efetivamente deixar de gerir tecnologia internamente — tipicamente as que já sentiram os limites do Tier 2, ou que desde o início têm complexidade suficiente (várias localizações, dependência crítica de sistemas, equipa maior).

**Objetivo:** a SolveIT assume, na prática, o papel de departamento de IT externo.

**Inclui tudo do Tier 2, mais:**
- Componente presencial mais alargada — agendamento prioritário, não necessariamente "mais horas" fixas `[VALIDAR estrutura exata]`
- Redes & Wi-Fi como serviço gerido (ver `SERVICE_NETWORKS.md`)
- Consultoria IT incluída — decisões tecnológicas acompanhadas continuamente, não só quando pedidas (ver `SERVICE_CONSULTING.md`)
- Reuniões de revisão periódicas com reporting `[VALIDAR cadência]`

**Nível de acompanhamento:** gestão contínua e proativa de praticamente toda a informática da empresa.

**Intervenções fora do âmbito acordado:** avaliadas e orçamentadas à parte — mesmo no Tier 3, não existe "ilimitado" (ver secção 7).

---

## 7. A decisão do benefício presencial no Tier 1 (análise pedida)

Pediste para analisar se "½ intervenção presencial incluída por mês" deve significar meia hora, meio período, ou outra unidade — e para propor uma formulação melhor se "½" for confusa.

**A minha análise:** "½ intervenção" é confusa para um cliente — não corresponde a nada físico ("o técnico vem e sai a meio?"). Há duas formas de resolver, com resultados muito diferentes:

**Opção A — meia hora por mês.** Numericamente é "½", mas na prática uma deslocação à Grande Lisboa já consome frequentemente mais de 30 minutos só na viagem — o cliente sente que o benefício é quase simbólico, o que enfraquece exatamente o objetivo que querias (tornar a avença tangível).

**Opção B — 1 intervenção completa (até 1h) a cada 2 meses**, em vez de todos os meses. Matematicamente é a mesma proporção (0,5 intervenções/mês, em média), mas o cliente recebe uma visita real e útil, só que com metade da frequência. É isto que recomendo, e é o que já está escrito nas secções 4–6 acima.

**A minha recomendação:** Opção B — *"1 intervenção presencial completa (até 1 hora), incluída a cada 2 meses."* Fica claro, tangível, e mantém o princípio que definiste (existe uma intervenção presencial periódica incluída na avença) sem prometer uma visita que na prática seria demasiado curta para ser útil.

**Alternativa mais generosa, para comparação:** o próprio benchmark de mercado assume como hipótese "1 intervenção presencial (até 1h) incluída todos os meses" — mais tangível ainda, mas exige confirmar se a margem do Tier 1 aguenta uma visita presencial garantida todos os meses (ver secção 8). Fica como decisão em aberto — ver secção 15.

---

## 8. Diferenciação entre tiers — o que sobe é responsabilidade, não horas

| | Tier 1 — Essencial | Tier 2 — Profissional | Tier 3 — Departamento IT |
|---|---|---|---|
| **O cliente ainda gere...** | A maior parte da segurança/backups sozinho, ou por conta própria | Pouco — a SolveIT já gere segurança, backups e M365 | Quase nada — a SolveIT gere tecnologia de ponta a ponta |
| **A SolveIT é...** | Alguém a quem recorrer | Um parceiro que acompanha | O departamento de IT da empresa |
| **Postura** | Reativa com prevenção leve | Preventiva e contínua | Proativa e estratégica |

A ideia central: subir de tier não significa "receber mais horas" — significa que a SolveIT passa a assumir mais partes da responsabilidade tecnológica que hoje ficam por conta do cliente (ou de ninguém).

---

## 9. O que NÃO estamos a vender

Explícito, para evitar problemas comerciais e legais mais tarde:

- **Suporte 24/7** — não está previsto em nenhum tier.
- **Tempo de resposta garantido em X minutos/horas** — não existe SLA definido; a linguagem pública deve manter-se como já está ("percebemos a urgência do seu caso logo na primeira conversa"), sem números.
- **Substituição gratuita de hardware.**
- **Licenças de software incluídas** sem estarem explicitamente especificadas (ex. Microsoft 365 é gerido, não pago pela SolveIT, salvo indicação contrária).
- **Projetos ilimitados** ou trabalho fora de âmbito sem orçamento prévio — mesmo no Tier 3.
- **Desenvolvimento de software.**
- **Recuperação de dados complexa** como serviço normal incluído (recuperação após incidente grave é avaliada e orçamentada à parte — distinto da gestão preventiva de backups, que essa sim está incluída nos tiers 2 e 3).
- **"Ilimitado"** em qualquer contexto — nem pedidos de suporte, nem intervenções, nem horas.

---

## 10. Economia do negócio

Esta secção é um **framework de cálculo**, não um resultado fechado — porque os inputs de custo não existem em nenhum documento do projeto. Preenchi o que consigo (preços de hipótese), e deixei `[VALIDAR]` tudo o que depende de dados internos da SolveIT que não tenho.

### 10.1 O que falta validar, por ordem de prioridade

| # | Pergunta | Porque importa | Estado |
|---|---|---|---|
| 1 | Quanto custa uma hora técnica à SolveIT (custo de oportunidade do tempo dos 2 sócios, não o preço cobrado)? | Sem isto, não há margem calculável em nenhum tier | `[VALIDAR]` |
| 2 | Tempo médio real esperado por cliente/mês, por tier | Determina quantos clientes cabem na capacidade disponível | `[VALIDAR]` |
| 3 | Custo de deslocação (combustível/tempo, não só o preço cobrado ao cliente) | Afeta diretamente a margem das intervenções presenciais | `[VALIDAR]` |
| 4 | Custo de ferramentas por dispositivo/utilizador (RMM, antivírus/EDR, backup gerido) | Custo fixo recorrente por cliente, independente de horas trabalhadas | `[VALIDAR]` |
| 5 | Quantas horas/semana cada sócio quer dedicar a avenças vs. pontual vs. admin do negócio | Define a capacidade total real, não teórica | `[VALIDAR]` |

### 10.2 Estrutura de cálculo (para preencheres quando tiveres os dados)

Por tier:

```
Receita mensal por cliente        = preço da avença (sem IVA, é o que fica para o negócio)
Custo mensal por cliente          = (tempo médio estimado × custo/hora técnica)
                                     + custo de ferramentas por dispositivo/utilizador
                                     + custo médio de deslocações incluídas
Margem por cliente                = Receita mensal − Custo mensal
Ponto de rutura                   = tier deixa de ser rentável quando o tempo real
                                     gasto ultrapassa consistentemente o tempo
                                     que a receita consegue cobrir
```

### 10.3 Capacidade — a pergunta certa não é "quantos clientes conseguimos ter", é "quantas horas temos"

Com 2 pessoas, a capacidade total de atendimento é finita e conhecida em teoria (nº de sócios × horas/semana disponíveis para clientes, depois de retirar tempo para administração, vendas, e o próprio trabalho de conta própria) — mas esse número não está definido em nenhum documento. Sem ele, qualquer "conseguimos suportar X clientes do Tier 2" seria inventado.

**O que posso dizer com confiança, sem inventar números:** o Tier 3 consome desproporcionalmente mais tempo de acompanhamento por cliente do que o Tier 1 — por isso, mesmo que o preço seja mais alto, o número de clientes Tier 3 que 2 pessoas conseguem servir bem é necessariamente pequeno (provavelmente poucas unidades, não dezenas) antes de a qualidade do serviço degradar. Isto é uma limitação estrutural de uma equipa de 2 pessoas, não uma opinião sobre o modelo de preços.

**Recomendação prática:** definir um número máximo de clientes Tier 3 simultâneos (ex. "não aceitar mais do que N Tier 3 ao mesmo tempo") antes de vender agressivamente esse tier — `[VALIDAR N]`.

### 10.4 Quando um cliente deixa de ser rentável

Um cliente torna-se não rentável quando o tempo real gasto consistentemente ultrapassa o que a avença cobre — tipicamente sinal de que a complexidade do ambiente do cliente não corresponde ao tier em que está. A resposta correta não é absorver o custo indefinidamente, é propor subida de tier ou rever o âmbito na renovação — não está previsto (nem faz sentido, dado o princípio "sem pacotes de horas") cobrar por excedentes pontuais pequenos, mas um padrão recorrente deve desencadear uma conversa sobre o tier certo.

---

## 11. Cliente ideal por tier

Exemplos ilustrativos, não clientes reais — para ajudar a calibrar o critério de aceitação por tier.

| Empresa (exemplo) | Nº pessoas | Complexidade | Tier provável | Motivo |
|---|---|---|---|---|
| Atelier de arquitetura, 3 pessoas | 3 | Baixa — poucos equipamentos, sem servidor próprio | Essencial | Precisa sobretudo de alguém a quem recorrer; não justifica gestão contínua de múltiplas áreas |
| Clínica dentária, 6 pessoas | 6 | Média — depende de software de gestão de pacientes, dados sensíveis | Profissional | Dependência forte de sistemas + necessidade real de segurança/backups geridos, não só reativos |
| Escritório de contabilidade, 10 pessoas | 10 | Média-alta — Microsoft 365 intensivo, prazos críticos (fecho de contas), dados financeiros sensíveis | Profissional ou Departamento IT | Entra no Profissional; sobe para Departamento IT se a dependência de prazos tornar qualquer paragem inaceitável |
| Retalho com 2 lojas + escritório, 15 pessoas | 15 | Alta — múltiplas localizações, rede entre lojas, TPA/POS | Departamento IT | Múltiplas localizações e dependência operacional direta da rede tornam gestão contínua e redes geridas essenciais |
| Empresa de logística, 25+ pessoas, sistemas críticos 24h | 25+ | Muito alta | Fora do âmbito atual | Acima da capacidade realista de uma equipa de 2 pessoas para dar o nível de acompanhamento que o próprio Tier 3 promete — ver secção 10.3 |

**Nota:** o mercado inicial da SolveIT são PME e negócios locais — a tabela reflete isso deliberadamente. Não desenhei o modelo para empresas de 100+ pessoas.

---

## 12. Estratégia de entrada

```
Sem SolveIT
    ↓
Intervenção pontual  ← primeiro contacto, ainda sem compromisso
    ↓
Confiança construída durante essa intervenção
    ↓
Primeira avença (tipicamente Tier 1 ou Tier 2)
    ↓
Tier superior (quando a complexidade/dependência do cliente cresce)
```

### 12.1 A primeira intervenção pontual é a oportunidade de construir confiança

Não deve ser tratada como uma venda isolada — é o momento em que o cliente forma a primeira impressão real (não só o que o site diz). Isto já está implícito na estrutura do funil pedida.

### 12.2 Onboarding pago para quem entra diretamente em avença

**A minha recomendação:** cobrar um fee de onboarding/diagnóstico inicial para quem entra diretamente numa avença (sem ter passado por uma intervenção pontual primeiro).

**Porquê:** um levantamento real do ambiente de IT de uma empresa (equipamentos, acessos, estado de backups, rede, licenciamento) consome várias horas de trabalho genuíno e produz um resultado concreto (um retrato documentado da situação do cliente) — dar isto de graça contradiz o princípio "a avença vende responsabilidade, não horas grátis", e cria o mesmo problema que os pacotes de horas: um incentivo a gastar tempo sem cobrar.

**Proposta:** fee de onboarding de €150–€250 + IVA `[VALIDAR — hipótese, falta confirmar contra tempo real necessário]`, que inclui:
- Levantamento do ambiente IT existente
- Revisão inicial de segurança e backups
- Configuração inicial do acompanhamento (acessos, prioridades, agenda de revisão)

**Isenção/desconto:** se o cliente já teve uma intervenção pontual com a SolveIT nos últimos 30 dias antes de assinar a avença, esse fee é dispensado ou reduzido — a intervenção pontual já deu à SolveIT uma primeira visão real do ambiente do cliente `[VALIDAR regra exata — ex. dispensar completamente vs. desconto de 50%]`.

---

## 13. Pricing recomendado para comunicação pública (site)

### 13.1 Intervenções pontuais — mostrar preço exato

**Recomendação: sim, mostrar publicamente.** É um preço simples de hora, fácil de justificar, baixo risco de comprometer margem, e reforça a transparência que já é um valor do posicionamento SolveIT. Mostrar sempre com IVA incluído (ver secção 2.2).

### 13.2 Avenças — "desde" para Tier 1 e 2, orçamento para Tier 3

**Recomendação:**
- **Tier 1 (Essencial):** mostrar preço exato ou "desde €179/mês + IVA" — é o ponto de entrada, e esconder o preço aqui cria fricção desnecessária logo na porta de entrada do funil.
- **Tier 2 (Profissional):** mostrar como "desde €299/mês + IVA" — sinaliza o ponto de partida sem prometer que serve para qualquer empresa sem avaliação.
- **Tier 3 (Departamento IT):** **não mostrar preço fixo** — "orçamento personalizado, a partir de €549/mês + IVA" ou similar. O próprio benchmark de mercado confirma que este tier varia com nº de postos e complexidade; um número fixo aqui seria enganoso nos dois sentidos (poderia subestimar ou sobrestimar consoante o cliente).

**Porquê não esconder tudo:** a instrução foi clara — não esconder preços só por hábito do setor. Como empresa pequena a entrar no mercado, mostrar preço onde é seguro mostrar (pontual, Tier 1, Tier 2) é uma vantagem competitiva de confiança, não um risco. Só o Tier 3 tem uma razão real (não um hábito) para não ter preço fixo: ele próprio, estruturalmente, não tem preço único.

---

## 14. Resumo — Modelo comercial recomendado

- **Pontual:** €60/h + IVA remoto, €85/h + IVA presencial (deslocação incluída na Grande Lisboa/Margem Sul), mínimo de 1 hora, blocos de 30 min depois disso.
- **Avença Essencial:** €179/mês + IVA — 1 intervenção presencial (até 1h) a cada 2 meses incluída.
- **Avença Profissional:** €299/mês + IVA — segurança, backups e M365 geridos continuamente; 1 intervenção presencial (até 2h) por mês.
- **Avença Departamento IT:** desde €549/mês + IVA, ajustado à empresa — tudo do Profissional + redes geridas + consultoria contínua.
- **Sem pacotes de horas em nenhum nível.**
- **Onboarding pago (€150–250 + IVA) para quem entra direto em avença**, dispensado se vier de uma intervenção pontual recente.
- **Site:** preços visíveis para pontual, Tier 1 e Tier 2; Tier 3 por orçamento.

Todos os valores em euros marcados acima são **hipóteses fundamentadas no benchmark de mercado**, não preços validados contra a economia real da SolveIT — ver secção 10.

---

## 15. Decisões pendentes

1. **Benefício presencial do Tier 1:** confirmar "1 visita completa a cada 2 meses" (minha recomendação) vs. "1 visita todos os meses" (hipótese do benchmark, mais generosa mas por validar economicamente).
2. **Os 5 inputs de custo da secção 10.1** — sem eles, os preços desta secção continuam a ser hipóteses, não uma decisão final de negócio.
3. **Número máximo de clientes Tier 3 em simultâneo** (secção 10.3).
4. **Valor exato do fee de onboarding e da regra de isenção** (secção 12.2).
5. **Percentagem/valor exato do preço preferencial de intervenções presenciais adicionais em avença** (secções 4 e 5).
6. **Cadência exata das revisões periódicas** nos Tiers 2 e 3 (trimestral? outra?).
7. Confirmar se os nomes dos tiers (Essencial / Profissional / Departamento IT) são aprovados, ou se preferes outros.
