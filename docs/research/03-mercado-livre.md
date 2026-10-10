# Suppley — regras e integração com o Mercado Livre

**Pesquisa:** 10 de outubro de 2026
**Uso:** levantamento inicial para uma integração de uso próprio.
**Importante:** disponibilidade de endpoint e permissão concedida à aplicação são coisas diferentes. Revalidar no programa de desenvolvedores antes de operar.

## O que a documentação permite investigar

- **Pedidos:** a API de vendas permite consultar pedidos, itens, status, preços/taxas e vínculos com pagamentos e envios. A integração deve ler o pedido e seu estado atual antes de disparar o fulfillment.
  Fonte: [Gerenciamento de vendas](https://developers.mercadolivre.com.br/devcenter/gerenciamento-de-vendas) — atualizada em 7 ago. 2026.
- **Notificações:** há notificações para pedidos, pagamentos, publicações e perguntas. A documentação recomenda usar o evento para saber que algo mudou e consultar o recurso para obter o estado atualizado.
  Fonte: [Receber notificações](https://developers.mercadolivre.com.br/pt_br/produto-consulta-de-usuarios/produto-receba-notificacoes) — atualizada em 11 set. 2026.
- **Autorização:** OAuth e permissões funcionais dão à aplicação acesso em nome do vendedor. Solicite somente escopos necessários, proteja tokens e segredos, permita revogação e evite expor credenciais ao modelo.
  Fontes: [OAuth e tokens](https://developers.mercadolivre.com.br/pt_br/publicacao-de-produtos/gestao-de-identidades-e-acessos-oauth-e-tokens) — 6 abr. 2026; [Permissões funcionais](https://developers.mercadolivre.com.br/pt_br/permissoes-funcionais/) — 21 nov. 2025.
- **Perguntas:** existe API para perguntas e respostas pré-venda, sujeita às políticas de conteúdo e do canal.
  Fonte: [Gerenciamento de perguntas e respostas](https://developers.mercadolivre.com.br/pt_br/convivencia-me1-me2/gerenciamento-perguntas-respostas).

## Restrições relevantes para atendimento automatizado

A documentação de boas práticas proíbe mensagens automáticas repetitivas ou modelos genéricos de qualquer tipo e orienta a não enviar confirmações de compra ou atualizações que a própria plataforma já informa. A regra aplicável pode depender do fluxo; o agente deve responder no contexto autorizado, sem disparos automáticos rotineiros.

Na arquitetura de mensageria intermediada, que está sendo implantada progressivamente para MLB/MLC, a conversa começa pelo comprador, o integrador pode enviar uma mensagem por vez ao agente e há 48 horas úteis para resolver a consulta. A leitura também pode marcar mensagens como lidas; para apenas monitorar, a documentação oferece mark_as_read=false. Respostas HTTP 202 com status pending_review são intermediárias e não comprovam entrega. Esses detalhes pertencem ao fluxo intermediado e devem ser verificados para a conta e a conversa em questão.

Fontes: [Boas práticas da plataforma](https://developers.mercadolivre.com.br/pt_br/envio-personalizado/boas-praticas-para-usar-a-plataforma) — 30 dez. 2025; [Gestão de mensagens pós-venda](https://developers.mercadolivre.com.br/pt_br/produto-consulta-de-usuarios/mensagens-post-venda) — 9 out. 2026.

## Implicação para o Suppley

1. Receber evento e reconciliar estado consultando a API.
2. Manter uma máquina de estados do pedido e impedir compras duplicadas com chave idempotente.
3. Usar a IA para entender exceções, preparar decisões e redigir respostas contextuais.
4. Fazer cumprir limites e permissões no backend; registrar evidência e resultado.
5. Não enviar mensagens de rotina apenas para parecer proativo.

## Pontos a confirmar antes da integração

- Se sua conta e o aplicativo têm os escopos de leitura e escrita necessários.
- Status atual de mudanças de API de pedidos e envios.
- Se o fluxo de mensagens da sua conta está intermediado e quais destinatários/limites se aplicam.
- Se a operação de compra após a venda e a origem do fornecedor são compatíveis com envio, prazo e regras do seu anúncio.

### Fontes oficiais

- [Documentação de desenvolvedores do Mercado Livre](https://developers.mercadolivre.com.br/)

## Testes e preparo do aplicativo

A documentação consultada diz que o Mercado Livre não oferece sandbox; os testes de integração usam usuários de teste, e transações de teste devem ocorrer apenas entre usuários de teste. Isso deve orientar a fase de desenvolvimento antes de conectar sua operação real.

A documentação também informa que, desde 30 de agosto de 2026, aplicações de Mercado Livre e Mercado Pago devem ficar separadas por unidade de negócio. Para o Suppley, que começa com marketplace, criar e configurar somente o app necessário para Mercado Livre.

Fontes: [Realização de testes](https://developers.mercadolivre.com.br/pt_br/realizacao-de-testes/realizacao-de-testes) — 30 dez. 2025; [Gerencie seu aplicativo](https://developers.mercadolivre.com.br/pt_br/produto-consulta-de-usuarios/gerencie-seu-aplicativo) — 6 ago. 2026.
