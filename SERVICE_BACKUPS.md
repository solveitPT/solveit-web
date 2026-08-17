# SolveIT — Página de Serviço: Backups

> Estratégia/conteúdo, ao nível de `SERVICE_SUPPORT_IT.md`. Estrutura própria (9 secções, diferente da de Suporte IT) — mesma linguagem visual, narrativa adaptada ao tema.
>
> **Estado: aprovado, pronto para implementação.** Todas as decisões de âmbito estão fechadas.

---

## 1. Mensagem central

> "Se o computador principal da sua empresa falhasse amanhã, conseguia continuar a trabalhar?"

Um backup útil não é "ter uma cópia" — é conseguir mesmo recuperar. Narrativa condutora: **Backup → Monitorização → Verificação → Recuperação**. A secção 5 existe especificamente para desfazer a falsa sensação de segurança de "temos um backup" quando nunca foi testado.

**Não prometido em lado nenhum da página:** recuperação garantida, RPO/RTO específicos, retenções específicas, número de cópias, armazenamento cloud específico, 100% de proteção, recuperação de ransomware garantida. Onde a copy precisaria de um número concreto, uso `[CONFIRMAR]`.

---

## 2. Estrutura da página

### 1. Hero
**Headline:** "Se o computador principal da sua empresa falhasse amanhã, conseguia continuar a trabalhar?"
**Subheadline:** "Um backup só é útil se conseguir mesmo recuperar os seus dados quando precisar. Tratamos da cópia, da verificação e da recuperação — não só de copiar ficheiros."
**CTA:** principal "Marcar uma conversa" → `#contacto`; secundário "Ver como funciona" → `#como-funciona`.
**Imagem:** sim — ver secção 4. Layout assimétrico (texto ~60% esquerda, imagem ~35-40% direita, 4:5), a mesma técnica já usada noutras secções do site — aqui aplicada ao hero porque esta página não usa a Travessia (reservada à homepage), por isso não há conflito de foco.
**Razão estratégica:** a pergunta direta substitui uma afirmação — obriga o visitante a responder mentalmente antes de ler mais.

### 2. As formas mais comuns de perder dados
**Headline:** "As formas mais comuns de perder dados."
**Copy (lista):**
- "Um disco avaria sem aviso."
- "Alguém apaga uma pasta importante sem querer."
- "Um ficheiro fica corrompido e ninguém dá por isso durante semanas."
- "Um ataque encripta os seus ficheiros e pede resgate para os devolver."
- "Existe uma cópia de segurança — mas nunca ninguém verificou se funciona."

**Linha de fecho:** "É por isto que ter só 'uma cópia' não costuma chegar."
**Razão estratégica:** o último item é deliberado — introduz o problema central da página (backup não testado) antes da secção 5 o resolver.

### 3. O que protegemos
**Headline:** "O que protegemos."
- **Computadores e equipamento principal** — o computador ou servidor que a sua empresa não pode perder.
- **Ficheiros e documentos de trabalho** — contratos, faturas, dados de clientes.
- **Email e Microsoft 365** — disponível como serviço; a sua inclusão na avença base ou como extra fica definida quando a estrutura de preços estiver fechada.
- **Sistemas específicos do seu negócio** — software de faturação ou gestão, avaliados caso a caso, consoante o sistema em questão.

### 4. Como funciona o sistema de backups
**Headline:** "Como funciona." *(id `#como-funciona`, alvo do CTA secundário do hero)*
**Copy (a narrativa condutora, em 4 passos — números justificados, é uma sequência real):**
1. **Backup** — cópias automáticas dos seus dados. A frequência é definida de acordo com a importância dos dados e a forma como a sua empresa trabalha, não é um número fixo para toda a gente.
2. **Monitorização** — verificamos que as cópias estão mesmo a acontecer, sem precisar de estar a vigiar.
3. **Verificação** — testamos periodicamente que os dados guardados conseguem realmente ser restaurados.
4. **Recuperação** — quando é preciso, restauramos os dados — é o objetivo desde o início.

### 5. Uma cópia só vale alguma coisa se souber que funciona
**Headline:** "Uma cópia de segurança só vale alguma coisa se souber que funciona."
**Copy:** "Não basta configurar um backup uma vez e esquecer. Monitorizamos se as cópias estão a acontecer como esperado, e testamos periodicamente a recuperação — para a primeira vez que restauramos os seus dados não ser também a primeira vez que descobrimos se funciona."
**Razão estratégica:** é a secção que mais diferencia "ter uma cópia" de "ter um backup a sério" — o argumento central pedido no briefing.

