# Gabarito — 06.02 Agrupamento hierárquico

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
