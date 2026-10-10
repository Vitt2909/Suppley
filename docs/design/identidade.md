# Identidade do Appley

**Registrado em:** 10 de outubro de 2026.
**Direção aceita:** Caixa Viva, com construção reproduzível em SVG.
**Estado:** exploração visual; poses e usos ainda serão refinados ao definir a interface.

## Personagem

Appley é o mascote do Suppley. Uma caixa de papelão claro ganha expressão e movimento para representar o agente pessoal do proprietário. A identidade reúne corpo levemente arredondado, abas largas caídas, fita menta com pequeno recorte na ponta, olhos ovais escuros com brilho, sobrancelhas expressivas, mãos pequenas e pés arredondados.

A pose principal mostra a lateral esquerda da caixa, um sorriso curto e uma das mãos levantada. As referências de estados exploram novas poses mantendo esses traços.

## Linguagem visual

- Papelão em tons dourados claros, com volume suave.
- Fita verde-menta como detalhe de reconhecimento.
- Olhos e boca em marrom muito escuro.
- Fundo marfim nas pranchas de apresentação.
- Gradientes simples, sombras leves e silhueta legível.
- Anatomia e formas que possam ser recriadas com caminhos SVG.

O SVG principal usa gradientes e filtros nativos, incluindo textura procedural de papel. Não contém imagem incorporada. Os grupos de rosto, braços, pés e abas facilitam ajustes e animações; eles ainda não têm animação implementada. Antes de animar, definir pontos de articulação, duração e comportamento em tamanhos pequenos.

## Arquivos

| Arquivo | Finalidade |
| --- | --- |
| [appley-caixa-viva.svg](../assets/appley-caixa-viva.svg) | Pose principal em formato vetorial editável |
| [appley-caixa-viva.png](../assets/appley-caixa-viva.png) | Prévia da pose principal em fundo marfim |
| [appley-poses-estados.png](../assets/appley-poses-estados.png) | Prancha de oito referências gerada com o gerador de imagens integrado |
| [suppley-banner.svg](../assets/suppley-banner.svg) | Banner da identidade anterior, preservado como histórico |

A prancha foi produzida a partir da prévia da pose principal. Ela é uma referência visual em PNG; as oito poses não foram vetorizadas.

## Estados propostos

| Referência | Significado na interface |
| --- | --- |
| Olá | Recepção e apresentação |
| Pensando | Análise ou investigação ativa |
| Trabalhando | Execução em andamento |
| Concluído | Resultado confirmado pela fonte responsável |
| Preciso de você | Informação, decisão ou autorização pendente |
| Em movimento | Progresso de uma tarefa com várias etapas |
| Descansando | Sem tarefa ativa |
| Ops! | Falha identificada, acompanhada de explicação e próximo passo |

O personagem deve acompanhar o estado real da tarefa. A expressão vem junto de texto que explica o que aconteceu e, quando necessário, qual ação o proprietário pode tomar. A pose comemorativa deve ser usada depois da confirmação do resultado.

A distinção entre “Trabalhando” e “Em movimento” será avaliada no desenho da interface. As expressões precisam continuar compreensíveis em tamanho pequeno; o uso da textura e de detalhes poderá ser reduzido nesses contextos.

## Próximo refinamento

Selecionar os estados necessários ao primeiro fluxo, adaptar as poses para SVG, definir variações compactas e registrar regras de animação. A escolha do mascote não define, por si só, as funções nem a autonomia do agente.
