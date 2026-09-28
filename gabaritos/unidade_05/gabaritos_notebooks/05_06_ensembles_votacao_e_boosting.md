# Gabarito — 05.06 Ensembles por votação e boosting

## U05-NB06-V01

A votação dura produz classe 1, pois dois de três modelos votam em 1. A probabilidade média é $(0,51+0,55+0,05)/3=0,37$, portanto a votação suave produz classe 0 no limiar 0,5. A divergência ocorre porque a votação dura ignora intensidade e a suave é fortemente afetada pela baixa probabilidade do terceiro modelo.

## U05-NB06-E01

O erro ponderado é $\varepsilon=0,25$. Logo, $\alpha=\frac12\log(0,75/0,25)=\frac12\log 3\approx0,549$. O objeto errado recebe atenção relativa maior na rodada seguinte; após a atualização binária usual, ele concentra metade do peso total e cada acerto fica com um sexto.

## U05-NB06-E02

Bagging treina modelos independentes em bootstraps, combina-os com pesos iguais e pode paralelizar. Boosting é sequencial, repondera casos conforme erros e pondera os votos dos modelos. Bagging combate principalmente variância; boosting pode reduzir viés, mas tende a ser mais sensível a rótulos errados e pontos difíceis.

## U05-NB06-E03

A votação pouco provavelmente ajudará porque os erros são perfeitamente correlacionados. Pode-se diversificar famílias de modelos e representações/pré-processamentos, ou usar reamostragem e subconjuntos de atributos. Toda alternativa deve ser escolhida por validação preservada e não apenas por aumentar diversidade.
