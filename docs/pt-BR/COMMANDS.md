# Referência de Comandos do GSD

Este documento descreve os comandos principais do GSD em Português.  
Para detalhes completos de flags avançadas e mudanças recentes, consulte também a [versêo em inglês](../COMMANDS.md).

---

## Fluxo Principal

| Comando | Finalidade | Quando usar |
|---------|------------|-------------|
| `/gsd:new-project` | Inicializaçêo completa: perguntas, pesquisa, requisitos e roadmap | Início de projeto |
| `/gsd:discuss-phase [N]` | Captura decisões de implementaçêo | Antes do planejamento |
| `/gsd:ui-phase [N]` | Gera contrato de UI (`UI-SPEC.md`) | Fases com frontend |
| `/gsd:plan-phase [N]` | Pesquisa + planejamento + verificaçêo | Antes de executar uma fase |
| `/gsd:execute-phase <N>` | Executa planos em ondas paralelas | Após planejamento aprovado |
| `/gsd:verify-work [N]` | UAT manual com diagnóstico automático | Após execuçêo |
| `/gsd:ship [N]` | Cria PR da fase validada | Ao concluir a fase |
| `/gsd:next` | Detecta e executa o próximo passo lógico | Qualquer momento |
| `/gsd:fast <texto>` | Tarefa curta sem planejamento completo | Ajustes triviais |

## Navegaçêo e Sessêo

| Comando | Finalidade |
|---------|------------|
| `/gsd:progress` | Mostra status atual e próximos passos |
| `/gsd:resume-work` | Retoma contexto da sessêo anterior |
| `/gsd:pause-work` | Salva handoff estruturado |
| `/gsd:session-report` | Gera resumo da sessêo |
| `/gsd:help` | Lista comandos e uso |
| `/gsd:update` | Atualiza o GSD |

## Gestêo de Fases

| Comando | Finalidade |
|---------|------------|
| `/gsd:add-phase` | Adiciona fase no roadmap |
| `/gsd:insert-phase [N]` | Insere trabalho urgente entre fases |
| `/gsd:remove-phase [N]` | Remove fase futura e reenumera |
| `/gsd:list-phase-assumptions [N]` | Mostra abordagem assumida pelo Claude |
| `/gsd:plan-milestone-gaps` | Cria fases para fechar lacunas de auditoria |

## Brownfield e Utilidades

| Comando | Finalidade |
|---------|------------|
| `/gsd:map-codebase` | Mapeia base existente antes de novo projeto |
| `/gsd:quick` | Tarefas ad-hoc com garantias do GSD |
| `/gsd:debug [desc]` | Debug sistemático com estado persistente |
| `/gsd:forensics` | Diagnóstico de falhas no workflow |
| `/gsd:settings` | Configuraçêo de agentes, perfil e toggles |
| `/gsd:set-profile <perfil>` | Troca rápida de perfil de modelo |

## Qualidade de Código

| Comando | Finalidade |
|---------|------------|
| `/gsd:review` | Peer review com múltiplas IAs |
| `/gsd:pr-branch` | Cria branch limpa sem commits de planejamento |
| `/gsd:audit-uat` | Audita dívida de validaçêo/UAT |

## Backlog e Threads

| Comando | Finalidade |
|---------|------------|
| `/gsd:add-backlog <desc>` | Adiciona item no backlog (999.x) |
| `/gsd:review-backlog` | Promove, mantém ou remove itens |
| `/gsd:plant-seed <ideia>` | Registra ideia com gatilho futuro |
| `/gsd:thread [nome]` | Gerencia threads persistentes |

---

## Exemplo rápido

```bash
/gsd:new-project
/gsd:discuss-phase 1
/gsd:plan-phase 1
/gsd:execute-phase 1
/gsd:verify-work 1
/gsd:ship 1
```
