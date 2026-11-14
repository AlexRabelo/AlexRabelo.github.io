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

- Nome: Alex Rabelo ( Mineiro )
- Local: São Paulo, SP, Brasil
- Empresa atual: Dexian Brasil (cliente BNP Paribas Cardif)
- Cargo: Analista de Infraestrutura Especialista (desde abr/2026)
- Anterior: Brasilseg — Especialista em Infraestrutura (dez/2018 a jan/2026)
- Voluntário: Escola da Nuvem — Mentor (set/2025 a ago/2026)
- Formação: Bacharelado em Ciência de Dados, Mackenzie (concluído jul/2026)
- Inglês: Básico

Projetos em destaque:

- wsl2-enterprise-linux-lab — Enterprise Linux no WSL 2: RHEL 10.2, CentOS 10, AL2023 e AL2027 Preview (nov/2026)
- lab-al2023-virtualbox — Amazon Linux 2023 no VirtualBox com Cloud-Init (nov/2026)
- ShellScript — Curso prático de Shell Script (Bash) para Automação e SRE (nov/2026)
- ProjetoAplicado_03 — Sistema web de recomendação de livros com ML Híbrido (set/2025)
- iac-aws-terraform-demo — Terraform AWS modular (set/2025)
- dio-lab-open-source — Lab Open Source da DIO (jul/2024)
- python-week-2022 — Template Python Week 2022 (abr/2022)

## Deploy

O GitHub Actions faz deploy automático para o GitHub Pages a cada push na branch `main`.

Site: https://alexrabelo.github.io/

## Validação

# 1. Nenhum gradiente decorativo (scanline é exceção)
grep -nE "linear-gradient|radial-gradient" assets/css/styles.css

# 2. Máximo 6 tamanhos de fonte
grep -oE "font-size:\s*[0-9.]+(rem|px)" assets/css/styles.css | sort -u | wc -l

# 3. prefers-reduced-motion presente
grep -c "prefers-reduced-motion" assets/css/styles.css   # >= 2

# 4. Nenhum input de comando (restrição de produto)
grep -riE "<input[^>]*type=[\"']text|contenteditable|command-line" index.html \
  && echo "FALHA: input de comando detectado" || echo "OK"

# 5. Nenhuma dependência externa além de Google Fonts
grep -oE 'src="https?://[^"]+' index.html | grep -v "fonts.googleapis.com" \
  && echo "REVISAR: dependência externa" || echo "OK"

# 6. Links externos com rel seguro
grep -oE '<a[^>]*target="_blank"[^>]*>' index.html | grep -v 'noopener' \
  && echo "FALHA: falta noopener" || echo "OK"

# 7. SVGs com dimensão explícita
grep -oE '<svg(?![^>]*width=)[^>]*>' index.html \
  && echo "FALHA: SVG sem width" || echo "OK"

# 8. Placeholders no conteúdo
grep -riE "lorem|ipsum|placeholder|TODO|em construção" index.html \
  && echo "FALHA: placeholder detectado" || echo "OK"

# 9. JSON-LD válido
node -e "
const fs=require('fs');
const h=fs.readFileSync('index.html','utf8');
const m=h.match(/<script type=\"application\/ld\+json\">([\s\S]*?)<\/script>/);
if(!m) throw new Error('JSON-LD ausente');
JSON.parse(m[1]);
console.log('JSON-LD OK');
"

# 10. Tamanho do JS
find . -name "*.js" -not -path "./node_modules/*" -exec wc -c {} + | tail -1

## Transparência de IA

Revisei este arquivo manualmente. Construí o site com auxílio de ferramentas de IA e revisei/testei tudo pessoalmente.