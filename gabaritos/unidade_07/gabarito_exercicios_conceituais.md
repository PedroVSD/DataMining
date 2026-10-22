# Unidade VII — Gabarito dos exercícios conceituais

## U07-C01

Uma anomalia **global** destoa do conjunto inteiro, como 95 °C em um equipamento que opera perto de 50 °C; a referência é a distribuição geral. Uma anomalia **contextual** destoa apenas sob uma condição, como 8 kW de madrugada quando esse consumo é comum à tarde; a referência é a distribuição condicionada ao horário. Uma anomalia **coletiva** é um conjunto ou sequência cujo padrão é incomum, ainda que cada elemento isolado seja plausível, como pequenas oscilações repetidas antes de uma falha; a referência inclui ordem e dependência entre observações.

**Elementos essenciais:** três definições, três exemplos e referência explícita.

## U07-C02

O escore mede desvio de uma referência, não mecanismo causal. Um mesmo valor pode ser produzido por causas distintas.

- erro de digitação: consultar registro de origem e regras de validade; comparar com documento ou sistema transacional;
- evento legítimo: verificar histórico, calendário e operação; confirmar com responsável ou fonte independente;
- fraude: examinar sequência, dispositivo, vínculos e autorização; encaminhar para investigação segundo procedimento e garantias aplicáveis.

Concordância entre detectores aumenta evidência de excepcionalidade, não prova uma causa.

## U07-C03

Misturar populações com escalas e processos diferentes pode fazer empresas parecerem anômalas apenas porque gastam mais. Uma unidade defensável seria “conta em uma semana”, separando ou condicionando por tipo de cliente. Contextos possíveis incluem porte ou tipo de conta, setor, canal, horário, país e histórico individual. A escolha deve preceder a inspeção dos resultados e corresponder à finalidade.

## U07-C04

Para os seis valores, $\bar{x}=10$. A soma dos quadrados dos desvios é 10, logo

$$s=\sqrt{10/(6-1)}=\sqrt{2}=1{,}414.$$

Para 12:

$$z=(12-10)/1{,}414=1{,}414.$$

O valor está 1,414 desvios-padrão acima da média. Isso descreve posição relativa; não basta para confirmar anomalia sem distribuição, contexto e custo dos erros.

## U07-C05

Com interpolação linear, $Q_1=3$, $Q_3=5{,}5$ e $IQR=2{,}5$. As cercas são

$$L=3-1{,}5(2{,}5)=-0{,}75,$$

$$U=5{,}5+1{,}5(2{,}5)=9{,}25.$$

Somente 20 está fora das cercas.

## U07-C06

A mediana é 4. Os desvios absolutos são 2, 1, 1, 0, 1, 2 e 16; portanto, $MAD=1$. Para 20:

$$z^{(r)}=0{,}6745(20-4)/1=10{,}792.$$

O valor tem grande afastamento robusto. O resultado é evidência de raridade, não diagnóstico da causa.

## U07-C07

- **Escore-z:** parte de média e desvio-padrão, é sensível a extremos e adequado como ponto de partida para distribuição aproximadamente simétrica, unimodal e estável.
- **IQR:** usa quartis, resiste melhor a extremos e é útil para exploração univariada sem exigir normalidade; cercas simétricas podem sinalizar em excesso a cauda de distribuições assimétricas.
- **MAD:** usa mediana e desvios absolutos, possui boa robustez e permite escore por observação; com muitos empates pode resultar em zero e tornar a divisão indefinida.

Nenhum método resolve sozinho mistura de populações, dependência temporal ou contexto ausente.

## U07-C08

Três mudanças defensáveis são: aplicar `log1p` quando a escala multiplicativa fizer sentido, reduzindo assimetria sem apagar a ordem; estimar limites condicionais por população, região ou período, evitando misturar processos; e modelar quantis ou usar cercas assimétricas calibradas em dados históricos, representando melhor as duas caudas. Também se deve validar os valores altos com conhecimento do domínio e avaliar taxas de falso alerta. Transformações precisam ser documentadas e não tornam valores automaticamente inválidos.

## U07-C09

$s_2(P)=0{,}3$ e $s_5(P)=1{,}4$. Com $k=2$, o escore descreve a vizinhança imediata e é sensível a pares ou pequenos bolsões. Com $k=5$, incorpora uma escala espacial maior. Um ponto pode deixar de parecer isolado ou passar a parecer isolado conforme $k$; por isso, devem-se justificar a escala relevante e examinar estabilidade em valores próximos.

## U07-C10

