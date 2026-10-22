# Gabarito — 07.04 Fluxo de decisão para detecção

## U07-NB04-V01

Esses diagnósticos descrevem aspectos parciais: normalidade e assimetria tratam distribuições marginais; gráficos dependem da projeção; e nenhum deles incorpora sozinho finalidade, custo, contexto, geometria multivariada ou mudança temporal. Eles excluem escolhas claramente inadequadas e geram hipóteses de candidatos. A decisão ainda exige comparação em desenvolvimento, avaliação reservada, sensibilidade e viabilidade operacional.

**Rubrica (4 pontos):** caráter parcial (1), fatores ausentes (1), papel de orientar candidatos (1), necessidade de validação (1).

## U07-NB04-E01

O escore-z é candidato inicial porque média e desvio-padrão representam razoavelmente uma distribuição simétrica e estável. O diagnóstico complementar deve incluir histograma ou gráfico quantil–quantil, comparação com mediana/MAD e verificação temporal. Eu trocaria para IQR ou MAD se surgissem caudas pesadas ou extremos influentes; para limites contextuais se aparecessem regimes por horário ou população; e para método multivariado se o desvio dependesse de combinação de atributos.

**Rubrica (6 pontos):** candidato (1), justificativa (1), diagnóstico (2), condição de troca e alternativa coerente (2).

## U07-NB04-E02

A finalidade depende de posição conjunta, portanto a rota é multivariada. Regiões não convexas de densidade semelhante com pontos externos favorecem DBSCAN: ele acompanha conectividade densa e marca ruído sem exigir grupos convexos. Os parâmetros centrais são `eps`, que define o raio, e `min_samples`, que define a densidade mínima. Devem-se testar valores próximos após padronização e verificar estabilidade, grupos fundidos e taxa de ruído. LOF pode ser comparador, mas não fornece diretamente as regiões conectadas.

**Rubrica (6 pontos):** rota multivariada (1), DBSCAN (1), geometria/densidade (2), dois parâmetros e sensibilidade (2).

## U07-NB04-E03

Solução esperada: ajustar três modelos `LocalOutlierFactor`, inverter `negative_outlier_factor_`, ordenar os escores e formar conjuntos com os dez primeiros índices. Calcular a interseção dos três conjuntos e, opcionalmente, Jaccard entre pares. A recomendação é estável apenas se os casos prioritários e a conclusão operacional persistirem; alta interseção não confirma causas, e baixa interseção exige revisar escala, tamanho da vizinhança ou método.

**Rubrica (7 pontos):** três ajustes (2), rankings (1), interseção ou Jaccard (2), conclusão de estabilidade (1), ressalva (1).

## U07-NB04-E04

O registro deve conter finalidade e ação; unidade e população; período de referência; atributos, transformações e escala; candidatos e exclusões; parâmetros e faixa testada; desenho temporal da avaliação; métricas alinhadas ao orçamento e custo; análise de estabilidade; método e limiar escolhidos; revisão humana; preservação do dado; monitoramento e responsáveis. Condição de suspensão possível: queda persistente da precisão abaixo do mínimo operacional, mudança da taxa de alertas fora da faixa acordada, impacto desigual não mitigado ou alteração documentada do processo que invalide a referência.

**Rubrica (10 pontos):** formulação (2), representação (1), candidatos/parâmetros (2), avaliação/custo (2), governança (2), condição de revisão ou suspensão (1).
