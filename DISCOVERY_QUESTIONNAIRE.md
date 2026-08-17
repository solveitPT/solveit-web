# SolveIT — Questionário de Discovery (Phase 0)

Para cada decisão: o que está em causa, as opções com vantagens/desvantagens, e a minha recomendação. Responde com o número da pergunta e a tua escolha (podes ajustar/perguntar antes de decidir).

---

### 1. Stack (framework do site)

O framework é a tecnologia que gera as páginas do site.

| Opção | Vantagens | Desvantagens |
|---|---|---|
| **Astro** | Performance máxima (envia quase zero JavaScript por omissão), excelente para SEO, mais simples de manter a longo prazo, ideal para sites de conteúdo/marketing como este. | Menos preparado "de fábrica" para funcionalidades de aplicação (login, dashboard de cliente) — precisaria de trabalho extra se isso vier a ser necessário. |
| **Next.js** | Mais preparado para evoluir para uma aplicação (área de cliente autenticada, portal), ecossistema React muito grande. | Mais peso e complexidade do que este site precisa agora; envia mais JavaScript ao browser por omissão; manutenção mais exigente para uma equipa pequena. |

**Recomendação:** Astro — a não ser que já tenhas planos concretos e próximos para um portal de cliente autenticado.

**A tua escolha:** Astro

---

### 2. Hosting (onde o site fica alojado)

| Opção | Vantagens | Desvantagens |
|---|---|---|
| **Vercel** | Excelente experiência de utilização, cada alteração gera automaticamente uma pré-visualização, rede rápida na Europa. | Plano gratuito tem limites de utilização; custos podem escalar com tráfego. |
| **Cloudflare Pages** | Plano gratuito muito generoso, rede global muito rápida, se o domínio também estiver na Cloudflare fica tudo no mesmo sítio. | Configuração de funções serverless (para o formulário de contacto) é ligeiramente diferente/menos direta. |
| **Netlify** | Muito fácil de usar, tem gestão de formulários incluída (poupa ter de configurar envio de email à parte). | Plano gratuito mais limitado que o da Cloudflare. |

**Recomendação:** Vercel ou Cloudflare Pages — equivalentes para este projeto. Netlify vale a pena só pela conveniência dos formulários nativos.

**A tua escolha:** Cloudflare Pages

---

### 3. Domínio

| Opção | Vantagens | Desvantagens |
|---|---|---|
| **.pt** | Reforça "empresa portuguesa" junto do público-alvo, ajuda em SEO local. | Registo normalmente exige NIF português (simples se a empresa já estiver constituída). |
| **.com** | Sem requisito de NIF, imagem mais "internacional". | Menos imediatamente reconhecível como negócio local. |

**Recomendação:** `.pt`, dado o posicionamento explícito para PME portuguesas.

**A tua escolha (e nome pretendido, ex. solveit.pt):** .com

---

### 4. Analytics (medição de visitas)

| Opção | Vantagens | Desvantagens |
|---|---|---|
| **Plausible / Fathom** (privacidade-first) | Não usa cookies, normalmente não obriga a banner de consentimento RGPD, interface simples, alinhado com o posicionamento de confiança da marca. | Métricas menos detalhadas que o GA4; tem custo mensal (não é gratuito). |
| **Google Analytics 4** | Gratuito, muito detalhado, integra com Google Ads/Search Console. | Usa cookies → exige banner de consentimento RGPD com opt-in explícito; mais um elemento legal/UI para gerir. |

**Recomendação:** Plausible/Fathom, para simplificar a parte legal e reforçar a mensagem de confiança. GA4 se preferires gratuito e não te incomodar o banner de cookies.

**A tua escolha:** Google Analytics 4
---

### 5. Destino dos leads (o que acontece ao submeter o formulário)

| Opção | Vantagens | Desvantagens |
|---|---|---|
| **Só email** | Simples, rápido de implementar, sem custo extra. | Sem histórico centralizado nem forma fácil de medir conversão ao longo do tempo. |
| **Email + registo (Airtable/Notion/CRM leve)** | Histórico de leads pesquisável, base para reporting. | Mais uma integração para configurar e manter. |
| **WhatsApp (como canal adicional)** | Canal preferido por muitos donos de PME em Portugal, resposta percebida como mais rápida. | Não deve substituir o formulário — perde-se registo estruturado e consentimento RGPD claro. |

**Recomendação:** Começar só com email (mais simples e rápido de lançar); adicionar registo em CRM mais tarde sem alterar o site. WhatsApp como botão adicional, não como substituto.

**A tua escolha:** Só email

---

