# Suppley — índice da pesquisa inicial

**Data da pesquisa:** 10 de outubro de 2026
**Objetivo:** guardar uma base de referência para começar o Suppley como agente pessoal de operações de e-commerce.

## Arquivos

1. [Anthropic: arquitetura de agentes](01-anthropic-agentes.md) — workflows, ferramentas, estado, avaliação, segurança e coordenação de agentes.
2. [OpenAI: agentes e ferramentas](02-openai-agentes.md) — Agents SDK, funções tipadas, aprovações, guardrails, traces e encerramentos anunciados.
3. [Mercado Livre](03-mercado-livre.md) — APIs de pedidos e notificações, OAuth e regras de mensagens.
4. [Shopee](04-shopee.md) — Open Platform, anúncios, dados de compradores e limites da evidência disponível.
5. [AliExpress](05-aliexpress.md) — Business Program, software aprovado, Open Platform e incertezas sobre APIs.
6. [Amazon](06-amazon.md) — SP-API privada, roles, mensagens por pedido e política de dropshipping.

## Conclusões iniciais para o Suppley

- Automatizar por regras o fluxo normal; usar o agente para investigar exceções e preparar decisões.
- Guardar pedidos, custos, estoque, autorizações e histórico numa fonte de verdade da aplicação.
- Dar ao modelo ferramentas específicas e limitar permissões no backend.
- Exigir aprovação para ações que gastem dinheiro, alterem anúncios/estoque fora dos limites ou criem compromissos com compradores.
- Validar cada integração por conta e região. Uma API documentada não garante acesso aprovado nem torna uma prática permitida pelas políticas do marketplace.
- Testar resultados no estado final do sistema e guardar o histórico de execuções.

## Como usar este pacote

Estes arquivos são guias de referência em Markdown, criados para leitura offline. Eles resumem fontes públicas oficiais e trazem links para os originais; não são cópias integrais dos documentos. Políticas e APIs mudam. Antes de conectar uma conta ou agir em produção, confirmar novamente os termos atuais, permissões concedidas, região e limites do aplicativo.
