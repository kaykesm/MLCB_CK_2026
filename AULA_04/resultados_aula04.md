
Relatório de Avaliação NLU - SAC Móveis Residenciais
1. Tabela Comparativa de Métricas (Dados de Teste)
Modelo	Acurácia Geral	F1-Score (Weighted)	Principais Erros na Matriz
KNN (K=3)	100%	1,00	Não apresentou erros na matriz de confusão.
Decision Tree	80%	0,80	Teve alguns erros entre as classes, principalmente envolvendo vendas, reclamações e logística.

O KNN teve um resultado melhor no conjunto de teste. Ele acertou todas as 30 frases utilizadas para teste, ficando com 100% de acurácia.

A Decision Tree acertou 24 das 30 frases, ficando com 80% de acurácia. Pela matriz de confusão, foi possível perceber que algumas frases acabaram sendo classificadas em outras intenções.

2. Análise dos Testes de Entrada (input())
Comportamento do KNN (10 testes)

Nos 10 testes realizados, o KNN conseguiu identificar corretamente a maioria das frases.

Alguns exemplos foram:

"Preciso do manual para montar meu armário" → suporte
"Quero devolver uma mesa que veio com defeito" → trocas_devolucoes
"Quero reclamar do atendimento da loja" → reclamacoes
"Onde está o meu pedido?" → logistica_entregas
"Qual o preço de um colchão queen size?" → vendas

O fallback foi acionado em dois testes. Isso aconteceu quando a confiança ficou abaixo de 50%. Foram eles:

"Veio faltando parafuso no meu móvel" → 33,33%
"Hoje o céu está muito bonito" → 33,33%

Também aconteceram alguns erros. Por exemplo, "Quero um sofá retrátil" foi classificado como reclamacoes, mesmo parecendo mais relacionado a vendas. A frase "Como faço para rastrear minha entrega?" também foi classificada como reclamacoes.

Então, mesmo tendo acertado 100% no conjunto de teste, o KNN teve alguns erros quando recebeu frases diferentes das que estavam no dataset.

Comportamento da Decision Tree (8 testes)
A Decision Tree apresentou alguns erros nos testes manuais.

Por exemplo:

"Quero comprar um guarda roupa" → foi classificado como trocas_devolucoes, mas seria esperado vendas.
"Preciso de ajuda para montar minha estante" → foi classificado como reclamacoes, mas seria esperado suporte.
"Qual o preço do sofá retrátil?" → foi classificado como logistica_entregas, mas seria esperado vendas.
"Minha mesa veio arranhada e quero trocar" → foi classificado como reclamacoes, mas seria esperado trocas_devolucoes.
"Preciso saber quando minha entrega vai chegar" → foi classificado como reclamacoes, mas seria esperado logistica_entregas.

Uma coisa que chamou atenção foi que todas as respostas apresentaram 100% de confiança, mesmo algumas estando erradas. Por causa disso, o fallback não foi utilizado em nenhum dos 8 testes.

3. Veredito Final

Melhor modelo para este projeto: KNN (K=3)

Justificativa técnica: Comparando os dois modelos, o KNN apresentou o melhor resultado. No conjunto de teste, ele conseguiu 100% de acurácia e F1-Score de 1,00, enquanto a Decision Tree conseguiu 80% de acurácia e F1-Score de 0,80.

Nos testes digitados, o KNN também conseguiu identificar várias frases corretamente e utilizou o fallback quando a confiança ficou abaixo de 50%. Porém, ele também apresentou alguns erros em frases novas.

A Decision Tree teve mais dificuldades para classificar algumas frases. Além disso, apresentou 100% de confiança em algumas respostas que estavam erradas.

Por esses resultados, considero o KNN (K=3) o melhor modelo entre os dois para este projeto. Mesmo assim, acredito que seria interessante aumentar a quantidade de frases do dataset para melhorar os resultados dos modelos.
