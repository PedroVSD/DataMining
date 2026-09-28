# Gabarito — 05.05 Bagging e florestas aleatórias

## U05-NB05-V01

A aparece uma vez, B duas, C nenhuma e D uma. C é OOB. A amostra tem tamanho quatro porque foram realizados quatro sorteios com reposição; repetição reduz a quantidade de objetos distintos, não a quantidade de sorteios.

## U05-NB05-E01

O voto majoritário é classe 1, por três votos contra dois. Se as árvores errassem sempre nos mesmos casos, o voto não corrigiria esses erros. Alta correlação reduz o benefício da agregação porque não há erros diferentes para se compensarem.

## U05-NB05-E02

Ambos treinam várias árvores sobre amostras bootstrap e agregam previsões. A floresta também sorteia atributos candidatos em cada divisão, o que tende a reduzir correlação entre árvores. max_features pequeno demais pode produzir árvores fracas e aumentar viés, anulando o ganho de diversidade.

## U05-NB05-E03

O ganho de 0,02 deve ser confrontado com incerteza amostral, estabilidade em reamostragens, custo operacional e necessidade de explicação. O acordo entre OOB 0,85 e teste 0,86 é favorável, mas não prova superioridade futura. Bagging é justificável quando o ganho e a estabilidade compensam o custo; uma árvore pode ser preferível se latência, transparência ou simplicidade predominarem.
