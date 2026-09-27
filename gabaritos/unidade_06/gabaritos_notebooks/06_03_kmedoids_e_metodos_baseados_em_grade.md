# Gabarito — 06.03 k-medoids e métodos baseados em grade

## U06-NB03-V01

A média é:

$$\bar x=\frac{1+2+3+20}{4}=6{,}5.$$

As somas de distâncias absolutas são:

- candidato 1: $0+1+2+19=22$;
- candidato 2: $1+0+1+18=20$;
- candidato 3: $2+1+0+17=20$;
- candidato 20: $19+18+17+0=54$.

Logo, 2 e 3 são medoides possíveis: há empate no custo mínimo. A média 6,5 não é um objeto observado e foi deslocada pelo extremo 20. Os medoides são observados e permanecem na região central dos três valores próximos.

**Critério de correção:** obter média 6,5, identificar os dois medoides e justificar pelo custo 20.

## U06-NB03-E01

Para medoides `(0,9)`, os custos individuais são $0,1,2,0,1$, totalizando 4.

Para `(1,9)`, são $1,0,1,0,1$, totalizando 3.

Para `(1,10)`, são $1,0,1,1,0$, também totalizando 3.

Assim, entre os pares examinados, `(1,9)` e `(1,10)` empatam como melhores. O empate ocorre porque 9 e 10 são igualmente adequados para representar o par final em distância absoluta. Um algoritmo pode retornar qualquer uma das soluções conforme inicialização e regra de desempate.

**Critério de correção:** calcular os três custos, identificar o empate e não atribuir significado à ordem dos representantes.

## U06-NB03-E02

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

## U06-NB03-E03

Existem dois componentes conectados:

1. `{(0,0), (0,1), (1,1)}`: todas as células se conectam por lado ou diagonal;
2. `{(5,5), (5,6)}`: as duas são vizinhas verticalmente.

Não existe uma cadeia de células densas entre os componentes. A vizinhança de oito direções permite deslocamentos de no máximo uma unidade em cada coordenada.

**Critério de correção:** formar exatamente os dois conjuntos e explicar a conectividade.

## U06-NB03-E04

Uma grade muito fina distribui os objetos por muitas células. Com limiar fixo, menos células atingem a densidade exigida, aumentando fragmentação e objetos não atribuídos. Ela preserva mais detalhe, mas aumenta o número de células, o custo de armazenamento e a sensibilidade ao alinhamento das fronteiras.

Uma grade muito grossa agrega muitos objetos por célula, aumenta cobertura e reduz o custo sobre células, mas pode conectar estruturas distintas, apagar vazios e produzir contornos excessivamente retangulares. Pontos próximos em lados opostos de uma fronteira podem ser tratados diferentemente; deslocar a origem da grade pode alterar o resultado.

Devem ser avaliadas várias resoluções e limiares, registrando grupos, cobertura, estabilidade e utilidade.

**Critério de correção:** relacionar ambas as direções a fragmentação ou fusão, cobertura, custo e fronteiras.

## U06-NB03-E05

Uma arquitetura inicial defensável é usar uma grade multirresolução inspirada em STING. Na ingestão, cada ponto atualiza contagens e resumos das células inferiores; níveis superiores agregam esses resumos. Consultas amplas começam em células grossas e descem apenas nas regiões relevantes. Isso atende volume, atualização e diferentes escalas sem executar novamente comparações entre todos os objetos.

DBSCAN pode ser aplicado em regiões candidatas ou janelas menores quando for necessário recuperar conectividade entre objetos com resolução fina. PAM é útil apenas em amostras ou subconjuntos pequenos quando representantes reais e uma distância especializada forem importantes; sua busca de trocas é inadequada como primeira operação sobre milhões de pontos por hora.

Devem ser monitorados resolução mínima, limiar, alinhamento das células, densidades diferentes, crescimento do número de células e perda de fronteiras diagonais. Resultados aproximados podem ser comparados periodicamente com análises em amostras de objetos.

**Critério de correção:** propor grade multirresolução como camada escalável, posicionar DBSCAN e PAM em papéis coerentes e registrar ao menos uma limitação verificável.

