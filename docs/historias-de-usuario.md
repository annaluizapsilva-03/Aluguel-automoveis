# Histórias de Usuário

Formato: **Como** [perfil], **quero** [ação], **para** [benefício]. Prioridade: Alta, Média ou Baixa.
Cada história indica as regras de negócio (RN) e o caso de uso (UC) relacionados.

## Todos os perfis

### HU02 - Entrar no sistema
**Como** cliente ou agente, **quero** entrar com e-mail e senha, **para** acessar apenas as funções do meu perfil.
- Credenciais inválidas mostram mensagem clara, sem revelar qual campo errou.
- Após o login, o usuário vê somente o menu do seu perfil.
- Páginas protegidas redirecionam para o login quando não há sessão.
- Prioridade: Alta | RN01 | UC03

## Perfil Cliente

### HU01 - Cadastrar-me como cliente
**Como** cliente, **quero** me cadastrar informando nome, CPF, RG, endereço, profissão e empregadores com rendimentos, **para** poder solicitar aluguéis.
- CPF e e-mail não podem repetir.
- É possível informar de 0 a 3 empregadores, cada um com valor de rendimento.
- A senha é guardada com hash, nunca em texto puro.
- Prioridade: Alta | RN01, RN06, RN14 | UC01

### HU03 - Gerenciar meus dados
**Como** cliente, **quero** consultar, editar e excluir meus dados, **para** mantê-los atualizados.
- Só vejo e altero o meu próprio cadastro.
- A edição continua respeitando o limite de 3 rendimentos.
- Não consigo me excluir se tiver pedidos ativos.
- Prioridade: Alta | RN02, RN06, RN17 | UC04

### HU04 - Gerenciar automóveis
**Como** cliente, **quero** cadastrar, consultar, editar e excluir automóveis, **para** usá-los nos pedidos.
- Marca, modelo, ano, placa, matrícula e proprietário são obrigatórios.
- O proprietário pode ser eu, uma empresa ou um banco.
- A placa não pode repetir.
- Não é possível excluir automóvel com pedido ativo.
- Prioridade: Alta | RN08, RN14, RN17 | UC05

### HU05 - Criar pedido de aluguel
**Como** cliente, **quero** criar um pedido escolhendo automóvel e período, **para** solicitar o aluguel.
- O pedido nasce com status Em análise e com a data de criação preenchida.
- O período precisa ser válido (início não posterior ao fim).
- Se o automóvel já tem pedido ativo no período, o sistema recusa e explica o motivo.
- Prioridade: Alta | RN01, RN15, RN16 | UC06

### HU06 - Editar pedido
**Como** cliente, **quero** editar um pedido ainda em análise, **para** corrigir informações.
- Só pedidos Em análise aceitam edição.
- Só posso editar pedidos meus.
- Prioridade: Média | RN02, RN10 | UC07

### HU07 - Cancelar pedido
**Como** cliente, **quero** cancelar um pedido, **para** desistir do aluguel.
- O cancelamento é permitido para pedidos Em análise ou Aprovado.
- Depois de cancelado, o pedido não pode mais ser aprovado nem executado.
- O sistema pede confirmação antes de cancelar.
- Prioridade: Alta | RN02, RN03, RN11 | UC08

### HU08 - Acompanhar meus pedidos
**Como** cliente, **quero** ver a lista e o status dos meus pedidos, **para** saber como está a análise.
- A lista mostra apenas pedidos meus, do mais recente para o mais antigo.
- Cada pedido exibe status, período, automóvel e, quando houver, parecer e justificativa do agente.
- Prioridade: Alta | RN02 | UC09

## Perfil Agente

### HU09 - Cadastrar agente
**Como** agente, **quero** me cadastrar informando nome, CNPJ, endereço e tipo (empresa ou banco), **para** analisar pedidos.
- CNPJ e e-mail não podem repetir.
- O tipo é obrigatório e define se posso conceder crédito.
- Prioridade: Alta | RN01, RN14 | UC02

### HU10 - Gerenciar agentes
**Como** agente, **quero** consultar, editar e excluir agentes, **para** manter o cadastro correto.
- Não é possível excluir agente que já registrou avaliações ou contratos.
- Prioridade: Média | RN17 | UC10

### HU11 - Ver pedidos pendentes
**Como** agente, **quero** listar os pedidos em análise, **para** saber o que preciso avaliar.
- A lista mostra só pedidos Em análise, com dados do cliente, rendimentos e automóvel.
- Prioridade: Alta | RN04 | UC11

### HU12 - Registrar avaliação financeira
**Como** agente, **quero** registrar parecer (aprovado ou reprovado) com justificativa, **para** concluir a análise.
- O sistema grava automaticamente o agente e a data da análise.
- A justificativa é obrigatória, principalmente na reprovação.
- Após o parecer, o status do pedido muda para Aprovado ou Reprovado.
- Pedidos que não estejam Em análise (inclusive cancelados) não podem ser avaliados.
- Prioridade: Alta | RN03, RN04, RN05, RN12 | UC12

### HU13 - Confirmar execução do contrato
**Como** agente, **quero** confirmar a execução de um pedido aprovado, **para** iniciar o contrato.
- Só pedidos Aprovado passam para Contrato em execução.
- Pedido cancelado nunca é executado.
- Prioridade: Média | RN03, RN13 | UC13

### HU14 - Registrar contrato de crédito
**Como** agente do tipo banco, **quero** registrar um contrato de crédito para um pedido, **para** financiar o aluguel.
- Informo valor financiado, prazo em meses e situação do crédito.
- Agente do tipo empresa não vê nem executa essa ação.
- Cada pedido tem no máximo um contrato de crédito.
- Prioridade: Média | RN07 | UC14

### HU15 - Gerenciar automóveis como agente
**Como** agente, **quero** cadastrar e manter automóveis cujo proprietário seja minha instituição, **para** disponibilizá-los para aluguel.
- O proprietário é a própria empresa ou banco logado.
- Valem as mesmas validações da HU04.
- Prioridade: Média | RN08, RN14, RN17 | UC05
