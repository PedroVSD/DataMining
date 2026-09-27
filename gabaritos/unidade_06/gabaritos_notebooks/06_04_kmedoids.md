# Gabarito — 06.04 k-medoids

## U06-NB04-V01

A média é:

$$\bar x=\frac{1+2+3+20}{4}=6{,}5.$$

As somas de distâncias absolutas são:

- candidato 1: $0+1+2+19=22$;
- candidato 2: $1+0+1+18=20$;
- candidato 3: $2+1+0+17=20$;
- candidato 20: $19+18+17+0=54$.

Logo, 2 e 3 são medoides possíveis: há empate no custo mínimo. A média 6,5 não é um objeto observado e foi deslocada pelo extremo 20. Os medoides são observados e permanecem na região central dos três valores próximos.

**Critério de correção:** obter média 6,5, identificar os dois medoides e justificar pelo custo 20.

## U06-NB04-E01

Para medoides `(0,9)`, os custos individuais são $0,1,2,0,1$, totalizando 4.

Para `(1,9)`, são $1,0,1,0,1$, totalizando 3.

Para `(1,10)`, são $1,0,1,1,0$, também totalizando 3.

Assim, entre os pares examinados, `(1,9)` e `(1,10)` empatam como melhores. O empate ocorre porque 9 e 10 são igualmente adequados para representar o par final em distância absoluta. Um algoritmo pode retornar qualquer uma das soluções conforme inicialização e regra de desempate.

**Critério de correção:** calcular os três custos, identificar o empate e não atribuir significado à ordem dos representantes.

## U06-NB04-E02

K-medoids é diretamente compatível porque pode receber uma matriz de distâncias de Gower e escolhe hospitais observados como representantes. O k-means padrão depende de médias e distância Euclidiana; médias de categorias nominais não têm significado e sua função objetivo não corresponde a Gower.

Ainda é necessário decidir e documentar:

- quais atributos representam a finalidade do agrupamento;
- tipos corretos, intervalos e tratamento de valores ausentes;
- pesos dos atributos na distância de Gower;
- número $k$ e procedimento de inicialização ou troca;
- custo computacional e eventual amostragem;
- estabilidade, tamanhos, perfis e utilidade dos grupos;
- se um hospital observado é realmente um representante comunicável.

**Critério de correção:** selecionar k-medoids pela matriz de dissimilaridade e listar decisões que mostrem que a métrica não elimina o trabalho de modelagem.
