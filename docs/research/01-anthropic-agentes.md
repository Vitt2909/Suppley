# Suppley — orientações oficiais da Anthropic para agentes

**Pesquisa:** 10 de outubro de 2026
**Uso:** referência de arquitetura para um agente pessoal que ajuda a gerir uma operação de comércio eletrônico.
**Escopo:** síntese de fontes oficiais; os links levam aos textos originais. Este arquivo não substitui a leitura das políticas e documentação vigentes durante a implementação.

## Recomendações que se aplicam ao Suppley

1. **Começar pela solução mais simples que resolva o problema.** Use rotinas determinísticas para tarefas previsíveis; reserve a decisão do agente para casos em que o caminho depende do contexto ou de informações incompletas. Agentes podem aumentar latência, custo e erros acumulados.
   Fonte: [Building effective agents](https://www.anthropic.com/engineering/building-effective-agents) — 19 dez. 2024.

2. **Dar ferramentas específicas, com limites claros.** Cada ferramenta deve dizer o que faz, quando deve ser chamada, quais argumentos aceita e como indica falhas. Prefira “consultar estoque do SKU” a uma ferramenta genérica que “faz qualquer coisa”. Devolva dados estruturados e contexto suficiente para o agente decidir.
   Fonte: [Writing effective tools for AI agents](https://www.anthropic.com/engineering/writing-tools-for-agents) — 11 set. 2025.

3. **Verificar o resultado no sistema.** Uma resposta dizendo “pedido atualizado” não prova que a atualização ocorreu. Confira o estado real da API ou do banco depois de cada ação importante. Inclua condições de parada e checkpoints para pedir sua decisão quando a situação sair dos limites definidos.
   Fonte: [Building effective agents](https://www.anthropic.com/engineering/building-effective-agents).

4. **Persistir o estado fora da conversa.** Pedido, estoque, custo, margem, fornecedor, autorização e histórico precisam ter uma fonte de verdade consultável. A conversa ou a memória implícita do modelo não substitui um registro operacional. Recupere só o contexto útil para cada tarefa.
   Fonte: [Effective context engineering for AI agents](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents) — 29 set. 2025.

5. **Medir tarefas e resultados reais.** Crie casos representativos e avalie tanto a execução quanto o estado final. Misture verificações objetivas — margem mínima, pedido não duplicado, estoque acima de zero — com revisão da qualidade de respostas. Leia os registros de execução para entender falhas.
   Fonte: [Demystifying evals for AI agents](https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents) — 9 jan. 2026.

6. **Limitar o alcance de cada agente.** Sites de fornecedores, anúncios e mensagens podem conter texto enganoso ou instruções que o agente não deve obedecer. Trate esse conteúdo como dado. Restrinja credenciais e permissões, separe leitura de escrita e faça cumprir limites no servidor, não apenas no prompt.
   Fonte: [How we contain Claude across products](https://www.anthropic.com/engineering/how-we-contain-claude) — 25 mai. 2026.

7. **Usar agentes especializados só quando valerem o custo.** Um coordenador pode acionar uma função especializada quando surge uma exceção. A pesquisa da Anthropic sobre múltiplos agentes descreve ganhos em tarefas de pesquisa específicas e também relata maior uso de tokens e coordenação; esses resultados não demonstram que vários agentes permanentes melhorem uma loja pessoal.
   Fonte: [How we built our multi-agent research system](https://www.anthropic.com/engineering/multi-agent-research-system) — 13 jun. 2025.

8. **Desenhar trabalhos longos para sobreviver entre execuções.** Salve progresso, eventos, pendências e critérios de conclusão. Não dependa de uma única sessão longa para concluir uma sequência operacional.
   Fonte: [Effective harnesses for long-running agents](https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents) — 26 nov. 2025.

## Exemplo aplicado

- Automação consulta pedido, status e estoque.
- Se tudo estiver dentro dos limites, segue o fluxo definido.
- Se houver divergência de preço, estoque ou prazo, o Suppley reúne evidências e propõe a próxima ação.
- O sistema valida margem, limite de gasto e identidade do item antes de permitir qualquer alteração externa.
- O resultado é confirmado pela API e registrado para auditoria.

## Observações

Os artigos são orientações de engenharia, não regras de marketplaces nem garantias de desempenho. O artigo de 2024 menciona tecnologias que podem ter mudado; use os princípios e confira a documentação atual antes de escolher ferramentas ou versões. A métrica de 90,2% divulgada no estudo de multiagentes vale para a avaliação interna de pesquisa da Anthropic, não para operações de e-commerce.
