# Cenários para especificar o Suppley

**Status:** candidatos à definição de produto. Estes cenários descrevem o comportamento a discutir, não funcionalidades já implementadas.

| Situação | Comportamento esperado | Evidência de resultado |
| --- | --- | --- |
| Venda com dados consistentes | Consultar estado do pedido e verificar o fluxo autorizado | Estado atual, produto correspondente e registro da ação |
| Custo mudou após a venda | Recalcular margem e indicar opções dentro dos limites | Custos com origem e cálculo verificável |
| Fornecedor sem estoque | Apresentar indisponibilidade; avaliar alternativa somente para item compatível | Disponibilidade consultada e identidade do produto |
| Variante ou produto não corresponde | Impedir substituição silenciosa e apresentar divergência | Comparação de SKU, atributos e variante |
| Informação desatualizada | Buscar nova consulta ou indicar dado insuficiente | Horário e fonte da informação |
| Mesmo evento recebido duas vezes | Reconhecer repetição e evitar efeito duplicado | Uma execução confirmada para a operação |
| API falhou durante uma escrita | Verificar se a ação ocorreu antes de repetir | Reconciliação de estado e registro de falha |
| Cliente pergunta sobre atraso | Consultar o pedido e preparar resposta compatível com o canal | Informação verificada e ação de mensagem permitida |
| Mensagem está em moderação | Mostrar resultado pendente | Status retornado pela plataforma |
| Ação supera gasto ou margem definidos | Apresentar decisão ao proprietário | Limite violado e consequências |
| Conteúdo externo tenta alterar instruções | Tratar o texto como dado e manter autorizações | Nenhuma ação concedida por conteúdo externo |
| Dados pessoais não têm uso autorizado | Usar informação mínima permitida ou interromper o fluxo | Autorização aplicável e dados enviados registrados |

Para cada cenário escolhido, especificar uma entrada fictícia, a ação permitida, a ação proibida, o estado final esperado e o que o proprietário vê. Depois da implementação, a verificação deve olhar também o estado real do sistema.
