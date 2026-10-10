# Suppley — regras e integração com a Shopee

**Pesquisa:** 10 de outubro de 2026
**Uso:** levantamento inicial para um app próprio de seller.
**Importante:** documentação da Open Platform é parcialmente dinâmica e o acesso depende do app, permissões, região e conta. Confirmar no Console antes de desenhar uma integração real.

## O que foi possível confirmar

- A Shopee mantém a [Open Platform](https://open.shopee.com/), [referência de API v2](https://open.shopee.com/documents/v2/api-reference) e [guia de desenvolvimento](https://open.shopee.com/developer-guide/213). O portal oficial lista grupos de APIs para produtos, pedidos, logística e chat, mas o conteúdo não foi totalmente legível na pesquisa automatizada. Portanto, esta pesquisa não confirma quais operações estarão disponíveis para uma conta brasileira ou para um aplicativo específico.
- A disponibilidade das operações e os limites precisam ser verificados no cadastro e aprovação do app, incluindo autorização, assinatura, quotas e região.

## Políticas brasileiras que afetam automação

- O guia oficial de violação de anúncios identifica itens proibidos, propriedade intelectual/falsificação, spam e baixa qualidade. Entre os exemplos a evitar estão links externos para desviar transação, dados pessoais em anúncios, conteúdo enganoso, excesso de palavras-chave e anúncio duplicado. Violações podem gerar penalidades ou limitar a conta.
  Fonte: [Guia de violação de anúncio](https://help.shopee.com.br/portal/4/article/76225-%5BOrienta%C3%A7%C3%B5es%5D-Guia-de-Viola%C3%A7%C3%A3o-de-An%C3%BAncio).

- A política diz que o vendedor (incluindo seus agentes) só pode usar dados pessoais do comprador recebidos da Shopee quando razoavelmente necessário para atendimento/transação e com consentimento prévio por escrito do comprador e da Shopee. Também veda contato fora da plataforma e divulgação a terceiros não autorizados sem consentimento por escrito; exige segurança e retenção apenas pelo tempo necessário. Portanto, minimizar dados no prompt é uma medida técnica, mas não substitui as autorizações descritas na política. Antes de enviar PII a um provedor externo de IA, confirmar que esse uso e compartilhamento estão autorizados; quando possível, remover ou mascarar dados pessoais.
  Fontes: [Termos de Serviço](https://help.shopee.com.br/portal/4/article/77113) e [Política de Privacidade, item 8.7](https://help.shopee.com.br/portal/4/article/77068).

- O chat da Shopee mede responsividade e espera atendimento rápido, personalizado e profissional. Isso é uma meta de qualidade do seller, não prova de que uma API de chat esteja habilitada para qualquer aplicativo.
  Fontes: [Introdução ao Chat](https://help.shopee.com.br/portal/4/article/76406-Introdu%C3%A7%C3%A3o-ao-Chat-da-Shopee) e [Taxa de resposta](https://help.shopee.com.br/portal/4/article/129713-%5BNovo%20na%20Shopee%5D-O-que-é-a-taxa-de-resposta-do-chat%3F).

## Implicação para o Suppley

- Criar um validador de anúncio para categoria, autenticidade, conteúdo, duplicidade e alegações.
- Minimizar dados pessoais no prompt e manter tokens de acesso no servidor.
- Monitorar chat e preparar respostas; habilitar envio automático somente quando a API, a política e o app aprovado confirmarem esse uso.
- Registrar alterações, aprovações e resultados para entender eventuais penalidades.
- Não presumir que uma resposta automatizada é permitida apenas porque existe um endpoint técnico.

## Limites desta pesquisa

A Open Platform retornou conteúdo limitado para inspeção automatizada. Não foi confirmada uma proibição geral de dropshipping para vendas regulares na Shopee Brasil; tampouco se deve extrapolar uma regra específica de Shopee Video para toda a operação de seller. Confirmar o fluxo de fornecedor, embalagem, prazos e obrigações no Help Center e no Seller Centre da conta.

### Fontes oficiais

- [Shopee Open Platform](https://open.shopee.com/)
- [Central de Ajuda Shopee Brasil](https://help.shopee.com.br/)
