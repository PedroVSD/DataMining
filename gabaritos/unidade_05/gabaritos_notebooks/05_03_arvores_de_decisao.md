# Gabarito — 05.03 Árvores de decisão

## U05-NB03-V01

Um identificador único permite criar divisões que isolam pessoas ou registros. Cada folha pode ficar pura porque passa a conter um único exemplo, levando a desempenho perfeito ou quase perfeito no treino.

Entretanto, essa divisão memoriza a identidade, não uma regularidade reutilizável. Um identificador novo não possui histórico que indique a classe e seus valores geralmente não têm significado de proximidade ou ordem. O atributo pode ainda favorecer divisões artificiais por ter alta cardinalidade. Por isso, identificadores técnicos devem ser excluídos antes do treinamento, salvo quando tenham uma função analítica explicitamente justificada.

**Rubrica (4 pontos):** explicar isolamento dos registros (1), diferenciar memorização de padrão (1), discutir novos valores (1) e recomendar remoção ou justificativa (1).

## U05-NB03-E01

Na raiz existem sete permanências e cinco cancelamentos:

$$
Gini(D)=1-\left(\frac{7}{12}\right)^2
-\left(\frac{5}{12}\right)^2
=\frac{35}{72}=0{,}4861.
$$

No grupo esquerdo, com atrasos menores ou iguais a 1, há seis permanências e um cancelamento:

$$
Gini(D_E)=1-\left(\frac{6}{7}\right)^2
-\left(\frac{1}{7}\right)^2
=\frac{12}{49}=0{,}2449.
$$

No grupo direito, com atrasos maiores que 1, há uma permanência e quatro cancelamentos:

$$
Gini(D_D)=1-\left(\frac{1}{5}\right)^2
-\left(\frac{4}{5}\right)^2
=\frac{8}{25}=0{,}3200.
$$

A impureza ponderada é

$$
Gini_{\text{divisão}}
=\frac{7}{12}(0{,}2449)+\frac{5}{12}(0{,}3200)
=0{,}2762.
$$

Logo, a redução é

$$
\Delta Gini=0{,}4861-0{,}2762=0{,}2099.
$$

As frações $7/12$ e $5/12$ ponderam o tamanho dos grupos; as frações internas representam a distribuição das classes dentro de cada grupo. A redução positiva mostra que a divisão produz subconjuntos mais homogêneos que a raiz.

**Rubrica (8 pontos):** Gini da raiz (2), Gini dos grupos (2), ponderação (2), redução e interpretação (2).

## U05-NB03-E02

O **perfil 1** possui um chamado de suporte. Na raiz, segue o ramo `chamados_suporte <= 1,5` e chega diretamente à folha com cinco permanências e nenhum cancelamento. A classe prevista é **permaneceu** e a proporção de cancelamento na folha é $0/5=0$.

O **perfil 2** possui quatro chamados, seguindo `chamados_suporte > 1,5`. Em seguida, como possui três atrasos, segue `atrasos_pagamento > 0,5` e chega à folha com nenhum caso de permanência e cinco cancelamentos. A classe prevista é **cancelou** e a proporção exibida é $5/5=1$.

Probabilidades 0 e 1 resultam da pureza das folhas nesta amostra muito pequena. Elas não garantem que todo novo cliente com o mesmo caminho terá o mesmo resultado. Ruído, mudança da população e poucos exemplos podem produzir contraexemplos.

**Rubrica (6 pontos):** caminho do perfil 1 (2), caminho do perfil 2 (2), classes, probabilidades e ressalva amostral (2).

## U05-NB03-E03

Uma escolha defensável é a profundidade 5:

- treino: acurácia 0,868 e F1 0,471;
- teste: acurácia 0,808 e F1 0,179;
- 24 folhas;
- diferença de acurácia treino–teste de 0,060.

Ela obtém a maior acurácia de teste entre as profundidades avaliadas e é muito menor que as árvores de profundidade 8 ou sem limite. Porém, seu F1 de teste ainda é baixo e 24 folhas podem dificultar comunicação.

Se a prioridade for uma explicação realmente compacta, profundidade 3 também é defensável: possui oito folhas, acurácia de teste 0,792 e diferença treino–teste de 0,040. A contrapartida é F1 de apenas 0,074, indicando baixa capacidade de encontrar cancelamentos.

Profundidade 8 e ausência de limite mostram sobreajuste: as acurácias de treino sobem para 0,930 e 1,000, enquanto as de teste caem para 0,754 e 0,750; as árvores chegam a 62 e 108 folhas. Assim, nenhuma alternativa deve ser implantada apenas por esta tabela. A escolha final depende do custo dos erros, validação e necessidade de explicação.

**Rubrica (8 pontos):** usar resultados de treino e teste (2), discutir F1 e acurácia (2), considerar folhas e diferença de desempenho (2), justificar a escolha sem universalizá-la (2).
