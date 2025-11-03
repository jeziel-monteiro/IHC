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

Para avaliar a capacidade de diferentes algoritmos de aprendizado de máquina em classificar a comunicabilidade do sistema, foi desenhado um protocolo experimental utilizando o software Weka. Abaixo, toda a descrição:

## 4.1. Ambiente e Conjunto de Dados
Software: Weka.

Conjunto de Dados: Foi utilizada a base sintética comunicabilidade_dados.arff, descrita na Seção 3, contendo 500 instâncias, 5 atributos preditores numéricos (Qtd_atividades, Tempo_gasto, Qtd_etiquetas, Num_ajudas, Qtd_erros) e 1 atributo-alvo nominal (comunicabilidade). 

## 4.2. Algoritmos Selecionados
Foram selecionados cinco algoritmos de classificação, cada um representando uma abordagem diferente de aprendizado, para testar distintas hipóteses sobre os dados:

ZeroR (weka.classifiers.rules.ZeroR):

Categoria: Regras (Baseline).

Propósito: Servir como linha de base (baseline) de desempenho. Este modelo simplesmente prevê a classe majoritária (a "moda") presente nos dados de treino, ignorando todos os atributos.

OneR (weka.classifiers.rules.OneR):

Categoria: Regras (Simples).

Propósito: Identificar qual dos cinco atributos, sozinho, possui o maior poder preditivo para a classe-alvo.

J48 (weka.classifiers.trees.J48):

Categoria: Árvores de Decisão (baseado no C4.5).

Propósito: Verificar se a lógica de classificação, que foi baseada em regras de pontuação (Seção 2), poderia ser "redescoberta" por um algoritmo que naturalmente gera regras "Se-Então".

IBk (weka.classifiers.lazy.IBk):

Categoria: Baseado em Instâncias (k-Nearest Neighbors).

Propósito: Avaliar a consistência e a separação dos grupos. Se instâncias da mesma classe (ex: "alta") estão numericamente "próximas" umas das outras, este modelo deve ter um bom desempenho.

NaiveBayes (weka.classifiers.bayes.NaiveBayes):

Categoria: Probabilístico (Bayesiano).

Propósito: Testar a eficácia de um modelo estatístico que calcula a probabilidade de uma instância pertencer a uma classe com base nos perfis médios de cada atributo.

# 5 - Resultados

### 5.2. Comparação dos Resultados - Validação das Regras Definidas
<div align="justify">
O ZeroR serve como a linha de base fundamental e demonstra o resultado das regras de pontuação, mas não a sua lógica. Este modelo ignora completamente todos os atributos preditivos
(Qtd_atividades, Qtd_erros, etc.) e simplesmente identifica qual classe final (baixa, media ou alta) é a mais frequente no conjunto de dados. O fato de o modelo prever "alta" para todas as instâncias e atingir 41.76% de acurácia nos informa apenas uma coisa sobre o resultado do seu sistema de pontuação: ele produziu um conjunto de dados onde "alta" é a classe mais comum (a moda). A única função do ZeroR, portanto, é estabelecer o limite mínimo de desempenho que qualquer modelo inteligente deveria superar.

O OneR atuou como um validador do atributo-chave. Ele determinou que Qtd_atividades era o previsor individual mais forte, o que está em perfeito alinhamento com as regras de pontuação definidas. Enquanto a regra manual dava +1 ponto para \ge 8 e -1 para \le 3, o OneR aprendeu regras quase idênticas de forma independente: >= 7.5 \rightarrow alta e < 4.5 \rightarrow baixa. Isso confirma que Qtd_atividades, mesmo sozinho, é um indicador robusto da classe de comunicabilidade, justificando a acurácia de 81.76% do modelo.

O J48 apresentou a correspondência mais perfeita, e sua alta acurácia (89.41%) é justificada pela natureza do problema. O sistema de pontuação original, que combina múltiplos atributos com regras "Se-Então" (como Qtd_erros <= 5 e Qtd_atividades >= 8), é, em essência, uma árvore de decisão. O J48, sendo um algoritmo construtor de árvores, foi o mais apto a "redescobrir" essa lógica. A prova de sua eficácia é que o modelo final utilizou exatamente os mesmos cinco atributos (Qtd_atividades, Tempo_gasto, Qtd_etiquetas, Num_ajudas, Qtd_erros) que compõem o sistema de pontuação manual.

O IBk (com k=1) validou a consistência dos grupos criados pelas regras. Modelos baseados em distância, como o k-NN, só funcionam bem se as instâncias da mesma classe estiverem "próximas" umas das outras no espaço de atributos. O sistema de pontuação garante exatamente isso: todas as instâncias alta (pontuação maior ou igual a +3) serão, por definição, numericamente semelhantes (poucos erros, poucas ajudas, muitas atividades), formando um "agrupamento" (cluster). A alta acurácia de 87.06% do IBk prova que as regras de negócio criaram grupos consistentes e bem definidos, permitindo que a lógica do "vizinho mais próximo" fosse eficaz.

O NaiveBayes funcionou como um reflexo estatístico das regras de pontuação. Embora não aprenda regras explícitas, ele aprendeu o perfil médio de cada classe. Por exemplo, a regra de negócio determina que Qtd_erros \le 5 é positivo e \ge 10 é negativo. O modelo NaiveBayes capturou isso perfeitamente, aprendendo que a média de Qtd_erros para a classe alta é 3.63, enquanto a média para a classe baixa é 12.03. O desempenho do modelo (83.53%) valida que as classes têm perfis estatísticos distintos, embora a suposição "ingênua" de independência dos atributos o tenha impedido de superar os modelos baseados em regras ou distância.
</div>

# 6 - Análise crítica dos resultados em relação ao domínio de IHC


