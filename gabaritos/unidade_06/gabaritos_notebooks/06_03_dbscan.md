# Gabarito — 06.03 DBSCAN

## U06-NB03-V01

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

## U06-NB03-E01

O aumento de eps amplia cada vizinhança. Com 0,12, muitas cadeias densas não se conectam: surgem 21 fragmentos e 100 objetos não atingem o critério. Com 0,22, regiões começam a se unir e quase todos os objetos são cobertos, mas seis fragmentos ainda permanecem. Com 0,38, as duas luas tornam-se dois componentes e nenhum objeto fica como ruído.

A terceira solução não deve ser aceita apenas por reduzir ruído. Um raio grande também pode unir regiões que deveriam permanecer separadas. É preciso examinar geometria, estabilidade para valores próximos, escala, métrica, conhecimento do domínio e finalidade.

**Critério de correção:** relacionar eps a conectividade, fragmentação e ruído, e rejeitar a minimização automática do ruído.

## U06-NB03-E02

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
