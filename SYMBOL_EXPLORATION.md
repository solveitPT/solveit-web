# SolveIT — Symbol Exploration (Direction B, 2ª iteração)

> Refinamento **apenas do símbolo** da Direção B. Wordmark, Paleta 3 (Grafite + Âmbar), Manrope/Inter, iconografia line e direção de ilustração mantêm-se exatamente como aprovados — nada disso foi alterado aqui.

## Porque o símbolo anterior foi rejeitado

O traço em "visto" lia-se demasiado perto de um checkmark de segurança/aprovação — comunicava "verificado" antes de comunicar "SolveIT". Precisava de uma geometria que não pertencesse já a outra categoria visual (segurança, produtividade, SaaS genérico).

## 5 alternativas conceptuais

*(Ver board visual para os desenhos, incluindo teste de legibilidade a tamanho muito pequeno.)*

### 1. Nó que se desfaz (recomendado)
**Conceito:** um enrolamento/espiral fechado que se estica e liberta numa linha reta e limpa.
**Porque encaixa na SolveIT:** é a única das cinco com ressonância direta na língua portuguesa — "desatar um nó" é a expressão idiomática para resolver um problema difícil. Não é uma metáfora traduzida do inglês, nasce diretamente do português.
**Porque evita clichés:** não é checkmark, não é escudo, não é nenhum ícone de categoria "cyber/IT" — é uma metáfora física universal (algo emaranhado a ficar simples).
**A tamanho pequeno:** funciona bem se reduzido a uma volta de espiral + uma linha — testado no board a 18px.
**Risco:** se tiver mais do que uma volta de espiral, perde legibilidade a tamanhos muito pequenos — a versão final tem de ser desenhada com o mínimo de curvas possível.

### 2. Alinhamento
**Conceito:** três barras curtas, cada uma menos inclinada do que a anterior, terminando numa barra perfeitamente vertical — desordem a tornar-se ordem, lida da esquerda para a direita num único olhar.
**Porque encaixa:** comunica estabilidade/consistência — relevante para o argumento de "parceiro que mantém tudo em ordem", não só quem resolve uma crise pontual.
**Porque evita clichés:** geometria pura, sem nenhuma associação a categorias de TI.
**A tamanho pequeno:** o mais robusto dos cinco — geometria simples, sem curvas, resiste bem a qualquer redução.
**Risco:** é o conceito mais genérico dos cinco — "barras a alinhar" é um padrão usado em várias categorias fora de IT, menos exclusivo à SolveIT do que o nó.

### 3. "S" em transformação
**Conceito:** um traço que começa angular/em ziguezague e termina numa curva suave — uma alusão abstrata ao "S" de Solve, sem ser uma letra literal.
**Porque encaixa:** liga-se diretamente ao nome sem competir com as direções tipográficas (A/C) já exploradas.
**Porque evita clichés:** não pertence a nenhuma categoria de ícone de TI.
**A tamanho pequeno:** risco — a diferença entre "ziguezague" e "curva suave" tende a perder-se a tamanhos de favicon, podendo colapsar num traço sem significado claro.
**Risco:** o mais difícil de garantir legível em todos os tamanhos pedidos.

### 4. Dobra resolvida
**Conceito:** uma forma com um canto vincado/dobrado de um lado, e um canto perfeitamente liso do lado oposto — algo rugoso a tornar-se plano.
**Porque encaixa:** metáfora fresca de "resolver" (alisar) que nenhuma das outras direções explorou.
**Porque evita clichés:** não pertence a nenhum cliché de cybersecurity/IT listado.
**Risco real:** o "canto dobrado" é uma convenção visual já usada universalmente para representar "página/documento" — há risco de má-leitura ("isto é um ícone de ficheiro?") em vez de comunicar a ideia pretendida. Recomendo não avançar com esta direção sem testar com utilizadores reais.

### 5. Ponto de convergência
**Conceito:** vários traços curtos e soltos, em ângulos diferentes, a convergir e fundir-se num único traço sólido.
**Porque encaixa:** talvez a ligação conceptual mais forte ao modelo de negócio — muitos problemas dispersos tornam-se um único parceiro que trata de tudo. É uma boa metáfora visual da avença.
**Porque evita clichés:** desenhado propositadamente com traços retos (não pontos/círculos) para não ser lido como "nós de rede" — risco a vigiar na execução final.
**A tamanho pequeno:** funciona, mas exige atenção ao número de traços (não mais de 4) para não colapsar num borrão.
**Risco:** se mal executado (traços a parecerem pontos), aproxima-se do cliché "network nodes" explicitamente a evitar.

## Recomendação final (histórico do processo)

**Direção 1 — Nó que se desfaz.**

É a que combina melhor os critérios pedidos: lê-se sem o wordmark, funciona a preto e branco e a tamanho muito pequeno com o mínimo de traços, não pertence a nenhuma categoria visual já ocupada por outra marca de TI, e tem uma ligação genuína (não traduzida) à língua e ao raciocínio português de "desatar um nó". A Direção 5 (Ponto de convergência) é a alternativa mais forte se preferirem um símbolo mais geométrico/menos orgânico — tem a ligação conceptual mais próxima ao modelo de avença, mas exige mais cuidado de execução para não se aproximar do cliché de "rede".

---

## Símbolo final aprovado

Depois de várias rondas de refinamento (incluindo uma correção por leitura anatómica indesejada e um desvio experimental para um conceito de "S deitado/infinito" que foi descartado por se aproximar demasiado de ícones genéricos de loop DevOps/CI-CD), o processo voltou ao conceito original "nó que se desfaz" e convergiu na seguinte versão:

**"Abertura ampla — curvatura reforçada" (2A).** Um anel quase fechado (grafite #1E2124) com uma pequena linha reta e curta a libertar-se (âmbar #D98C2B), terminada em corte plano — sem ponta redonda, sem gancho, sem leitura de cadeado (a linha sai sempre para cima/lado, nunca para baixo).

Geometria de referência (SVG, viewBox 0 0 40 40, escalar proporcionalmente para cada aplicação):
```
Anel (grafite):   M22.5 13.5 A9 9 0 1 1 15 25   — stroke-width ~3.4 (escalar até ~6 a 16px), stroke-linecap round
Libertação (âmbar): M15.6 24.2 L22.5 18          — stroke-width ~3.4 (escalar até ~4.4 a 16px), stroke-linecap square
```

**Estado:** aprovado pelo cliente. Esta é a versão final do símbolo da Direção B — não avançar para mais rondas de exploração sem pedido explícito. Os ficheiros vetoriais de produção (variações de tamanho, espessura otimizada por breakpoint, exports finais) ficam para a Phase 3 — Design System.
