# Portfólio — Alex Luiz Rabelo

Site pessoal publicado no GitHub Pages. Não é um currículo bonito; funciona como uma interface de sistema, com shell prompt no topo, tela de boot no hero, tabela de processos para os projetos e log de sistema para a experiência profissional.

Todo o conteúdo vem de `content/linkedin.md` e `content/projects.json`. Não há placeholders nem lorem ipsum.

## Estrutura

```
├── index.html
├── 404.html
├── assets/css/styles.css
├── content/
│   ├── linkedin.md
│   └── projects.json
├── docs/design-tokens.css
├── docs/design-telemetry.css
├── skills-lock.json
└── README.md
```

## Design

O site segue o conceito "Telemetria do Profissional". Cada seção se comporta como um módulo de sistema:

- **Hero**: sequência de boot que carrega módulos (`alex_rabelo.sre`, `cloud.infra`, `ia.operacoes`) e avisa que o sistema está pronto, com 28+ anos de uptime.
- **Navegação**: um prompt `> _` no topo. Clicar em um comando muda a seção.
- **Projetos**: listados como processos (`ps aux`), com PID, stack, status e data de atualização.
- **Experiência**: registro de sistema com timestamps (`[abr/2026]`) e nível `info`.
- **Contato**: endpoint com ícones de e-mail, LinkedIn e GitHub. Sem texto ao lado dos ícones.

Paleta: fundo `#050607`, acento único `#66fcf1`. Sem gradientes, sem cards arredondados idênticos e sem setinhas `→` no final de links.

## Conteúdo

- Nome: Alex Luiz Rabelo
- Local: São Paulo, SP, Brasil
- Empresa atual: Dexian Brasil (cliente BNP Paribas Cardif)
- Cargo: Analista de Infraestrutura Especialista (desde abr/2026)
- Anterior: Brasilseg — Especialista em Infraestrutura (dez/2018 a jan/2026)
- Voluntário: Escola da Nuvem — Mentor (set/2025 a ago/2026)
- Formação: Bacharelado em Ciência de Dados, Mackenzie (concluído jul/2026)
- Inglês: Limited Working

Projetos em destaque:

- lab-redhat-wsl2 — RHEL no WSL2 (nov/2026)
- iac-terraform-ai-review — revisão de planos Terraform com LLM (nov/2026)
- mlops-k8s-recomendacao — deploy de ML em Kubernetes (nov/2026)
- llmops-rag-infra — plataforma LLMOps com RAG (nov/2026)
- shellscript-sre-toolkit — scripts Bash com CI (nov/2026)
- iac-aws-terraform-demo — Terraform AWS modular (set/2025)

## Deploy

O GitHub Actions faz deploy automático para o GitHub Pages a cada push na branch `main`.

Site: https://alexrabelo.github.io/

## Validação

```bash
# Nenhum placeholder no conteúdo
grep -riE "lorem|ipsum|fulano|sicrano|placeholder|TODO|example\.com" index.html content/ && echo "FALHA" || echo "OK"

# Espaçamentos fora da escala de 8px no CSS
grep -oE "padding[^;]*[0-9]+px" assets/css/styles.css | grep -vE "(8|16|24|32|48|64|96)px"

# Até 4 tamanhos de fonte distintos
grep -oE "font-size:\s*[0-9.]+rem" assets/css/styles.css | sort -u | wc -l

# Gradientes proibidos
grep -riE "linear-gradient|radial-gradient" assets/css/styles.css && echo "FALHA" || echo "OK"
```

## Transparência de IA

Revisei este arquivo manualmente. Construí o site com auxílio de ferramentas de IA e revisei/testei tudo pessoalmente.