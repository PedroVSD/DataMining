# Unidade VI — Análise de Grupos — Múltipla escolha

**Instruções:** assinale uma única alternativa por questão. O gabarito comentado é distribuído separadamente.

## U06-M01

Qual afirmação distingue corretamente agrupamento de classificação?

- [ ] **A.** Agrupamento sempre encontra classes naturais existentes
- [ ] **B.** Agrupamento forma grupos sem usar rótulos-alvo no ajuste
- [ ] **C.** Classificação não utiliza exemplos rotulados
- [ ] **D.** Os dois métodos possuem necessariamente a mesma avaliação

## U06-M02

No k-means, a etapa de atualização:

- [ ] **A.** aumenta deliberadamente a SSE
- [ ] **B.** remove todos os pontos distantes
- [ ] **C.** escolhe o valor de $k$
- [ ] **D.** substitui cada centroide pela média dos pontos atribuídos

## U06-M03

Por que padronizar atributos pode alterar um agrupamento baseado em distância Euclidiana?

- [ ] **A.** Porque muda a contribuição relativa das dimensões para a distância
- [ ] **B.** Porque cria os rótulos corretos dos grupos
- [ ] **C.** Porque elimina qualquer correlação
- [ ] **D.** Porque torna todos os objetos igualmente distantes

## U06-M04

Sobre a SSE do k-means quando $k$ aumenta, é correto afirmar que ela:

- [ ] **A.** sempre aumenta
- [ ] **B.** permanece necessariamente constante
- [ ] **C.** tende a diminuir, o que impede escolher $k$ apenas pelo menor valor
- [ ] **D.** torna-se uma medida externa

## U06-M05

Na ligação simples, a distância entre dois grupos é:

- [ ] **A.** a distância entre seus centroides
- [ ] **B.** a menor distância entre um ponto de cada grupo
- [ ] **C.** a maior distância entre um ponto de cada grupo
- [ ] **D.** o aumento da SSE

## U06-M06

Em um dendrograma, um corte horizontal serve para:

- [ ] **A.** padronizar os atributos
- [ ] **B.** remover pontos de borda
- [ ] **C.** inverter a ordem temporal dos dados
- [ ] **D.** obter uma partição em certo nível da hierarquia

## U06-M07

No DBSCAN, um ponto de borda:

- [ ] **A.** não é central, mas está na vizinhança de um ponto central
- [ ] **B.** sempre recebe o rótulo de ruído
- [ ] **C.** expande obrigatoriamente a região densa
- [ ] **D.** possui mais vizinhos que qualquer ponto central

## U06-M08

Qual efeito é esperado ao usar um `eps` excessivamente grande?

- [ ] **A.** Todo ponto torna-se necessariamente ruído
- [ ] **B.** O número de dimensões cai
- [ ] **C.** Regiões distintas podem ser unidas em um mesmo grupo
- [ ] **D.** O método passa a exigir o número de grupos

## U06-M09

Para o silhouette de um objeto, um valor negativo indica que ele:

- [ ] **A.** possui distância zero a todos os objetos
- [ ] **B.** está, em média, mais próximo de outro grupo que do seu próprio
- [ ] **C.** deve ser apagado da base
- [ ] **D.** pertence ao maior grupo

## U06-M10

Qual direção indica melhora no índice Davies–Bouldin?

- [ ] **A.** valores acima de 1 em qualquer situação
- [ ] **B.** valores mais próximos do número de grupos
- [ ] **C.** valores negativos
- [ ] **D.** valores menores, aproximando-se de zero

## U06-M11

Duas partições diferem apenas pela troca dos números usados como rótulos. O Rand ajustado deve ser:

- [ ] **A.** 1
- [ ] **B.** 0
- [ ] **C.** negativo
- [ ] **D.** igual ao número de grupos

## U06-M12

Uma medida externa de agrupamento exige principalmente:

- [ ] **A.** apenas a SSE do algoritmo
- [ ] **B.** um centroide para cada grupo
- [ ] **C.** uma partição ou rótulo de referência relevante
- [ ] **D.** que todos os grupos sejam esféricos

## U06-M13

