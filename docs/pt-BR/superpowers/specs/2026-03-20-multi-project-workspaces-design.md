# Especificaçêo: Design de Multi-Project Workspaces (pt-BR)

Data original: 2026-03-20  
Fonte canônica: `docs/superpowers/specs/2026-03-20-multi-project-workspaces-design.md`

---

## Problema

Times e desenvolvedores frequentemente precisam trabalhar em múltiplos repositórios/áreas em paralelo, mantendo isolamento de estado de planejamento sem perder fluidez operacional.

## Proposta

Introduzir workspaces multi-projeto com:

- isolamento de `.planning/` por workspace
- suporte a múltiplos repositórios (worktree/clone)
- comandos para criaçêo, listagem e remoçêo

## Objetivos de design

- isolamento forte de estado
- operaçêo simples via comandos (`new/list/remove workspace`)
- baixo acoplamento com o workflow padrêo
- fácil observabilidade do que está ativo

## Modelo conceitual

- **Workspace**: unidade isolada de execuçêo GSD
- **Member repos**: repositórios associados ao workspace
- **Manifest**: arquivo de metadados com estrutura e status

## Fluxo de uso

1. Criar workspace com nome e repositórios alvo
2. Inicializar/retomar fluxo GSD dentro do workspace
3. Operar fases normalmente com estado isolado
4. Finalizar e remover quando concluído

## Considerações

- comandos devem deixar explícito o contexto atual
- limpeza precisa remover artefatos derivados com segurança
- comportamento deve ser previsível em ambientes monorepo

## Critérios de aceitaçêo

- workspaces independentes nêo colidem estado
- listagem mostra workspace ativo e metadados essenciais
- remoçêo limpa artefatos sem afetar repositórios externos

---

> [!NOTE]
> Esta versêo em Português resume a especificaçêo de design para uso prático. O arquivo original em inglês mantém o detalhamento normativo completo.
