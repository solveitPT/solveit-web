# SolveIT — Project Plan

> Documento de planeamento. Nenhum código ou conteúdo final foi criado a partir deste documento — serve para alinhar decisões antes da implementação.

> **Phase 0 — Discovery: concluída.** Ver secção 13 ("Decisions Locked") para o resultado. As secções deste documento foram atualizadas para refletir as decisões tomadas.

---

## 1. Resumo da análise

O diretório do projeto está vazio (só contém `.claude/` com skills instaladas). Não existe stack, repositório git, package.json nem assets. Isto é um **greenfield project** — proponho stack de raiz, sem restrições de legado.

---

## 2. Crítica à proposta inicial

Pontos onde a proposta original é ajustada, com justificação:

1. **Estrutura de serviços demasiado fragmentada.** A lista de serviços (suporte, redes/Wi-Fi, M365, email, backups, segurança, endpoints, equipamentos, cloud, consultoria, monitorização, avenças) daria ~10+ páginas finas, más para SEO (conteúdo diluído, canibalização de keywords) e más para manutenção. **Consolidar em 6 páginas-pilar** (secção 4).
2. **Homepage com 11 secções tem redundância.** "Proposta de valor" (3) e "Porque escolher a SolveIT" (8) sobrepõem-se; "Prevenção/backups/segurança" (6) repete conteúdo que já vive em Serviços e Avenças. **Reduzir para 9 secções**, sem repetição (secção 5).
3. **Secção de testemunhos/prova social.** Instrução explícita foi não inventar nada — mas uma secção de testemunhos vazia ou com "placeholder" visível é pior do que não a ter (parece site incompleto/pouco confiável, o oposto do objetivo). **Recomendação: omitir esta secção completamente na v1**, e substituí-la por afirmações de compromisso verificáveis (ex.: "resposta em X horas úteis", "sem fidelização a contratos longos") — só se a SolveIT se comprometer a cumpri-las.
4. **"We Solve IT" como headline principal.** O público-alvo é dono de PME não-técnico, em Portugal. Um hero 100% em inglês reduz clareza imediata (contraria o objetivo nº1: "perceba rapidamente o que a SolveIT faz"). **Recomendação: usar "We Solve IT" como tagline de marca/assinatura junto ao logótipo, mas o hero principal em português.**
5. **"It's broken? We Solve IT."** é uma framing reativa (conserto depois de avariar) que contradiz o modelo de negócio pretendido (avença, prevenção, parceiro contínuo). Boa para uma página de suporte pontual, má como mensagem principal da marca.
6. **Publicar preços ou não é uma decisão de negócio, não de design** — ver Decisions Required.

---

## 3. Arquitetura técnica proposta

### 3.1 Stack

**Decidido: Astro + TypeScript + Tailwind CSS, deploy em Cloudflare Pages.**

Justificação:
- O site é essencialmente conteúdo estático/marketing (não uma aplicação com estado/autenticação). O Astro envia **zero JS por omissão** e só hidrata os componentes interativos (formulário de contacto, acordeão FAQ, menu mobile) — o melhor ponto de partida possível para Core Web Vitals e SEO.
- Content Collections do Astro tratam páginas de serviços/FAQ como dados tipados (Markdown/MDX + schema), sem precisar de CMS na v1.
- Tailwind acelera consistência do design system (tokens = configuração central) sem CSS solto por página.
- Caminho de crescimento claro: se no futuro precisarem de uma área de cliente autenticada (portal, tickets), isso pode viver como uma app à parte (ex. Next.js) sem reescrever o site institucional.

**Alternativa considerada: Next.js (App Router).** Mais indicado se, desde já, estiver planeada uma área de cliente/portal autenticado a curto prazo. Para um site institucional de lead-gen, é mais peso do que o necessário.

### 3.2 Hosting

**Decidido: Cloudflare Pages.** Plano gratuito generoso, rede rápida na Europa. Como o formulário de contacto (Phase 6) vai correr como função serverless, usaremos **Cloudflare Pages Functions** (Workers) em vez de Vercel Functions/Netlify Functions — a arquitetura de `/src` mantém-se igual, só muda o runtime da função de envio de email.

