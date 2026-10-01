# Gabarito — 05.03 Classificadores bayesianos

## U05-NB03-V01

Naive Bayes multiplica probabilidades condicionais como se os atributos fossem independentes dentro da classe. Atributos correlacionados podem refletir a mesma evidência, que acaba contabilizada duas vezes e pode gerar posterior extrema. Isso não torna toda classificação incorreta: a classe correta ainda pode ter o maior escore, e a simplificação reduz parâmetros. Desempenho e calibração precisam ser avaliados separadamente.

## U05-NB03-E01

Para $mathbf{x}=(	ext{web},	ext{não urgente},	ext{não premium})$, ambas as prévias valem $6/12=0{,}5$.

Para $C=	ext{sim}$:

$$
P(	ext{web}mid C=	ext{sim})=rac{2+1}{6+2}=rac38,quad
P(	ext{não urgente}mid C=	ext{sim})=rac{1+1}{6+2}=rac28,
$$

$$
P(	ext{não premium}mid C=	ext{sim})=rac{2+1}{6+2}=rac38.
$$

Logo, $operatorname{escore}(C=	ext{sim})=0{,}5(3/8)(2/8)(3/8)=0{,}017578125$.

Para $C=	ext{não}$:

$$
P(	ext{web}mid C=	ext{não})=rac58,quad
P(	ext{não urgente}mid C=	ext{não})=rac68,quad
P(	ext{não premium}mid C=	ext{não})=rac58.
$$

Logo, $operatorname{escore}(C=	ext{não})=0{,}5(5/8)(6/8)(5/8)=0{,}146484375$.

Normalizando, $P(C=	ext{sim}midmathbf{x})=0{,}1071$ e $P(C=	ext{não}midmathbf{x})=0{,}8929$. A previsão é **não prioritária**.

## U05-NB03-E02

Sem suavização,

$$
P(	ext{canal=telefone}mid C=	ext{não})=rac06=0,
$$

e o produto inteiro da classe não prioritária torna-se zero, independentemente das outras evidências. Com Laplace e três categorias:

$$
P(	ext{canal=telefone}mid C=	ext{não})
=rac{0+1}{6+3}=rac19.
$$

O fator pequeno reduz o escore, mas não o anula. A mudança para três categorias deve ser aplicada coerentemente às estimativas desse atributo.

## U05-NB03-E03

Naive Bayes é uma boa referência inicial para documentos por ocorrências de palavras: estima frequências por classe, trabalha bem com matrizes esparsas e oferece treino e previsão rápidos. A hipótese de independência ignora relações entre palavras e pode contar expressões correlacionadas como evidências separadas. Além disso, a classe vencedora pode ser útil mesmo quando a posterior não é bem calibrada; avaliação de discriminação e calibração deve usar dados separados.
