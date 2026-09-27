# Unidade VI — Gabarito comentado da múltipla escolha

| Questão | Resposta | Questão | Resposta | Questão | Resposta | Questão | Resposta |
|---:|:---:|---:|:---:|---:|:---:|---:|:---:|
| 1 | B | 5 | B | 9 | B | 13 | B |
| 2 | D | 6 | D | 10 | D | 14 | D |
| 3 | A | 7 | A | 11 | A | 15 | A |
| 4 | C | 8 | C | 12 | C | 16 | C |
| 17 | B | 18 | D | 19 | A | 20 | C |
| 21 | B | 22 | D | 23 | A | 24 | C |

## Justificativas

### U06-M01 — B

Agrupamento constrói grupos sem um alvo usado para ensinar a partição. Isso não garante categorias naturais nem torna sua avaliação igual à classificação.

### U06-M02 — D

A atualização calcula a média dos pontos atualmente atribuídos a cada grupo. A atribuição, e não a atualização, escolhe o centroide mais próximo.

### U06-M03 — A

Distância Euclidiana soma contribuições das dimensões; mudar escalas altera seus pesos numéricos. Padronizar não cria verdade, igualdade de distâncias nem independência.

### U06-M04 — C

Permitir mais grupos não aumenta a SSE ótima e normalmente a reduz. Por isso, escolher apenas o mínimo favoreceria o maior $k$ considerado.

### U06-M05 — B

Ligação simples usa o par mais próximo entre grupos. O par mais distante define a ligação completa; aumento da SSE caracteriza Ward.

### U06-M06 — D

Cada ramo interceptado por um corte horizontal corresponde a um grupo naquele nível. O corte não transforma atributos nem altera a ordem dos dados.

### U06-M07 — A

O ponto de borda não alcança `min_samples`, mas pertence à vizinhança de um central. Ele entra no grupo sem expandir a cadeia por conta própria.

### U06-M08 — C

Raio grande aumenta conexões e pode fundir regiões distintas. O DBSCAN continua sem exigir número de grupos e não reduz dimensões.

### U06-M09 — B

Silhouette negativo ocorre quando $a(i)>b(i)$: a distância média ao próprio grupo supera a do grupo alternativo mais próximo. Isso pede investigação, não exclusão automática.

### U06-M10 — D

Davies–Bouldin é uma razão de dispersão e separação cuja direção desejável é para baixo, com limite inferior zero. Não é necessário que seja negativo ou acima de 1.

### U06-M11 — A

O ARI compara pares e é invariante à permutação dos nomes dos grupos. Partições equivalentes recebem valor 1.

### U06-M12 — C

Uma medida externa compara a solução com rótulos ou partição de referência. SSE e centroides são informações internas e não constituem referência externa.

### U06-M13 — B

Repetições permitem medir se pequenas mudanças produzem composições semelhantes. Renomear rótulos não altera a partição; uma única projeção não testa estabilidade.

### U06-M14 — D

Excluir quase metade dos objetos muda a população avaliada. O escore só é interpretável junto à regra de cálculo, cobertura, ruído e sensibilidade aos parâmetros.

### U06-M15 — A

A alternativa A descreve comportamento observável, período e comparação, sem atribuir valor moral ou identidade fixa às pessoas.

### U06-M16 — C

Qualidade interna é apenas uma dimensão. Instabilidade e falta de utilidade impedem uma recomendação defensável e contradizem a ideia de grupos naturais garantidos.

### U06-M17 — B

O medoide pertence ao conjunto observado e minimiza dissimilaridades. A média pode não ser observada e não é definida para todo tipo de objeto.

### U06-M18 — D

Depois de resumir a grade, muitas operações dependem do número de células, e não de comparações repetidas entre todos os objetos. Resolução e limiar continuam necessários.

### U06-M19 — A

CLIQUE encontra unidades densas em subconjuntos das dimensões e usa monotonicidade para restringir a busca. Não é um método supervisionado nem centrado em médias.

### U06-M20 — C

Células grandes agregam áreas extensas, podendo preencher separações e impor limites horizontais ou verticais grosseiros. O limiar continua influente.

### U06-M21 — B

Responsabilidade é uma probabilidade posterior normalizada entre os componentes para um objeto. Ela não é rótulo observado nem distância bruta.

### U06-M22 — D

Na etapa M, as responsabilidades calculadas na etapa E atuam como pesos para reestimar proporções, médias e covariâncias.

### U06-M23 — A

`full` estima uma matriz de covariância completa para cada componente, permitindo orientações diferentes. `spherical` restringe os contornos a esferas.

### U06-M24 — C

BIC menor indica melhor equilíbrio entre verossimilhança e penalização de complexidade entre os candidatos. Estabilidade, ajuste e significado ainda precisam ser verificados.

## Distribuição das respostas

| A | B | C | D |
|---:|---:|---:|---:|
| 6 | 6 | 6 | 6 |