Qual procedimento investiga diretamente estabilidade?

- [ ] **A.** Renomear o grupo 0 como grupo 1
- [ ] **B.** Repetir a análise sob sementes ou amostras próximas e comparar partições
- [ ] **C.** Escolher a solução com mais grupos
- [ ] **D.** Usar somente uma projeção em duas dimensões

## U06-M14

Um DBSCAN apresenta silhouette alto após excluir 45% dos objetos como ruído. A comunicação mais adequada é:

- [ ] **A.** declarar superioridade sem ressalvas
- [ ] **B.** converter os ruídos em um único grupo e ocultar a mudança
- [ ] **C.** ignorar o silhouette
- [ ] **D.** relatar o escore, o critério de cálculo, a cobertura e a quantidade de ruído

## U06-M15

Qual nome de perfil é mais responsável?

- [ ] **A.** “maior frequência de compras no trimestre analisado”
- [ ] **B.** “clientes ruins”
- [ ] **C.** “pessoas sem valor”
- [ ] **D.** “grupo naturalmente inferior”

## U06-M16

Uma solução apresenta ótimas métricas internas, mas é instável e não apoia a decisão pretendida. A conclusão correta é:

- [ ] **A.** deve ser adotada porque uma métrica basta
- [ ] **B.** a instabilidade é irrelevante em agrupamento
- [ ] **C.** não há evidência suficiente para recomendá-la como solução útil
- [ ] **D.** os grupos representam necessariamente categorias naturais

## U06-M17

Um medoide é:

- [ ] **A.** sempre a média numérica do grupo
- [ ] **B.** um objeto observado que minimiza a soma de dissimilaridades no grupo
- [ ] **C.** qualquer ponto marcado como ruído
- [ ] **D.** o número de células densas

## U06-M18

A principal ideia de escalabilidade dos métodos baseados em grade é:

- [ ] **A.** comparar novamente todos os pares em cada consulta
- [ ] **B.** exigir que todos os atributos sejam categóricos
- [ ] **C.** eliminar parâmetros de resolução
- [ ] **D.** realizar operações sobre células resumidas em vez de somente sobre objetos individuais

## U06-M19

O CLIQUE diferencia-se por procurar:

- [ ] **A.** células densas também em subespaços de atributos
- [ ] **B.** apenas centroides Euclidianos
- [ ] **C.** uma árvore supervisionada
- [ ] **D.** exclusivamente grupos esféricos

## U06-M20

Uma grade excessivamente grossa tende a:

- [ ] **A.** preservar todos os detalhes locais
- [ ] **B.** criar necessariamente mais células vazias
- [ ] **C.** fundir regiões distintas e produzir fronteiras grosseiras
- [ ] **D.** tornar a escolha do limiar irrelevante

## U06-M21

Em um GMM, a responsabilidade $r_{ij}$ representa:

- [ ] **A.** a distância Euclidiana sem normalização
- [ ] **B.** a probabilidade posterior de o componente $j$ explicar o objeto $i$
- [ ] **C.** o número de componentes escolhido pelo BIC
- [ ] **D.** uma classe observada usada no treinamento

## U06-M22

Na etapa M do algoritmo EM para GMM:

- [ ] **A.** todos os objetos recebem probabilidade exatamente 0 ou 1
- [ ] **B.** o número de atributos é reduzido
- [ ] **C.** as responsabilidades são descartadas
- [ ] **D.** pesos, médias e covariâncias são atualizados usando as responsabilidades

## U06-M23

Qual tipo de covariância permite que cada componente tenha uma elipse com orientação própria?

- [ ] **A.** `full`
- [ ] **B.** `spherical`
- [ ] **C.** `tied` com matriz diagonal fixa
- [ ] **D.** nenhuma, pois GMM produz apenas círculos

## U06-M24

Ao comparar GMMs pelo BIC, prefere-se inicialmente:

- [ ] **A.** o maior BIC, independentemente do ajuste
- [ ] **B.** sempre o modelo com mais componentes
- [ ] **C.** o menor BIC entre os candidatos, seguido de outras validações
- [ ] **D.** o modelo cujos rótulos têm números maiores
