# Gabarito — 05.01 Processo e avaliação de classificação

## U05-NB01-V01

O classificador alcança 90% de acurácia porque acerta todos os 90% de casos negativos. Entretanto, ele prevê zero positivos e não encontra nenhum dos 10% de casos de interesse.

$$
\operatorname{Revocação}=\frac{VP}{VP+FN}=\frac{0}{0+10}=0.
$$

Como a precisão e a revocação positivas são nulas, a medida F1 também vale 0. Logo, a acurácia alta apenas reproduz a classe majoritária e não demonstra utilidade para localizar positivos.

**Rubrica (3 pontos):** relacionar a acurácia à classe majoritária (1), calcular revocação 0 (1) e F1 0 com interpretação (1).

## U05-NB01-E01

A matriz apresenta $VN=120$, $FP=6$, $FN=19$ e $VP=5$, totalizando 150 clientes.

### Acurácia

$$
\operatorname{Acurácia}=\frac{VP+VN}{VP+VN+FP+FN}
=\frac{5+120}{150}=0{,}833.
$$

### Precisão

$$
\operatorname{Precisão}=\frac{VP}{VP+FP}
=\frac{5}{5+6}=0{,}455.
$$

Entre os 11 clientes sinalizados, 5 realmente cancelaram.

### Revocação

$$
\operatorname{Revocação}=\frac{VP}{VP+FN}
=\frac{5}{5+19}=0{,}208.
$$

O modelo encontrou 5 dos 24 clientes que cancelaram e deixou de sinalizar 19.

### F1

$$
F1=\frac{2VP}{2VP+FP+FN}
=\frac{10}{10+6+19}=0{,}286.
$$

Os seis falsos positivos são clientes contatados que não cancelariam. Os 19 falsos negativos são cancelamentos não sinalizados. A acurácia da árvore, 0,833, é ligeiramente inferior à do *baseline*, 0,840; ainda assim, a árvore encontra alguns positivos e possui AUC-ROC 0,716, enquanto o *baseline* não encontra nenhum e possui AUC-ROC 0,500. A escolha depende do custo e do objetivo, não apenas da acurácia.

**Rubrica (8 pontos):** identificação das quatro contagens (2), quatro cálculos corretos (4) e interpretação contextual dos dois erros (2).

## U05-NB01-E02

Os custos exibidos são:

- limiar 0,30: $13+5(14)=83$;
- limiar 0,50: $6+5(19)=101$;
- limiar 0,70: $0+5(24)=120$.

Com a função $FP+5FN$, o menor custo é 83, obtido pelo limiar 0,30. Esse limiar aceita 13 falsos positivos para reduzir os falsos negativos de 19, no limiar 0,50, para 14.

A escolha não é universal. Se contatar um cliente for caro, invasivo ou limitado por capacidade operacional, o peso de $FP$ deverá aumentar. Nesse caso, um limiar mais alto pode se tornar preferível porque reduz contatos indevidos, mesmo deixando escapar mais cancelamentos. Também seria necessário validar custos, estabilidade e calibração com dados reais.

**Rubrica (5 pontos):** calcular os três custos (2), selecionar 0,30 sob os pesos declarados (1) e explicar como outro custo de falso positivo pode alterar a decisão (2).
