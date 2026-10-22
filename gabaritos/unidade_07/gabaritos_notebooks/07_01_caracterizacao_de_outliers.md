# Gabarito — 07.01 Caracterização de outliers

## U07-NB01-V01

O valor 12 kW pertence à faixa observada durante o expediente e, portanto, não se destaca quando comparado globalmente com todos os períodos. Às 3h, porém, a referência apropriada é o consumo de outras madrugadas, tipicamente menor. O mesmo valor pode então se afastar do padrão condicional ao horário. A classificação depende de haver uma diferença real entre regimes e de o horário ser contexto relevante.

**Rubrica (4 pontos):** referência global (1), referência horária (1), classificação contextual (1), dependência do contexto (1).

## U07-NB01-E01

- **Leitura instantânea:** representa picos globais ou contextuais em um momento, mas não descreve duração ou ordem.
- **Janela de cinco minutos:** representa comportamento coletivo local, como oscilação, tendência curta ou combinação de sensores; resume vários instantes.
- **Trajetória diária:** representa forma, sequência, sazonalidade e mudança de regime ao longo do dia, embora possa esconder eventos breves se for excessivamente agregada.

A melhor unidade depende do mecanismo de interesse e da velocidade com que uma ação precisa ocorrer.

**Rubrica (6 pontos):** três unidades (3), tipo de padrão para cada uma (2), compromisso ou finalidade (1).

## U07-NB01-E02

Exemplo: em uma população adulta, altura de 1,80 m e peso de 50 kg podem aparecer separadamente nos dados, mas a combinação pode ser rara em relação à associação usual entre altura e peso. Uma análise univariada examina apenas as distribuições marginais e pode não sinalizar nenhum valor. A análise multivariada considera a posição conjunta ou o afastamento da relação entre atributos. O exemplo descreve raridade, não diagnóstico de saúde.

**Rubrica (5 pontos):** dois valores marginalmente plausíveis (2), combinação rara (1), limitação univariada (1), interpretação prudente (1).

## U07-NB01-E03

Resposta-modelo:

| Área | Unidade | Referência | Atributos | Causa possível | Consequência de falso alerta |
|---|---|---|---|---|---|
| indústria | janela de sensores por máquina | mesmo modelo e regime operacional | temperatura, pressão e vibração | desgaste ou sensor descalibrado | parada e inspeção desnecessárias |
| finanças | transação de uma conta | histórico da conta e contas comparáveis | valor, horário, local e canal | fraude ou viagem legítima | bloqueio indevido e dano ao cliente |

Outras áreas são válidas quando os cinco elementos estão coerentes. O método detecta desvio; a causa precisa ser verificada.

**Rubrica (8 pontos):** duas áreas (1), unidades (2), referências (1), atributos (1), causas (1), consequências (2).

## U07-NB01-E04

Explicações alternativas incluem: subpopulação rara e legítima; erro de medição ou integração; mudança recente de processo; efeito da escala ou de atributos irrelevantes; distorção da projeção bidimensional; ou evento adversarial.

Antes de caracterizar o grupo, deve-se: consultar os dados nas dimensões originais e testar outras escalas; verificar origem, qualidade e período dos registros; comparar estabilidade em amostras ou projeções; e obter conhecimento do domínio. Três dessas verificações, bem justificadas, atendem ao enunciado.

**Rubrica (7 pontos):** quatro explicações (4), três verificações (3).