### 6. Área de atuação real

Não é uma escolha técnica — é informação que preciso para escrever copy honesta e configurar corretamente o SEO local (o site não deve prometer cobertura que não existe).

**Pergunta:** A SolveIT atende remotamente a nível nacional? E presencialmente, em que distrito(s)/concelho(s)?

**Resposta:** a Nivel nacional, remoto todo o lado presencial na grande lisboa / margem sul do tejo 
---

### 7. Transparência de preços

| Opção | Vantagens | Desvantagens |
|---|---|---|
| **Mostrar faixas/tiers indicativos** (ex. "a partir de X€/mês") | Reduz fricção — donos de PME preferem transparência; filtra à partida quem não está no orçamento certo. | Exige que a estrutura de preços já esteja definida internamente; concorrência vê os valores. |
| **Só "pedir orçamento"** | Flexibilidade total para adaptar a proposta a cada cliente; não expõe pricing. | Mais fricção — parte dos visitantes desiste sem saber sequer a ordem de grandeza. |

**Recomendação:** Se já houver uma estrutura de preços interna definida, mostrar faixas indicativas (sem valores exatos). Caso contrário, "pedir orçamento" para já, e revisitar quando os preços estiverem fechados.

**A tua escolha:** vou mostrar os valores reais, mas para já ainda não estão definidos mantem esta parte em aberto

---

### 8. Uso da tagline "We Solve IT"

| Opção | Vantagens | Desvantagens |
|---|---|---|
| **Headline principal da homepage** | Memorável, trocadilho forte. | Reduz clareza imediata para público não-técnico que lê rápido — contraria o objetivo nº1 do site (perceber rapidamente o que a empresa faz). |
| **Assinatura de marca junto ao logótipo** | Mantém o trocadilho na identidade visual sem sacrificar clareza; hero principal fica em português, direto ao ponto. | — |

**Recomendação:** Assinatura de marca; hero principal em português.

**A tua escolha:** Assinatura de marca junto ao logótipo

---

### 9. Fotografia vs ilustração

| Opção | Vantagens | Desvantagens |
|---|---|---|
| **Fotografia real da equipa/escritório** | Reforça "proximidade" e confiança — pessoas reais, não stock. Diferencia de concorrência genérica. | Exige sessão fotográfica profissional (custo, tempo); precisa de haver equipa/escritório fotografável já. |
| **Ilustração/gráficos abstratos** | Disponível imediatamente, controlo total do estilo, sem dependências externas. | Menos "humano" à primeira vista se não for bem executado. |

**Recomendação:** Ilustração para o lançamento (não há fricção de agenda/custo), substituindo por fotografia real assim que existir — não é uma escolha definitiva, é sequencial.

**A tua escolha:** Ilustração/gráficos abstratos

---

### 10. Dados legais da empresa

Necessários para o rodapé e a Política de Privacidade (podem ser dados depois, mas bloqueiam o lançamento final).

**Preciso de:** Nome legal da empresa, NIF, morada da sede social.

**Resposta:** _______ (podes deixar em branco por agora e enviar mais tarde)

---

### 11. Logótipo / identidade visual

**Pergunta:** Já existe logótipo/paleta de cores definida, ou isso faz parte deste projeto (nesse caso entra na Phase 1 — Brand)?

**Resposta:** não existe ainda faz parte do projecto

---

### 12. Aprovação da arquitetura de informação consolidada

Proposta: 6 páginas-pilar de serviço (suporte-it, segurança, backups, cloud-microsoft-365, consultoria-it, redes-e-wifi opcional) em vez da lista original mais fragmentada; homepage com 9 secções em vez de 11 (ver `PROJECT_PLAN.md`, secções 4 e 5).

**A tua resposta (aprovar / ajustar):** aprovar

---

### 13. Secção de testemunhos/prova social

| Opção | Vantagens | Desvantagens |
|---|---|---|
| **Omitir completamente na v1** | Evita a perceção de "site incompleto" numa secção que existe precisamente para gerar confiança. | — |
| **Placeholder "brevemente"** | Nenhuma vantagem clara. | Pode comunicar inexperiência/site por acabar. |

**Recomendação:** Omitir, e adicionar assim que houver testemunhos reais.

**A tua escolha:** Omitir, e adicionar assim que houver testemunhos reais.
---

## Como responder

Podes responder aqui mesmo no chat, número a número (nem todas precisam de resposta longa — várias têm a recomendação como resposta implícita se concordares). Onde não tiveres a informação ainda (ex. dados legais, fotografia), diz "a confirmar depois" e seguimos com placeholder marcado.
