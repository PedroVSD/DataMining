# Gabarito — 06.03 Avaliação de agrupamentos

## U06-NB03-V01

Silhouette 0,71 indica boa coesão e separação médias segundo a distância utilizada, mas pode ser elevado porque dois objetos extremos formaram um pequeno grupo artificialmente isolado. O escore não informa, sozinho, se o grupo é estável, útil ou substantivamente defensável.

Verificações adicionais incluem:

1. examinar tamanhos, distribuições e os dois objetos para verificar erros, duplicações ou casos genuinamente distintos;
2. repetir a análise com amostras, sementes e parâmetros próximos para avaliar se o pequeno grupo reaparece;
3. comparar Davies–Bouldin, cobertura, soluções com outro número de grupos e métodos coerentes com a geometria;
4. validar com conhecimento do domínio se separar os objetos responde ao objetivo;
5. avaliar consequências de decisões tomadas a partir de um grupo tão pequeno.

**Critério de correção:** explicar a limitação do valor médio e apresentar três verificações pertencentes a dimensões diferentes da avaliação.

## U06-NB03-E01

Para A:

$$
s(A)=\frac{5-2}{\max(2,5)}=\frac35=0{,}60.
$$

A está, em média, mais próximo do próprio grupo que do grupo alternativo mais próximo.

Para B:

$$
s(B)=\frac{3-4}{\max(4,3)}=-\frac14=-0{,}25.
$$

B está, em média, mais próximo de outro grupo que do grupo ao qual foi atribuído; convém investigar sua atribuição.

A média dos dois é:

$$
\bar s=\frac{0{,}60-0{,}25}{2}=0{,}175.
$$

Esse valor médio modesto oculta comportamentos diferentes, reforçando a necessidade de examinar silhouettes individuais.

**Critério de correção:** obter 0,60, −0,25 e 0,175 e interpretar o sinal de cada objeto.

## U06-NB03-E02

Se os rótulos externos representam de fato a finalidade, a solução **B** é a recomendação inicial:

- possui o maior ARI externo, 0,78;
- cobre 100% dos objetos;
- tem estabilidade alta, 0,88;
- embora silhouette 0,35 e Davies–Bouldin 0,98 sejam piores que nas outras soluções, não são evidências de colapso e avaliam uma pergunta diferente.

A é mais favorável internamente e um pouco mais estável, mas seu ARI 0,31 indica baixa concordância com a finalidade externa. C lidera as duas métricas internas, porém cobre apenas 68%, possui estabilidade 0,40 e ARI 0,25; seu aparente desempenho pode decorrer da exclusão de objetos difíceis.

A recomendação ainda é provisória. Deve-se verificar a qualidade dos rótulos externos, tamanhos e perfis dos grupos, custos dos erros e estabilidade sob reamostragem. Se a referência não representar o objetivo real, o peso atribuído ao ARI precisa ser revisto.

**Critério de correção:** recomendar B pelo objetivo declarado, comparar as cinco dimensões e registrar que a validade da referência deve ser examinada.

## U06-NB03-E03

As duas partições colocam exatamente os mesmos pares juntos e separados. Apenas os nomes foram permutados: o grupo 0 da primeira corresponde ao grupo 2 da segunda; o 1 corresponde ao 0; o 2 corresponde ao 1. Por isso, o ARI é 1.

Os números dos grupos são identificadores arbitrários, não valores ordinais. Não se pode concluir que o grupo 2 seja maior, melhor ou posterior ao grupo 1. Ao comparar execuções, deve-se comparar composição ou usar uma medida invariante à permutação, como o ARI.

**Critério de correção:** identificar a igualdade das partições e rejeitar interpretação ordinal dos rótulos.

## U06-NB03-E04

Resultados executados no estudo Wine:

| Método | Grupos | Ruídos | Cobertura | Silhouette sem ruído | Davies–Bouldin sem ruído | ARI externo |
|---|---:|---:|---:|---:|---:|---:|
| k-means | 3 | 0 | 1,000 | 0,285 | 1,389 | 0,897 |
| Ward | 3 | 0 | 1,000 | 0,277 | 1,419 | 0,790 |
| DBSCAN | 2 | 55 | 0,691 | 0,348 | 1,124 | 0,329 |

Para aproximar os três cultivares, recomenda-se inicialmente o **k-means**: ele cobre todos os vinhos e possui o maior ARI, 0,897. Ward é uma alternativa plausível, mas sua concordância externa e suas métricas internas foram um pouco inferiores neste experimento. A recomendação não prova que os cultivares sejam esféricos nem garante generalização; deve ser testada em outras amostras.

Para investigar apenas regiões químicas densas, o **DBSCAN** pode ser útil: entre os objetos atribuídos, possui silhouette maior e Davies–Bouldin menor. Contudo, forma apenas dois grupos, marca 55 dos 178 vinhos como ruído e tem cobertura de 69,1%. Suas métricas internas foram calculadas depois de retirar esses objetos e não são diretamente equivalentes às soluções com cobertura total.

As métricas foram calculadas nas 13 dimensões padronizadas; a projeção PCA serve somente para visualização. Os rótulos de cultivar também não participaram do ajuste.

**Critério de correção:** apresentar recomendações distintas para as duas finalidades, usar cobertura ao interpretar o DBSCAN e não tratar a projeção bidimensional como base das métricas.

## U06-NB03-E05

Exemplo de protocolo:

1. **Definir finalidade e população:** registrar qual decisão a segmentação apoiará, período dos dados e unidade de análise.
2. **Construir:** justificar atributos, transformações, escala, distância, algoritmo e parâmetros; excluir identificadores e variáveis sem relação com o objetivo.
3. **Avaliar:** relatar tendência, métricas internas, eventual referência externa, estabilidade, tamanhos, cobertura e ruído.
4. **Perfilar:** examinar médias, medianas, dispersões e distribuições nos atributos originais; procurar heterogeneidade dentro de cada grupo.
5. **Nomear:** usar descrições observáveis e temporais, como “maior frequência de compras no período”, evitando rótulos morais ou essencialistas.
6. **Validar:** discutir perfis com especialistas e pessoas afetadas quando cabível; testar se sustentam a finalidade e se não são apenas efeito de escala ou amostragem.
7. **Avaliar consequências:** investigar impactos desiguais, possibilidade de contestação e riscos do uso dos grupos para decisões individuais.
8. **Monitorar:** acompanhar mudança de distribuição, tamanhos, perfis, estabilidade e resultados; definir prazo de revisão e condições para abandonar a solução.

Os rótulos numéricos devem permanecer descritos como arbitrários, e a comunicação deve afirmar que os perfis resumem os dados observados, sem estabelecer causalidade ou identidade fixa.

**Critério de correção:** cobrir construção, descrição, validação, linguagem, consequências e monitoramento com ações verificáveis.

