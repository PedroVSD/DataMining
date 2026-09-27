# Unidade VI — Exercícios conceituais

**Tema:** fundamentos, k-means, agrupamento hierárquico, DBSCAN e avaliação de grupos  
**Objetivos avaliados:** formular uma análise de grupos; calcular e interpretar etapas dos algoritmos; comparar geometrias e parâmetros; avaliar qualidade, estabilidade e utilidade; comunicar segmentações de forma responsável.  
**Tempo estimado:** 150 minutos  
**Instruções:** justifique as respostas, apresente cálculos e declare as escolhas de distância, escala e parâmetros. Numerações de grupos são arbitrárias.

## Fundamentos e k-means

1. **U06-C01.** Diferencie agrupamento e classificação. Para uma segmentação de clientes, defina uma unidade de análise, três atributos apropriados, um atributo que deveria ser excluído e uma possível finalidade.

2. **U06-C02.** Uma base utiliza gasto anual entre R$ 500 e R$ 100.000 e número de compras entre 1 e 30. Explique o efeito provável da distância Euclidiana bruta e proponha uma preparação sem vazamento. Em que situação manter a escala original seria defensável?

3. **U06-C03.** Considere os pontos $A=(0,0)$, $B=(0,2)$, $C=(6,4)$ e $D=(8,4)$, com centroides iniciais $\mu_1=A$ e $\mu_2=C$. Execute uma iteração do k-means: atribua os pontos, atualize os centroides e calcule a SSE antes e depois da atualização.

4. **U06-C04.** Para $k=1,2,3,4,5$, as SSEs são 900, 410, 150, 125 e 112. Use o método do cotovelo para propor $k$ e calcule as reduções absolutas sucessivas. Explique por que aumentar $k$ até a SSE mínima observada não é uma regra válida.

5. **U06-C05.** Explique por que k-means pode falhar em duas luas, em grupos de tamanhos muito diferentes e diante de outliers. Para cada caso, indique uma alternativa ou verificação.

## Agrupamento hierárquico e densidade

6. **U06-C06.** Compare agrupamento aglomerativo e divisivo. Explique o que uma folha, uma junção e a altura significam em um dendrograma e como um corte produz uma partição.

7. **U06-C07.** Considere $C_1=\{(0,0),(0,2)\}$ e $C_2=\{(3,0),(3,4)\}$. Calcule as ligações simples, completa e média pela distância Euclidiana. Explique qual delas é mais afetada pelo par mais distante.

8. **U06-C08.** Um dendrograma possui alturas de fusão 0,2; 0,4; 0,5; 2,8 e 5,1 para seis objetos. Que número de grupos seria sugerido pelo primeiro grande salto? Mostre onde faria o corte e indique duas razões pelas quais essa escolha ainda deve ser validada.

9. **U06-C09.** Com `eps=1` e `min_samples=4`, incluindo o próprio ponto, P possui cinco objetos na vizinhança; Q possui três, mas está ao alcance de P; R possui dois e não está ao alcance de nenhum ponto central. Classifique P, Q e R e explique o papel de cada tipo no crescimento do grupo.

10. **U06-C10.** Explique os efeitos de aumentar separadamente `eps` e `min_samples` no DBSCAN. Por que um único par de valores pode não representar bem grupos com densidades muito diferentes?

11. **U06-C11.** Compare k-means, Ward e DBSCAN para: (a) quatro grupos compactos em dois milhões de objetos; (b) uma taxonomia exploratória com 300 objetos; (c) rotas curvas com registros isolados. Justifique a escolha inicial e apresente uma ressalva para cada cenário.

## Avaliação, interpretação e decisão

12. **U06-C12.** Calcule o silhouette de um objeto com $a(i)=3$ e $b(i)=7$. Depois calcule para $a(j)=5$ e $b(j)=4$. Interprete os sinais e obtenha a média dos dois.

13. **U06-C13.** Duas soluções têm: A — silhouette 0,52 e Davies–Bouldin 0,74; B — silhouette 0,48 e Davies–Bouldin 0,68. É possível declarar uma vencedora apenas com esses valores? Explique o que cada índice favorece e indique outras evidências necessárias.

14. **U06-C14.** A referência é `[0,0,1,1,2,2]`. Compare conceitualmente as partições X=`[1,1,2,2,0,0]` e Y=`[0,1,0,1,2,2]` pelo Rand ajustado. Qual deve obter ARI 1 e por quê? Que tipos de concordância entre pares foram rompidos em Y?

15. **U06-C15.** Diferencie tendência de agrupamento e estabilidade. Um k-means é altamente estável em dados dominados por um atributo de grande escala. Por que isso não basta para validar a solução? Proponha um teste para a tendência e dois testes de estabilidade.

16. **U06-C16.** Uma segmentação de estudantes será usada para oferecer apoio acadêmico. Elabore um protocolo de seleção responsável que inclua finalidade, atributos, avaliação, perfis, linguagem, impacto, possibilidade de revisão e monitoramento.

## Desafio opcional

17. **U06-C17.** Compare duas estratégias para avaliar DBSCAN: calcular métricas internas tratando todo ruído como um único grupo ou excluir o ruído e informar cobertura. Discuta problemas das duas estratégias e proponha uma forma transparente de relatar os resultados.

