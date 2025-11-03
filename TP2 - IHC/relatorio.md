# 1 - Definição do problema

## Contexto e Motivação

Para um sistema ser eficiente e que atenda ao seu usuário, é importante que se dê uma atenção maior entre os mesmos, esse é o foco do fundamento de comunicabilidade, no qual tem o objetivo de transmitir ao usuário de forma eficaz e eficiente as intenções e princípios de interação que guiaram o seu design. Com isso, o nosso trabalho definiu a comunicabilidade para a classificação supervisionada aplicada a problema de interação humano computador pro análise crítico bem como ter maior compreensão dos sistemas em relação a melhoria na Usabilidade e experiência do usuário.

## Atributos
Os atributos estão relacionados ao esforço, tempo e compreensão do usuário ao sistema, dentre eles temos:

- **Qtd_atividades**: Número de tarefas concluídas;
- **Tempo_gasto**: Tempo total em segundos da execução das tarefas;
- **Qtd_etiquetas**: Número de etiquetas violadas;
- **Num_ajudas_solicitadas**: Número de ajuda que o usuário solicitou;
- **Qtd_erros**: Número de falhas passos incorretos que o usuário cometeu ao tentar concluir as atividades.

## Classe-Alvo
A classe-alvo é a comunicabilidade, em que foi divida em multiclasse:

- **Alta**: O sistema apresenta um índice alto de comunicabilidade;
- **Média**: O sistema apresenta um índice médio de comunicabilidade;
- **Baixa**: O sistema apresenta um índice baixo de comunicabilidade.

## Sistema
Para a base sintética, foi gerado com o auxílio de IA, um sistema eccomerce simples contendo 10 tarefas, exclusivamente para dar um contexto ao trabalho:

**Tarefas**
1. Encontrar produto específico;
2.  Adicionar ao carrinho;
3. Criar conta;
4. Realizar login;
5. Aplicar cupom;
6. Alterar quantidade no carrinho;
7. calcular frete;
8. Selecionar método de pagamento;
9. Preencher dados de entrega;
10. Finalizar compra;

# 2 - Regras usadas para gerar a classe-alvo
As definições e os critérios da classe-alvo foram organizados da seguinte maneira:

1. Os atributos foram categorizados por um sistema de pontuação, no qual cada atributo contribui com +1 ou -1.

#### Tabela de pontuação por atributo 
| Atributo | Ponto Positivo (**+1**) | Ponto Negativo (**-1**) |
| :--- | :--- | :--- |
| Qtd\_atividades | $\ge 8$ | $\le 3$ |
| Tempo\_gasto | $\ge 301$ | $\le 200$ |
| Qtd\_erros | $\le 5$ | $\ge 10$ |
| Num\_ajudas\_solicitadas | $\le 3$ | $\ge 8$ |
| Qtd\_etiquetas | $\le 3$ | $\ge 8$ |

2. A lógica de classificação para a comunicabilidade do sistema é:

- **Alta**: $\ge +3$;
- **Baixa**:  $\le -3$;
- **Média**: caso contrário.

# 3 - Descrição da base sintética

| Item | Descrição |
| :--- | :--- |
| **Ferramenta** | Gemini |
| **Formato** | .arff — compatível com o software Weka |
| **instâncias** | 500 instâncias |
| **Atributos** | 5 atributos númericos |
| **Classe-alvo** | 1 classe-alvo (multiclasse) |
| **Link para a base** | |

# 4 - Descrição dos experimentos Weka

# 5 - Resultados

### 5.1. Validação das Regras Definidas

O ZeroR serve como a linha de base fundamental e demonstra o resultado das regras de pontuação, mas não a sua lógica. Este modelo ignora completamente todos os atributos preditivos
(Qtd_atividades, Qtd_erros, etc.) e simplesmente identifica qual classe final (baixa, media ou alta) é a mais frequente no conjunto de dados. O fato de o modelo prever "alta" para todas as instâncias e atingir 41.76% de acurácia nos informa apenas uma coisa sobre o resultado do seu sistema de pontuação: ele produziu um conjunto de dados onde "alta" é a classe mais comum (a moda). A única função do ZeroR, portanto, é estabelecer o limite mínimo de desempenho que qualquer modelo inteligente deveria superar.
O OneR atuou como um validador do atributo-chave. Ele determinou que Qtd_atividades era o previsor individual mais forte, o que está em perfeito alinhamento com as regras de pontuação definidas. Enquanto a regra manual dava +1 ponto para \ge 8 e -1 para \le 3, o OneR aprendeu regras quase idênticas de forma independente: >= 7.5 \rightarrow alta e < 4.5 \rightarrow baixa. Isso confirma que Qtd_atividades, mesmo sozinho, é um indicador robusto da classe de comunicabilidade, justificando a acurácia de 81.76% do modelo.
</div>

# 6 - Análise crítica dos resultados em relação ao domínio de IHC


