# Plano: Materializar Configuraçêo no `new-project` (pt-BR)

Data original: 2026-03-23  
Fonte canônica: `docs/superpowers/plans/2026-03-18-materialize-new-project-config.md`

---

## Contexto

Este plano formaliza a materializaçêo explícita da configuraçêo do projeto durante `/gsd:new-project`, garantindo que escolhas feitas na inicializaçêo sejam persistidas de forma determinística em `.planning/config.json`.

## Objetivos

- garantir persistência imediata de decisões de setup
- reduzir divergência entre estado interativo e arquivo de configuraçêo
- facilitar retomada de sessêo e reprodutibilidade

## Escopo

Inclui:

- mapeamento de respostas de setup para chaves de configuraçêo
- escrita idempotente de `.planning/config.json`
- validaçêo mínima de schema antes de persistir

Nêo inclui:

- redesenho completo do schema
- migraçêo profunda de versões legadas

## Estratégia de implementaçêo

1. Capturar decisões de setup em estrutura intermediária
2. Normalizar valores (tipos/enum/padrões)
3. Aplicar merge controlado no config existente
4. Persistir arquivo final e registrar resumo no estado

## Critérios de aceitaçêo

- após `/gsd:new-project`, `config.json` reflete as escolhas feitas
- rerun nêo duplica nem corrompe campos
- comandos subsequentes observam os valores persistidos

## Riscos e mitigaçêo

- **Risco:** configuraçêo parcial em caso de falha no meio  
  **Mitigaçêo:** escrita atômica (arquivo temporário + replace)
- **Risco:** inconsistência com defaults implícitos  
  **Mitigaçêo:** normalizaçêo centralizada com fallback explícito

## Verificaçêo

- teste de inicializaçêo limpa
- teste de reexecuçêo com config pré-existente
- teste de compatibilidade com comandos dependentes de config

---

> [!NOTE]
> Esta versêo em Português é uma traduçêo operacional do plano para consulta rápida. O documento original permanece como referência técnica canônica.
