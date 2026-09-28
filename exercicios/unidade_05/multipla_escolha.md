# Unidade V — Classificação e Regressão — Múltipla escolha

**Instruções:** assinale uma única alternativa por questão. O gabarito comentado é distribuído separadamente.

## U05-M01

Qual situação caracteriza regressão?

- [ ] **A.** Prever a espécie de uma flor
- [ ] **B.** Estimar o valor numérico de consumo mensal
- [ ] **C.** Classificar uma mensagem como fraude ou legítima
- [ ] **D.** Atribuir uma categoria de risco

## U05-M02

Qual procedimento constitui vazamento na avaliação?

- [ ] **A.** Fixar a semente da divisão
- [ ] **B.** Estratificar um alvo categórico
- [ ] **C.** Ajustar o modelo apenas no treino
- [ ] **D.** Escolher repetidamente hiperparâmetros pelo teste final

## U05-M03

A métrica que responde “entre os positivos reais, quantos foram encontrados?” é:

- [ ] **A.** Revocação
- [ ] **B.** Precisão
- [ ] **C.** Especificidade
- [ ] **D.** Acurácia

## U05-M04

Reduzir o limiar de classificação geralmente:

- [ ] **A.** Reduz positivos e falsos positivos
- [ ] **B.** Não altera a matriz de confusão
- [ ] **C.** Aumenta positivos previstos e tende a elevar a revocação
- [ ] **D.** Garante menor custo em qualquer aplicação

## U05-M05

A principal simplificação do Naive Bayes é assumir:

- [ ] **A.** Classes igualmente frequentes
- [ ] **B.** Independência condicional dos atributos dada a classe
- [ ] **C.** Distância Euclidiana entre objetos
- [ ] **D.** Relação causal entre evidências e classe

## U05-M06

A suavização de Laplace é usada principalmente para:

- [ ] **A.** Padronizar atributos numéricos
- [ ] **B.** Remover classes raras
- [ ] **C.** Escolher o número de vizinhos
- [ ] **D.** Evitar que frequência não observada produza probabilidade zero

## U05-M07

No k-NN, atributos em escalas muito diferentes podem:

- [ ] **A.** Fazer o atributo de maior amplitude dominar a distância
- [ ] **B.** Tornar a escolha de distância irrelevante
- [ ] **C.** Garantir vizinhos mais representativos
- [ ] **D.** Eliminar a necessidade de validação

## U05-M08

Aumentar muito $k$ tende a:

- [ ] **A.** Memorizar cada ponto isolado
- [ ] **B.** Reduzir sempre o tempo de previsão
- [ ] **C.** Suavizar a decisão e aproximá-la da classe majoritária
- [ ] **D.** Tornar escala e atributos irrelevantes

## U05-M09

Em uma árvore de decisão, a previsão final fica:

- [ ] **A.** Na raiz
- [ ] **B.** No ramo mais longo
- [ ] **C.** No atributo de maior importância
- [ ] **D.** Na folha alcançada pelo objeto

## U05-M10

Um nó de classificação puro possui índice Gini:

- [ ] **A.** 1
- [ ] **B.** 0
- [ ] **C.** 0,5 em qualquer problema
- [ ] **D.** Igual ao número de classes

## U05-M11

Qual padrão sugere sobreajuste de uma árvore?

- [ ] **A.** Desempenho muito alto no treino e queda relevante no teste
- [ ] **B.** Resultados idênticos ao baseline em todas as partições
- [ ] **C.** Poucas folhas e erros iguais
- [ ] **D.** Uso de atributos numéricos

## U05-M12

Importância alta de um atributo em uma árvore significa que:

- [ ] **A.** O atributo causa o alvo
- [ ] **B.** Seu valor deve ser aumentado por intervenção
- [ ] **C.** Ele reduziu impureza naquela árvore, sem prova causal
- [ ] **D.** Ele será importante em qualquer população

## U05-M13

Se $y=30$ e $\hat y=36$, o resíduo $y-\hat y$ é:

- [ ] **A.** 6
- [ ] **B.** −6
- [ ] **C.** 66
- [ ] **D.** 1,2

## U05-M14

Qual métrica de regressão penaliza mais fortemente erros grandes e permanece na unidade do alvo?

- [ ] **A.** Acurácia
- [ ] **B.** $R^2$
- [ ] **C.** MSE
- [ ] **D.** RMSE

## U05-M15

$R^2<0$ no teste indica que o modelo:

- [ ] **A.** Foi pior, em erro quadrático, que a referência pela média
- [ ] **B.** Explicou causalmente uma relação negativa
- [ ] **C.** Possui resíduos todos negativos
- [ ] **D.** Não pode produzir previsões numéricas

## U05-M16

Prever para 400 m² após treinar apenas entre 40 e 180 m² é:

- [ ] **A.** Interpolação segura
- [ ] **B.** Classificação ordinal
- [ ] **C.** Extrapolação que exige cautela
- [ ] **D.** Evidência causal

## U05-M17

No bagging, cada modelo-base é treinado principalmente em:

- [ ] **A.** Uma amostra bootstrap do treino
- [ ] **B.** Todo o conjunto de teste
- [ ] **C.** Apenas objetos classificados corretamente
- [ ] **D.** Uma classe por vez

## U05-M18

Além de bootstrap, a floresta aleatória diversifica árvores por:

- [ ] **A.** Remoção do alvo
- [ ] **B.** Subconjuntos aleatórios de atributos em cada divisão
- [ ] **C.** Uso obrigatório de distância Euclidiana
- [ ] **D.** Um único nível de profundidade

## U05-M19

Qual característica distingue boosting de bagging?

- [ ] **A.** Não usa modelos-base
- [ ] **B.** Sempre produz uma árvore única
- [ ] **C.** Constrói modelos sequencialmente, dando atenção aos erros anteriores
- [ ] **D.** Usa o teste para atualizar pesos

## U05-M20

Se todos os componentes erram exatamente os mesmos objetos, a principal limitação é:

- [ ] **A.** Excesso de classes
- [ ] **B.** Falta de escala
- [ ] **C.** Ausência de bootstrap no teste
- [ ] **D.** Falta de diversidade útil

## U05-M21

A importância por permutação mede principalmente:

- [ ] **A.** A queda de desempenho ao destruir a informação de um atributo
- [ ] **B.** O efeito causal de aumentar o atributo
- [ ] **C.** A quantidade de valores distintos
- [ ] **D.** A frequência do alvo

## U05-M22

Um valor de Shapley local positivo indica que o atributo:

- [ ] **A.** Causa o desfecho
- [ ] **B.** Elevou a saída explicada em relação ao valor-base
- [ ] **C.** Deve ser removido
- [ ] **D.** É globalmente o mais importante

## U05-M23

Dois atributos fortemente correlacionados podem apresentar baixa importância individual por permutação porque:

- [ ] **A.** Permutação só funciona em regressão
- [ ] **B.** A correlação elimina o alvo
- [ ] **C.** Um pode substituir informação do outro
- [ ] **D.** Ambos se tornam causais

## U05-M24

Qual conclusão é responsável?

- [ ] **A.** Maior Shapley prova causalidade
- [ ] **B.** Importância de impureza vale para qualquer população
- [ ] **C.** Explicações dispensam teste
- [ ] **D.** Relevância depende do modelo, dados, métrica e referência
