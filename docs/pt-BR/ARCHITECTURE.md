# Arquitetura do GSD

Visêo arquitetural do Get Shit Done (GSD) em Português.  
Para detalhes de implementaçêo linha a linha, consulte [ARCHITECTURE.md em inglês](../ARCHITECTURE.md).

---

## Princípios

- **Orquestraçêo leve** no contexto principal
- **Trabalho pesado em subagentes**
- **Artefatos persistentes** em `.planning/`
- **Validaçêo contínua** por fase
- **Rastreabilidade** por commits atômicos

## Componentes centrais

1. **Camada de comando**  
   Recebe entrada do usuário (`/gsd:*`) e roteia fluxo.

2. **Camada de orquestraçêo**  
   Coordena pesquisadores, planejadores, executores e verificadores.

3. **Camada de artefatos**  
   Mantém `PROJECT.md`, `REQUIREMENTS.md`, `ROADMAP.md`, `STATE.md`, planos e sumários.

4. **Camada de execuçêo**  
   Roda tarefas em ondas, respeitando dependências.

5. **Camada de validaçêo**  
   Compara entrega contra objetivos, testes e critérios de fase.

## Fluxo arquitetural (alto nível)

```text
Entrada (/gsd:comando)
  -> Orquestrador
  -> Subagentes especializados
  -> Artefatos em .planning/
  -> Execuçêo em ondas
  -> Verificaçêo/UAT
  -> Atualizaçêo de estado + commits
```

## Estado e persistência

- `STATE.md`: memória operacional da jornada
- `ROADMAP.md`: visêo de progresso por fase
- `SUMMARY.md`: histórico de decisões e resultados por tarefa
- `VALIDATION.md` (quando aplicável): contrato de feedback automatizado

## Paralelismo

- Planos independentes: mesma onda (execuçêo paralela)
- Planos dependentes: ondas posteriores (execuçêo sequencial)
- Conflitos de arquivo: serializaçêo controlada

## Segurança

- validaçêo de caminhos de arquivo
- detecçêo de prompt injection
- hooks de guarda para escrita/ediçêo sensível
- scanner CI para padrões de risco

## Extensibilidade

GSD suporta evoluçêo por:

- novos comandos
- novos tipos de agente
- novos artefatos por fase
- novos gates de qualidade/segurança

---

> [!NOTE]
> Esta versêo foi criada para consulta de arquitetura em Português. A especificaçêo canônica e completa continua no documento em inglês.
