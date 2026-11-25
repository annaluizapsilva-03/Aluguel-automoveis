# Matriz de Rastreabilidade

Mostra de onde vem cada requisito e onde ele aparece na modelagem. Use na defesa para provar que nada do enunciado ficou de fora.

| Requisito | Regras | Histórias | Casos de uso | Classes envolvidas |
|---|---|---|---|---|
| RF01 Clientes | RN01, RN06, RN14, RN17 | HU01, HU03 | UC01, UC04 | Cliente, Rendimento, Usuario |
| RF02 Automóveis | RN08, RN14, RN17 | HU04, HU15 | UC05 | Automovel, Proprietario |
| RF03 Agentes | RN14, RN17 | HU09, HU10 | UC02, UC10 | Agente, Usuario |
| RF04 Pedidos | RN02, RN03, RN10, RN11, RN15, RN16 | HU05, HU06, HU07, HU08 | UC06, UC07, UC08, UC09 | PedidoAluguel, Cliente, Automovel |
| RF05 Avaliação | RN03, RN04, RN05, RN12, RN13 | HU11, HU12, HU13 | UC11, UC12, UC13 | AvaliacaoFinanceira, Agente, PedidoAluguel |
| RF06 Contrato de crédito | RN07 | HU14 | UC14 | ContratoCredito, Agente |
| RF07 Autenticação e perfis | RN01, RN02, RN04 | HU02 | UC03 | Usuario, Perfil |

## Conferência de cobertura
- Todas as 9 regras do enunciado (RN01 a RN09) aparecem em ao menos uma história e em ao menos um diagrama.
- Todo caso de uso tem pelo menos uma história, e toda história tem um caso de uso.
- Os 5 status mínimos do enunciado estão no enum StatusPedido e no diagrama de estados.
