# Referência de Ferramentas CLI

Resumo em Português das ferramentas CLI do GSD.  
Para API completa (assinaturas, argumentos e comportamento detalhado), consulte [CLI-TOOLS.md em inglês](../CLI-TOOLS.md).

---

## Objetivo

As ferramentas CLI permitem que comandos e agentes do GSD executem ações padronizadas de:

- leitura e escrita de artefatos
- gerenciamento de fases e roadmap
- execuçêo e validaçêo de planos
- integraçêo com git e automaçêo

## Áreas funcionais

### Projeto e estado

- inicializaçêo de artefatos (`PROJECT`, `REQUIREMENTS`, `ROADMAP`, `STATE`)
- atualizaçêo de estado por fase
- controle de milestones

### Planejamento

- criaçêo de planos atômicos
- validaçêo pré-execuçêo
- consolidaçêo de pesquisa

### Execuçêo

- despacho de tarefas por onda
- persistência de sumários
- checkpoints de progresso

### Verificaçêo

- comparaçêo de saída com objetivos
- geraçêo de relatórios de validaçêo
- apoio ao UAT

### Utilitários

- leitura/escrita segura de arquivos
- parsing de argumentos
- normalizaçêo de paths

## Boas práticas para autores de agentes

- Use artefatos existentes como fonte de verdade
- Evite lógica duplicada entre agentes
- Registre saídas em arquivos canônicos de fase
- Garanta que toda tarefa tenha critério claro de done/verify

---

## Fluxo típico (programático)

```text
Ler contexto do projeto
 -> montar input da etapa
 -> executar ferramenta CLI
 -> persistir artefatos
 -> atualizar estado/roadmap
 -> retornar resumo para o orquestrador
```

---

> [!NOTE]
> Este arquivo é um guia prático em Português para quem integra ou estende workflows. Para contratos estritos e detalhes técnicos completos, use o documento original em inglês.
