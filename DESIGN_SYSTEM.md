# SolveIT — Design System (Phase 3)

> Implementação viva do design system, construída sobre a identidade aprovada em `BRAND_IDENTITY.md` e `SYMBOL_EXPLORATION.md`. Pré-visualização em `/showcase`. Nenhuma página final do site foi construída nesta fase — ver `PROJECT_PLAN.md` para as fases seguintes (Homepage, Service Pages).

---

## 1. Stack

- **Astro** (static output) + **TypeScript**
- **Tailwind CSS v4** via `@tailwindcss/vite` (CSS-first config com `@theme`, sem `tailwind.config.js`)
- **Manrope** e **Inter** self-hosted via `@fontsource-variable/*` (variable fonts — um único ficheiro cobre todos os pesos, sem CDN externo)
- Zero frameworks de UI (React/Vue/etc.) — componentes `.astro` puros, HTML nativo sempre que possível

## 2. Design tokens

Fonte de verdade: `src/styles/global.css`, bloco `@theme` + `:root`.

| Categoria | Tokens |
|---|---|
| Cor | `--color-graphite`, `--color-secondary`, `--color-amber`, `--color-amber-hover`, `--color-amber-tint`, `--color-bg`, `--color-surface`, `--color-text`, `--color-muted`, `--color-border`, `--color-error`, `--color-error-bg` |
| Tipografia | `--font-heading` (Manrope Variable), `--font-body` (Inter Variable) |
| Radius | `--radius-sm` (6px), `--radius-md` (10px), `--radius-lg` (16px) |
| Sombra | `--shadow-sm`, `--shadow-md` (sempre tingidas de grafite, nunca preto puro) |
| Motion | `--duration-fast/base/slow`, `--ease-standard` |
| Layout | `--container-content` (1280px), `--container-prose` (68ch) |

Os tokens de cor/tipografia/radius/sombra usam a namespace `@theme` do Tailwind v4, por isso geram automaticamente utilitários (`bg-graphite`, `text-amber`, `rounded-lg`, etc.) além de ficarem disponíveis como `var(--color-graphite)` em CSS. Motion e layout ficam fora da namespace do Tailwind (não têm utilitário dedicado) e são usados diretamente via `var()`.

## 3. Tipografia

Escala fluida via `clamp()` — sem overrides manuais por breakpoint. Aplicada tanto aos elementos semânticos (`h1`–`h6`) como a classes equivalentes (`.h1`–`.h6`) para os casos em que o peso visual não deve corresponder ao nível semântico da página.

| Elemento | Fonte | Peso | Tamanho (mobile → desktop) |
|---|---|---|---|
| H1 | Manrope | 800 | 36px → 56px |
| H2 | Manrope | 700 | 28px → 36px |
| H3 | Manrope | 700 | 22px → 24px |
| H4 | Manrope | 700 | 18px → 20px |
| H5 | Manrope | 600 | 18px |
| H6 | Manrope | 600 | 16px |
| Body | Inter | 400 | 16px |
| `.body-lg` | Inter | 400 | 18px |
| `.text-small` / `small` | Inter | 400 | 14px |
| `.label` | Inter | 600, uppercase, tracking 0.08em | 12px |

## 4. Componentes (`src/components/`)

| Componente | Ficheiro | Notas |
|---|---|---|
| Logo | `Logo.astro` | Geometria do símbolo aprovado (2A) embutida — **não editar path data**. Props: `variant` (full/mark), `theme` (color/mono), `wordmark` (two-tone/mono), `size`. |
| Icon | `Icon.astro` | 13 ícones curados, grelha 24px, traço 1.6px. Sem clichés de TI. |
| Button | `Button.astro` | `primary` (âmbar), `secondary` (contorno grafite), `ghost`. Renderiza `<a>` ou `<button>` consoante `href`. |
| Card | `Card.astro` | Base para qualquer bloco elevado; `interactive` ativa hover lift. |
| ServiceCard | `ServiceCard.astro` | Card + IconContainer + Icon + link "Saber mais". |
| Badge | `Badge.astro` | `amber` (preenchido) / `graphite` (contorno). |
| IconContainer | `IconContainer.astro` | Moldura arredondada para ícones em cards. |
| FaqItem | `FaqItem.astro` | `<details>/<summary>` nativo — **zero JavaScript**. |
| SectionHeading | `SectionHeading.astro` | Eyebrow + H2 + parágrafo de apoio; `align` left/center. |
| CtaSection | `CtaSection.astro` | Banda full-width, tom `graphite` ou `surface`. Aceita `<slot name="heading">` para título com destaque parcial, e `<slot />` default para conteúdo livre (ex. formulário) em vez dos botões — usado na CTA final da homepage. |
| Header | `Header.astro` | Menu mobile com ~10 linhas de JS (toggle de classe); nav desktop 100% CSS. |
| Footer | `Footer.astro` | Colunas de navegação + placeholders legais claramente marcados. |
| Input / Textarea / FormGroup | `form/*.astro` | Estilo `.field` partilhado (definido uma vez em `global.css`); estados default/hover/focus/inválido. |