### 3.3 Estrutura de pastas (alto nível, sem código)

```
/src
  /components      → Button, Card, ServiceCard, FAQItem, Nav, Footer, CTASection, Hero, Badge
  /layouts          → BaseLayout, ServiceLayout, LegalLayout
  /pages
    index.astro
    servicos/index.astro
    servicos/suporte-it.astro
    servicos/redes-e-equipamentos.astro   (ou fundida em suporte-it — ver Decisions Required)
    servicos/seguranca.astro
    servicos/backups.astro
    servicos/cloud-microsoft-365.astro
    servicos/consultoria-it.astro
    solucoes.astro
    sobre.astro
    contactos.astro
    politica-privacidade.astro
    politica-cookies.astro
  /content          → content collections (serviços, FAQ) com schema tipado
  /styles           → design tokens (cores, tipografia, espaçamento) como variáveis CSS / config Tailwind
  /assets           → ícones (svg), imagens, og-image
/public
  robots.txt, favicon, sitemap (gerado automaticamente)
```

### 3.4 SEO técnico (base para todas as páginas)

- Título e meta description únicos por página, seguindo template consistente.
- Open Graph + Twitter Card por página (imagem própria, não genérica).
- URL canónica, `hreflang=pt-PT`.
- Sitemap XML gerado no build + `robots.txt`.
- Dados estruturados (schema.org): `Organization`/`LocalBusiness` no layout base, `Service` nas páginas de serviço, `FAQPage` na secção de FAQ, `BreadcrumbList` nas páginas internas.
- Hierarquia de headings correta (um único `<h1>` por página), texto alternativo em todas as imagens.
- Core Web Vitals como critério de aceitação em todas as fases de UI (não só no fim).

### 3.5 Analytics e formulário

- **Analytics: decidido GA4.** Consequência direta: o site **precisa de banner de consentimento de cookies** com opt-in granular antes de o GA4 disparar (o script só deve carregar depois do consentimento, não antes com bloqueio a posteriori). Isto entra como componente obrigatório no design system (Phase 3) e como texto legal na Política de Cookies (Phase 8) — deixou de ser opcional.
- Formulário de contacto: função serverless (Cloudflare Pages Function) → envio de email (ex. Resend) + honeypot/anti-spam. Checkbox de consentimento RGPD obrigatório, com link para Política de Privacidade. Destino: só email (sem CRM/planilha na v1).

---

## 4. Sitemap / Arquitetura de informação proposta

```
/                                  Homepage
/servicos                          Serviços (visão geral, grid → páginas-pilar)
/servicos/suporte-it                Suporte remoto + presencial, manutenção, gestão de equipamentos, monitorização
/servicos/redes-e-wifi              (opcional — ver Decisions Required: fundir em suporte-it ou manter separado)
/servicos/seguranca                 Segurança informática + proteção de endpoints
/servicos/backups                   Backups e recuperação / continuidade de negócio
/servicos/cloud-microsoft-365       Cloud, Microsoft 365, email empresarial
/servicos/consultoria-it            Consultoria tecnológica + monitorização
/solucoes                          Avenças / modelo de parceria (planos, se decidido publicar)
/sobre                             Sobre a SolveIT
/contactos                         Contactos (formulário + telefone + email + morada se aplicável)
/politica-privacidade              Legal — RGPD
/politica-cookies                  Legal — cookies
/blog                              (placeholder de rota — Phase 12, não lançar vazio)
```

Notas:
- Não criar páginas de localização (`/lisboa`, `/porto`) na v1 — risco de thin/duplicate content sem base de clientes real nessas zonas. Reconsiderar em Phase 12 com dados reais de onde vêm os leads.
- `/blog` fica reservado na arquitetura de URLs desde já, para não ter de migrar links/SEO mais tarde, mas só é construído em fase futura.

---

## 5. Homepage — estrutura proposta (revista)

