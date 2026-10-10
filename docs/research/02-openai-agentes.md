# Suppley — orientações oficiais da OpenAI para agentes

**Pesquisa:** 10 de outubro de 2026
**Uso:** referência de desenho e operação de agentes com ferramentas para uma loja pessoal.
**Escopo:** síntese de documentação oficial. Os links levam às fontes originais e devem ser conferidos novamente durante a implementação.

## Recomendações que se aplicam ao Suppley

1. **Use um coordenador para manter o controle do fluxo.** No padrão “agentes como ferramentas”, o agente principal chama especialistas e continua responsável pela decisão e resposta. Handoffs servem quando o especialista deve assumir a interação. Para o Suppley, começar com um agente coordenador e ferramentas/funções especializadas é mais simples de controlar.
   Fontes: [Orquestração no Agents SDK](https://openai.github.io/openai-agents-python/multi_agent/) e [guia de escolha do Agents SDK](https://developers.openai.com/api/docs/guides/agents/sdk).

2. **Defina ferramentas pequenas e tipadas.** Funções como consultar pedido, consultar estoque, calcular margem e preparar resposta são mais fáceis de validar do que uma ferramenta ampla com várias consequências. Use esquemas estruturados e valide IDs, valores, permissões e limites no servidor. Strict mode ajuda a validar argumentos estruturados, mas não comprova que a ação é correta.
   Fonte: [Function calling](https://developers.openai.com/api/docs/guides/function-calling).

3. **Exija aprovação para efeitos externos sensíveis.** O Agents SDK oferece interrupções de aprovação humana para chamadas de ferramentas. Isso pode proteger ações como pagar fornecedor, cancelar pedido, publicar anúncio ou enviar mensagem. Mesmo com aprovação do SDK, a aplicação deve validar limites e autorização a cada chamada.
   Fonte: [Human-in-the-loop no Agents SDK](https://openai.github.io/openai-agents-python/human_in_the_loop/).

4. **Coloque controles também nas ferramentas.** Guardrails de entrada e saída do agente não são substitutos de validação de cada chamada. Controles na ferramenta podem inspecionar ações antes e depois de executá-las; decisões importantes devem falhar de modo seguro quando faltarem dados.
   Fontes: [Guardrails](https://openai.github.io/openai-agents-python/guardrails/) e [ferramentas do Agents SDK](https://openai.github.io/openai-agents-python/ref/tool/).

5. **Registre execuções e avalie cenários concretos.** Traces ajudam a entender chamadas, falhas, transferências e tempos. No Agents SDK, o tracing está habilitado por padrão no fluxo normal de servidor e pode registrar chamadas e resultados de ferramentas. Filtre segredos e dados pessoais, restrinja acesso e defina retenção; auditoria não exige guardar todo o conteúdo bruto. Mantenha casos para preço alterado, estoque desatualizado, margem abaixo do piso, mensagem ambígua e API indisponível. Confira o estado final, além da resposta do agente.
   Fontes: [Tracing](https://openai.github.io/openai-agents-python/tracing/) e [Integrações e observabilidade](https://developers.openai.com/api/docs/guides/agents/integrations-observability), [avaliação de agentes](https://developers.openai.com/api/docs/guides/agent-evals) e [trace grading](https://developers.openai.com/api/docs/guides/trace-grading).

6. **Trate conteúdo externo como entrada não confiável.** Mensagens, páginas de fornecedores e anúncios podem tentar alterar as instruções do agente. Limite o que ele pode ler e fazer, teste tentativas de desvio e use aprovação humana quando apropriado.
   Fontes: [Safety best practices](https://developers.openai.com/api/docs/guides/safety-best-practices) e [Safety in building agents](https://developers.openai.com/api/docs/guides/agent-builder-safety).

7. **Não dependa de ferramentas com encerramento anunciado.** Na data desta pesquisa, a OpenAI informa que o Agent Builder está previsto para encerrar em 30 de novembro de 2026. A plataforma Evals fica somente para leitura a partir de 31 de outubro de 2026 e está prevista para encerrar em 30 de novembro de 2026. As orientações apontam o Agents SDK como caminho para fluxos mantidos em código.
   Fonte: [Deprecations da OpenAI](https://developers.openai.com/api/docs/deprecations).

## Aplicação inicial ao Suppley

- Manter pedidos, estoque, custos, margem, permissões e histórico em uma fonte de dados da aplicação.
- Começar com um coordenador, poucas ferramentas e fluxo normal previsível.
- Pedir aprovação para mudanças ou comunicações que possam gerar custo, penalidade ou compromisso com comprador.
- Registrar o que foi consultado, proposto, aprovado, executado e confirmado.
- Comparar custo, latência, taxa de erro e economia de trabalho antes de ampliar a autonomia.

## Observações

O Agents SDK é uma opção de implementação, não uma decisão já tomada para o projeto. Recursos e nomes de APIs mudam; verificar documentação atual, preços, retenção de dados e disponibilidade na conta antes de integrar.
