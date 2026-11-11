---
name: Alex Rabelo — Portfólio
description: Portfólio profissional de plataforma/SRE/DevOps com metáfora de interface de sistema (telemetria do profissional), tema escuro, fonte mono + sans e acento único ciano.
colors:
  primary: "#66fcf1"
  neutral-bg: "#050607"
  neutral-surface: "#161B22"
  neutral-surface-2: "#1C2430"
  neutral-surface-3: "#24303d"
  neutral-border: "#2B3742"
  neutral-border-strong: "#3A4756"
  neutral-text: "#E6EDF3"
  neutral-text-dim: "#8B949E"
  neutral-text-mute: "#94A3B8"
typography:
  display:
    fontFamily: "JetBrains Mono", ui-monospace, SFMono-Regular, Menlo, monospace
    fontSize: "3rem"
    lineHeight: 1.05
    letterSpacing: "-0.02em"
  headline:
    fontFamily: "Inter", system-ui, -apple-system, sans-serif
    fontSize: "2rem"
    fontWeight: 600
    lineHeight: 1.2
    letterSpacing: "-0.01em"
  title:
    fontFamily: "Inter", system-ui, -apple-system, sans-serif
    fontSize: "1.5rem"
    fontWeight: 600
    lineHeight: 1.35
  body:
    fontFamily: "Inter", system-ui, -apple-system, sans-serif
    fontSize: "1rem"
    lineHeight: 1.6
  label:
    fontFamily: "JetBrains Mono", ui-monospace, SFMono-Regular, Menlo, monospace
    fontSize: "0.8125rem"
    letterSpacing: "0.06em"
rounded:
  sm: "4px"
  md: "6px"
  lg: "12px"
  full: "9999px"
spacing:
  1: "8px"
  2: "16px"
  3: "24px"
  4: "32px"
  5: "48px"
  6: "64px"
  8: "128px"
components:
  button-ghost:
    backgroundColor: "transparent"
    textColor: "{colors.neutral-text}"
    rounded: "{rounded.sm}"
    padding: "8px 16px"
  button-primary:
    backgroundColor: "{colors.primary}"
    textColor: "{colors.neutral-bg}"
    rounded: "{rounded.sm}"
    padding: "8px 16px"
  card:
    backgroundColor: "{colors.neutral-surface-2}"
    textColor: "{colors.neutral-text}"
    rounded: "{rounded.md}"
    padding: "24px"
  navigation:
    backgroundColor: "transparent"
    textColor: "{colors.neutral-text-dim}"
    padding: "16px 24px"
  chip:
    backgroundColor: "{colors.neutral-bg}"
    textColor: "{colors.neutral-text-dim}"
    rounded: "{rounded.md}"
    padding: "8px 24px"
---

# Design System: Alex Rabelo — Portfólio

## Overview

**Creative North Star: "Telemetria do Profissional"**

Cada seção do site se comporta como um módulo de sistema: prompt de boot no topo, hero como tela de boot, projetos como tabela de processos (PID, stack, status, atualização) e experiência como log de sistema com timestamps. É um portfólio de plataforma/SRE/DevOps dirigido a recrutadores, gestores de contratação e potenciais clientes de infraestrutura e nuvem. A personalidade é técnica, direta e em pt-BR; a densidade é baixa (muitos espaços em branco, seções arejadas) e a filosofia estética é "black velvet": superfícies escuras, bordas hairline, branco-sujo sobre preto e um único acento ciano. A tipografia é dividida por função: JetBrains Mono carrega a identidade de desenvolvedor (cabeçalhos, rótulos, dados, código) e Inter carrega a leitura longa (parágrafos, lead). Não há logo, gradientes decorativos (exceto a scanline sutil do corpo) nem JavaScript.

**Key Characteristics:**
- Tema escuro, fundo #050607 (Preto Vulcão) e acento único #66fcf1 (Ciano Terminal).
- Mono para dados/rótulos/cabeçalhos, sans para leitura longa; no máximo 6 tamanhos de fonte.
- Flat-by-default: profundidade por camadas tonais e bordas hairline, sem sombras projetadas.
- Botões ghost por padrão; um único botão preenchido (primário) como exceção.
- Acessibilidade de padrão: skip-link, foco visível, prefers-reduced-motion, SVGs com dimensão explícita.

## Colors

Paleta enxuta de um único acento ciano sobre neutros de preto-vulcão a cinza-quase-branco, com papel definido para cada tom.