1. **Hero** — proposta de valor clara em PT + CTA primário + CTA secundário.
2. **O problema que reconhece** — 3–4 situações comuns de PME sem IT interno (computador lento, medo de perder dados, ninguém a apoiar quando algo falha) — gera identificação.
3. **Serviços** — grid das 6 páginas-pilar, cada uma com 1 frase, sem detalhe técnico.
4. **Como trabalhamos** — processo em 3–4 passos (ex.: Conversa inicial → Avaliação → Proposta → Acompanhamento contínuo).
5. **Modelo de parceria (avenças)** — avença mensal, previsibilidade de custo, inclui prevenção/monitorização/backups — é aqui que entra a narrativa de "prevenção antes do problema".
6. **Porque escolher a SolveIT** — diferenciadores reais e verificáveis (linguagem simples, sem jargão; resposta em X horas úteis; sem fidelização longa) — placeholders marcados até serem confirmados.
7. **FAQ** — objeções reais de compra (preço, duração de contrato, horário de suporte, se atendem remoto/presencial).
8. **CTA final** — repetição do CTA principal, tom convidativo, não agressivo.
9. **Footer** — navegação secundária, contactos, links legais, redes sociais (se existirem).

---

## 6. Design System (proposto)

| Token | Direção |
|---|---|
| **Cor primária** | Azul profundo/confiante (não roxo/violeta — evita estética "AI startup") |
| **Cor secundária/CTA** | Um accent quente (âmbar/laranja) só para ações — cria contraste com o azul, humaniza |
| **Neutros** | Cinzentos quentes / off-white, não cinza puro — sensação "premium acessível" |
| **Tipografia títulos** | Sans-serif geométrica/humanista forte (ex. família tipo Inter/Manrope/General Sans) |
| **Tipografia corpo** | Mesma família ou par com boa legibilidade em texto longo |
| **Radius** | Moderado (8–12px) — amigável sem parecer app "SaaS AI" (pill-shape em tudo) |
| **Sombras** | Subtis, só em cards, nunca decorativas |
| **Espaçamento** | Grid 4/8pt |
| **Breakpoints** | Mobile-first: 375 / 640 / 768 / 1024 / 1280 / 1440 |
| **Ícones** | Set de line-icons monocromático (ex. Phosphor/Lucide) — não clipart de tecnologia |
| **Imagem** | Evitar stock photos de "pessoas de fato" e servidores; preferir ilustração/gráficos abstratos geométricos na v1, até existirem fotos reais da equipa/escritório |

---

## 7. Direção de copy (estrutura, não texto final)

Padrão recomendado para a mensagem central, alinhado com a sugestão do utilizador:

> **"Você trata do seu negócio. Nós tratamos da sua informática."**

Avaliação das taglines propostas:
- **"We Solve IT."** → **decidido**: assinatura de marca junto ao logótipo (não como headline principal).
- **"It's broken? We Solve IT."** → reativa, contradiz o posicionamento de parceiro proativo. Usar (traduzida) apenas em contexto de suporte pontual, não na homepage.
- **"We solve IT before it breaks."** → boa para a secção de avenças/prevenção (traduzir para PT).
- **"You run your business. We solve the IT."** → estrutura forte, é a base do padrão de copy recomendado acima.
- **"Your IT department, without the IT department."** → boa para a secção de avenças (posicionamento "parceiro externo").

---

## 8. Estratégia SEO

- **Técnico**: ver secção 3.4.
- **Conteúdo**: cada página-pilar-de-serviço visa um cluster de keywords (ex. `/servicos/backups` → "backups empresas", "backup automático PME"), com FAQ genuína na própria página (reforça SEO + reduz fricção de compra).
- **Local**: depende de decisão sobre área de atuação real (ver Decisions Required). `LocalBusiness` schema só deve declarar área de serviço que a empresa consegue mesmo cobrir.
- **Longo prazo (Phase 12)**: blog/recursos para autoridade temática (guias práticos, não conteúdo de AI/tecnologia avançada, para não desviar do posicionamento PME).

---

## 9. Legal / RGPD

