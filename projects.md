---
layout: page
title: Projetos & Labs
permalink: /projetos/
---

# Projetos & Labs

Cada lab abaixo está documentado em seu próprio repositório no GitHub. Clique nos cards para ver o código, a documentação e a seção de transparência de IA.

<div class="project-list">
  {% assign sorted = site.posts | sort: "date" | reverse %}
  {% for post in sorted %}
    {% if post.categories contains "lab" %}
    <article class="project-item">
      <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
      <p>{{ post.excerpt }}</p>
      <span class="tags">{{ post.tags | join: " · " }}</span>
    </article>
    {% endif %}
  {% endfor %}
</div>

## Repositórios relacionados

- [iac-aws-terraform-demo](https://github.com/AlexRabelo/iac-aws-terraform-demo) — IaC com Terraform para AWS (VPC, EC2, S3, CI/CD).
- [ShellScript](https://github.com/AlexRabelo/ShellScript) — Curso prático de Shell Script do zero à automação real.
- [ciencia-de-dados](https://github.com/AlexRabelo/ciencia-de-dados) — Portfólio de Ciência de Dados.
- [ProjetoAplicado_03](https://github.com/AlexRabelo/ProjetoAplicado_03) — Sistema de recomendação de livros com Machine Learning Híbrido.
