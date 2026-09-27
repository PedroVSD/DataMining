# Unidade V — Gabarito dos exercícios conceituais

## U05-C01

Classificação prevê categorias; regressão estima valores numéricos. No abandono, a unidade pode ser um estudante matriculado, os atributos podem incluir participação e entregas disponíveis até uma data de referência, e o alvo é `abandonou`/`permaneceu`. No tempo de conclusão, a unidade pode ser uma execução de atividade, os atributos podem incluir tipo e complexidade, e o alvo é duração em minutos. Em ambos, atributos posteriores ao desfecho causariam vazamento.

**Essencial:** natureza do alvo, unidade, atributos temporalmente disponíveis e alvo de cada exemplo.

## U05-C02

Treino ajusta os parâmetros; validação orienta escolhas como profundidade e $k$; teste estima uma única vez o desempenho final. Consultar repetidamente o teste adapta decisões às particularidades dele, transformando-o informalmente em validação e produzindo estimativa otimista. Pode-se usar divisão treino/validação/teste ou validação cruzada apenas dentro do treino, preservando o teste.

## U05-C03

Há 1.000 casos:

$$Acurácia=(810+40)/1000=0{,}85,$$
$$Precisão=40/(40+90)=0{,}3077,$$
$$Revocação=40/(40+60)=0{,}40,$$
$$F1=2(40)/(2(40)+90+60)=80/230=0{,}3478.$$

Sempre prever negativo acerta os 900 negativos: acurácia 0,90, mas revocação e F1 positivas iguais a zero. A acurácia menor do primeiro modelo não implica menor utilidade para encontrar positivos.

## U05-C04

$$Custo_A=100(10)+8(500)=R\$5.000,$$
$$Custo_B=250(10)+3(500)=R\$4.000.$$

B possui menor custo sob os pesos declarados. A resposta muda com valores das fraudes, custo de investigação, capacidade operacional, efeitos sobre clientes e distribuição futura; os pesos precisam ser estimados no domínio.

## U05-C05

Com prévias 0,5:

$$s_1=0{,}5(0{,}8)(0{,}5)=0{,}20,$$
$$s_2=0{,}5(0{,}3)(0{,}9)=0{,}135.$$

A soma é 0,335. As posteriores normalizadas são $0{,}20/0{,}335=0{,}5970$ e $0{,}135/0{,}335=0{,}4030$. A previsão é $C_1$. Isso pressupõe independência condicional de $x_1$ e $x_2$ dentro de cada classe.

## U05-C06

Independência condicional aproxima $P(\mathbf{x}\mid C)$ pelo produto das probabilidades de cada atributo dado $C$. Se um fator for zero, todo o produto se torna zero e ignora as demais evidências. Laplace soma uma pequena contagem a cada categoria e ajusta o denominador, evitando zero. Ela suaviza estimativas, mas não corrige dependência entre atributos nem garante calibração.

## U05-C07

Uma diferença de milhares de reais domina numericamente uma diferença de poucos atrasos na distância. O escalonador deve ser ajustado somente no treino; suas médias e desvios ou mínimos e máximos são então aplicados sem novo ajuste à validação, ao teste e a novos casos. Ajustar a transformação antes da divisão vazaria informações das partições externas.

## U05-C08

$k=1$ segue o exemplo mais próximo, cria fronteira detalhada e é sensível a ruído. Um $k$ muito grande suaviza a fronteira e pode reduzir ruído, mas tende à classe majoritária e pode apagar nichos. A busca k-NN permanece custosa porque compara novos casos aos exemplos armazenados. Escolhe-se $k$ por validação ou validação cruzada dentro do treino, junto à escala e distância; o teste fica reservado à estimativa final.

## U05-C09

Raiz é a primeira pergunta; nó interno é uma pergunta intermediária; ramo é um resultado da pergunta; folha contém a previsão. Regra: **SE** renda ≤ R$ 3.000 **E** atrasos > 1, **ENTÃO** prever a classe registrada na folha, por exemplo risco alto. Uma regra completa contém todas as condições do caminho.

## U05-C10

Na raiz:

$$Gini=1-(8/10)^2-(2/10)^2=0{,}32.$$

O grupo $(7,0)$ é puro: $Gini_1=0$. No grupo $(1,2)$:

$$Gini_2=1-(1/3)^2-(2/3)^2=4/9=0{,}4444.$$

Ponderando:

$$Gini_{div}=7/10(0)+3/10(4/9)=0{,}1333.$$

A redução é $0{,}32-0{,}1333=0{,}1867$.

## U05-C11

Há forte sobreajuste: desempenho perfeito no treino, queda no teste e árvore muito complexa. Pré-poda pode limitar `max_depth` e aumentar `min_samples_leaf` ou `min_samples_split`. Pós-poda pode usar poda por custo-complexidade para substituir subárvores por folhas. As escolhas devem ocorrer por validação dentro do treino.

## U05-C12

Importância soma reduções de impureza usadas pela árvore; não representa intervenção. Atributos correlacionados podem compartilhar importância ou fazer um deles absorvê-la. Alta cardinalidade oferece mais divisões candidatas e pode ser favorecida. Um identificador pode memorizar registros e criar folhas puras sem generalizar. Causalidade exigiria desenho próprio e controle de explicações alternativas.

## U05-C13

$$\hat y=20+3(10)=50,$$
$$e=y-\hat y=44-50=-6.$$

O intercepto 20 é a previsão em $x=0$; o coeficiente 3 é a variação prevista em $y$ por unidade de $x$; o resíduo negativo indica observação seis unidades abaixo da previsão. A utilidade prática do intercepto depende de $x=0$ estar no domínio observado.

## U05-C14

Resíduos: $[-2,2,-3,3]$. Logo:

$$MAE=(2+2+3+3)/4=2{,}5,$$
$$RMSE=\sqrt{(4+4+9+9)/4}=\sqrt{6{,}5}=2{,}550.$$

O RMSE é pelo menos o MAE porque a média quadrática dá peso maior aos erros de maior magnitude; são iguais quando os erros absolutos possuem a mesma magnitude.

## U05-C15

Mantendo os demais atributos do modelo constantes, 1 m² adicional está associado a aumento previsto de quatro unidades monetárias; um ano adicional está associado a redução prevista de duas unidades monetárias. As unidades precisam acompanhar o alvo, por exemplo mil reais por m² e mil reais por ano. Área e quartos correlacionados carregam informação semelhante, podendo tornar coeficientes instáveis e dependentes de quais variáveis foram incluídas. Nenhum coeficiente prova causalidade.

## U05-C16

Interpolação ocorre dentro da região observada; 400 m² é extrapolação porque excede 180 m². Deve-se verificar faixa conjunta dos atributos, existência de imóveis comparáveis, resíduos por faixa, estabilidade temporal, conhecimento do mercado e modelos alternativos; pode-se recusar ou sinalizar a previsão. $R^2$ resume desempenho médio na distribuição avaliada e não valida prolongamento linear fora dela.