### 6. Recuperação quando é necessário
**Headline:** "Recuperação quando é necessário."
**Copy:** "Se perder ficheiros, se um equipamento avariar, ou se for alvo de um incidente como um ataque de ransomware, o processo de recuperação começa de imediato: identificamos o que precisa de ser restaurado, e repomos os dados a partir da cópia mais recente e íntegra disponível. Cada situação é avaliada individualmente — não prometemos que qualquer cenário é sempre 100% recuperável, mas a recuperação é sempre a nossa prioridade imediata."
**Razão estratégica:** cumpre a instrução de não prometer recuperação garantida, sem soar evasivo — explica o processo, não o resultado.

### 7. Pontual ou acompanhamento contínuo
**Headline:** "Pontual ou acompanhamento contínuo."
- **Pontual** — "Configuração inicial de um sistema de backups, ou apoio pontual numa recuperação, sem compromisso continuado."
- **Avença** — "Backup, monitorização e verificação contínuos, como parte do acompanhamento regular da sua informática — para nunca ter de se perguntar se está protegido."

**CTA:** "Conhecer a avença" → `/solucoes` (link neutro, sem badge — mesma disciplina de `SERVICE_SUPPORT_IT.md`).

### 8. FAQ
**1. Com que frequência são feitas as cópias de segurança?**
Não há uma frequência única para todas as empresas — definimos a frequência de acordo com a importância dos dados e a forma como a sua empresa trabalha, não um número genérico aplicado a todos os casos.

**2. Como sabem que o backup está a funcionar sem eu ter de verificar?**
Monitorizamos se as cópias estão a acontecer como esperado, e testamos periodicamente se conseguimos mesmo restaurar os dados — não ficamos à espera de precisar para descobrir se funciona.

**3. Se eu for vítima de um ataque de ransomware, conseguem recuperar tudo?**
Não podemos garantir a recuperação total em todos os cenários — cada incidente é diferente — mas o objetivo do sistema de backups é precisamente permitir recuperar os seus dados sem ter de pagar um resgate. Avaliamos cada situação caso a caso.

**4. Os backups ficam guardados onde?**
As cópias são sempre mantidas em localizações separadas do equipamento original — não faria sentido guardar o backup no mesmo sítio que pode falhar. Consoante o cenário, podemos combinar armazenamento local e cloud.

**5. Preciso de ter backups mesmo sendo uma empresa pequena?**
Sim — o risco de perder dados não depende do tamanho da empresa. Muitas vezes, uma empresa pequena sente mais o impacto de perder ficheiros importantes, precisamente por não ter uma equipa de IT interna para reagir rapidamente.

**CTA:** "Ainda tem dúvidas? Fale connosco." → `#contacto`.

### 9. CTA final
**Headline:** "Vamos proteger os seus dados."
**Subheadline:** "Descreva a sua situação atual — remoto em todo o país, presencial na Grande Lisboa e Margem Sul do Tejo."
**Conteúdo:** mesmo formulário reutilizado (`CtaSection` + `FormGroup`/`Input`/`Textarea`).

---

## 3. Design

Direção 3 — A Travessia **não repetida** aqui (reservada à homepage). Reutiliza integralmente tokens, tipografia, componentes e o registo "calmo" já estabelecido em `/servicos/suporte-it`.

## 4. Imagem

Uma imagem, no hero (ver secção 2.1). Ficheiro já fornecido e tratado: `src/assets/images/services/backup-drive-status-light.jpg` — disco externo com luz de estado acesa, ambiente calmo, luz natural. Literaliza "monitorização" sem clichés (sem servidor dramático, sem azul).

## 5. SEO

**Title:** "Backups para Empresas"
**Meta description:** "Backup, monitorização e verificação de dados para a sua empresa, com foco em conseguir recuperar quando for preciso — não apenas copiar ficheiros."
**H1:** "Se o computador principal da sua empresa falhasse amanhã, conseguia continuar a trabalhar?"
**H2/H3:** "As formas mais comuns de perder dados." / "O que protegemos." / "Como funciona." / "Uma cópia de segurança só vale alguma coisa se souber que funciona." / "Recuperação quando é necessário." / "Pontual ou acompanhamento contínuo." / "Perguntas frequentes." / "Vamos proteger os seus dados."
**Intenções de pesquisa:** "backup empresas", "backup automático empresas", "cópias de segurança empresas", "recuperação de dados empresas", "proteção de dados PME".

---

## Decisions required

Nenhuma por resolver.

**Decisões fechadas pelo cliente:**
- Email/Microsoft 365: serviço disponível, não assumido como incluído na avença base — inclusão/pricing definidos posteriormente.
- Sistemas específicos do negócio: caso a caso.
- Frequência: sem número fixo — definida pela importância dos dados e forma de trabalho da empresa.
- Armazenamento: sem arquitetura única prometida — cópias em localizações separadas do equipamento original, combinando local e cloud consoante o cenário.
- Backup ≠ recuperação garantida de ransomware (mantido explicitamente na secção 6 e FAQ 3).
- Posicionamento mantido como Backup + Monitorização + Verificação + Recuperação, não "fazer cópias".
