# alexrabelo.github

Portfólio técnico de Alex Rabelo — Cloud, DevOps & SRE.

Site construído com Jekyll e hospedado no GitHub Pages.

## Estrutura

- `index.md` — Página inicial com hero, projetos em destaque e CTA.
- `projects.md` — Lista de labs e repositórios relacionados.
- `about.md` — Sobre, stack, certificações e contato.
- `_posts/` — Posts de labs e pesquisas de mercado.
- `assets/css/custom.css` — Estilos customizados.

## Como rodar localmente

```bash
bundle install
bundle exec jekyll serve
```

Acesse http://localhost:4000

## Como publicar

1. Crie um repositório no GitHub (ex: `alexrabelo.github`).
2. Faça push para o branch `main`.
3. Ative o GitHub Pages em Settings → Pages (branch `main`, pasta `/root`).
4. O site ficará disponível em `https://AlexRabelo.github.io/alexrabelo.github/`.
