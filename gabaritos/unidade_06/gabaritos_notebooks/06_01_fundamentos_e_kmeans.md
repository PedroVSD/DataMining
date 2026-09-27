# Gabarito — 06.01 Fundamentos e k-means

## U06-NB01-V01

Os números 0 e 1 são apenas identificadores internos dos grupos. Eles não indicam que o grupo 1 seja maior, melhor ou posterior ao grupo 0. Se os centroides forem inicializados em outra ordem, uma solução geometricamente igual pode receber rótulos trocados. Comparações entre execuções devem alinhar grupos por membros, centroides ou um procedimento de correspondência, não pelo número bruto do rótulo.

**Rubrica (3 pontos):** ausência de ordem ou qualidade (1), possibilidade de permutação (1), forma adequada de comparar (1).

## U06-NB01-E01

Com centroides iniciais $\boldsymbol{\mu}_0=(1,1)$ e $\boldsymbol{\mu}_1=(6,5)$, por exemplo, a distância de B a $\boldsymbol{\mu}_0$ é

$$
d(B,\boldsymbol{\mu}_0)
=\sqrt{(1{,}5-1)^2+(2-1)^2}
=\sqrt{1{,}25}=1{,}118.
$$

Sua distância a $\boldsymbol{\mu}_1$ é

$$
\sqrt{(1{,}5-6)^2+(2-5)^2}=5{,}408,
$$

logo B vai ao grupo 0. As atribuições completas são A, B e C no grupo 0; D, E e F no grupo 1.

Os centroides atualizados são

$$
\boldsymbol{\mu}_0
=\left(\frac{1+1{,}5+2}{3},\frac{1+2+1{,}2}{3}\right)
=(1{,}5,1{,}4),
$$

$$
\boldsymbol{\mu}_1
=\left(\frac{6+6{,}5+7}{3},\frac{5+5{,}8+5{,}2}{3}\right)
=(6{,}5,5{,}333).
$$

Antes da atualização, a SSE é

$$
(0+1{,}25+1{,}04)+(0+0{,}89+1{,}04)=4{,}220.
$$

Depois da atualização, as parcelas somam aproximadamente

$$
(0{,}41+0{,}36+0{,}29)
+(0{,}361+0{,}218+0{,}268)
=1{,}907.
$$

A queda ocorre porque a média minimiza a soma das distâncias quadráticas dos pontos atribuídos.

**Rubrica (10 pontos):** distâncias e atribuições (3), dois centroides (3), duas SSE (3), interpretação (1).

## U06-NB01-E02

Na escala bruta:

- os 60 clientes econômicos frequentes formam o grupo 1;
- os 60 premium frequentes e os 60 premium ocasionais formam o grupo 0.

O gasto, cuja amplitude numérica é maior, orienta a divisão entre econômico e premium. Um uso possível seria diferenciar estratégias por valor médio de compra.

Após padronização:

- os econômicos frequentes e premium frequentes formam o grupo 0;
- os premium ocasionais formam o grupo 1.

A frequência passa a ter peso comparável e separa clientes ocasionais dos frequentes. Um uso possível seria investigar ações diferentes de recorrência. Nenhuma solução é a verdade dos clientes; cada uma operacionaliza uma pergunta.

**Rubrica (8 pontos):** partição bruta (2), partição padronizada (2), atributo dominante (2), usos e ressalva interpretativa (2).

## U06-NB01-E03

$k=3$ é uma proposta defensável. A SSE cai de 360,00 em $k=1$ para 139,34 em $k=2$ e para 21,90 em $k=3$. Depois, as reduções são menores: 15,14, 11,13 e 9,03 para $k=4,5,6$.

Isso sugere um cotovelo em 3, mas não prova que existam exatamente três tipos naturais. A decisão deve incluir, por exemplo:

- estabilidade das atribuições em reamostragens ou períodos;
- silhouette ou outra medida de coesão e separação;
- interpretação dos perfis e tamanhos;
- utilidade para uma decisão real;
- sensibilidade a escala, atributos, inicialização e valores atípicos.

Qualquer proposta alternativa precisa comparar as reduções de SSE e justificar as verificações adicionais.

**Rubrica (6 pontos):** leitura da tabela (2), proposta justificável (1), rejeição da prova automática (1), duas verificações adicionais (2).

## U06-NB01-E04

As duas luas são curvas e não convexas. O k-means representa cada grupo por uma média e atribui cada ponto ao centroide Euclidiano mais próximo. As regiões de proximidade entre centroides possuem fronteiras lineares, que cortam os arcos em vez de acompanhá-los.

Métodos baseados em densidade, como DBSCAN, são mais adequados porque podem conectar pontos por vizinhanças densas e recuperar formas arbitrárias, além de admitir ruído. A escolha ainda depende de escala, densidade e parâmetros.

**Rubrica (5 pontos):** geometria das luas (1), centroides e distância (2), família baseada em densidade (1), ressalva (1).
