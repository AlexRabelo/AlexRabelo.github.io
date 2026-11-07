---
layout: post
title: "Lab: Red Hat Enterprise Linux em WSL2 + OpenCode"
date: 2026-11-07 10:00:00 -0300
categories: [lab, linux, wsl2, sre, ia]
tags: [redhat, wsl2, opencode, linux, infraestrutura, ia]
excerpt: "Laboratório de administração Linux: Red Hat Enterprise Linux rodando no WSL2 com OpenCode como agente de apoio para tarefas de infraestrutura."
---

## O problema

Rodar Red Hat Enterprise Linux (RHEL) localmente para estudos e testes de administração geralmente exige máquinas virtuais pesadas (VMware, VirtualBox) ou instâncias na nuvem. O WSL2 permite rodar Linux nativamente no Windows com melhor integração, mas a documentação oficial da Red Hat para WSL2 é escassa — boa parte foca em Ubuntu, Debian ou Fedora.

## O que não é óbvio aqui

Não se trata apenas de instalar uma distro no WSL2. O desafio foi:

1. Configurar **systemd** dentro do WSL2 (não vem habilitado por padrão em todas as imagens RHEL).
2. Ajustar rede e integração com VS Code remoto.
3. Criar um script de provisionamento idempotente que valide pré-requisitos, instale pacotes essenciais e configure o ambiente.
4. Integrar o **OpenCode** como agente de apoio para automação de tarefas de infraestrutura (gerar rascunho de scripts, analisar logs, sugerir correções — sempre com revisão humana).

## Stack

- Red Hat Enterprise Linux (WSL2)
- Bash / Shell Script
- GitHub Actions (ShellCheck + Bats)
- OpenCode (agente de IA local)
- systemd, cron, backups rotativos

## Como este projeto foi construído (transparência de IA)

| Etapa | Ferramenta / IA usada | O que eu fiz |
|-------|----------------------|--------------|
| Pesquisa de documentação RHEL + WSL2 | Leitura de docs oficiais | Validei cada passo manualmente |
| Rascunho do script de provisionamento | OpenCode como sugestão | Reescrevi com strict mode, trap de sinais, logging |
| Validação de sintaxe | ShellCheck + `bash -n` | Executei, corrigi warnings, rodei 3 vezes do zero |
| Testes automatizados | Bats | Escrevi os casos de teste |
| Integração OpenCode | OpenCode CLI | Testei como copiloto; não executei comandos destrutivos sem aprovação |

## Resultados

- Ambiente RHEL funcional em WSL2 provisionado em menos de 5 minutos.
- Script idempotente: pode ser executado novamente sem quebrar o ambiente.
- CI verde em todos os pushes.
- OpenCode usado para gerar rascunhos; decisão final sempre humana.

## Decisões que a IA não tomou

- Escolha do WSL2 em vez de VirtualBox (performance e integração com Windows).
- Estrutura de pastas do repositório.
- Quais métricas de sucesso definir.
- Responsabilidade pelo que roda em produção.

## Link para o repositório

[github.com/AlexRabelo/lab-redhat-wsl2-opencode](https://github.com/AlexRabelo/lab-redhat-wsl2-opencode) *(repositório a ser criado)*
