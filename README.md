# Portfólio — Alex Rabelo

Site de portfólio profissional publicado no GitHub Pages.

## Estrutura de arquivos

```
├── index.html
├── assets/
│   ├── css/styles.css
│   └── js/main.js (se necessário)
├── content/
│   ├── linkedin.md
│   └── projects.json
├── .github/workflows/deploy.yml
└── README.md
```

## Design — 7 Princípios

A página segue os 7 princípios de design de interface:

1. **Ponto focal claro** — Hero com um único CTA primário ("Ver Projetos").
2. **Espaçamento em escala** — Múltiplos de 8px via CSS custom properties (`--space-1` a `--space-7`).
3. **Hierarquia por peso e cor** — Máximo 2 famílias tipográficas (Outfit para títulos, Source Sans 3 para corpo), 4 tamanhos de fonte, títulos peso 700.
4. **Cor com parcimônia** — Um acento (ciano `#22d3ee`) usado apenas em CTA, foco e links. Sem gradientes.
5. **Conteúdo real** — Dados extraídos do LinkedIn e repositórios do GitHub. Sem placeholders.
6. **Detalhes consistentes** — Raio de borda 12px (aninhados 8px), bordas 1px, sombras em camadas.
7. **Movimento conectado** — Transições 150–250ms, `prefers-reduced-motion` respeitado.

## Deploy

O GitHub Actions faz o deploy automático para o GitHub Pages a cada push na branch `main`.

Site: https://alexrabelo.github.io/

## Validação

Execução dos comandos de validação (pré-requisito: servidor local na porta 8000):

```bash
# 1. Nenhum placeholder
grep -riE "lorem|ipsum|fulano|sicrano|placeholder|TODO|example\.com" index.html content/ && echo "FALHA" || echo "OK"

# 2. Espaçamentos fora da escala de 8px
grep -oE "padding[^;]*[0-9]+px" assets/css/styles.css | grep -vE "(8|16|24|32|48|64|96)px"

# 3. Tamanhos de fonte distintos (≤ 4)
grep -oE "font-size:\s*[0-9.]+rem" assets/css/styles.css | sort -u | wc -l

# 4. Gradientes proibidos
grep -riE "linear-gradient|radial-gradient" assets/css/styles.css && echo "FALHA" || echo "OK"
```

## Conteúdo

- Conteúdo do LinkedIn: `content/linkedin.md`
- Projetos do GitHub: `content/projects.json`