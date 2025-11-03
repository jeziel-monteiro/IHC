# 1 - Definição do problema

## 1.1 Contexto e Motivação

Para um sistema ser eficiente e que atenda ao seu usuário, é importante que se dê uma atenção maior entre os mesmos, esse é o foco do fundamento de comunicabilidade, no qual tem o objetivo de transmitir ao usuário de forma eficaz e eficiente as intenções e princípios de interação que guiaram o seu design. Com isso, o nosso trabalho definiu a comunicabilidade para a classificação supervisionada aplicada a problema de interação humano computador pro análise crítico bem como ter maior compreensão dos sistemas em relação a melhoria na Usabilidade e experiência do usuário.

## 1.2 Atributos
Os atributos estão relacionados ao esforço, tempo e compreensão do usuário ao sistema, dentre eles temos:

- **Qtd_atividades**: Número de tarefas concluídas;
- **Tempo_gasto**: Tempo total em segundos da execução das tarefas;
- **Qtd_etiquetas**: Número de etiquetas violadas;
- **Num_ajudas_solicitadas**: Número de ajuda que o usuário solicitou;
- **Qtd_erros**: Número de falhas passos incorretos que o usuário cometeu ao tentar concluir as atividades.

## 1.3 Classe-Alvo
A classe-alvo é a comunicabilidade, em que foi divida em multiclasse:

- **Alta**: O sistema apresenta um índice alto de comunicabilidade;
- **Média**: O sistema apresenta um índice médio de comunicabilidade;
- **Baixa**: O sistema apresenta um índice baixo de comunicabilidade.

## 1.4 Sistema
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
<div align="justify">

## 5.1 Tabela de Acurácia

| Algoritmo | Acurácia |
| :--- | :--- |
| **ZeroR** | 41.76% |
| **OneR** | 81.76% |
| **J48** | 89.41% |
| **Ibk (K-nn)** | 87.06% |
| **Naive Bayes** | 83.53% |

- Com uma Acurácia de 41.76%, o ZeroR trabalha de maneira bem simplista, ignorando todos os atributos de previsão, por isso é tratado apenas como linha de base.
- Com uma Acurácia de 81.76%, o OneR já funciona de maneira diferente do anterior. Ele testa cada atributo individualmente, calculando a taxa de erro de cada um e, no final, escolhe o único atributo que, sozinho, forneceu a menor taxa de erro.
- Com uma Acurácia de 89.41%, o J48 trabalha de maneira mais complexa, criando um conjunto de regras “Se-Então” aninhadas (uma árvore, ou, como conhecemos, Tree), usando múltiplos atributos em combinação para tomar uma decisão.
- Com uma Acurácia de 87.06% (e não 87.85%), o IBk não funciona construindo um modelo de regras; ele apenas memoriza os dados de treinamento. Ele calcula a distância para todos os pontos do conjunto de treinamento, encontra o único ponto mais próximo e, assim, a nova instância recebe a mesma classe.
- Com uma Acurácia de 83.53%, o Naive Bayes se trata de um modelo probabilístico. Ele não constrói regras; em vez disso, calcula a probabilidade de uma instância pertencer a cada uma das classes e, no fim, escolhe a classe com maior probabilidade.

## 5.2 Matriz de Confusão

**ZeroR**

<img width="280" height="195" alt="ZeroR" src="https://github.com/user-attachments/assets/a6be3939-75c2-4675-9c2c-e7d6370bef42" />


- Sua Matriz de Confusão demonstra como o ZeroR opera: ele escolhe a classe mais comum ('Alta') para todas as instâncias, identificando a moda geral. Por isso, a classe 'Alta' é a única com instâncias previstas.

**OneR**

<img width="280" height="195" alt="OneR" src="https://github.com/user-attachments/assets/5e65f53d-f907-4161-89ad-c24255736ada" />


- Sua Matriz de Confusão, a princípio, tenta prever todas as três classes. O modelo apresenta uma taxa bem pequena de Falsos Negativos nas classes 'Alta' e, principalmente, 'Baixa', enquanto a classe 'Média' possui uma taxa maior de erros.

