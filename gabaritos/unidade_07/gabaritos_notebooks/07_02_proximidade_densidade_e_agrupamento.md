# Gabarito — 07.02 Proximidade, densidade e agrupamento

## U07-NB02-V01

LOF avalia a razão entre a densidade dos vizinhos e a densidade do ponto. Um ponto na borda de uma região muito densa pode ter densidade bem menor que seus vizinhos e receber LOF alto mesmo com distância absoluta moderada. Um ponto em região esparsa pode estar mais distante em termos absolutos, mas ter densidade semelhante à vizinhança e LOF próximo de 1.

**Rubrica (4 pontos):** comparação local (2), grupo denso (1), região esparsa (1).

## U07-NB02-E01

Para $k=2$, o vizinho mais distante entre os dois primeiros está a 0,7, então $s_2(P)=0{,}7$. Para $k=4$, o quarto vizinho está a 1,6, então $s_4(P)=1{,}6$. O aumento não prova que P mudou; mede isolamento em uma escala de vizinhança maior.

**Rubrica (4 pontos):** dois resultados (2), relação com $k$ (1), interpretação (1).

## U07-NB02-E02

Uma solução reproduzível é ajustar `LocalOutlierFactor(n_neighbors=k)` para cada valor e ordenar `-negative_outlier_factor_`.

Nos dados do notebook, os índices entre os dez primeiros são:

| Vizinhos | Índices priorizados |
|---:|---|
| 5 | 183, 302, 304, 305, 307, 308, 313, 314, 315, 317 |
| 15 | 218, 302, 304, 305, 307, 308, 312, 313, 314, 317 |
| 40 | 218, 302, 304, 305, 307, 308, 312, 313, 314, 317 |

Os índices 302, 304, 305, 307, 308, 313, 314 e 317 aparecem nos três rankings e formam o núcleo estável. Os casos 183 e 315 são sensíveis à vizinhança pequena; 218 e 312 entram em escalas maiores. Estabilidade aumenta confiança na raridade, não confirma a causa.

**Rubrica (8 pontos):** três ajustes (2), rankings (2), interseção (2), interpretação (2).

## U07-NB02-E03

Mantendo `min_samples=8`, os resultados são:

| `eps` | Grupos | Alertas | Precisão | Revocação |
|---:|---:|---:|---:|---:|
| 0,20 | 2 | 65 | 0,262 | 0,944 |
| 0,28 | 2 | 34 | 0,412 | 0,778 |
| 0,40 | 2 | 13 | 0,846 | 0,611 |

Ao aumentar `eps`, mais pontos tornam-se alcançáveis: caem alertas e revocação, enquanto a precisão aumenta neste exemplo. Escolher `eps` pelo melhor resultado nos rótulos reservados adapta o método ao teste e produz estimativa otimista. Parâmetros devem ser definidos em desenvolvimento, por critérios operacionais ou validação separada, e avaliados em período não usado na escolha.

**Rubrica (8 pontos):** tabela (4), efeito do parâmetro (2), vazamento/otimismo (2).

## U07-NB02-E04

Um protocolo possível mantém dez vagas semanais, define o ranking antes de observar desfechos e registra todos os casos investigados. Uma pequena amostra aleatória de não alertas deve ser revisada periodicamente para estimar casos perdidos, respeitando custo e autorização. Avaliam-se precisão@10, impacto evitado, tempo de revisão, taxa de reversão e desempenho por subgrupo; revocação deve ser tratada como incerta quando o universo não está rotulado. A validação deve ser temporal e o limiar não pode ser reajustado no mesmo período usado para reportar desempenho.

**Rubrica (8 pontos):** orçamento e ranking (1), registro (1), amostra de não alertas (2), métricas e incerteza (2), validação temporal (1), subgrupos (1).

## U07-NB02-E05

Exemplo de ficha, sem consultar `anomalia_referencia`:

| Campo | Conteúdo esperado |
|---|---|
| identificador | `OBS-314`, por exemplo |
| razão observável | recebeu quatro votos; registrar escores e regras acionadas |
| contexto necessário | origem, horário, unidade, histórico e eventos relacionados |
| decisão provisória | investigar, liberar, corrigir erro confirmado ou manter inconclusivo |
| evidência | documentos, logs e responsável pela revisão |
| revisão | data, revisor, justificativa e possibilidade de contestação |

O procedimento deve ser repetido para os cinco primeiros casos. “É anomalia porque o rótulo vale 1” é inválido: esse rótulo existe apenas para a avaliação sintética e não estaria disponível na operação.

**Rubrica (7 pontos):** cinco casos (1), razão do alerta (1), contexto (1), decisão (1), evidência/rastreabilidade (1), revisão (1), não uso do rótulo oculto (1).
