# Unidade VI — Gabarito dos exercícios conceituais

## U06-C01

Classificação aprende, a partir de exemplos rotulados, uma função para atribuir classes conhecidas. Agrupamento não utiliza um rótulo-alvo no ajuste; constrói grupos segundo representação, proximidade e algoritmo escolhidos.

Exemplo defensável: unidade = um cliente ativo no último ano; atributos = frequência de compras, gasto médio por compra e proporção de categorias distintas adquiridas; excluir = identificador do cliente, pois seu número não representa comportamento; finalidade = adaptar comunicações ou investigar padrões de uso. Seria necessário definir período, tratamento de clientes novos, escala e consequências da segmentação. Outros conjuntos de atributos são válidos se coerentes com uma finalidade explícita.

**Elementos essenciais:** supervisão, unidade, três atributos justificáveis, uma exclusão justificada e finalidade.

## U06-C02

Na escala bruta, diferenças de dezenas de milhares de reais tendem a dominar diferenças de até 29 compras. A partição refletirá principalmente gasto, mesmo que frequência seja substantivamente importante.

Procedimento: dividir os dados conforme o desenho da análise; ajustar um transformador, como `StandardScaler` ou uma transformação robusta, somente no conjunto usado para construir o modelo; aplicar os parâmetros aprendidos aos demais dados; executar e validar o agrupamento. Em uma análise descritiva única sem divisão, ainda se devem guardar os parâmetros para reproduzir a transformação em dados futuros.

Manter a escala original é defensável se as unidades já expressam pesos desejados para o objetivo ou se uma distância em unidades monetárias possui interpretação substantiva deliberada. A decisão deve ser documentada, não resultar apenas da conveniência.

## U06-C03

Com $\mu_1=(0,0)$ e $\mu_2=(6,4)$:

- A: distâncias 0 e $\sqrt{52}$, então grupo 1;
- B: distâncias 2 e $\sqrt{52}$, então grupo 1;
- C: distâncias $\sqrt{52}$ e 0, então grupo 2;
- D: distâncias $\sqrt{80}$ e 2, então grupo 2.

Os centroides atualizados são:

$$
\mu'_1=\frac{(0,0)+(0,2)}2=(0,1),\qquad
\mu'_2=\frac{(6,4)+(8,4)}2=(7,4).
$$

Antes da atualização:

$$SSE=0^2+2^2+0^2+2^2=8.$$

Depois:

$$SSE=1^2+1^2+1^2+1^2=4.$$

A atribuição não mudou nessa iteração, mas a atualização reduziu a SSE pela metade.

## U06-C04

As reduções sucessivas são:

| Mudança | Redução da SSE |
|---|---:|
| $1\to2$ | $900-410=490$ |
| $2\to3$ | $410-150=260$ |
| $3\to4$ | $150-125=25$ |
| $4\to5$ | $125-112=13$ |

O primeiro achatamento forte ocorre depois de $k=3$, então $k=3$ é um candidato. Escolher simplesmente a menor SSE observada favoreceria sempre o maior $k$ testado, pois a SSE não aumenta quando novos grupos são permitidos. O candidato deve ser confrontado com estabilidade, outras métricas, tamanhos e utilidade dos grupos.

## U06-C05

- **Duas luas:** centroides e regiões de Voronoi do k-means favorecem grupos convexos, podendo cortar cada lua. DBSCAN ou ligação simples podem acompanhar conectividade; deve-se verificar sensibilidade a parâmetros e ruído.
- **Tamanhos ou dispersões diferentes:** a minimização da SSE pode dividir o grupo grande ou absorver o pequeno. Comparar métodos, examinar tamanhos e silhouettes individuais e testar modelos apropriados à geometria.
- **Outliers:** a média é deslocada por valores extremos. Investigar a origem, usar método robusto como k-medoids ou DBSCAN e comparar resultados com e sem os pontos, sem removê-los automaticamente.

## U06-C06

O método aglomerativo começa com um grupo por objeto e realiza fusões; o divisivo começa com todos juntos e realiza divisões. Em um dendrograma, a folha representa um objeto, a junção registra a união de ramos e sua altura representa o valor do critério de ligação naquela fusão. A altura não é quantidade de objetos. Um corte horizontal intercepta ramos; cada ramo interceptado define um grupo composto pelas folhas abaixo dele.

## U06-C07

As distâncias entre grupos são:

$$3,\quad 5,\quad \sqrt{13},\quad \sqrt{13}.$$

Portanto:

$$d_{simples}=3,$$

$$d_{completa}=5,$$

$$d_{média}=\frac{3+5+2\sqrt{13}}4\approx3{,}803.$$

A ligação completa é determinada diretamente pelo par mais distante e, portanto, é a mais afetada por ele. A média também muda, mas dilui o par entre todas as combinações; a simples depende apenas do par mais próximo.

## U06-C08

O primeiro grande salto ocorre de 0,5 para 2,8. Um corte com altura entre esses valores, por exemplo 1,5, preserva as três primeiras fusões e produz $6-3=3$ grupos.

A escolha deve ser validada porque um salto pode depender da escala, distância e ligação; e porque três grupos podem não ser estáveis, interpretáveis ou úteis. Também se devem examinar tamanhos, outliers, cortes próximos e conhecimento do domínio.

## U06-C09

- P é **central**, pois sua vizinhança contém cinco objetos e satisfaz `min_samples=4`; ele pode expandir a região densa.
- Q é **borda**, pois não satisfaz o limiar com três objetos, mas está ao alcance do central P; entra no grupo, porém não o expande.
- R é **ruído**, pois não é central nem está na vizinhança de um central; recebe rótulo `-1` nesse ajuste.

