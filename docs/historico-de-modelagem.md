# Histórico de Evolução dos Modelos

Este documento registra como os diagramas UML e as regras evoluem a cada sprint, conforme a regra RN09 (alterações relevantes no modelo devem refletir nos diagramas e no código) e o critério de avaliação "evolução e atualização dos modelos ao longo das sprints".

**Como usar:** a cada mudança relevante, acrescente uma linha na tabela da sprint correspondente, informando o que mudou, por que mudou e quais arquivos foram atualizados.

## Sprint 1 - Modelagem (versão 1.0)

**Entregas:** diagrama de casos de uso, histórias de usuário, diagrama de classes e diagrama de pacotes. Foram adicionados também o diagrama de estados do pedido, as regras de negócio, o dicionário de dados e a matriz de rastreabilidade.

| Data | Artefato | Mudança | Motivo |
|---|---|---|---|
| 25/11/2026 | Casos de uso | Criados UC01 a UC14, com Agente Banco como especialização de Agente | Cobrir os perfis Cliente e Agente e a exclusividade do banco no contrato de crédito (RN07) |
| 25/11/2026 | Classes | Criadas as classes de domínio, enums e a interface Proprietário | Permitir que o dono do automóvel seja cliente, empresa ou banco (RN08) |
| 25/11/2026 | Classes | Rendimento como composição de Cliente, multiplicidade 0..3 | Limite de três vínculos (RN06) |
| 25/11/2026 | Pacotes | Definidas as camadas View, Controller, Model e Infraestrutura | Arquitetura MVC exigida pelo enunciado |
| 25/11/2026 | Estados | Criado o ciclo de vida do pedido com os cinco status mínimos | Impedir que pedido cancelado seja aprovado ou executado (RN03) |
| 25/11/2026 | Regras | Incluídas RN10 a RN17 como decisões do grupo | Preencher lacunas do enunciado (edição, cancelamento, unicidade, sobreposição de períodos, exclusão) |

## Sprint 2 - Implementação inicial (versão 2.0)

| Data | Artefato | Mudança | Motivo |
|---|---|---|---|
| _a preencher_ | | | |

## Sprint 3 - Versão final (versão 3.0)

| Data | Artefato | Mudança | Motivo |
|---|---|---|---|
| _a preencher_ | | | |

## Checklist de coerência (conferir a cada sprint)
- [ ] Toda classe do código existe no diagrama de classes, com os mesmos atributos.
- [ ] Toda pasta do código corresponde a um pacote do diagrama de pacotes.
- [ ] Toda funcionalidade implementada tem história e caso de uso.
- [ ] Todo status usado no código está no enum e no diagrama de estados.
- [ ] README e tabela de rastreabilidade atualizados.
