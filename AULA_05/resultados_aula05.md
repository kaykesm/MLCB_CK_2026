Questão 1 — Qual modelo apresentou melhor desempenho?
A Regressão Logística apresentou melhor desempenho em todas as métricas avaliadas. Ela obteve 75,00% de Accuracy, 79,17% de Precision, 75,00% de Recall e 75,36% de F1-Score. Já o KNN apresentou 56,25% de Accuracy, 52,50% de Precision, 56,25% de Recall e 52,14% de F1-Score.

Questão 2 — Por que os resultados podem ser diferentes mesmo utilizando os mesmos embeddings?
Os resultados podem ser diferentes porque cada algoritmo utiliza uma estratégia diferente para realizar a classificação. A Regressão Logística aprende uma relação entre os vetores e as classes, enquanto o KNN classifica uma nova mensagem com base na proximidade dela em relação aos exemplos de treinamento. Portanto, mesmo utilizando os mesmos embeddings, os modelos podem interpretar e utilizar essas representações de maneiras diferentes.

Questão 3 — O KNN utiliza distância. Por que a qualidade dos embeddings é particularmente importante para esse algoritmo?
A qualidade dos embeddings é especialmente importante para o KNN porque o algoritmo utiliza a distância entre os vetores para encontrar os exemplos mais semelhantes. Se mensagens semanticamente diferentes estiverem próximas no espaço vetorial, o KNN poderá classificá-las incorretamente. Embeddings de melhor qualidade tendem a organizar mensagens semelhantes em regiões mais próximas e mensagens diferentes em regiões mais separadas.

Questão 4 — Se o sistema tivesse 100 mil mensagens e centenas de intenções, você escolheria KNN? Justifique.
Eu não escolheria o KNN para esse cenário. O KNN precisa comparar uma nova mensagem com os exemplos armazenados para encontrar os vizinhos mais próximos. Com 100 mil mensagens e centenas de intenções, isso pode aumentar significativamente o custo computacional e o tempo de classificação. Além disso, neste experimento o KNN apresentou desempenho inferior à Regressão Logística.

Questão 5 — Qual modelo você escolheria para colocar em produção neste cenário?
Eu escolheria a Regressão Logística para colocar em produção neste cenário. Ela apresentou desempenho superior em todas as métricas avaliadas e possui uma abordagem mais adequada para classificação baseada em vetores, além de ser mais eficiente para lidar com um volume maior de mensagens do que o KNN. O uso do fallback também permite encaminhar mensagens cuja confiança esteja abaixo do limiar definido para atendimento humano.
