# Gabarito — 05.04 Regressão linear simples e múltipla

## U05-NB04-V01

Os números podem ser apenas códigos. Se 0, 1 e 2 representam, por exemplo, `baixo`, `médio` e `alto`, não é necessariamente válido interpretar a distância entre 0 e 1 como igual à distância entre 1 e 2 nem prever 1,6 como categoria. O alvo continua categórico e exige classificação, possivelmente ordinal.

Exemplo categórico: espécie codificada como 0, 1 ou 2. Exemplo numérico: consumo mensal em kWh, no qual diferenças e valores intermediários possuem significado quantitativo.

**Rubrica (4 pontos):** distinguir código de quantidade (2) e fornecer os dois exemplos coerentes (2).

## U05-NB04-E01

Com os valores completos do modelo:

$$
\hat y=-34{,}1269+3{,}97755(80)=284{,}0769.
$$

Usando apenas os valores arredondados exibidos:

$$
\hat y\approx-34{,}127+3{,}978(80)=284{,}113.
$$

A pequena diferença decorre do arredondamento. A chamada do modelo retorna aproximadamente **284,077 mil reais**.

O coeficiente 3,97755 está em milhares de reais previstos por m² adicional. O intercepto −34,1269 está em milhares de reais e posiciona a reta quando a área vale zero; como zero está fora da faixa observada, ele não possui interpretação imobiliária direta.

**Rubrica (6 pontos):** fórmula e substituição (2), resultado e arredondamento (2), unidades e cautela com o intercepto (2).

## U05-NB04-E02

Os resíduos são definidos por observado menos previsto:

$$
\mathbf e=[100-110,\ 120-115,\ 130-140]=[-10,5,-10].
$$

O MAE é

$$
MAE=\frac{|-10|+|5|+|-10|}{3}=\frac{25}{3}=8{,}333.
$$

O RMSE é

$$
RMSE=\sqrt{\frac{(-10)^2+5^2+(-10)^2}{3}}
=\sqrt{75}=8{,}660.
$$

A média observada é $116{,}667$. A soma total dos quadrados é $466{,}667$ e a soma dos quadrados dos resíduos é 225. Logo:

$$
R^2=1-\frac{225}{466{,}667}=0{,}518.
$$

MAE e RMSE possuem a mesma unidade do alvo. O RMSE é um pouco maior porque penaliza mais os erros de magnitude 10. O $R^2$ indica redução de aproximadamente 51,8% no erro quadrático em relação à referência pela média, sem implicar causalidade.

**Rubrica (8 pontos):** resíduos (2), MAE (2), RMSE (2), $R^2$ e interpretação (2).

## U05-NB04-E03

No teste:

| Modelo | MAE | RMSE | $R^2$ |
|---|---:|---:|---:|
| Baseline | 132,018 | 155,039 | −0,002 |
| Regressão simples | 44,539 | 56,386 | 0,867 |
| Regressão múltipla | 26,386 | 33,345 | 0,954 |

Diante do *baseline*, a regressão múltipla reduz:

- MAE em $132{,}018-26{,}386=105{,}632$ mil reais;
- RMSE em $155{,}039-33{,}345=121{,}694$ mil reais.

Diante da regressão simples, reduz:

- MAE em $44{,}539-26{,}386=18{,}153$ mil reais;
- RMSE em $56{,}386-33{,}345=23{,}041$ mil reais.

O $R^2=0{,}954$ indica que, neste teste sintético, o erro quadrático foi 95,4% menor que o da referência baseada na média observada. Isso expressa desempenho preditivo, não que os atributos expliquem causalmente 95,4% do preço.

**Rubrica (8 pontos):** comparação com baseline (2), comparação com regressão simples (2), leitura das unidades (2), interpretação não causal de $R^2$ (2).

## U05-NB04-E04

Exemplo de resposta:

- `area_m2`: coeficiente 3,268. Mantidos os demais atributos constantes, 1 m² adicional está associado a aumento previsto de 3,268 mil reais.
- `idade_anos`: coeficiente −1,993. Mantidos os demais constantes, um ano adicional está associado a redução prevista de 1,993 mil reais.

Também seriam válidas as interpretações de `quartos` — 26,647 mil reais previstos por quarto — e `distancia_centro_km` — redução prevista de 4,633 mil reais por quilômetro.

O imóvel de 250 m² recebe previsão de 962,7 mil reais, mas o máximo da área de treino é inferior a esse valor. Trata-se de extrapolação: a fórmula prolonga a relação linear sem evidência de que preços se comportem assim nessa região.

Os coeficientes são associações condicionais ao conjunto de atributos. Área, quartos, localização e características omitidas se relacionam; não houve intervenção controlada. Portanto, não demonstram efeitos causais.

**Rubrica (8 pontos):** dois coeficientes com sinal, magnitude e unidade (4), extrapolação (2), ressalva causal e variáveis relacionadas ou omitidas (2).