- Política de Privacidade e Política de Cookies como páginas dedicadas.
- **Banner de consentimento de cookies: obrigatório** (decidido GA4 na secção 3.5). O GA4 só deve carregar depois de consentimento explícito (opt-in), não antes com bloqueio a posteriori — isto é um requisito RGPD, não um "nice to have".
- Formulário de contacto: checkbox de consentimento explícito + link para política de privacidade + finalidade de tratamento de dados declarada.
- Dados legais da empresa (NIF, sede, nome legal) — **ainda por fornecer**. Usar placeholders claramente marcados `[PLACEHOLDER: A CONFIRMAR]` até serem fornecidos; **bloqueador de lançamento** até serem substituídos por dados reais.

---

## 10. Diretrizes de comunicação — backups e segurança

Confirmado e reforçado o instinto do utilizador. Evitar sempre claims absolutos ("100% seguro", "proteção garantida"). Preferir linguagem de mitigação de risco:
- "Reduzimos o risco de perda de dados."
- "Backups automáticos e monitorizados."
- "Preparação para recuperação após falhas ou incidentes."
- "Proteção e continuidade do negócio."

Esta diretriz aplica-se a toda a copy de `/servicos/seguranca` e `/servicos/backups`, e deve ser revista antes de qualquer publicação (risco legal de overclaiming).

---

## 11. Plano de execução por fases

### PHASE 0 — Discovery ✅ CONCLUÍDA
**Objetivo:** Fechar todas as decisões de negócio/técnicas que bloqueiam design e conteúdo.
**Resultado:** Ver secção 13 ("Decisions Locked"). Stack, hosting e analytics fechados; dados legais e nome de domínio exato ainda pendentes (não bloqueiam o início do Phase 1).

### PHASE 1 — Brand & Content ✅ CONCLUÍDA
**Resultado:** Direção verbal aprovada (`HOMEPAGE_STRATEGY.md`) e identidade visual aprovada (`BRAND_IDENTITY.md` + `SYMBOL_EXPLORATION.md`) — Direção B (wordmark + símbolo), Paleta 3 (Grafite + Âmbar), Manrope + Inter, iconografia line, ilustração abstrata, e símbolo final ("Abertura ampla — curvatura reforçada").

**Objetivo (histórico):** Definir identidade verbal e visual mínima — **inclui criação de logótipo de raiz**, já que não existe nenhum ativo de marca atual.
**Tarefas:** Criar logótipo + paleta de cores + tipografia (de raiz, conforme decidido no Discovery); escrever copy real da homepage e páginas-pilar com base nas direções da secção 7 (hero em português, "We Solve IT" como assinatura de marca); recolher/confirmar diferenciadores reais (secção 5.6); confirmar nome de domínio exato em `.com` e verificar disponibilidade.
**Ficheiros/componentes:** Nenhum código ainda — documento de brand + copy deck + ficheiros de logótipo (SVG/PNG).
**Dependências:** Phase 0.
**Critérios de aceitação:** Logótipo aprovado, copy da homepage e de 1 página de serviço aprovada pelo cliente.
**Riscos:** Sem inputs reais do negócio (diferenciadores, tom), tanto o logótipo como a copy arriscam ficar genéricos — este é o phase com mais dependência de input direto do cliente.
**Resultado esperado:** Logótipo + brand guide leve + copy deck aprovado.

### PHASE 2 — UX / Information Architecture
**Objetivo:** Validar sitemap final e wireframes de baixa fidelidade.
**Tarefas:** Aprovar sitemap (secção 4), wireframes da homepage e de 1 página-pilar, fluxo de conversão (CTA → formulário → confirmação).
**Dependências:** Phase 0, Phase 1.
**Critérios de aceitação:** Sitemap e wireframes aprovados.
**Riscos:** Mudar IA depois do Phase 4+ é caro (recriação de componentes/rotas).
**Resultado esperado:** Wireframes aprovados + sitemap final.

### PHASE 3 — Design System ✅ IMPLEMENTADA (pendente revisão visual final)
**Resultado:** Tokens, tipografia, componentes base, Header/Footer e página `/showcase` implementados em Astro + Tailwind v4. Ver `DESIGN_SYSTEM.md` para detalhe completo e decisões pendentes. Build de produção sem erros; falta uma passagem visual do cliente em `npm run dev` antes de avançar para Phase 4.