**J48**

<img width="280" height="195" alt="J48" src="https://github.com/user-attachments/assets/200a1823-aa42-48e6-aefc-03a7fb383801" />


- Sua Matriz de Confusão foi perfeita na análise da classe 'Baixa', apresentando apenas Verdadeiros Positivos, além de alcançar um desempenho quase perfeito na classe 'Alta'. Restou novamente à classe 'Média' a maior taxa de Falsos Negativos, apesar de ainda manter um bom desempenho.

**Ibk (K-nn)**

<img width="280" height="195" alt="Ibk (K-nn)" src="https://github.com/user-attachments/assets/acb5b74b-a198-43db-801f-4df4ea8565aa" />


- Sua Matriz de Confusão apresenta um desempenho praticamente perfeito na classe 'Baixa', com apenas um Falso Negativo (e não Falso Positivo). Dessa vez, a classe com mais erros é a 'Alta' (com 11 Falsos Negativos), sugerindo que, no espaço de atributos, esses 11 pontos 'Alta' estão mais próximos da 'Média'. A classe 'Média' também se encontra com uma taxa elevada de erros, com 10 no total.

**Naive Bayes**

<img width="280" height="195" alt="Naive Bayes" src="https://github.com/user-attachments/assets/833ec1c5-0bce-4415-8e94-f8b49f4ad343" />


- Em sua matriz de confusão, apesar de ter Recall perfeito na classe 'Baixa' (0 Falsos Negativos), o modelo classificou 9 instâncias que eram realmente da classe 'Média' como 'Baixa', diminuindo bastante sua Precisão (Precision) para a classe 'Baixa'. A classe 'Alta' foi bem consistente, com apenas 8 erros, enquanto a classe 'Média', novamente, teve o pior desempenho, acumulando 20 Falsos Negativos (e não Falsos Positivos).

## 5.3 Comparação dos Resultados

| Algoritmo | Como Funciona (Neste Caso) | Principal Ponto Fraco (Onde Errou) |
| :--- | :--- | :--- |
| ZeroR | Linha de base. Apenas previu a classe mais comum (alta) para todas as instâncias. | Ignorou 100% das classes baixa e media.|
| OneR | Criou 3 regras simples baseadas apenas no atributo Qtd_atividades. | Foi o pior modelo (sem contar o ZeroR) para a classe media (21 erros).|
| J48 | Criou uma árvore de regras complexa usando 5 atributos para tomar decisões. | O melhor de todos, mas ainda errou 14 instâncias da classe media.|
| IBk (k-nn) | "Preguiçoso". Classificou cada instância com base na classe do seu "vizinho" mais próximo. | Muito bom, mas confundiu 11 instâncias alta com media.|
| NaiveBayes | Probabilístico. Calculou a chance de ser de cada classe com base nas médias estatísticas dos atributos. | Errou muito na classe media (20 erros) e teve baixa precisão na baixa.|

## 5.4 Comparação dos Resultados - Validação das Regras Definidas
<div align="justify">
  
O ZeroR serve como a linha de base fundamental e demonstra o resultado das regras de pontuação, mas não a sua lógica. Este modelo ignora completamente todos os atributos preditivos (Qtd_atividades, Qtd_erros, etc.) e simplesmente identifica qual classe final (baixa, media ou alta) é a mais frequente no conjunto de dados. O fato de o modelo prever "alta" para todas as instâncias e atingir 41.76% de acurácia nos informa apenas uma coisa sobre o resultado do seu sistema de pontuação: ele produziu um conjunto de dados onde "alta" é a classe mais comum (a moda). A única função do ZeroR, portanto, é estabelecer o limite mínimo de desempenho que qualquer modelo inteligente deveria superar.