A distância alcançável usa $\max\{d_k(o),d(p,o)\}$ para reduzir instabilidade causada por distâncias muito pequenas dentro de uma região densa. A densidade local alcançável é o inverso da média dessas distâncias: distâncias pequenas implicam densidade alta. O LOF calcula a média das razões entre densidade dos vizinhos e densidade do ponto. LOF próximo de 1 significa densidade comparável; muito acima de 1 indica que o ponto é menos denso que sua vizinhança. Limiar e $k$ continuam dependentes do problema.

## U07-C11

A distância ao k-ésimo vizinho é absoluta: pontos do grupo esparso tendem a ter distâncias grandes e podem dominar o ranking mesmo sendo típicos de sua região. LOF é relativo: compara cada ponto com vizinhos e pode considerar normais pontos inseridos na região esparsa, sinalizando uma quebra local perto do grupo compacto. Os métodos discordam por avaliarem isolamento global e desvio local, respectivamente.

## U07-C12

Aumentar `eps` amplia vizinhanças, normalmente incorpora mais pontos às regiões densas e reduz ruído, mas pode unir estruturas. Aumentar `min_samples` exige maior densidade, normalmente reduz pontos centrais e aumenta ruído. Um ponto `-1` apenas não foi alcançado por regiões densas sob a escala, distância e parâmetros escolhidos; pode ser evento legítimo raro, borda, região esparsa, erro ou outro fenômeno.

## U07-C13

Na estratégia de **grupo pequeno**, grupos abaixo de certo tamanho recebem prioridade; ela pode confundir uma subpopulação rara legítima com anomalia. Na estratégia de **distância ao representante**, pontos muito distantes do centroide ou medoide do próprio grupo são sinalizados; ela pode falhar em grupos alongados ou não convexos e depende da escala. Ambas também herdam erros do agrupamento e exigem análise de estabilidade.

## U07-C14

Precisão $=8/20=0{,}4$. Revocação $=8/25=0{,}32$. Assim,

$$F1=\frac{2(0{,}4)(0{,}32)}{0{,}4+0{,}32}\approx0{,}356.$$

Se somente alertas são investigados, as anomalias fora da lista permanecem sem confirmação. O total 25 pode estar subestimado e a amostra rotulada depende do próprio detector, produzindo viés de verificação. Uma amostra aleatória fora dos alertas ajuda a estimar falhas, se ética e operacionalmente possível.

## U07-C15

O critério deve incorporar valor ou custo esperado. Por exemplo, estimar para cada método `ganho dos casos confirmados − custo de investigação − custo dos casos perdidos`, usando faixas de incerteza. Também se pode reservar parte das dez vagas a alto impacto e parte a alta probabilidade, impondo limites de risco e equidade. O segundo método pode ser preferível se o valor esperado e a cobertura de casos críticos compensarem sua menor precisão.

## U07-C16

Um protocolo completo deve: definir finalidade e ações permitidas; delimitar população, período e unidade; selecionar atributos, escala e contexto; preservar dados brutos e rastrear versões; separar períodos de desenvolvimento e avaliação; comparar referências e métodos; escolher limiar segundo custo e orçamento; avaliar precisão, revocação, estabilidade e subgrupos; investigar com revisão humana e evidência adicional; proibir sanção automática; permitir correção e contestação; registrar decisão; monitorar distribuição, taxa de alerta, confirmações, impacto e mudança; e definir quando recalibrar ou suspender o sistema.

## U07-C17

Exemplo: em uma população, $x$ e $y$ têm distribuições aproximadamente normais e correlação positiva. O ponto $(1{,}2,-1{,}2)$ não é extremo em nenhuma marginal, mas fica longe da faixa diagonal ocupada pelas combinações usuais. Uma análise separada de $x$ e $y$ pode não sinalizá-lo; a representação conjunta revela que ele viola a relação entre os atributos.

Sem padronização, a variável de maior amplitude pode dominar distâncias. A correlação define direções de variação comum, tornando mais relevante o afastamento perpendicular à relação. Uma projeção pode revelar o padrão quando preserva essa direção ou escondê-lo quando comprime justamente a dimensão do desvio. A conclusão deve ser verificada no espaço original.

## U07-C18 — Desafio opcional

Com muitas dimensões, distâncias podem se concentrar: o vizinho mais próximo e o mais distante ficam relativamente parecidos. Rankings k-NN tornam-se instáveis e as razões de densidade do LOF perdem contraste; atributos irrelevantes também dominam a medida.

Um experimento deve separar períodos ou treino/teste, ajustar padronização e redução somente no treino e comparar dimensões retidas. Para cada variante, medir estabilidade dos rankings, precisão@orçamento, revocação em rótulos disponíveis e desempenho em subtipos raros. Inspecionar casos perdidos é indispensável: maior precisão média não compensa apagar a anomalia relevante. A redução e seus parâmetros devem ser versionados.
