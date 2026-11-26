# Referência de Recursos do GSD

Visêo em Português dos recursos centrais do GSD.  
Para catálogo completo e detalhamento exaustivo, consulte [FEATURES.md em inglês](../FEATURES.md).

---

## Recursos principais

- **Desenvolvimento orientado por fases** com artefatos de planejamento versionados
- **Engenharia de contexto** para reduzir degradaçêo de qualidade em sessões longas
- **Planejamento em tarefas atômicas** para execuçêo mais previsível
- **Execuçêo em ondas paralelas** com controle por dependências
- **Commits atômicos por tarefa** para rastreabilidade e rollback
- **Verificaçêo pós-execuçêo** com foco em objetivos da fase
- **UAT guiado** via `/gsd:verify-work`
- **Suporte brownfield** com `/gsd:map-codebase`
- **Workstreams** para trilhas paralelas sem colisêo de estado
- **Backlog, seeds e threads** para memória de médio/longo prazo

## Qualidade e segurança

- **Plan-check** antes de executar
- **Nyquist validation** para mapear requisito -> validaçêo automatizada
- **Detecçêo de prompt injection** em entradas do usuário
- **Prevençêo de path traversal** em caminhos fornecidos
- **Hooks de proteçêo** para alterações fora de contexto de workflow

## UX de frontend

- **`/gsd:ui-phase`**: contrato visual antes da execuçêo
- **`/gsd:ui-review`**: auditoria visual em 6 pilares
- **UI safety gate** para uso de registries de terceiros

## Operaçêo e manutençêo

- **Perfis de modelo** (`quality`, `balanced`, `budget`, `inherit`)
- **Ajuste por toggles** para custo/qualidade/velocidade
- **Diagnóstico forense** com `/gsd:forensics`
- **Relatório de sessêo** com `/gsd:session-report`

---

## Atalhos recomendados por cenário

| Cenário | Comandos |
|--------|----------|
| Projeto novo | `/gsd:new-project` -> `/gsd:discuss-phase` -> `/gsd:plan-phase` -> `/gsd:execute-phase` |
| Correçêo rápida | `/gsd:quick` |
| Código existente | `/gsd:map-codebase` -> `/gsd:new-project` |
| Fechamento de release | `/gsd:audit-milestone` -> `/gsd:complete-milestone` |

---

> [!NOTE]
> Este arquivo é uma versêo de referência rápida em Português para facilitar uso diário. Para detalhes de baixo nível, requisitos formais e comportamento completo de cada recurso, use o documento original em inglês.