### Primary
- **Ciano Terminal** (#66fcf1): único acento da marca. Usado em links, hover/focus de botões, outline de foco-visible, ponto de status do cabeçalho, timestamps da experiência, cabeçalhos de seção (.section-head) e lede de destaque no hero. Regra de uso: ≤10% de qualquer tela — sua raridade é o ponto (The One Voice Rule). Nunca em gradientes decorativos.

### Neutral
- **Preto Vulcão** (#050607): fundo principal do corpo e da página 404; fundo do skip-link e da seleção de texto (::selection).
- **Superfície** (#161B22): superfície base de cartões, containers e tabela de projetos.
- **Superfície 2** (#1C2430): blocos de código e estado elevado de cartões.
- **Superfície 3** (#24303d): estado hover de cartões e entradas da timeline.
- **Borda** (#2B3742): hairline borders padrão entre seções, cards, tabela e controles visuais.
- **Borda forte** (#3A4756): hover de cartões e botões do GitHub; polegar da barra de rolagem.
- **Texto** (#E6EDF3): texto principal do corpo.
- **Texto dim** (#8B949E): texto secundário, links visitados, rótulos de stack técnica.
- **Texto mute** (#94A3B8): texto mais fraco, cabeçalhos de coluna da tabela, lead do hero.

**The One Voice Rule.** O acento primário (#66fcf1) aparece em ≤10% de qualquer tela dada. Sua raridade é o ponto: quanto menos acento, mais autoridade ele tem quando aparece.

## Typography

**Display Font:** JetBrains Mono (com ui-monospace, SFMono-Regular, Menlo, monospace como fallback)
**Body Font:** Inter (com system-ui, -apple-system, sans-serif como fallback)
**Label/Mono Font:** JetBrains Mono (com ui-monospace, SFMono-Regular, Menlo, monospace como fallback)

**Character:** O pareamento é técnico e direto. O mono identifica a camada de "sistema" (boot, processos, log, rótulos, dados, código); o sans sustenta a leitura longa de sobre, experiência e formação. A escada de tamanhos respeita a hierarquia Material adaptada ao tom de sistema.

### Hierarchy
- **Display** (peso padrão, 3rem, 1.05): h1 do hero e prompt de boot; identidade máxima de cada tela.
- **Headline** (600, 2rem, 1.2): h2 das seções (Sobre, Experiência, Projetos, Contato, Formação).
- **Title** (600, 1.5rem, 1.35): h3 dentro de entradas da timeline e cards de informação.
- **Body** (peso padrão, 1rem, 1.6): parágrafos de corpo; comprimento de linha limitado a ~65ch em seções (.section p) e ~62ch no lead do hero.
- **Label** (600, 0.8125rem, letter-spacing 0.06em, maiúsculo): .section-head (rótulos de seção) e cabeçalhos de coluna da tabela de projetos.

## Layout

Modelo de container único: largura máxima 1120px, centralizado, padding horizontal 24px (space-3). Seções com padding vertical 64px (space-8) e borda superior hairline 1px #2B3742. Cabeçalho fixo (sticky) no topo com desfocagem de fundo (backdrop-filter blur 12px), cor rgba(13,17,23,.92), borda inferior hairline e altura mínima 64px. O ritmo de espaçamento escala em 8/16/24/32/48/64/128px (space-1 a space-8). Parágrafos de corpo limitam a linha a 65ch para leitura confortável.

### Responsivo (640px)
Em telas até 640px: display cai para 2rem, headline para 1.5rem, o hero reduz padding vertical para 48px (space-6), a grade de "sobre" colapsa para uma coluna, a navegação vira um menu absoluto à direita e a tabela de projetos se transforma em cards empilhados.

## Elevation & Depth

O sistema é flat-by-default: não usa sombras projetadas (box-shadow). A profundidade é transmitida por camadas tonais (fundo → superfície → superfície-2 → superfície-3) e por bordas hairline #2B3742. No hover, cartões e entradas sobem para superfície-3 com borda #3A4756. O foco por teclado usa outline 2px #66fcf1 com deslocamento de 3px. Sob prefers-reduced-motion, animações e transições são reduzidas a 0.01ms e a scanline some.

## Shapes

Form language baseada em raios discretos e bordas finas: raio base 4px (sm) para a tabela de projetos; 6px (md) para botões, cartões, controles e links sociais; 12px (lg) para o skip-link (arredondado apenas no canto inferior-direito); 9999px (full) para o ponto de status e o polegar da barra de rolagem. Todas as bordas são de 1px #2B3742 (hairline). Não há gradientes decorativos, exceto a scanline sutil e fixa do corpo.

## Components

### Buttons
- **Shape:** raio 4px (sm), preenchimento transparente por padrão.
- **Ghost (padrão):** fundo transparente, borda 1px #2B3742, texto #E6EDF3, fonte mono fs-sm (0.875rem), padding 8px 16px (space-1 space-2). Hover/focus-visible: borda e texto → #66fcf1. Active: escala 0.96.
- **Primary (.btn-primary):** preenchido #66fcf1, texto #050607, mesmo raio e padding; hover → #66d9f0. É o único elemento preenchido colorido do site; nunca serve como padrão de CTA (herda do arquétipo Resend, adaptado: ciano em vez de violeta).
- **Secundário/terciário:** não existem como categorias formais; links de ação usam o estilo chip abaixo.

### Chips / Links sociais (.icon-link, .stack-btn)
- **Style:** fundo #050607 (#161B22 nos botões de stack), borda 1px #2B3742, raio 6px (md), padding 8px 24px (ícones sociais) ou 8px 16px (stack), texto #E6EDF3 (#8B949E nos stack), fonte mono fs-sm, peso 600. Hover/focus-visible: fundo #1C2430, borda e texto → #66fcf1. SVGs com 24px e dimensão explícita.

### Cards / Containers (info-card, service-card, entrada da timeline)
- **Corner Style:** raio 6px (md).
- **Background:** #1C2430 (superfície-2).
- **Shadow Strategy:** nenhum; profundidade por camada tonal (veja Elevation & Depth).
- **Border:** 1px #2B3742 (hairline).
- **Internal Padding:** 24px (space-3).
- **Hover:** fundo → #24303d (superfície-3), borda → #3A4756 (border-strong).

### Inputs / Fields
Não há campos de formulário no site (sem inputs de comando nem contenteditable, por restrição de produto). Blocos de código (.code-block) funcionam como campos de leitura: fundo #1C2430, borda 1px #2B3742, raio 6px, padding 24px, fonte mono 0.8125rem, texto #8B949E, overflow horizontal automático.

### Navigation
- **Style, typography, states:** links em fonte mono 0.8125rem, maiúsculo, #8B949E; hover/focus-visible → #66fcf1, sem sublinhado. Espaçamento entre links 16px (space-2). Cabeçalho: sticky, desfocado, rgba(13,17,23,.92), borda inferior #2B3742. Mobile (≤640px): menu absoluto à direita com fundo #050607, links em bloco com padding 8px 16px, hover fundo #161B22 e texto #66fcf1.

### Tabela de Projetos (.modulos)
- **Style:** fundo #161B22 (superfície), borda 1px #2B3742, raio 4px (sm), fonte mono fs-sm (0.875rem).
- **Cabeçalhos:** #8B949E, peso 600, tamanho 0.8125rem, maiúsculo, letter-spacing 0.05em.
- **Células:** #94A3B8, alinhamento numérico tabular.
- **Hover da linha:** fundo rgba(102,252,241,0.06).
- **Mobile:** cada linha vira um card empilhado com fundo #161B22, borda #2B3742, raio 6px e padding 24px.

## Do's and Don'ts

### Do:
- **Do** use #66fcf1 (Ciano Terminal) como único acento, em ≤10% de cada tela (The One Voice Rule).
- **Do** mantenha bordas hairline de 1px #2B3742 entre superfícies.
- **Do** use mono para dados, rótulos, cabeçalhos e código; sans para leitura longa.
- **Do** respeite prefers-reduced-motion (animações e transições a 0.01ms).
- **Do** mantenha o skip-link "Pular para o conteúdo" e o foco visível (outline 2px #66fcf1).
- **Do** use SVGs com dimensão explícita, JSON-LD válido e links externos com rel noopener.

### Don't:
- **Don't** use gradientes decorativos (exceto a scanline do corpo).
- **Don't** ultrapasse 6 tamanhos de fonte.
- **Don't** adicione cores adicionais de marca ou logo; não há ativos de marca vinculantes além do README.
- **Don't** use botões preenchidos coloridos como padrão; o preenchido é exceção reservada ao primário único.
- **Don't** adicione inputs de comando nem contenteditable; a linha de comando não é navegável pelo usuário.
- **Don't** invente placeholders, lorem ipsum ou dados; todo o conteúdo vem de content/ e repositórios reais no GitHub.
