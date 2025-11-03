# 1 - Definição do problema

## 1.1 Contexto e Motivação
<div align="justify">
&ensp;Para um sistema ser eficiente e que atenda ao seu usuário, é importante que se dê uma atenção maior entre os mesmos, esse é o foco do fundamento de comunicabilidade, no qual tem o objetivo de transmitir ao usuário de forma eficaz e eficiente as intenções e princípios de interação que guiaram o seu design. Com isso, o nosso trabalho definiu a comunicabilidade para a classificação supervisionada aplicada a problema de interação humano computador pro análise crítico bem como ter maior compreensão dos sistemas em relação a melhoria na Usabilidade e experiência do usuário.

## 1.2 Atributos
&ensp;Os atributos estão relacionados ao esforço, tempo e compreensão do usuário ao sistema, dentre eles temos:

- **Qtd_atividades**: Número de tarefas concluídas;
- **Tempo_gasto**: Tempo total em segundos da execução das tarefas;
- **Qtd_etiquetas**: Número de etiquetas violadas;
- **Num_ajudas**: Número de ajuda que o usuário solicitou;
- **Qtd_erros**: Número de falhas passos incorretos que o usuário cometeu ao tentar concluir as atividades.

## 1.3 Classe-Alvo
&ensp;A classe-alvo é a comunicabilidade, em que foi divida em multiclasse:

- **Alta**: O sistema apresenta um índice alto de comunicabilidade;
- **Média**: O sistema apresenta um índice médio de comunicabilidade;
- **Baixa**: O sistema apresenta um índice baixo de comunicabilidade.

## 1.4 Sistema
&ensp;Para a base sintética, foi gerado com o auxílio de IA, um sistema eccomerce simples contendo 10 tarefas, exclusivamente para dar um contexto ao trabalho:

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
10. Finalizar compra.

# 2 - Regras usadas para gerar a classe-alvo
&ensp;As definições e os critérios da classe-alvo foram organizados da seguinte maneira:

1. Os atributos foram categorizados por um sistema de pontuação, no qual cada atributo contribui com +1 ou -1.