O OneR atuou como um validador do atributo-chave. Ele determinou que Qtd_atividades era o previsor individual mais forte, o que está em perfeito alinhamento com as regras de pontuação definidas. Enquanto a regra manual dava +1 ponto para $\ge 8 e -1$ para $\le 3$, o OneR aprendeu regras quase idênticas de forma independente: >= 7.5 \rightarrow alta e < 4.5 \rightarrow baixa. Isso confirma que Qtd_atividades, mesmo sozinho, é um indicador robusto da classe de comunicabilidade, justificando a acurácia de 81.76% do modelo.

O J48 apresentou a correspondência mais perfeita, e sua alta acurácia (89.41%) é justificada pela natureza do problema. O sistema de pontuação original, que combina múltiplos atributos com regras "Se-Então" (como Qtd_erros <= 5 e Qtd_atividades >= 8), é, em essência, uma árvore de decisão. O J48, sendo um algoritmo construtor de árvores, foi o mais apto a "redescobrir" essa lógica. A prova de sua eficácia é que o modelo final utilizou exatamente os mesmos cinco atributos (Qtd_atividades, Tempo_gasto, Qtd_etiquetas, Num_ajudas, Qtd_erros) que compõem o sistema de pontuação manual.

O IBk (com k=1) validou a consistência dos grupos criados pelas regras. Modelos baseados em distância, como o k-NN, só funcionam bem se as instâncias da mesma classe estiverem "próximas" umas das outras no espaço de atributos. O sistema de pontuação garante exatamente isso: todas as instâncias alta (pontuação maior ou igual a +3) serão, por definição, numericamente semelhantes (poucos erros, poucas ajudas, muitas atividades), formando um "agrupamento" (cluster). A alta acurácia de 87.06% do IBk prova que as regras de negócio criaram grupos consistentes e bem definidos, permitindo que a lógica do "vizinho mais próximo" fosse eficaz.

O NaiveBayes funcionou como um reflexo estatístico das regras de pontuação. Embora não aprenda regras explícitas, ele aprendeu o perfil médio de cada classe. Por exemplo, a regra de negócio determina que Qtd_erros $\le 5$ é positivo e $\ge 10$ é negativo. O modelo NaiveBayes capturou isso perfeitamente, aprendendo que a média de Qtd_erros para a classe alta é 3.63, enquanto a média para a classe baixa é 12.03. O desempenho do modelo (83.53%) valida que as classes têm perfis estatísticos distintos, embora a suposição "ingênua" de independência dos atributos o tenha impedido de superar os modelos baseados em regras ou distância.
</div>

# 6 - Análise crítica dos resultados em relação ao domínio de IHC
<div align="justify">

A análise dos resultados, sob a ótica da Interação Humano-Computador (IHC), oferece uma forte validação quantitativa para as heurísticas de interação usadas. O sucesso do modelo J48 (89.41% de acurácia) é a principal prova disso, demonstrando que o sistema de pontuação manual é consistente, lógico e "aprendível". Essencialmente, o J48 conseguiu "redescobrir" as regras de IHC, confirmando que os atributos escolhidos, como Qtd_erros e Num_ajudas, são indicadores reais e mensuráveis da qualidade da interação.

Além disso, o modelo OneR identificou o atributo Qtd_atividades como o indicador-chave (ou proxy) mais poderoso, uma descoberta prática para avaliadores de IHC. O sucesso do modelo IBk (87.06%) e as visualizações dos dados também confirmam que as regras de IHC foram eficazes em criar "agrupamentos" de dados consistentes e separáveis, onde a "Alta" comunicabilidade (vermelho) se agrupa claramente em oposição à "Baixa" (azul).

Finalmente, a análise crítica mais importante reside na fonte de erro: todos os modelos tiveram sua maior dificuldade com a classe 'Média'. Isso sugere que, embora as regras de IHC sejam excelentes para definir o sucesso e o fracasso claros ('Alta' e 'Baixa'), a definição de uma interação "mediana" é inerentemente ambígua. Esta classe representa a "zona cinzenta" da IHC, onde comportamentos mistos do usuário tornam a categorização difícil, tanto para um especialista humano quanto para um algoritmo.	