## 5. Estados

| Estado | Implementação |
|---|---|
| Hover | `:hover` em CSS — botões escurecem o âmbar, cards elevam com `--shadow-md`, links passam a âmbar. |
| Focus | `:focus-visible` global — anel **grafite** sobre fundos claros, anel **âmbar** sobre fundos escuros (`.surface-dark`). Nunca removido. |
| Active | Botão primário desloca 1px no `:active` (feedback tátil). |
| Disabled | `opacity: 0.45` + `pointer-events: none` + `aria-disabled`/`disabled`. |
| Validação/erro | `.field--invalid` (borda vermelha) + `FormGroup` mostra `role="alert"` associado via `aria-describedby`. |

## 6. Responsive

Mobile-first, breakpoints Tailwind por omissão (`sm` 640 / `md` 768 / `lg` 1024 / `xl` 1280). O header muda de menu colapsável (`<768px`) para navegação inline (`≥768px`) por CSS; a tipografia escala continuamente via `clamp()` em vez de saltos por breakpoint.

## 7. Acessibilidade

- **Contraste verificado (WCAG AA)**: grafite sobre âmbar ≈5.9:1, branco sobre grafite ≈16:1, `--color-muted` sobre branco ≈4.8:1.
- **Âmbar nunca é cor de texto isolada sobre fundo claro** (≈2.7:1 — falha AA). Só usado como preenchimento sólido (com texto grafite), ícone, borda ou elemento grande.
- **Foco**: `:focus-visible` global, nunca `outline: none` sem substituto.
- **Motion**: `@media (prefers-reduced-motion: reduce)` anula globalmente durações de transição/animação.
- **HTML semântico**: `<header>`, `<nav>`, `<main>`, `<footer>`, `<details>` nativos — o acordeão de FAQ e o disclosure não dependem de ARIA simulado por JavaScript.
- **Teclado**: todos os componentes interativos (botões, links, accordion, menu mobile) são operáveis só com teclado.

## 8. Conteúdo

Toda a copy usada em `/showcase` vem de `HOMEPAGE_STRATEGY.md` (aprovada). Onde ainda não existe copy real (respostas de FAQ, número de telefone, dados legais), está marcado explicitamente como `[PLACEHOLDER]` — nunca inventado.

## 9. Como rever

```bash
npm run dev
```

Abrir `http://localhost:4321/showcase`.

## 9b. Correção de acessibilidade (Phase 4)

O botão do menu mobile em `Header.astro` tinha 40×40px — abaixo do alvo mínimo de toque de 44×44px (WCAG 2.2 AA / Apple HIG / Material). Corrigido para 44×44px durante a revisão de acessibilidade da homepage.

## 10. Decisões pendentes

1. **Nome de domínio exato** — footer usa placeholder de email até estar confirmado (`PROJECT_PLAN.md`, itens em aberto).
2. **Dados legais da empresa** (NIF, nome legal, sede) — placeholder no footer, bloqueador de lançamento (não de desenvolvimento).
3. **SLA de resposta** — usado como placeholder no FAQ e na secção "Porque a SolveIT"; a confirmar com o cliente antes da Phase 6.
4. **Verificação visual em browser real** — a pré-visualização automatizada usada nesta sessão não consegue compor frames (limitação do ambiente, não do código); a lógica de interação (accordion nativo, toggle do menu mobile) foi validada via DOM/CSSOM, mas recomendo uma passagem visual rápida em `npm run dev` num browser normal antes de aprovar definitivamente.
