# Gabarito — 06.04 Modelos de mistura Gaussiana

## U06-NB04-V01

A atribuição rígida escolhe o componente 0, pois 0,52 é a maior responsabilidade. Entretanto, 0,45 para o componente 1 é quase tão alto; comunicar apenas “grupo 0” faz o objeto parecer tão seguro quanto outro com responsabilidades `[0.99, 0.01, 0.00]`.

O vetor completo mostra que o objeto está próximo de uma região de sobreposição ou que o modelo tem pouca evidência para diferenciá-lo. As probabilidades continuam condicionadas ao número de componentes, às Gaussianas, aos atributos e aos dados ajustados.

**Critério de correção:** indicar componente 0 e explicar quantitativamente a ambiguidade entre 0 e 1.

## U06-NB04-E01

As contribuições não normalizadas são:

$$
\pi_1p(x\mid C_1)=0{,}6\cdot0{,}2=0{,}12,
$$

$$
\pi_2p(x\mid C_2)=0{,}4\cdot0{,}5=0{,}20.
$$

A soma é 0,32. Logo:

$$P(C_1\mid x)=\frac{0{,}12}{0{,}32}=0{,}375,$$

$$P(C_2\mid x)=\frac{0{,}20}{0{,}32}=0{,}625.$$

O componente 2 recebe a atribuição rígida, embora permaneça incerteza de 37,5% atribuída ao primeiro segundo o modelo.

**Critério de correção:** incluir os pesos da mistura, normalizar pela soma 0,32 e obter probabilidades que somem 1.

## U06-NB04-E02

Na etapa E, os pesos, médias e covariâncias atuais são usados para calcular, para cada objeto, uma responsabilidade por componente. Na etapa M, essas responsabilidades funcionam como pesos fracionários:

- o peso $\pi_j$ é atualizado pela fração efetiva de massa atribuída ao componente;
- a média $\mu_j$ é a média ponderada pelas responsabilidades;
- a covariância $\Sigma_j$ é a dispersão ponderada em torno da nova média.

As etapas se repetem, aumentando ou mantendo a log-verossimilhança, até convergência. A função possui ótimos locais e componentes podem começar em regiões inadequadas ou colapsar. Múltiplas inicializações permitem comparar soluções e conservar a de maior verossimilhança. Isso não elimina a necessidade de avaliar estabilidade ou significado.

**Critério de correção:** relacionar E às responsabilidades, M aos três conjuntos de parâmetros e justificar inicializações por ótimos locais.

## U06-NB04-E03

- `spherical`: uma variância por componente; contornos circulares ou esféricos;
- `diag`: uma variância por dimensão e componente, sem covariâncias; elipses alinhadas aos eixos;
- `tied`: uma matriz completa compartilhada; todos os componentes têm a mesma orientação e forma;
- `full`: uma matriz completa por componente; cada um possui orientação e dispersão próprias.

Para dois grupos elípticos com orientações diferentes, `full` é a escolha inicial mais flexível. Seu custo é estimar mais parâmetros, exigir mais dados, aumentar processamento e risco de sobreajuste ou covariância quase singular. A escolha deve ser comparada a modelos mais simples por BIC/AIC, estabilidade e diagnóstico.

**Critério de correção:** caracterizar os quatro tipos e ligar `full` simultaneamente à flexibilidade e ao custo estatístico.

## U06-NB04-E04

O menor BIC é 910, correspondente a **três componentes**. O aumento posterior indica que a melhora de ajuste não compensa a penalização adicional segundo o BIC.

Antes de aceitar a solução, deve-se ao menos:

1. repetir o ajuste com sementes e amostras diferentes;
2. comparar AIC, tipos de covariância e números próximos de componentes;
3. inspecionar tamanhos, covariâncias, responsabilidades e objetos ambíguos;
4. verificar se Gaussianas representam razoavelmente os dados e se não há componente degenerado;
5. interpretar os componentes no domínio e avaliar sua utilidade e consequências.

**Critério de correção:** selecionar três e apresentar três verificações que não sejam apenas repetir o mesmo BIC.

## U06-NB04-E05

O GMM com covariâncias completas é uma escolha inicial para representar elipses com orientações distintas e preservar responsabilidades nas regiões sobrepostas. O k-means fornece uma referência simples, mas impõe atribuição rígida e favorece regiões aproximadamente esféricas. O DBSCAN pode investigar os isolados e formas densamente conectadas, mas pode ter dificuldade com sobreposição e densidades diferentes.

Uma análise defensável seria:

1. preparar atributos e escala sem usar rótulos externos;
2. ajustar GMMs com diferentes componentes e covariâncias, várias inicializações e regularização;
3. comparar BIC/AIC, estabilidade, diagnóstico visual e responsabilidades;
4. relatar atribuições rígidas apenas junto à maior responsabilidade e aos casos ambíguos;
5. executar DBSCAN ou análise de densidade como diagnóstico complementar dos isolados;
6. investigar cada isolado antes de chamá-lo de erro ou removê-lo;
7. comparar com k-means para mostrar o efeito da hipótese geométrica;
8. validar perfis e finalidade no domínio.

GMM também pode ser sensível a isolados e criar um componente para explicá-los; portanto, não substitui investigação de qualidade e procedência dos dados.

**Critério de correção:** escolher GMM pela sobreposição e elipses, atribuir papéis coerentes aos outros métodos e preservar explicitamente a incerteza.

