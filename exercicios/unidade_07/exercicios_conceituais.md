# Unidade VII — Exercícios conceituais

**Tema:** detecção de *outliers* por métodos estatísticos, proximidade, densidade e agrupamento

**Objetivos avaliados:** distinguir tipos e causas de anomalias; calcular escores e limites; comparar pressupostos; avaliar alertas com rótulos raros; propor investigação, comunicação e monitoramento responsáveis.

**Tempo estimado:** 150 minutos

**Instruções:** justifique as respostas, apresente cálculos e diferencie detecção, confirmação e ação. Use três casas decimais quando necessário.

## Fundamentos e contexto

1. **U07-C01.** Diferencie anomalias globais, contextuais e coletivas. Forneça um exemplo de cada uma e identifique a referência usada.

2. **U07-C02.** Um valor extremo pode resultar de erro de digitação, evento legítimo raro ou fraude. Explique por que nenhum escore numérico distingue sozinho essas causas e proponha duas verificações para cada hipótese.

3. **U07-C03.** Uma empresa detecta gastos incomuns misturando pessoas físicas e empresas. Explique o risco dessa referência e proponha uma unidade de análise e dois contextos relevantes.

## Métodos estatísticos

4. **U07-C04.** Para `[8, 9, 10, 10, 11, 12]`, calcule média, desvio-padrão amostral e escore-z do valor 12. Interprete sem aplicar automaticamente um limiar.

5. **U07-C05.** Para `[2, 3, 3, 4, 5, 6, 20]`, use a interpolação linear do pandas para calcular $Q_1$, $Q_3$, IQR e cercas de 1,5 IQR. Identifique os valores sinalizados.

6. **U07-C06.** Calcule mediana, MAD e escore-z robusto do valor 20 nos dados da questão anterior. Use $z^{(r)}=0{,}6745(x-\tilde{x})/MAD$.

7. **U07-C07.** Compare escore-z, IQR e MAD quanto a pressupostos, resistência a extremos, assimetria e casos degenerados. Em que cenário cada um seria um ponto de partida razoável?

8. **U07-C08.** Uma distribuição de renda é fortemente assimétrica à direita e todos os valores altos legítimos são sinalizados pela regra do IQR. Proponha três alterações na análise e explique o que cada uma resolve.

## Proximidade, densidade e agrupamento

9. **U07-C09.** As distâncias de P aos cinco vizinhos mais próximos são 0,2; 0,3; 0,5; 0,9 e 1,4. Calcule o escore de distância ao k-ésimo vizinho para $k=2$ e $k=5$. Discuta a sensibilidade a $k$.

10. **U07-C10.** Explique os três componentes do LOF: distância alcançável, densidade local alcançável e razão de densidades. Interprete LOF próximo de 1 e muito maior que 1.

11. **U07-C11.** Compare distância ao k-ésimo vizinho e LOF em dados com um grupo compacto e outro esparso. Por que os rankings podem discordar?

12. **U07-C12.** Explique como `eps` e `min_samples` alteram os pontos marcados como ruído pelo DBSCAN. Por que ruído não é sinônimo de erro?

13. **U07-C13.** Descreva duas estratégias de detecção baseadas em agrupamento: grupo pequeno e distância ao representante. Apresente uma falha possível de cada estratégia.

## Avaliação e decisão

14. **U07-C14.** Um detector emite 20 alertas, dos quais 8 são confirmados. Existem 25 anomalias conhecidas no período. Calcule precisão, revocação e F1. Explique por que os valores podem estar enviesados se somente os alertas forem investigados.

15. **U07-C15.** Dois métodos têm precisão@10 de 0,8 e 0,6. O segundo encontra casos com impacto financeiro médio cinco vezes maior. Proponha um critério de decisão que não escolha apenas pela precisão.

16. **U07-C16.** Elabore um protocolo operacional de detecção de anomalias que inclua finalidade, população, representação, validação temporal, orçamento, revisão humana, preservação do dado, impactos sobre pessoas e monitoramento.

## Desafio opcional

17. **U07-C17.** Em alta dimensionalidade, distâncias entre vizinhos tendem a se tornar menos contrastantes. Explique consequências para k-NN e LOF e proponha um experimento para verificar se redução de dimensionalidade ajuda sem ocultar anomalias relevantes.
