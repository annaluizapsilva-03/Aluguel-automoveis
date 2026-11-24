# Histórias de Usuário

Formato: **Como** [perfil], **quero** [ação], **para** [benefício]. Prioridade: A (alta), M (média), B (baixa).

## Perfil: Cliente

| ID | História | Critérios de aceitação | Prio |
|---|---|---|---|
| HU01 | Como cliente, quero me cadastrar informando nome, CPF, RG, endereço, profissão e empregadores com rendimentos, para poder usar o sistema. | CPF único; no máximo 3 empregadores/rendimentos; senha armazenada com hash. | A |
| HU02 | Como cliente, quero entrar com e-mail e senha, para acessar minhas funcionalidades. | Credenciais inválidas exibem erro claro; acesso depende do perfil. | A |
| HU03 | Como cliente, quero consultar, editar e excluir meus dados, para mantê-los atualizados. | Só vejo e altero meus próprios dados; limite de 3 rendimentos mantido. | A |
| HU04 | Como cliente, quero cadastrar, consultar, editar e excluir automóveis, para disponibilizá-los em pedidos. | Todo automóvel tem proprietário identificado; placa única. | A |
| HU05 | Como cliente, quero criar um pedido de aluguel escolhendo automóvel e período, para solicitar o aluguel. | Pedido nasce com status "Em análise" e data de criação; período válido (início anterior ao fim). | A |
| HU06 | Como cliente, quero editar um pedido ainda em análise, para corrigir informações. | Pedidos cancelados, aprovados ou em execução não podem ser editados. | M |
| HU07 | Como cliente, quero cancelar meu pedido, para desistir do aluguel. | Status vira "Cancelado"; pedido cancelado não pode ser aprovado nem executado. | A |
| HU08 | Como cliente, quero ver a lista e o status dos meus pedidos, para acompanhar a análise. | Lista mostra apenas meus pedidos, com status e parecer do agente quando houver. | A |

## Perfil: Agente (empresa ou banco)

| ID | História | Critérios de aceitação | Prio |
|---|---|---|---|
| HU09 | Como agente, quero me cadastrar informando nome, CNPJ, endereço e tipo (empresa ou banco), para analisar pedidos. | CNPJ único; tipo obrigatório. | A |
| HU10 | Como agente, quero consultar, editar e excluir agentes cadastrados, para manter o cadastro correto. | Não exclui agente com avaliações registradas. | M |
| HU11 | Como agente, quero listar os pedidos em análise, para saber o que preciso avaliar. | Lista só pedidos "Em análise", com dados do cliente e rendimentos. | A |
| HU12 | Como agente, quero registrar parecer (aprovado ou reprovado) com justificativa, para concluir a análise financeira. | Registra agente, data e observação; status atualizado; não avalia pedido cancelado. | A |
| HU13 | Como agente, quero confirmar a execução de um pedido aprovado, para iniciar o contrato. | Só pedidos "Aprovado" viram "Contrato em execução". | M |
| HU14 | Como agente do tipo banco, quero registrar contrato de crédito com valor, prazo e situação, para financiar o aluguel. | Só agente tipo banco concede crédito; contrato ligado a um pedido. | M |

## Regras transversais
- Somente usuários cadastrados e autenticados acessam o sistema.
- Cada perfil só acessa as operações permitidas a ele.
