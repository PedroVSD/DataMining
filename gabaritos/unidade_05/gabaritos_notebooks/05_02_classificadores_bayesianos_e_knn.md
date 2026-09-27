# Gabarito — 05.02 Classificadores bayesianos e k-NN

## U05-NB02-V01

O Naive Bayes multiplica probabilidades condicionais como se os atributos fossem independentes dentro de cada classe. Se dois atributos estiverem muito correlacionados — por exemplo, “muitos chamados” e “texto urgente” — ambos podem refletir quase a mesma situação. Ao multiplicar os dois fatores, o método trata essa evidência redundante como duas contribuições separadas e pode produzir uma posterior excessivamente extrema.

Isso não torna necessariamente todas as classificações incorretas. Mesmo com probabilidades mal calibradas, a classe correta ainda pode receber o maior escore. A simplificação também reduz a quantidade de parâmetros que precisam ser estimados e pode funcionar bem quando os dados são limitados. O desempenho e a calibração devem ser verificados em dados separados.

**Rubrica (4 pontos):** explicar a multiplicação das evidências (1), identificar redundância (1), distinguir ordenação de classes de calibração (1) e exigir avaliação empírica (1).

## U05-NB02-E01

O caso é $\mathbf{x}=(\text{web},\text{não urgente},\text{não premium})$. As duas classes possuem probabilidade prévia $6/12=0{,}5$.

Na classe prioritária há dois casos `web`, um `não urgente` e dois `não premium`. Com Laplace:

$$
\operatorname{escore}(\text{sim})
=0{,}5\times\frac{2+1}{6+2}
\times\frac{1+1}{6+2}
\times\frac{2+1}{6+2}
=0{,}017578125.
$$

Na classe não prioritária há quatro casos `web`, cinco `não urgente` e quatro `não premium`:

$$
\operatorname{escore}(\text{não})
=0{,}5\times\frac{4+1}{6+2}
\times\frac{5+1}{6+2}
\times\frac{4+1}{6+2}
=0{,}146484375.
$$

A soma é $0{,}1640625$. Portanto:

$$
P(\text{sim}\mid\mathbf{x})
=\frac{0{,}017578125}{0{,}1640625}
=0{,}1071,
$$

$$
P(\text{não}\mid\mathbf{x})
=\frac{0{,}146484375}{0{,}1640625}
=0{,}8929.
$$

A classe prevista é **não prioritária**.

**Rubrica (8 pontos):** prévias (1), seis probabilidades condicionais com Laplace (3), dois escores (2), normalização e classe correta (2).

## U05-NB02-E02

Na escala original, os três vizinhos são:

1. E, distância 5,831;
2. D, distância 6,403;
3. C, distância 15,000.

E e D pertencem à classe `não`; C pertence à classe `sim`. A votação prevê **não**.

Depois da padronização, os três vizinhos são:

1. C, distância 0,942;
2. E, distância 1,493;
3. B, distância 1,644.

C e B pertencem à classe `sim`; E pertence à classe `não`. A votação prevê **sim**.

Na escala original, a diferença em meses domina: E e D estão a apenas cinco meses do novo cliente, apesar das diferenças de três e quatro chamados. Após a padronização, a diferença de quatro chamados de D se torna grande em relação à dispersão desse atributo, enquanto C possui exatamente quatro chamados. Assim, C passa a ser o vizinho mais próximo e B entra no conjunto, alterando a maioria.

**Rubrica (6 pontos):** vizinhos originais e classe (2), vizinhos padronizados e classe (2), explicação numérica do efeito da escala (2).

## U05-NB02-E03

Para milhares de documentos representados por ocorrências de palavras, **Naive Bayes** é uma primeira referência plausível. Ele estima a frequência das palavras por classe, treina e prevê rapidamente e costuma lidar bem com representações esparsas. Sua limitação é tratar palavras condicionalmente correlacionadas como independentes; além disso, suas probabilidades podem não estar bem calibradas.

Para justificar uma decisão individual por casos semelhantes, **k-NN** é mais natural: podem-se apresentar os documentos ou registros mais próximos que participaram da votação. Porém, essa justificativa depende da qualidade da distância. Em alta dimensionalidade, documentos podem parecer igualmente distantes, atributos irrelevantes podem dominar e a busca pode ser cara.

Respostas alternativas são aceitáveis quando relacionam explicitamente a escolha à representação, ao custo computacional e à necessidade de explicação.

**Rubrica (6 pontos):** Naive Bayes e justificativa (2), k-NN e justificativa (2), uma limitação pertinente para cada método (2).
