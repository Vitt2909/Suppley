# Suppley — regras e integração com a Amazon

**Pesquisa:** 10 de outubro de 2026
**Uso:** referência para app privado Seller Central e fulfillment de pedidos.
**Importante:** a página de dropshipping consultada declara aplicação aos Estados Unidos. Conferir o texto e os requisitos da conta/marketplace brasileiro antes de tratar a regra como territorialmente completa.

## Acesso à API para uso próprio

- A SP-API permite automatizar fluxos de pedidos, envio, pagamentos, listagens, preço e inventário, conforme as APIs e roles concedidas.
  Fonte: [Onboarding como desenvolvedor](https://developer-docs.amazon.com/sp-api/docs/onboarding-overview).
- Um app privado é para a própria organização. A documentação diz que é necessário ter uma conta de venda Professional no Seller Central; conta Individual não é elegível para desenvolver esse tipo de app. O usuário principal conclui o registro, e a Amazon revisa o perfil, dados, segurança e permissões solicitadas.
  Fontes: [SP-API Registration Overview](https://developer-docs.amazon.com/sp-api/lang-en_EN/docs/sp-api-registration-overview) e [Register as a Private SP-API Developer](https://developer-docs.amazon.com/sp-api/docs/register-as-a-private-developer).
- As roles controlam quais operações e dados o app pode acessar; dados pessoais podem exigir acesso/segurança adicional. A integração deve solicitar o mínimo necessário e manter credenciais e PII protegidas.

## Mensagens ao comprador

A API de mensagens permite primeiro consultar as ações habilitadas para um pedido. O retorno lista os tipos de mensagem e caminhos disponíveis para aquele pedido; não é uma permissão para o agente escrever qualquer mensagem. A documentação informa limites de taxa que podem variar por uso/conta.

Fonte: [getMessagingActionsForOrder](https://developer-docs.amazon.com/sp-api/lang-en_EN/reference/getmessagingactionsfororder).

## Política de dropshipping

A orientação oficial brasileira da Amazon diz que o seller deve continuar identificado como vendedor registrado, combinar isso com o fornecedor, remover documentos/embalagens que identifiquem terceiros e continuar responsável pelas devoluções. Ela proíbe certos envios diretos quando outra loja ou seller aparece como vendedor. A página do Seller Central também detalha essas exigências, mas indica aplicação nos Estados Unidos; confirme os termos vigentes na sua conta brasileira.

Fontes: [Amazon Brasil: Dropshipping](https://venda.amazon.com.br/sellerblog/dropshipping) e [Drop Shipping Policy no Seller Central](https://sellercentral.amazon.com/help/hub/reference/external/G201808410?locale=en-SG).

## Restrição específica do DBA

Se você optar pelo Delivery by Amazon (DBA), a página brasileira diz que, para a modalidade de coleta, deve ser usado um único endereço de envio. Isso é uma condição do DBA, não uma regra geral de toda a SP-API nem um limite geral da Amazon para dropshipping.

Fonte: [DBA — cadastro e endereço](https://venda.amazon.com.br/cresca/dba).

## Implicação para o Suppley

- Confirmar se sua conta e o marketplace-alvo permitem app privado e quais roles foram aprovadas.
- Começar com sandbox e dados simulados; só depois testar ações reais.
- Antes de responder ao cliente, buscar as ações permitidas para aquele pedido na API.
- Para dropshipping, obter acordo explícito do fornecedor e verificar embalagem, nota, devoluções, prazos e identidade do seller; confirmar regra local do Brasil.
- Não expor dados pessoais do comprador ao modelo ou a serviços externos sem necessidade e autorização aplicável.
- Usar idempotência e limites para compras, mudanças de preço/estoque e cancelamentos.

### Fontes oficiais

- [Amazon Selling Partner API](https://developer-docs.amazon.com/sp-api/)
- [Seller Central: Drop Shipping Policy](https://sellercentral.amazon.com/help/hub/reference/external/G201808410?locale=en-SG)
