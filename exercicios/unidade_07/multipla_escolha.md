# Unidade VII — Detecção de *Outliers* — Múltipla escolha

**Instruções:** assinale uma única alternativa por questão. O gabarito comentado é distribuído separadamente.

## U07-M01

Uma observação é contextual quando:

- [ ] **A.** é incomum apenas em relação a uma condição como horário ou perfil
- [ ] **B.** possui sempre o maior valor numérico da base
- [ ] **C.** foi confirmada como erro de coleta
- [ ] **D.** forma obrigatoriamente um grupo unitário

## U07-M02

Qual situação representa melhor uma anomalia coletiva?

- [ ] **A.** Um único preço digitado com uma casa decimal a mais
- [ ] **B.** O maior valor de uma distribuição normal
- [ ] **C.** Uma sequência de pequenas oscilações que, em conjunto, forma padrão incomum
- [ ] **D.** Qualquer ponto com escore-z positivo

## U07-M03

Um alerta de anomalia permite concluir diretamente que houve fraude?

- [ ] **A.** Sim, se dois detectores concordarem
- [ ] **B.** Não; ele indica desvio da referência e requer investigação causal
- [ ] **C.** Sim, se o valor estiver fora da cerca do boxplot
- [ ] **D.** Não, porque fraude nunca pode ser detectada em dados

## U07-M04

No escore-z, o denominador representa:

- [ ] **A.** a mediana
- [ ] **B.** o intervalo interquartil
- [ ] **C.** a quantidade de alertas
- [ ] **D.** o desvio-padrão da referência

## U07-M05

Qual limitação afeta média e desvio-padrão na detecção de extremos?

- [ ] **A.** Podem ser deslocados pelos próprios extremos
- [ ] **B.** Só podem ser usados em atributos nominais
- [ ] **C.** Não permitem valores negativos
- [ ] **D.** Produzem sempre o mesmo resultado do MAD

## U07-M06

A cerca superior usual da regra do IQR é:

- [ ] **A.** $Q_1+Q_3$
- [ ] **B.** $Q_3+1{,}5(Q_3-Q_1)$
- [ ] **C.** $\bar{x}+3s$ em qualquer distribuição
- [ ] **D.** $\tilde{x}+MAD$

## U07-M07

O MAD é calculado como:

- [ ] **A.** média dos desvios quadráticos em relação à média
- [ ] **B.** diferença entre máximo e mínimo
- [ ] **C.** mediana dos desvios absolutos em relação à mediana
- [ ] **D.** distância ao k-ésimo vizinho

## U07-M08

Se $MAD=0$, a atitude mais adequada é:

- [ ] **A.** declarar todo valor como normal
- [ ] **B.** dividir por zero e ignorar o aviso
- [ ] **C.** excluir os valores repetidos
- [ ] **D.** reconhecer a degeneração e escolher outra referência ou tratamento

## U07-M09

Na distância ao k-ésimo vizinho, aumentar $k$ geralmente:

- [ ] **A.** amplia a vizinhança usada e suaviza detalhes locais
- [ ] **B.** elimina a necessidade de padronização
- [ ] **C.** torna todas as distâncias iguais a zero
- [ ] **D.** fornece a causa da anomalia

## U07-M10

Um LOF próximo de 1 indica que o objeto:

- [ ] **A.** é certamente uma fraude
- [ ] **B.** tem densidade local semelhante à de seus vizinhos
- [ ] **C.** está exatamente no centroide global
- [ ] **D.** deve ser removido

## U07-M11

Por que LOF pode ser útil quando há regiões com densidades distintas?

- [ ] **A.** Porque ignora completamente os vizinhos
- [ ] **B.** Porque exige rótulos de anomalia no treino
- [ ] **C.** Porque compara a densidade do ponto com a densidade local dos vizinhos
- [ ] **D.** Porque sempre encontra o mesmo número de alertas

## U07-M12

No uso do DBSCAN para detecção, o rótulo `-1` significa:

- [ ] **A.** erro confirmado no registro
- [ ] **B.** maior distância possível ao centroide
- [ ] **C.** classe negativa conhecida
- [ ] **D.** ponto fora das regiões densas sob os parâmetros usados

## U07-M13

Qual risco existe ao marcar todo grupo pequeno como anômalo?

- [ ] **A.** Uma subpopulação rara e legítima pode ser tratada como erro
- [ ] **B.** O método deixa de usar qualquer atributo
- [ ] **C.** A escala passa a ser irrelevante
- [ ] **D.** Todo grupo grande recebe LOF infinito

## U07-M14

Precisão@10 mede:

- [ ] **A.** a proporção de toda a base investigada
- [ ] **B.** a proporção de casos confirmados entre os dez primeiros alertas
- [ ] **C.** a quantidade total de anomalias existentes
- [ ] **D.** a estabilidade do detector ao longo do tempo

## U07-M15

Se apenas casos alertados recebem rótulo, a avaliação sofre principalmente de:

- [ ] **A.** normalização excessiva
- [ ] **B.** permutação de grupos
- [ ] **C.** viés de verificação ou seleção
- [ ] **D.** ausência de um escore contínuo

## U07-M16

Qual prática é mais responsável após gerar um alerta sobre uma pessoa?

- [ ] **A.** Aplicar sanção automática para reduzir custo
- [ ] **B.** Apagar o dado original depois da correção
- [ ] **C.** Divulgar publicamente o escore individual
- [ ] **D.** Registrar a razão, revisar o contexto e permitir contestação
