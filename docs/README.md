# Documentação do Projeto

Índice da documentação (Sprint 1 - Modelagem). Todos os diagramas têm fonte editável em `diagramas/*.puml` (PlantUML).

| Documento | Conteúdo |
|---|---|
| [regras-de-negocio.md](regras-de-negocio.md) | Requisitos funcionais e regras de negócio (RN01 a RN17) |
| [historias-de-usuario.md](historias-de-usuario.md) | 15 histórias de usuário com critérios de aceitação |
| [casos-de-uso.md](casos-de-uso.md) | Diagrama e especificação dos casos de uso |
| [modelo-de-dominio.md](modelo-de-dominio.md) | Diagrama de classes, dicionário de dados e decisões |
| [arquitetura.md](arquitetura.md) | Diagrama de pacotes (MVC) e ciclo de vida do pedido |
| [rastreabilidade.md](rastreabilidade.md) | Matriz requisito, regra, história, caso de uso e classe |
| [historico-de-modelagem.md](historico-de-modelagem.md) | Registro da evolução dos modelos a cada sprint |

## Como atualizar os diagramas
1. Edite o arquivo `.puml` correspondente.
2. Gere o PNG (VS Code com a extensão PlantUML: *Export Current Diagram*, ou plantuml.com/plantuml).
3. Substitua o PNG em `diagramas/` e faça commit dos dois arquivos.

Regra do projeto: qualquer mudança no código que altere regras ou modelo deve atualizar também os diagramas e este índice (RN09).
