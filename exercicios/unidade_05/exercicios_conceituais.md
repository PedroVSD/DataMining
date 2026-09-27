# Unidade V — Exercícios conceituais

**Tema:** classificação, avaliação, Naive Bayes, k-NN, árvores e regressão linear  
**Objetivos avaliados:** formular tarefas supervisionadas; interpretar métricas e custos; explicar intuitivamente os três classificadores; calcular divisões de árvores; ajustar e avaliar regressões; comunicar limitações e evitar conclusões causais.  
**Tempo estimado:** 150 minutos  
**Instruções:** justifique decisões, apresente cálculos e interprete resultados no contexto. Não atribua causalidade a resultados preditivos.

## Formulação e avaliação de classificação

1. **U05-C01.** Diferencie classificação e regressão. Para cada tarefa, defina unidade de análise, atributos e alvo: prever abandono de um curso; estimar o tempo até a conclusão de uma atividade.

2. **U05-C02.** Explique as funções de treino, validação e teste. Por que escolher hiperparâmetros repetidamente com base no teste constitui vazamento do processo de avaliação?

3. **U05-C03.** Uma base de teste possui $VN=810$, $FP=90$, $FN=60$ e $VP=40$. Calcule acurácia, precisão, revocação e F1 da classe positiva. Compare com o classificador que sempre prevê negativo.

4. **U05-C04.** Em detecção de fraude, um falso negativo custa R$ 500 e um falso positivo custa R$ 10. Compare os classificadores A, com $FP=100$ e $FN=8$, e B, com $FP=250$ e $FN=3$. Qual possui menor custo sob esses pesos? Por que essa resposta não é universal?

## Naive Bayes e k-NN

5. **U05-C05.** Para duas classes igualmente frequentes, um objeto possui $P(x_1\mid C_1)=0{,}8$, $P(x_2\mid C_1)=0{,}5$, $P(x_1\mid C_2)=0{,}3$ e $P(x_2\mid C_2)=0{,}9$. Calcule os escores e posteriores do Naive Bayes e indique a classe.

6. **U05-C06.** Explique a independência condicional e a correção de Laplace. O que aconteceria ao produto do Naive Bayes se uma probabilidade condicional fosse zero?

7. **U05-C07.** Um k-NN usa renda entre R$ 1.000 e R$ 50.000 e número de atrasos entre 0 e 4. Explique por que a renda pode dominar a distância Euclidiana e proponha um procedimento correto de padronização sem vazamento.

8. **U05-C08.** Compare $k=1$ e um $k$ muito grande quanto a ruído, fronteira local, classe majoritária e custo de previsão. Explique como escolher $k$ sem usar o teste final.

## Árvores de decisão

9. **U05-C09.** Diferencie raiz, nó interno, ramo e folha. Converta um caminho com as condições “renda ≤ 3.000” e “atrasos > 1” em uma regra `SE–ENTÃO`.

10. **U05-C10.** Um nó possui oito objetos da classe 0 e dois da classe 1. Uma divisão gera grupos $(7,0)$ e $(1,2)$. Calcule o Gini da raiz, dos grupos, a impureza ponderada e a redução de Gini.

11. **U05-C11.** Uma árvore obtém acurácia 100% no treino e 68% no teste, com 240 folhas. Diagnostique o problema e proponha duas estratégias de pré-poda e uma de pós-poda.

12. **U05-C12.** Explique por que importância por redução de impureza não mede efeito causal. Discuta atributos correlacionados, alta cardinalidade e identificadores.

## Regressão linear

13. **U05-C13.** Para $\hat y=20+3x$, calcule a previsão em $x=10$ e o resíduo quando $y=44$. Interprete intercepto, coeficiente e sinal do resíduo.

14. **U05-C14.** Para valores observados $[10,20,30,40]$ e previstos $[12,18,33,37]$, calcule resíduos, MAE e RMSE. Explique por que RMSE é maior ou igual ao MAE.

15. **U05-C15.** Em uma regressão de preço, os coeficientes são 4 para área e −2 para idade. Interprete-os com unidades e a expressão “mantendo os demais constantes”. Explique como colinearidade entre área e número de quartos pode afetar os coeficientes.

16. **U05-C16.** Um modelo treinado com imóveis entre 40 e 180 m² recebe um imóvel de 400 m². Diferencie interpolação de extrapolação, proponha verificações antes de usar a previsão e explique por que $R^2$ alto não resolve o problema.
