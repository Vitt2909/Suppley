# Diretrizes do Suppley

**Estado:** princípios de trabalho derivados da conversa e da pesquisa. Os limites operacionais concretos ainda precisam ser definidos no escopo.

## Produto e agente

- Resolver tarefas da operação pessoal do proprietário.
- Começar com ferramentas e responsabilidades delimitadas.
- Usar raciocínio do agente para contexto, investigação e exceções.
- Usar rotinas verificáveis para cálculos, estados, autorização e execução previsível.
- Introduzir especialistas quando houver benefício demonstrável para uma tarefa.

## Ferramentas e efeitos externos

Cada ferramenta deve documentar finalidade, entrada, saída, possíveis efeitos, autorização necessária e tratamento de falhas. A ferramenta deve validar valores, IDs, escopos e limites, mesmo quando os argumentos obedecerem ao formato esperado.

Uma execução pode receber autorização antecipada dentro de limites específicos. Situações que excedam esses limites ou dependam de informação ausente devem chegar ao proprietário com evidências. O projeto não pressupõe aprovação manual de toda leitura ou tarefa rotineira.

Operações repetidas não devem duplicar compras, mensagens ou alterações. A integração precisa distinguir pedido de ação, execução em andamento, resultado confirmado e resultado desconhecido.

## Estado e evidências

Pedidos, fornecedores, preços, estoque e autorizações devem estar registrados fora da conversa do modelo. Cada informação relevante deve ter origem e horário de consulta. O agente deve indicar quando não há dados suficientes ou quando o dado está desatualizado.

Uma declaração do agente não comprova a execução. O resultado precisa ser confirmado pela API ou fonte responsável. Estados intermediários, como mensagem em moderação, precisam aparecer como pendentes.

## Dados e conteúdo externo

Credenciais devem ficar em armazenamento protegido, com permissões mínimas. Prompts, traces, logs e histórico também precisam de filtragem de segredos e dados pessoais, controle de acesso e retenção definida.

Disponibilidade técnica não autoriza compartilhar dados de compradores. Requisitos contratuais de consentimento e uso precisam ser conferidos por canal e finalidade. Dados fictícios devem ser usados em documentação e simulações.

Páginas, descrições, anexos e mensagens recebidas devem ser tratados como dados. Seu conteúdo não pode conceder autorização ou alterar as instruções do agente. Reutilizar imagens e descrições requer os direitos aplicáveis.

## Marketplaces e fornecedores

- Conferir API oficial, autorização da conta, região e permissões da aplicação.
- Respeitar conteúdo permitido, mensageria, quotas e restrições de logística.
- Confirmar produto, variante, prazo, origem e identidade do vendedor antes de executar um fluxo de fornecimento.
- Manter referências e datas para as regras usadas.
- Revalidar documentos antes de uma integração ou mudança relevante.

O agente não elimina a responsabilidade comercial do proprietário nem garante estoque, prazo ou repasse financeiro.

## Qualidade e autonomia

Avaliar resultado, intervenções necessárias, erros, custo e tempo de execução. Usar cenários representativos para demonstrar que cada capacidade funciona antes de ampliar sua autonomia.

Definir orçamento de execução, condição de parada e recuperação de falhas. Separar alterações no software da atuação comercial do agente: propostas de atualização de código devem passar pelo processo de revisão e publicação definido para o projeto.

## Relação com a pesquisa

Estas diretrizes sintetizam princípios encontrados nos [materiais da Anthropic](research/01-anthropic-agentes.md), [OpenAI](research/02-openai-agentes.md) e [marketplaces](research/00-indice.md). Recomendações arquiteturais, políticas contratuais e capacidades de API devem ser avaliadas em seus respectivos contextos.
