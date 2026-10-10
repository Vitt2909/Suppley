# Escopo de produto — Appley

**Status:** em definição.
**Versão:** rascunho 0.1.
**Proprietário:** usuário do Appley.
**Base:** [contexto](../contexto.md), [decisões](decisoes.md) e [diretrizes](../diretrizes.md).

## Intenção já registrada

Criar um agente pessoal de operações de e-commerce, apoiado por automações, para acompanhar fornecedores, pedidos, catálogo e atendimento. A intenção de comprar do fornecedor depois de uma venda precisa ser validada no fluxo concreto.

## Hipótese para a primeira versão

Mercado Livre, um fornecedor e poucos produtos. Um supervisor acompanha a operação, investiga divergências e apresenta decisões com evidências. Esta hipótese ainda não fixa o escopo.

## Decisões necessárias

| Tema | Pergunta a resolver | Estado |
| --- | --- | --- |
| Primeiro fluxo | Qual rotina deve funcionar de ponta a ponta primeiro? | Em aberto |
| Marketplace | Qual conta e canal serão usados inicialmente? | Mercado Livre proposto |
| Fornecedor | Qual fornecedor, origem de envio e acordo operacional? | Em aberto |
| Dados | Como consultar catálogo, custo, estoque e prazo? | Em aberto |
| Economia | Quais custos entram na margem e qual limite de gasto? | Em aberto |
| Autonomia | Quais ações pode executar e em quais condições? | Em aberto |
| Atendimento | Quais mensagens e canais estarão disponíveis? | Em aberto |
| Interface | Como receber pendências, decisões e alertas? | Em aberto |
| Infraestrutura | Onde executar, guardar estado e proteger credenciais? | Em aberto |

## Capacidades candidatas

| Capacidade | Resultado esperado para o proprietário | Dependência |
| --- | --- | --- |
| Acompanhar pedidos | Saber o que está pendente e por quê | API e estado atual |
| Verificar fornecimento | Saber se o produto correto pode ser entregue | Dados atuais e acordo com fornecedor |
| Calcular margem | Entender receita, custos e resultado estimado | Definição e origem de todos os custos |
| Investigar exceções | Receber opções fundamentadas | Ferramentas de consulta e limites |
| Preparar atendimento | Receber resposta contextual correta | Política e dados autorizados do canal |
| Executar ações delimitadas | Reduzir trabalho em tarefas confiáveis | Autorizações e confirmação da execução |

## Contrato de cada fluxo

Ao escolher uma capacidade, preencher: gatilho, dados necessários, fontes e validade, ações possíveis, limites, autorizações, estados finais, falhas recuperáveis, condição de parada e informação apresentada ao proprietário.

## Critérios de aceitação a definir

- Resultado observável para cada fluxo selecionado.
- Tratamento de dados ausentes, obsoletos e conflitantes.
- Prevenção de efeitos duplicados e recuperação de falhas.
- Evidências necessárias para executar uma ação.
- Limites de tempo, custo e intervenção humana.
- Regras aplicáveis à integração e aos dados.

Usar os [cenários de operação](cenarios.md) como ponto de partida, sem presumir que todas as situações serão implementadas na primeira versão.

## Entregas para fechar este escopo

- [ ] Primeiro fluxo escolhido e descrito.
- [ ] Fornecedor e acesso aos dados confirmados.
- [ ] Integração e permissões disponíveis identificadas.
- [ ] Custos, prazos e autonomia especificados.
- [ ] Interface e critérios de aceitação definidos.
- [ ] Arquitetura escolhida em função desses requisitos.