**Objetivo (histórico):** Construir os tokens e componentes base reutilizáveis.
**Tarefas:** Definir tokens (cor, tipografia, espaçamento — secção 6) em Tailwind config; construir componentes base (Button, Card, Nav, Footer, FAQItem, ServiceCard, Hero, CTASection, **CookieConsentBanner** — obrigatório dado o GA4, ver secção 9) em Storybook ou página de estilo isolada.
**Ficheiros/componentes:** `/src/styles`, `/src/components/*`.
**Dependências:** Phase 1 (identidade visual aprovada).
**Critérios de aceitação:** Componentes revistos visualmente em isolamento, responsivos, acessíveis (contraste AA, focus states).
**Riscos:** Sem este passo, cada página fica inconsistente e retrabalho aumenta nas fases seguintes.
**Resultado esperado:** Design system funcional e documentado.

### PHASE 4 — Homepage ✅ IMPLEMENTADA (pendente revisão visual final)
**Resultado:** Homepage implementada em `src/pages/index.astro` seguindo a Direção 3 — "A Travessia" (ver `HOMEPAGE_ART_DIRECTION.md`), com a disciplina editorial da Direção 1 aplicada à secção de serviços. Copy 100% de `HOMEPAGE_STRATEGY.md` — nada inventado. Build e `astro check` sem erros. Falta a mesma revisão visual pendente da Phase 3 (o ambiente de preview automatizado desta sessão não compõe frames).

**Objetivo (histórico):** Implementar a homepage completa com a estrutura da secção 5.
**Tarefas:** Compor secções com os componentes do design system; ligar CTAs ao formulário/Phase 6.
**Dependências:** Phase 2, Phase 3.
**Critérios de aceitação:** Homepage responsiva, Core Web Vitals dentro de metas (LCP < 2.5s, CLS < 0.1), sem conteúdo placeholder visível.
**Riscos:** Tentação de adicionar secções fora do plano — manter disciplina de 9 secções.
**Resultado esperado:** Homepage pronta para revisão.

### PHASE 5 — Service Pages ✅ CONCLUÍDA (6/6 páginas-pilar + /solucoes + /sobre implementadas)
**Progresso:** As 6 páginas-pilar de serviço, `/solucoes` e `/sobre` estão implementadas — `/servicos/suporte-it`, `/servicos/backups`, `/servicos/seguranca`, `/servicos/cloud-microsoft-365`, `/servicos/redes-e-wifi`, `/servicos/consultoria-it`, `/solucoes`, `/sobre` (ver `SERVICE_SUPPORT_IT.md`, `SERVICE_BACKUPS.md`, `SERVICE_SECURITY.md`, `SERVICE_CLOUD.md`, `SERVICE_NETWORKS.md`, `SERVICE_CONSULTING.md`, `SOLUTIONS_STRATEGY.md`, `ABOUT_STRATEGY.md`) — cada uma com estrutura e narrativa próprias, não cópias entre si; fronteiras de âmbito entre páginas mantidas consistentes via cross-links em vez de duplicar promessas. `/servicos` (índice) liga às 6. `/solucoes` explica o modelo de avença sem preços/SLA/duração de contrato (nada disso está fechado comercialmente) e reutiliza `ServiceCard` pela primeira vez numa página real, dentro de um contentor emoldurado para não parecer repetição de `/servicos`. `/sobre` é deliberadamente mais curta e sem FAQ — dá contexto humano (porquê, para quem, como trabalhamos) sem repetir conteúdo comercial já coberto em `/solucoes`; sem história da empresa/números de equipa inventados, por decisão explícita do cliente. `BaseLayout` inclui canonical + Open Graph básico.

> ✅ **Inconsistência resolvida:** "Sem fidelização a contratos longos." removido da homepage (`index.astro`, `showcase.astro`, `HOMEPAGE_STRATEGY.md`) — o cliente confirmou que as condições contratuais ainda não estão fechadas. A lista "Porque escolher a SolveIT" fica com 3 itens em vez de 4.

