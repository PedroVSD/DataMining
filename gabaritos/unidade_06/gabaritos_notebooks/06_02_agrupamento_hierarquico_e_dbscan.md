# Gabarito — 06.02 Agrupamento hierárquico e DBSCAN

Este arquivo contém respostas-modelo completas para as atividades do notebook. Numerações de grupos produzidas por algoritmos são arbitrárias: o que importa é a composição dos grupos.

## U06-NB02-V01

Na ligação completa, a distância entre dois grupos é a maior distância entre um ponto do primeiro grupo e um ponto do segundo. Portanto, a fusão na altura 4,2 informa que, naquele estágio, os dois grupos unidos tinham distância de ligação completa igual a 4,2, na unidade dos atributos ou da métrica utilizada.

A altura não conta objetos. O tamanho do novo grupo é a soma das quantidades de objetos dos dois ramos fundidos e deve ser obtido acompanhando suas folhas. Além disso, em outras ligações a altura tem outra interpretação: na ligação simples é a menor distância entre os grupos; em Ward, relaciona-se ao aumento da variabilidade interna.

**Critério de correção:** distinguir explicitamente altura de fusão e cardinalidade, relacionando 4,2 ao critério de ligação completa.

## U06-NB02-E01

As quatro distâncias entre pontos de grupos diferentes são:

$$
d(A,C)=4,\qquad d(A,D)=\sqrt{20},\qquad
d(B,C)=\sqrt{17},\qquad d(B,D)=\sqrt{17}.
$$

Logo:

- ligação simples: $\min\{4,\sqrt{20},\sqrt{17},\sqrt{17}\}=4$;
- ligação completa: $\max\{4,\sqrt{20},\sqrt{17},\sqrt{17}\}=\sqrt{20}\approx4{,}472$;
- ligação média:

$$
\frac{4+\sqrt{20}+2\sqrt{17}}{4}\approx4{,}180.
$$

Para Ward, $n_1=n_2=2$, $\boldsymbol m_1=(0;0{,}5)$ e $\boldsymbol m_2=(4;1)$. Assim:

$$
\Delta SSE
=\frac{n_1n_2}{n_1+n_2}\lVert\boldsymbol m_1-\boldsymbol m_2\rVert^2
=\frac{2\cdot2}{4}\left[(0-4)^2+(0{,}5-1)^2\right]
=16{,}25.
$$

Os valores não precisam coincidir porque simples, completa e média resumem distâncias entre pares, enquanto Ward mede o aumento da soma dos quadrados dentro dos grupos. Também possuem interpretações e, no caso de Ward, escala numérica distintas.

**Critério de correção:** apresentar os quatro cálculos de distância entre pares, aplicar corretamente cada ligação, obter $\Delta SSE=16{,}25$ e explicar a diferença entre os critérios.

## U06-NB02-E02

O corte em 2,0 produz três grupos:

1. $\{A,B,C\}$;
2. $\{D,E\}$;
3. $\{F,G,H\}$.

Visualmente, traça-se uma linha horizontal na altura 2,0 e contam-se os três ramos verticais interceptados. As folhas abaixo de cada ramo fornecem seus membros. A tabela confirma que A, B e C receberam um rótulo comum; D e E, outro; F, G e H, um terceiro. Os números `1`, `2` e `3` poderiam ser permutados sem alterar a partição.

**Critério de correção:** indicar os três conjuntos, explicar o corte horizontal e não atribuir significado ordinal aos números dos grupos.

## U06-NB02-E03

Com `eps=0.55` e `min_samples=5`, o resultado executado é:

| Objeto | Tipo | Grupo |
|---|---|---:|
| P | central | 0 |
| Q | central | 0 |
| R | central | 0 |
| S | borda | 0 |
| T | central | 0 |
| U | central | 0 |
| V | borda | 0 |
| W | ruído | -1 |

Ao aumentar apenas `min_samples`, um ponto precisa reunir mais objetos dentro do mesmo raio para continuar central. Se deixar de atingir o limiar, mas permanecer na vizinhança de algum outro ponto ainda central, passa a ser borda. Se ele não for central nem estiver ao alcance de um central, passa a ser ruído. Como a perda de pontos centrais também pode interromper cadeias de conectividade, a mudança pode fragmentar ou eliminar um grupo.

**Critério de correção:** classificar todos os objetos e explicar as duas possíveis transições usando vizinhança e conectividade.

## U06-NB02-E04

Uma resposta possível é iniciar pelo **DBSCAN**. Rotas curvas são grupos não convexos, registros isolados podem ser tratados explicitamente como ruído e o método não exige informar previamente o número de grupos. O k-means tende a dividir o espaço em regiões associadas a centroides e pode cortar as rotas transversalmente. Ward também favorece grupos compactos porque minimiza o aumento da SSE, embora seu dendrograma seja útil para explorar níveis de granularidade.

Devem ser documentados:

- a unidade representada por cada ponto ou trajetória;
- os atributos e a representação das trajetórias;
- a métrica de distância — Euclidiana entre coordenadas pode ser inadequada para trajetórias completas;
- a projeção cartográfica e as unidades espaciais;
- a padronização, se houver atributos de naturezas diferentes;
- os valores de `eps` e `min_samples`, como foram investigados e a proporção de ruído resultante;
- a estabilidade diante de pequenas alterações dos parâmetros;
- a interpretação e o uso pretendido dos grupos.

Uma limitação importante é a possibilidade de rotas possuírem densidades muito diferentes: um único par `eps`/`min_samples` pode unir rotas densas ou eliminar rotas esparsas. Também é necessário verificar se a distância escolhida respeita sequência, direção e geometria das trajetórias. Nesse caso, representações próprias para trajetórias ou métodos de densidade hierárquicos podem ser investigados.

**Critério de correção:** justificar a escolha pela geometria e pelo ruído, comparar os três métodos, documentar decisões concretas e apontar pelo menos uma limitação relevante.

