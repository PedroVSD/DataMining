# Gabarito — 06.05 Métodos baseados em grade

## U06-NB05-V01

Existem dois componentes conectados:

1. `{(0,0), (0,1), (1,1)}`: todas as células se conectam por lado ou diagonal;
2. `{(5,5), (5,6)}`: as duas são vizinhas verticalmente.

Não existe uma cadeia de células densas entre os componentes. A vizinhança de oito direções permite deslocamentos de no máximo uma unidade em cada coordenada.

**Critério de correção:** formar exatamente os dois conjuntos e explicar a conectividade.

## U06-NB05-E01

Uma grade muito fina distribui os objetos por muitas células. Com limiar fixo, menos células atingem a densidade exigida, aumentando fragmentação e objetos não atribuídos. Ela preserva mais detalhe, mas aumenta o número de células, o custo de armazenamento e a sensibilidade ao alinhamento das fronteiras.

Uma grade muito grossa agrega muitos objetos por célula, aumenta cobertura e reduz o custo sobre células, mas pode conectar estruturas distintas, apagar vazios e produzir contornos excessivamente retangulares. Pontos próximos em lados opostos de uma fronteira podem ser tratados diferentemente; deslocar a origem da grade pode alterar o resultado.

Devem ser avaliadas várias resoluções e limiares, registrando grupos, cobertura, estabilidade e utilidade.

**Critério de correção:** relacionar ambas as direções a fragmentação ou fusão, cobertura, custo e fronteiras.

## U06-NB05-E02

Uma arquitetura inicial defensável é usar uma grade multirresolução inspirada em STING. Na ingestão, cada ponto atualiza contagens e resumos das células inferiores; níveis superiores agregam esses resumos. Consultas amplas começam em células grossas e descem apenas nas regiões relevantes. Isso atende volume, atualização e diferentes escalas sem executar novamente comparações entre todos os objetos.

DBSCAN pode ser aplicado em regiões candidatas ou janelas menores quando for necessário recuperar conectividade entre objetos com resolução fina. PAM é útil apenas em amostras ou subconjuntos pequenos quando representantes reais e uma distância especializada forem importantes; sua busca de trocas é inadequada como primeira operação sobre milhões de pontos por hora.

Devem ser monitorados resolução mínima, limiar, alinhamento das células, densidades diferentes, crescimento do número de células e perda de fronteiras diagonais. Resultados aproximados podem ser comparados periodicamente com análises em amostras de objetos.

**Critério de correção:** propor grade multirresolução como camada escalável, posicionar DBSCAN e PAM em papéis coerentes e registrar ao menos uma limitação verificável.