**Objetivo (histórico):** Construir as 6 páginas-pilar de serviço + `/servicos` + `/solucoes` + `/sobre`.
**Tarefas:** Layout de página de serviço reutilizável (`ServiceLayout`), conteúdo aprovado no Phase 1, FAQ por página, internal linking entre páginas. Em `/solucoes`: estrutura preparada para mostrar faixas de preço reais assim que definidas (decidido no Discovery — preços ainda não fechados), lançar com CTA "peça uma avaliação" no lugar dos valores, sem redesenhar a página quando os preços ficarem prontos.
**Dependências:** Phase 3, Phase 1.
**Critérios de aceitação:** Todas as páginas com título/meta únicos, FAQ funcional, sem duplicação de conteúdo entre páginas.
**Riscos:** Conteúdo fraco/duplicado prejudica SEO — validar unicidade antes de publicar.
**Resultado esperado:** Todas as páginas de serviço publicadas em staging.

### PHASE 6 — Lead Generation ✅ CONCLUÍDA
**Resultado:** `/contactos` implementada — hero, formulário (Nome/Empresa/Email obrigatórios, Telefone opcional, Mensagem obrigatória), contacto direto por email, nota de expectativas, CTA final. Envio via **Web3Forms** (não Resend/Cloudflare Functions, conforme secção 3.5 original) — decisão revista porque ainda não há hosting/domínio/conta Cloudflare configurados; Web3Forms evita infraestrutura própria nesta fase. Validação client-side com mensagens de erro acessíveis (`role="alert"`, `aria-invalid`, `aria-describedby`), estado de loading, estado de sucesso e de erro com fallback para o email direto, honeypot anti-spam. `.env`/`PUBLIC_WEB3FORMS_ACCESS_KEY` documentado em `.env.example` — a chave real fica de fora do código-fonte por decisão do cliente, apesar de a Web3Forms considerar esta chave segura para ser pública. Access Key real fornecida pelo cliente e testada com um envio real de ponta a ponta (email de teste confirmado a chegar a `solveit.email@gmail.com`).

**Objetivo (histórico):** Formulário de contacto funcional e fiável.
**Tarefas:** Formulário com validação, honeypot anti-spam, envio de email, estados de sucesso/erro claros, acessível por teclado.
**Dependências:** Phase 0 (decisão de destino de leads), Phase 3.
**Critérios de aceitação:** Email de teste recebido de forma fiável, sem spam falso-positivo, formulário acessível por teclado.
**Riscos:** Plano gratuito do Web3Forms limitado a 250 submissões/mês — suficiente para o volume esperado de uma PME, mas a acompanhar se o spam automático se tornar um problema (o botcheck honeypot reduz este risco, mas a Web3Forms recomenda hCaptcha para proteção mais forte — não implementado nesta fase por precisar de configuração adicional na conta).
**Resultado esperado:** Fluxo de conversão end-to-end funcional.

### PHASE 7 — SEO
**Objetivo:** Implementar SEO técnico e validar SEO de conteúdo.
**Tarefas:** Meta tags, Open Graph, sitemap.xml, robots.txt, schema.org (`Organization`, `Service`, `FAQPage`, `BreadcrumbList`), verificação Google Search Console.
**Dependências:** Phase 4, Phase 5.
**Critérios de aceitação:** Rich results test sem erros; sitemap indexado; sem keyword stuffing.
**Riscos:** Reclamações de área de serviço não coincidentes com a realidade (penalização/perda de confiança).
**Resultado esperado:** Site pronto para indexação.

### PHASE 8 — Legal / GDPR
**Objetivo:** Conformidade legal mínima para lançamento.
**Tarefas:** Política de Privacidade, Política de Cookies, banner de consentimento (se aplicável), textos de consentimento no formulário, dados legais reais no footer.
**Dependências:** Phase 0 (dados legais reais), Phase 6.
**Critérios de aceitação:** Nenhum placeholder legal visível; banner de cookies coerente com o analytics escolhido.
**Riscos:** Lançar com dados legais placeholder — **bloqueador de lançamento**.
**Resultado esperado:** Site em conformidade RGPD.