## 2.1 Tabela de pontuação por atributo 
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
## 3.1 Tabela de requisitos da base
| Item | Descrição |
| :--- | :--- |
| **Ferramenta** | Gemini |
| **Formato** | .arff — compatível com o software Weka |
| **instâncias** | 500 instâncias |
| **Atributos** | 5 atributos númericos |
| **Classe-alvo** | 1 classe-alvo (multiclasse) |
| **Link para a base** | [comunicabilidade.arff](https://drive.google.com/drive/folders/1stLx6XCPeD8Ajohc_5s8rtSHb19Cae5J?usp=sharing) |

# 4 - Descrição dos experimentos Weka
<div align="justify">
 
&ensp;Para avaliar a capacidade de diferentes algoritmos de aprendizado de máquina em classificar a comunicabilidade do sistema, foi desenhado um protocolo experimental utilizando o software Weka. Abaixo, toda a descrição:

## 4.1. Ambiente e Conjunto de Dados
- Software: Weka;

- Conjunto de Dados: Foi utilizada a base sintética comunicabilidade_dados.arff, descrita na Seção 3, contendo 500 instâncias, 5 atributos preditores numéricos (Qtd_atividades, Tempo_gasto, Qtd_etiquetas, Num_ajudas, Qtd_erros) e 1 atributo-alvo nominal (comunicabilidade). 

## 4.2. Algoritmos Selecionados
&ensp;Foram selecionados cinco algoritmos de classificação, cada um representando uma abordagem diferente de aprendizado, para testar distintas hipóteses sobre os dados:

**ZeroR**:

- Categoria: Regras (Baseline);

- Propósito: Servir como linha de base (baseline) de desempenho. Este modelo simplesmente prevê a classe majoritária (a "moda") presente nos dados de treino, ignorando todos os atributos.

![[Resultados do ZeroR](https://i.postimg.cc/tgc987FQ/Zero-R.png)](https://i.postimg.cc/tgc987FQ/Zero-R.png)
<p align="center">
Figura 1: Resultado da execução do ZeroR.
</p>

**OneR** 
(weka.classifiers.rules.OneR):

- Categoria: Regras (Simples);

- Propósito: Identificar qual dos cinco atributos, sozinho, possui o maior poder preditivo para a classe-alvo.

![[Resultados do OneR](https://i.postimg.cc/cJCsDfgb/One-R.png)](https://i.postimg.cc/cJCsDfgb/One-R.png)
<p align="center">
Figura 2: Resultado da execução do OneR.
</p>

**J48** 
(weka.classifiers.trees.J48):

- Categoria: Árvores de Decisão (baseado no C4.5);

- Propósito: Verificar se a lógica de classificação, que foi baseada em regras de pontuação (Seção 2), poderia ser "redescoberta" por um algoritmo que naturalmente gera regras "Se-Então".

![[Resultados do J48](https://i.postimg.cc/VNvY7XrG/J48.png)](https://i.postimg.cc/VNvY7XrG/J48.png)
<p align="center">
Figura 3: Resultado da execução do J48.
</p>

**IBk** 
(weka.classifiers.lazy.IBk):

- Categoria: Baseado em Instâncias (k-Nearest Neighbors);

- Propósito: Avaliar a consistência e a separação dos grupos. Se instâncias da mesma classe (ex: "alta") estão numericamente "próximas" umas das outras, este modelo deve ter um bom desempenho.

![[Resultados do IBk](https://i.postimg.cc/vZ3YL0B6/IBK.png)](https://i.postimg.cc/vZ3YL0B6/IBK.png)
<p align="center">
Figura 4: Resultado da execução do IBk (k=1).
</p>

**NaiveBayes**
(weka.classifiers.bayes.NaiveBayes):

- Categoria: Probabilístico (Bayesiano);

- Propósito: Testar a eficácia de um modelo estatístico que calcula a probabilidade de uma instância pertencer a uma classe com base nos perfis médios de cada atributo.

![[Resultados do NaiveBayes](https://i.postimg.cc/zfvJdTbx/Naive-Bayes.png)](https://i.postimg.cc/zfvJdTbx/Naive-Bayes.png)
<p align="center">
Figura 5: Resultado da execução do NaiveBayes.
</p>

**RandomForest** 
(weka.classifiers.trees.RandomForest):

- Categoria: Método de Conjunto (Ensemble) de Árvores de Decisão;

- Propósito: Testar a robustez e a estabilidade das regras de pontuação. Ao construir um "comitê" de árvores de decisão (em vez de apenas uma, como o J48) com base em subconjuntos aleatórios dos dados, este modelo avalia se a lógica de classificação é um sinal forte e geral, capaz de ser identificado consistentemente por múltiplos "especialistas".

![[Resultados do Random Forest](https://i.postimg.cc/jj2s8ywm/Random-Forest.png)](https://i.postimg.cc/jj2s8ywm/Random-Forest.png)
<p align="center">
Figura 6: Resultado da execução do Random Forest.
</p>

## 4.3 Exploração de Dados

**Matriz de Dispersão**

Esta imagem é uma Matriz de Dispersão (Plot Matrix) gerada pela aba "Visualize" do software Weka. Ela compara visualmente cada atributo do conjunto de dados contra todos os outros.

Os pontos são coloridos de acordo com as três classes de comunicabilidade (vermelho, azul e ciano para "alta", "média" e "baixa").

![[Resultados do Random Forest](https://i.postimg.cc/L4fVDBQx/weka-ihc-visualize.png)](https://i.postimg.cc/L4fVDBQx/weka-ihc-visualize.png)
<p align="center">
Figura 7: Matriz de Dispersão.
</p>

### 4.3.1 Alguns exemplos de gráficos de dispersão

**Quantidade de Erros x Quantidade de Etiquetas**

Este gráfico de dispersão (scatter plot) do Weka ilustra a forte relação entre a Qtd_erros (eixo X, de 1 a 15) e a Qtd_etiquetas (eixo Y, de 1 a 11).

Alta (verde): Os pontos estão concentrados no canto inferior esquerdo, indicando que sistemas com alta comunicabilidade apresentam poucos erros e poucas etiquetas violadas.

Baixa (azul): Os pontos agrupam-se no canto superior direito, mostrando que sistemas com baixa comunicabilidade têm muitos erros e muitas etiquetas violadas.

Média (vermelho): Os pontos ocupam a região intermediária e também se sobrepõem ao grupo 'alta', o que reforça a ideia de que a classe 'média' é um caso-limite entre as duas.

![[Resultados do Random Forest](https://i.postimg.cc/zDWk7S2k/erros-por-etiquetas.png)](https://i.postimg.cc/zDWk7S2k/erros-por-etiquetas.png)
<p align="center">
Figura 8: Quantidade de Erros x Quantidade de Etiquetas.
</p>

**Quantidade de Etiquetas x Comunicabilidade**

Este gráfico de dispersão (scatter plot) do Weka visualiza diretamente a relação entre a classe-alvo comunicabilidade (eixo X) e o atributo Qtd_etiquetas (eixo Y).

A imagem confirma de forma explícita as regras de negócio usadas na geração dos dados:

Classe 'baixa' (azul): Ocorre quase exclusivamente quando a Qtd_etiquetas violadas é alta (aproximadamente de 6 a 11).

Classe 'alta' (verde): Ocorre predominantemente quando a Qtd_etiquetas é baixa (aproximadamente de 1 a 6).

Classe 'media' (vermelho): Ocupa uma faixa central, mas se espalha por quase todo o espectro de valores de etiquetas, representando os casos que não se enquadram nos extremos "alto" ou "baixo".

![[Resultados do Random Forest](https://i.postimg.cc/8kWb4BXh/comunicabilidade-quantde-Etiqueta.png)](https://i.postimg.cc/8kWb4BXh/comunicabilidade-quantde-Etiqueta.png)
<p align="center">
Figura 9: Quantidade de Etiquetas x Comunicabilidade
</p>

**Tempo Gasto x Comunicabilidade**

Este gráfico de dispersão do Weka compara a classe-alvo comunicabilidade (eixo X) com o atributo Tempo_gasto (eixo Y).

A visualização mostra uma separação de classes muito nítida, que se alinha perfeitamente com as regras de pontuação definidas:

Classe 'baixa' (azul): Está fortemente concentrada na faixa inferior de Tempo_gasto (aproximadamente de 103s a 250s). Isso valida a regra de que um tempo de execução muito baixo ($\le 200s$) é um indicador negativo (-1 ponto), sugerindo que o usuário pode ter abandonado as tarefas rapidamente por frustração.

Classe 'alta' (verde): Agrupa-se distintamente na faixa superior de Tempo_gasto (aproximadamente de 250s a 400s). Isso valida a regra de que um tempo de execução alto ($\ge 301s$) é um indicador positivo (+1 ponto), sugerindo que o usuário estava engajado e completando o conjunto de tarefas.

Classe 'media' (vermelho): Ocupa a região intermediária, preenchendo o espaço entre os dois extremos.

![[Resultados do Random Forest](https://i.postimg.cc/NGTxD7Ck/comunicabilidade-tempo-Gasto.png)](https://i.postimg.cc/NGTxD7Ck/comunicabilidade-tempo-Gasto.png)
<p align="center">
Figura 10: Tempo Gasto x Comunicabilidade
</p>

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
| **Random Forest** | 90% |

- Com uma Acurácia de 41.76%, o ZeroR trabalha de maneira bem simplista, ignorando todos os atributos de previsão, por isso é tratado apenas como linha de base;
- Com uma Acurácia de 81.76%, o OneR já funciona de maneira diferente do anterior. Ele testa cada atributo individualmente, calculando a taxa de erro de cada um e, no final, escolhe o único atributo que, sozinho, forneceu a menor taxa de erro;
- Com uma Acurácia de 89.41%, o J48 trabalha de maneira mais complexa, criando um conjunto de regras “Se-Então” aninhadas (uma árvore, ou, como conhecemos, Tree), usando múltiplos atributos em combinação para tomar uma decisão;
- Com uma Acurácia de 87.06% (e não 87.85%), o IBk não funciona construindo um modelo de regras; ele apenas memoriza os dados de treinamento. Ele calcula a distância para todos os pontos do conjunto de treinamento, encontra o único ponto mais próximo e, assim, a nova instância recebe a mesma classe;
- Com uma Acurácia de 83.53%, o Naive Bayes se trata de um modelo probabilístico. Ele não constrói regras; em vez disso, calcula a probabilidade de uma instância pertencer a cada uma das classes e, no fim, escolhe a classe com maior probabilidade;
- Com uma Acurácia de 90%, o Random Forest se trata de um modelo robusto. Configurado para receber 100 árvores de decisão para classificar os dasdos. Ele constrói diversos árvores de Decisão simples e combina os resultaodos para chegar a uma resposta final muito mais robusta.
  
## 5.2 Matriz de Confusão

**ZeroR**

<img width="280" height="195" alt="image" src="https://github.com/user-attachments/assets/ad781bbf-0dd0-4c67-9d1c-e0a898cd7eac" />


- Sua Matriz de Confusão demonstra como o ZeroR opera: ele escolhe a classe mais comum ('Alta') para todas as instâncias, identificando a moda geral. Por isso, a classe 'Alta' é a única com instâncias previstas.

**OneR**

<img width="280" height="195" alt="image" src="https://github.com/user-attachments/assets/9b9f2246-bed8-4cdf-a05a-265e21234539" />


- Sua Matriz de Confusão, a princípio, tenta prever todas as três classes. O modelo apresenta uma taxa bem pequena de Falsos Negativos nas classes 'Alta' e, principalmente, 'Baixa', enquanto a classe 'Média' possui uma taxa maior de erros.

**J48**

<img width="280" height="195" alt="image" src="https://github.com/user-attachments/assets/c4c00f33-c10e-4a80-a65d-3f629f40b31a" />


- Sua Matriz de Confusão foi perfeita na análise da classe 'Baixa', apresentando apenas Verdadeiros Positivos, além de alcançar um desempenho quase perfeito na classe 'Alta'. Restou novamente à classe 'Média' a maior taxa de Falsos Negativos, apesar de ainda manter um bom desempenho.

**Ibk (K-nn)**

<img width="280" height="195" alt="image" src="https://github.com/user-attachments/assets/acbdb915-2872-40d6-9134-2b0332653dc1" />


- Sua Matriz de Confusão apresenta um desempenho praticamente perfeito na classe 'Baixa', com apenas um Falso Negativo (e não Falso Positivo). Dessa vez, a classe com mais erros é a 'Alta' (com 11 Falsos Negativos), sugerindo que, no espaço de atributos, esses 11 pontos 'Alta' estão mais próximos da 'Média'. A classe 'Média' também se encontra com uma taxa elevada de erros, com 10 no total.

**Naive Bayes**

<img width="280" height="195" alt="image" src="https://github.com/user-attachments/assets/7c35f6c2-8277-4999-947e-ebb6dbc9a686" />


- Sua Matriz de Confusão, apesar de ter Recall perfeito na classe 'Baixa' (0 Falsos Negativos), o modelo classificou 9 instâncias que eram realmente da classe 'Média' como 'Baixa', diminuindo bastante sua Precisão (Precision) para a classe 'Baixa'. A classe 'Alta' foi bem consistente, com apenas 8 erros, enquanto a classe 'Média', novamente, teve o pior desempenho, acumulando 20 Falsos Negativos (e não Falsos Positivos).
  
**Random Forest**
  
  <img width="280" height="195" alt="Random Forest" src="https://github.com/user-attachments/assets/16547c88-7b5a-4de2-9805-93e963e2cfd8" />

  
  - Sua Matriz de Confusão, possui uma taxa de acerto perfeita na Classe "baixa" com 34 Verdadeiros Positivos. Sua análise Classe "baixa" foi quase perfeita também, possuindo apenas 6 Falsos Positivos, com uma taxa de Acerto de 91.5%. Como era de se esperar, a Classe "Média" possui a maior taxa de erros, tendo 11 instâncias classificadas erroneamente, ainda assim, considerando o histórico, foi uma taxa de acerto bem acima da média.

## 5.3 Comparação dos Resultados

| Algoritmo | Como Funciona (Neste Caso) | Principal Ponto Fraco (Onde Errou) |
| :--- | :--- | :--- |
| **ZeroR** | Linha de base. Apenas previu a classe mais comum (alta) para todas as instâncias. | Ignorou 100% das classes baixa e media.|
| **OneR** | Criou 3 regras simples baseadas apenas no atributo Qtd_atividades. | Foi o pior modelo (sem contar o ZeroR) para a classe media (21 erros).|
| **J48** | Criou uma árvore de regras complexa usando 5 atributos para tomar decisões. | O melhor de todos, mas ainda errou 14 instâncias da classe media.|
| **IBk (k-nn)** | "Preguiçoso". Classificou cada instância com base na classe do seu "vizinho" mais próximo. | Muito bom, mas confundiu 11 instâncias alta com media.|
| **NaiveBayes** | Probabilístico. Calculou a chance de ser de cada classe com base nas médias estatísticas dos atributos. | Errou muito na classe media (20 erros) e teve baixa precisão na baixa.|
| **Random Forest** | Constrói 100 árvores de decisão e classifica pela "votação" da maioria. | O modelo mais preciso (17 erros), mas a classe "media" ainda foi a mais difícil (11 erros). |

## 5.4 Comparação dos Resultados - Validação das Regras Definidas
<div align="justify">
  
&ensp;O ZeroR serve como a linha de base fundamental e demonstra o resultado das regras de pontuação, mas não a sua lógica. Este modelo ignora completamente todos os atributos preditivos (Qtd_atividades, Qtd_erros, etc.) e simplesmente identifica qual classe final (baixa, media ou alta) é a mais frequente no conjunto de dados. O fato de o modelo prever "alta" para todas as instâncias e atingir 41.76% de acurácia nos informa apenas uma coisa sobre o resultado do seu sistema de pontuação: ele produziu um conjunto de dados onde "alta" é a classe mais comum (a moda). A única função do ZeroR, portanto, é estabelecer o limite mínimo de desempenho que qualquer modelo inteligente deveria superar.

&ensp;O OneR atuou como um validador do atributo-chave. Ele determinou que Qtd_atividades era o previsor individual mais forte, o que está em perfeito alinhamento com as regras de pontuação definidas. Enquanto a regra manual dava +1 ponto para $\ge 8 e -1$ para $\le 3$, o OneR aprendeu regras quase idênticas de forma independente: >= 7.5 \rightarrow alta e < 4.5 \rightarrow baixa. Isso confirma que Qtd_atividades, mesmo sozinho, é um indicador robusto da classe de comunicabilidade, justificando a acurácia de 81.76% do modelo.

&ensp;O J48 apresentou a correspondência mais perfeita, e sua alta acurácia (89.41%) é justificada pela natureza do problema. O sistema de pontuação original, que combina múltiplos atributos com regras "Se-Então" (como Qtd_erros <= 5 e Qtd_atividades >= 8), é, em essência, uma árvore de decisão. O J48, sendo um algoritmo construtor de árvores, foi o mais apto a "redescobrir" essa lógica. A prova de sua eficácia é que o modelo final utilizou exatamente os mesmos cinco atributos (Qtd_atividades, Tempo_gasto, Qtd_etiquetas, Num_ajudas, Qtd_erros) que compõem o sistema de pontuação manual.

&ensp;O IBk (com k=1) validou a consistência dos grupos criados pelas regras. Modelos baseados em distância, como o k-NN, só funcionam bem se as instâncias da mesma classe estiverem "próximas" umas das outras no espaço de atributos. O sistema de pontuação garante exatamente isso: todas as instâncias alta (pontuação maior ou igual a +3) serão, por definição, numericamente semelhantes (poucos erros, poucas ajudas, muitas atividades), formando um "agrupamento" (cluster). A alta acurácia de 87.06% do IBk prova que as regras de negócio criaram grupos consistentes e bem definidos, permitindo que a lógica do "vizinho mais próximo" fosse eficaz.

&ensp;O NaiveBayes funcionou como um reflexo estatístico das regras de pontuação. Embora não aprenda regras explícitas, ele aprendeu o perfil médio de cada classe. Por exemplo, a regra de negócio determina que Qtd_erros $\le 5$ é positivo e $\ge 10$ é negativo. O modelo NaiveBayes capturou isso perfeitamente, aprendendo que a média de Qtd_erros para a classe alta é 3.63, enquanto a média para a classe baixa é 12.03. O desempenho do modelo (83.53%) valida que as classes têm perfis estatísticos distintos, embora a suposição "ingênua" de independência dos atributos o tenha impedido de superar os modelos baseados em regras ou distância.

&ensp;O RandomForest está perfeitamente de acordo com as regras definidas e, de fato, reforça a complexidade delas. O algoritmo funciona construindo um "comitê" de 100 árvores de decisão (semelhantes ao J48) e usa a votação delas para classificar. Visto que o seu sistema de pontuação original já é um conjunto complexo de regras combinadas (somando pontos de 5 atributos), um modelo de ensemble como o RandomForest é teoricamente ideal para "aprender" essa lógica. A prova disso está nos resultados: o RandomForest alcançou a maior acurácia de todos os modelos (90.0%), superando por uma pequena margem a já excelente árvore de decisão única J48 (89.41%). Isso demonstra que, ao combinar as "opiniões" de 100 árvores, o modelo foi o mais eficaz em replicar o sistema de pontuação original e lidar com as "zonas cinzentas" (como a classe media) que confundiam os modelos mais simples.
</div>

# 6 - Análise crítica dos resultados em relação ao domínio de IHC
<div align="justify">

## 6.1 Análise crítica

&ensp;A análise dos modelos de machine learning vai além de uma simples competição de acurácia; ela atua como uma validação quantitativa das heurísticas de IHC usadas para definir o conceito de "comunicabilidade". Os resultados são extremamente positivos, pois confirmam que os comportamentos observáveis do usuário (os atributos) são, de fato, preditores robustos da qualidade da interação. O sucesso dos modelos baseados em árvores é a validação mais forte. O problema foi definido por um sistema de pontuação manual, que é, em essência, um conjunto de regras "Se-Então". Os modelos de melhor desempenho foram justamente o J48 (uma única árvore de decisão)  e o RandomForest (um conjunto de 100 árvores). O sucesso deles prova que as regras de IHC definidas são lógicas, consistentes e "aprendíveis". O J48, por exemplo, utilizou os mesmos cinco atributos do sistema de pontuação manual para construir seu modelo, mostrando uma correspondência direta.

&ensp;O resultado do OneR (81.76% de acurácia) oferece o insight mais prático para um avaliador de IHC. O modelo determinou que Qtd_atividades era o previsor individual mais forte. As regras que ele aprendeu (< 4.5 para 'baixa', > 7.5 para 'alta') são quase idênticas às regras de pontuação manuais ($\le 3$ e $\ge 8$), validando este atributo como um proxy poderoso e confiável para medir a comunicabilidade.

&ensp;O sucesso do IBk (k-NN) confirmam que as definições de IHC criam grupos de comportamento distintos. As visualizações mostram que 'Alta' comunicabilidade (vermelho) se agrupa onde erros e etiquetas são baixos, enquanto 'Baixa' (azul) se agrupa onde são altos. O bom desempenho do IBk, um modelo baseado em distância, prova que essas regras de pontuação criam "clusters" de usuários que são matematicamente consistentes e separáveis.

&ensp;A análise crítica mais importante vem dos erros. Em todos os modelos de alto desempenho (J48 , IBk , Naive Bayes  e RandomForest), a classe 'Média' foi consistentemente a mais difícil de classificar e a maior fonte de falsos negativos. Isso sugere que, embora as heurísticas de IHC sejam excelentes para definir o sucesso claro ('Alta') e o fracasso claro ('Baixa'), a interação "mediana" é inerentemente ambígua. Esses usuários provavelmente exibem comportamentos mistos (ex: rápidos, mas com muitos erros) que desafiam uma categorização simples, representando a verdadeira "zona cinzenta" da interação, tanto para algoritmos quanto para avaliadores humanos.