As classificações podem mudar com os parâmetros ou com novos dados.

## U06-C10

Aumentar `eps` amplia vizinhanças, geralmente reduz ruído e fragmentação, mas pode unir regiões distintas. Aumentar `min_samples` torna o critério de densidade mais exigente, geralmente reduz o número de centrais e pode aumentar ruído ou fragmentação.

Se um grupo é denso e outro esparso, um `eps` pequeno adequado ao primeiro pode destruir o segundo; um `eps` grande adequado ao segundo pode unir estruturas na região densa. Devem-se examinar gráficos de vizinhos, parâmetros próximos e, se necessário, métodos capazes de representar densidade variável.

## U06-C11

**(a)** K-means é uma escolha inicial pela escala de dois milhões de objetos e pela geometria compacta. Ressalva: requer $k$, padronização e verificação de inicializações e outliers; técnicas escaláveis ou amostras podem ser necessárias.

**(b)** Agrupamento hierárquico é apropriado para explorar níveis e produzir dendrograma com 300 objetos. Ressalva: distância e ligação mudam a árvore, e uma fusão não é revista.

**(c)** DBSCAN é inicial pela forma curva, ruído explícito e ausência de $k$. Ressalva: `eps` e `min_samples` são sensíveis, e densidades distintas ou distância inadequada às trajetórias podem comprometer o resultado.

## U06-C12

Para $i$:

$$s(i)=\frac{7-3}{7}=\frac47\approx0{,}571.$$

O objeto está mais próximo do próprio grupo. Para $j$:

$$s(j)=\frac{4-5}{5}=-0{,}2.$$

O valor negativo indica maior proximidade média ao grupo alternativo. A média é:

$$\frac{0{,}571-0{,}2}{2}\approx0{,}186.$$

A média oculta que um dos objetos tem atribuição questionável.

## U06-C13

Não há vencedor inequívoco. A possui silhouette maior, favorecendo maior distância relativa ao grupo alternativo. B possui Davies–Bouldin menor, favorecendo menor razão entre dispersão interna e separação na pior comparação de cada grupo. A diferença é pequena e os índices resumem a geometria segundo a distância escolhida.

São necessárias evidências sobre estabilidade, número e tamanho dos grupos, cobertura e ruído, distribuição dos silhouettes, referência externa se pertinente, interpretabilidade, sensibilidade ao pré-processamento e utilidade. A decisão depende da finalidade.

## U06-C14

X deve obter ARI 1 porque apenas permuta os rótulos: os pares juntos e separados são idênticos aos da referência. Em Y, pares que deveriam estar juntos, como os objetos das posições 1–2 e 3–4, foram separados. Também surgem uniões indevidas entre objetos de classes diferentes, como posições 1 e 3 ou 2 e 4. O último par permanece junto. Logo, Y tem concordância parcial, inferior a 1.

## U06-C15

Tendência pergunta se os dados possuem estrutura não aleatória que justifique agrupamento. Estabilidade pergunta se a solução reaparece sob pequenas mudanças. Uma partição pode ser muito estável porque o atributo de maior escala domina todas as execuções, embora represente um artefato numérico e não a finalidade.

Para tendência, pode-se comparar distâncias com dados uniformes ou usar repetidamente a estatística de Hopkins. Para estabilidade, pode-se variar sementes/inicializações e comparar partições por ARI; e reamostrar ou perturbar levemente os dados, reconstruindo a solução e comparando objetos comuns. Também se devem repetir alternativas de escala e atributos.

## U06-C16

Um protocolo completo deve:

1. definir apoio acadêmico como finalidade e impedir usos punitivos não autorizados;
2. delimitar população, período e unidade estudante–período;
3. selecionar atributos relacionados ao apoio, documentar escala e excluir identificadores e proxies inadequados;
4. proteger dados sensíveis e verificar necessidade, base institucional e acesso;
5. comparar métodos e parâmetros com métricas internas, eventual referência, estabilidade, cobertura e tamanhos;
6. perfilar com distribuições e exemplos, não apenas médias;
7. usar nomes observáveis e temporais, como “menor participação recente”, evitando “desmotivados”;
8. validar com docentes e estudantes e examinar impactos desiguais entre grupos;
9. oferecer apoio sem negar oportunidades, possibilitar contestação e revisão individual;
10. monitorar mudança dos dados, perfis, estabilidade, cobertura e efeitos das intervenções, definindo condições para suspender a segmentação.

Agrupamentos não diagnosticam causas e não substituem contato com o estudante.

## U06-C17 — Desafio opcional

Tratar todo ruído como um único grupo faz parecer que objetos possivelmente dispersos formam uma classe coerente. Isso pode piorar ou distorcer silhouette e Davies–Bouldin, pois o rótulo `-1` significa “não atribuído a região densa”, não “mesmo grupo”.

Excluir o ruído avalia apenas a parte mais fácil ou densa e pode inflar as métricas, sobretudo quando a exclusão é grande. Soluções com coberturas diferentes deixam de ser diretamente comparáveis.

Uma comunicação transparente deve apresentar: parâmetros e métrica; número de grupos; quantidade e proporção de ruído; cobertura; métricas calculadas somente nos não ruídos com essa condição explícita; análise separada dos ruídos; sensibilidade a parâmetros próximos; e, quando útil, uma análise alternativa mostrando como conclusões mudam sob outra regra. Nenhum escore isolado deve ocultar a cobertura.

