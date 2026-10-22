# Gabarito — 07.02 Detecção univariada

## U07-NB02-V01

É uma possível anomalia contextual: o valor só pode ser avaliado em relação ao tipo de cliente, porte, período e comportamento histórico. Um limiar global mistura distribuições distintas; pode sinalizar empresas legítimas em excesso ou deixar de perceber gastos incomuns de pessoas físicas.

**Rubrica (4 pontos):** tipo contextual (1), referência condicionada (1), falha do limite global (1), ausência de diagnóstico automático (1).

## U07-NB02-E01

Com a interpolação linear do pandas, $Q_1=5$, $Q_3=6{,}5$ e $IQR=1{,}5$. Logo,

$$L=5-1{,}5(1{,}5)=2{,}75,$$

$$U=6{,}5+1{,}5(1{,}5)=8{,}75.$$

Somente 30 está fora das cercas. O resultado depende da convenção de quartis, especialmente em amostras pequenas.

**Rubrica (6 pontos):** quartis (2), IQR (1), cercas (2), identificação e ressalva (1).

## U07-NB02-E02

Média e desvio-padrão usam todos os valores e podem ser deslocados por extremos, reduzindo o próprio escore-z. Mediana e MAD resistem a uma proporção maior de contaminação e preservam melhor o centro e a escala do conjunto principal.

A regra robusta ainda pode falhar em dados multimodais, sazonais ou contextuais; em uma distribuição com muitos empates, $MAD=0$; e em uma cauda legítima longa, um limiar simétrico pode produzir falsos alertas. Robustez contra extremos não substitui uma referência adequada.

**Rubrica (6 pontos):** influência nos dois pares de medidas (3), cenário de falha (2), interpretação prudente (1).

## U07-NB02-E03

Fluxo-modelo:

1. congelar uma cópia do registro bruto, horário, unidade, sensor e versão do processamento;
2. repetir a medição ou consultar sensor redundante e calibração para testar falha técnica;
3. verificar manutenção, mudança de regime, comando operacional e condições ambientais;
4. consultar histórico e eventos comparáveis para avaliar raridade legítima;
5. registrar evidências e classificar como erro confirmado, evento legítimo, caso suspeito ou inconclusivo;
6. corrigir somente em camada derivada, preservando valor e motivo da alteração;
7. usar o desfecho para monitorar e recalibrar o detector.

**Rubrica (8 pontos):** preservação/rastreabilidade (2), falha de sensor (1), mudança operacional (1), evento legítimo (1), decisão com incerteza (2), retroalimentação (1).

## U07-NB02-E04

Com a semente e os dados do notebook, os três limiares sinalizam somente a observação 95:

| Limiar | Alertas |
|---:|---:|
| 3,0 | 1 |
| 3,5 | 1 |
| 4,0 | 1 |

Neste conjunto, o resultado é estável porque o caso injetado está bem separado e os demais escores ficam abaixo de 3. Em geral, reduzir o limiar aumenta sensibilidade e carga de investigação; aumentá-lo reduz alertas, mas pode perder eventos. A ausência de mudança nestes três valores não autoriza generalização.

**Rubrica (6 pontos):** três execuções (2), contagens (1), compromisso (2), ressalva (1).
