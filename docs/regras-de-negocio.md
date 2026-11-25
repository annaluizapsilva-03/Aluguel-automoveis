# Requisitos e Regras de Negócio

## Requisitos funcionais

| ID | Requisito | Origem |
|---|---|---|
| RF01 | Cadastrar, consultar, editar e excluir clientes (nome, CPF, RG, endereço, profissão, até 3 empregadores com rendimento) | Enunciado 4.1 |
| RF02 | Cadastrar, consultar, editar e excluir automóveis (marca, modelo, ano, placa, matrícula, proprietário) | 4.2 |
| RF03 | Cadastrar agentes do tipo empresa ou banco (nome, CNPJ, endereço, tipo) | 4.3 |
| RF04 | Cliente cria, consulta, edita e cancela seus pedidos de aluguel e acompanha o status | 4.4 |
| RF05 | Agente consulta pedidos pendentes e registra avaliação financeira (parecer e justificativa), atualizando o status | 4.5 |
| RF06 | Associar, opcionalmente, um contrato de crédito (banco, valor, prazo, situação) ao pedido | 4.6 |
| RF07 | Autenticação com cadastro prévio e controle de acesso por perfil (Cliente e Agente) | Seção 3 |

## Regras do enunciado

| ID | Regra |
|---|---|
| RN01 | Apenas usuários cadastrados e autenticados podem utilizar o sistema. |
| RN02 | Um cliente cria, edita, consulta e cancela apenas os seus próprios pedidos. |
| RN03 | Um pedido cancelado não pode ser aprovado nem colocado em execução. |
| RN04 | Apenas agentes realizam avaliações financeiras. |
| RN05 | A avaliação registra qual agente a realizou. |
| RN06 | Um cliente possui no máximo três vínculos de empregador/rendimento. |
| RN07 | Um contrato de crédito só pode ser concedido por um agente do tipo banco. |
| RN08 | Todo automóvel possui proprietário identificado: cliente, empresa ou banco. |
| RN09 | Mudanças relevantes em regras ou modelo são refletidas nos diagramas UML e no código. |

## Regras complementares (decisões do grupo)

| ID | Regra | Justificativa |
|---|---|---|
| RN10 | O cliente só edita pedidos com status Em análise. | Evita alterar algo já avaliado. |
| RN11 | O cliente só cancela pedidos Em análise ou Aprovado. | Pedido Reprovado ou em execução já está encerrado ou comprometido. |
| RN12 | Só pedidos Em análise podem ser avaliados. | Garante uma avaliação por pedido. |
| RN13 | Só pedidos Aprovado podem passar para Contrato em execução. | Execução depende de aprovação financeira. |
| RN14 | CPF, CNPJ, e-mail e placa são únicos no sistema. | Identificação sem duplicidade. |
| RN15 | A data de início do aluguel não pode ser posterior à data de fim, nem anterior à data de criação. | Período válido. |
| RN16 | Um automóvel não pode ter dois pedidos ativos (Em análise, Aprovado ou Contrato em execução) com períodos sobrepostos. | Evita conflito de reservas. |
| RN17 | Não se exclui cliente, agente ou automóvel que possua pedidos ativos ou avaliações registradas. | Preserva a integridade do histórico. |

## Status do pedido

| Status | Significado | Próximos status |
|---|---|---|
| Em análise | Criado pelo cliente, aguardando avaliação | Aprovado, Reprovado, Cancelado |
| Aprovado | Aprovado financeiramente pelo agente | Contrato em execução, Cancelado |
| Reprovado | Recusado na análise financeira | (final) |
| Cancelado | Cancelado pelo cliente | (final) |
| Contrato em execução | Aprovado e confirmado para execução | (final) |

Nenhum status adicional foi criado. Se algum for incluído, atualize esta tabela, o diagrama de estados e o diagrama de classes.