### PHASE 9 — Performance / Accessibility
**Objetivo:** Garantir qualidade técnica transversal.
**Tarefas:** Auditoria Lighthouse (Performance/SEO/Accessibility/Best Practices), correção de contraste, navegação por teclado, `alt` text, lazy-loading de imagens.
**Dependências:** Phases 4–8 concluídas.
**Critérios de aceitação:** Lighthouse ≥ 90 em todas as categorias, sem erros de acessibilidade críticos (axe).
**Riscos:** Animações/imagens mal otimizadas no fim do processo — deve ser validado continuamente, não só aqui.
**Resultado esperado:** Site tecnicamente robusto.

### PHASE 10 — Testing
**Objetivo:** Validação cross-browser/dispositivo e revisão de conteúdo final.
**Tarefas:** Testes em Chrome/Safari/Firefox/Edge, mobile real (iOS/Android), revisão de copy final (incluindo guardrails da secção 10), teste do formulário em produção-simulada.
**Dependências:** Phase 9.
**Critérios de aceitação:** Sem bugs visuais/funcionais bloqueadores; copy revista e aprovada.
**Resultado esperado:** Site pronto para deploy.

### PHASE 11 — Deployment ✅ SITE NO AR (`https://solve-it.pt`)
**Resultado:** Repositório em [github.com/solveitPT/solveit-web](https://github.com/solveitPT/solveit-web). Deploy feito na Cloudflare (Workers & Pages, projeto `solveit-web`) via **upload estático manual** (não Git-conectado — a integração "Connect to Git" falhou por um erro temporário do lado do GitHub Apps; ficou registado como possível melhoria futura, sem urgência). Domínio `solve-it.pt` registado via dominios.pt, nameservers apontados para a Cloudflare (`mona.ns.cloudflare.com` / `peyton.ns.cloudflare.com`), domínio custom adicionado ao Worker. HTTPS automático confirmado a funcionar. Formulário de `/contactos` testado em produção com um envio real — confirmado a chegar a `solveit.email@gmail.com`.

**Nota:** como o deploy é por upload manual, alterações futuras ao código exigem `npm run build` local + novo upload manual (ou reativar a ligação Git quando o erro do GitHub Apps resolver) — não há deploy automático a cada `git push` por agora.

**Pendente:** submissão de sitemap ao Google Search Console; analytics (GA4, decidido no Discovery mas ainda não implementado); `www.solve-it.pt` como domínio adicional (opcional).

**Objetivo (histórico):** Publicar em produção.
**Tarefas:** Configurar domínio, SSL, DNS, variáveis de ambiente (email/analytics), deploy em produção, submissão de sitemap ao Google Search Console.
**Riscos:** DNS/propagação, certificados SSL — ambos resolvidos sem incidentes de fundo (a exceção foi a perda do domínio `solveit.pt` original por um problema de verificação de email no registrador anterior, não relacionado com Cloudflare).

### PHASE 12 — Future improvements
**Objetivo:** Roadmap pós-lançamento (não bloqueia o lançamento).
**Candidatos:** Blog/recursos (autoridade SEO), testemunhos reais assim que existirem, páginas de localização (se houver dados reais de procura), CMS headless se o volume de conteúdo justificar, área de cliente autenticada (se o negócio evoluir nesse sentido), expansão de serviços para cloud/cybersecurity/automação avançada (conforme mencionado, mas fora do âmbito da v1).

---

## 12. Riscos gerais do projeto

1. **Scope creep** — 6 páginas de serviço + soluções + legal em simultâneo. Mitigação: priorizar homepage + 1–2 páginas-pilar para validação antes de escalar às restantes.
2. **Dados legais/reais em falta** — testemunhos, NIF, morada, área de serviço. Mitigação: placeholders claramente marcados + checklist de bloqueio de lançamento (Phase 8).
3. **Overclaiming em backups/segurança** — risco legal e de credibilidade. Mitigação: revisão de copy dedicada (Phase 10) contra a secção 10 deste documento.
4. **Convergência visual com outros sites MSP** (grelhas genéricas de ícone+texto). Mitigação: investir em voz visual própria no Phase 3 (cor, ilustração, tipografia) sem contrariar o pedido de simplicidade/poucas animações.
5. **Decisão de analytics/cookies tardia** afeta componentes (banner) e legal — deve fechar-se no Phase 0, não depois.

---

## 13. DECISIONS LOCKED (resultado do Discovery — 2026-08-16)

| # | Decisão | Resultado | Nota |
|---|---|---|---|
| 1 | Stack | **Astro + TypeScript + Tailwind** | Conforme recomendado. |
| 2 | Hosting | **Cloudflare Pages** | Formulário de contacto usa Cloudflare Pages Functions. |
| 3 | Domínio | **`solve-it.pt`** — confirmado e registado (2026-08-17) | Decisão revista duas vezes: inicialmente `.com` (secção 13 antiga), depois `solveit.pt` (registado via Amen.pt) — perdido por um problema de verificação de email na Amen, não recuperável a tempo. Domínio final: **`solve-it.pt`** (com hífen), registado via dominios.pt. Continua alinhado com a recomendação inicial (`.pt` para reforço de "empresa portuguesa"/SEO local); a transferir DNS para Cloudflare. |
| 4 | Analytics | **Google Analytics 4** | Contrário à recomendação — implica banner de consentimento de cookies **obrigatório** (RGPD, opt-in antes do script carregar). Impacto direto em Phase 3 e Phase 8. |
| 5 | Destino dos leads | **Só email** | Sem CRM/planilha nem WhatsApp na v1. |
| 6 | Área de atuação | **Remoto: nacional. Presencial: Grande Lisboa / Margem Sul do Tejo.** | Usar exatamente esta área na copy e no schema `LocalBusiness` — não alargar sem validação. |
| 7 | Preços | **Mostrar valores reais — mas ainda não definidos** | `/solucoes` lança com CTA de orçamento, estrutura pronta para receber faixas de preço assim que fechadas internamente (sem exigir redesenho). **Item em aberto** — precisa de follow-up antes do Phase 5 ou fica com placeholder até lá. |
| 8 | Tagline "We Solve IT" | **Assinatura de marca junto ao logótipo** | Conforme recomendado. Hero principal em português. |
| 9 | Fotografia vs ilustração | **Ilustração/gráficos abstratos** | Conforme recomendado. |
| 10 | Dados legais da empresa | **Por fornecer** | Placeholder `[A CONFIRMAR]` até serem dados — bloqueador de lançamento (Phase 8), não de arranque. |
| 11 | Logótipo | **Não existe — a criar no projeto** | Entra explicitamente no Phase 1 como entregável. |
| 12 | IA consolidada (6 páginas-pilar, homepage 9 secções) | **Aprovado** | Sem alterações à estrutura proposta. |
| 13 | Secção de testemunhos | **Omitir na v1** | Conforme recomendado; adicionar quando existirem testemunhos reais. |

**Itens ainda em aberto (não bloqueiam o arranque, mas precisam de fecho antes das fases indicadas):**
- Estrutura de preços da avença → antes do Phase 5 (ou lança-se `/solucoes` só com CTA de orçamento e atualiza-se depois sem redesenho).
- Dados legais da empresa (NIF, nome legal, sede) → antes do Phase 8 (bloqueador de lançamento).

---

## 14. RECOMMENDED NEXT STEP

Discovery está fechado. **Próximo passo: Phase 1 — Brand & Content.**

Como não existe logótipo nem paleta de marca, este é o phase com maior dependência de trabalho criativo de raiz: logótipo, paleta de cores, tipografia, e a primeira versão de copy real da homepage + 1 página de serviço (em português, com "We Solve IT" só como assinatura). Proponho começar pela identidade visual (logótipo + paleta), porque o Design System (Phase 3) depende diretamente dela — sem isso, os componentes ficam bloqueados.

Ação concreta: queres que avance já para a criação do logótipo/identidade visual (posso gerar direções visuais para escolheres), ou preferes começar pela copy da homepage primeiro?
