--- RESULTADOS DO LAB 01 (AULA 03) ---
Mensagem: 'Preciso urgente da segunda via da fatura'
Intenção Predita: [segunda_via]
Vocabulário Filtrado (sem stopwords): ['2a', '2a via', 'aberto', 'acordo', 'acordo pagar', 'alterar', 'alterar endereço', 'app', 'atrasada', 'atualizo', 'atualizo dados', 'boleto', 'cadastramento', 'dados', 'dados residenciais', 'débito', 'débito aberto', 'dívida', 'emitir', 'emitir segunda', 'endereço', 'endereço cadastramento', 'fatura', 'fatura atrasada', 'fazer', 'fazer um', 'gostaria', 'gostaria alterar', 'negociar', 'negociar pagamento', 'no', 'no app', 'onde', 'onde atualizo', 'pagamento', 'pagamento dívida', 'pagar', 'pagar débito', 'posso', 'posso emitir', 'residenciais', 'residenciais no', 'segunda', 'segunda via', 'um', 'um acordo', 'via', 'via boleto', 'via fatura']

Respostas das perguntas:

1. Qual o impacto da remoção de stopwords no tamanho do vocabulário do modelo?
A remoção de stopwords reduz o tamanho do vocabulário do modelo, pois elimina palavras muito comuns e pouco relevantes para a classificação, como “de”, “da”, “do”, “a”, “o”, “para” e “como”. Com isso, o modelo trabalha com menos características e consegue se concentrar nas palavras que realmente ajudam a identificar a intenção da mensagem. No exemplo, termos importantes como “segunda via”, “fatura”, “negociar”, “dívida” e “endereço” permanecem no vocabulário.

2. O que significa a configuração ngram_range=(1, 2) no TfidfVectorizer?
A configuração ngram_range=(1, 2) faz com que o TfidfVectorizer considere unigramas e bigramas.

Unigramas: palavras individuais, como fatura, dívida e endereço.
Bigramas: combinações de duas palavras consecutivas, como segunda via, fatura atrasada e negociar pagamento.
Isso é importante porque algumas combinações de palavras possuem um significado mais específico. Por exemplo, “segunda via” é muito mais representativo da intenção de solicitar uma nova fatura do que apenas a palavra “via”.

3. Como a remoção de palavras genéricas ajuda a evitar classificações incorretas?
A remoção de palavras genéricas diminui o ruído nos dados. Palavras como “como”, “meu”, “minha”, “para” e “preciso” podem aparecer em diferentes tipos de mensagens e, portanto, não ajudam muito a diferenciar as intenções.

Ao removê-las, o modelo consegue dar mais importância às palavras e expressões específicas de cada intenção. Por exemplo, “segunda via” está diretamente relacionada à intenção segunda_via, enquanto “negociar pagamento” está relacionada a negociar_divida. Dessa maneira, o modelo tem mais informações relevantes para realizar uma classificação correta.




--- RESULTADOS DO LAB 02 (AULA 03) ---

--- Relatório de Classificação ---
                     precision    recall  f1-score   support

horario_atendimento       0.50      1.00      0.67         1
        localizacao       0.00      0.00      0.00         1
    troca_devolucao       0.00      0.00      0.00         1

           accuracy                           0.33         3
          macro avg       0.17      0.33      0.22         3
       weighted avg       0.17      0.33      0.22         3

--- Matriz de Confusão ---
[[1 0 0]
 [1 0 0]
 [0 1 0]]


Respostas das perguntas:

1. O que representam as métricas Precision, Recall e F1-Score no relatório?

Precision (Precisão): indica, entre todas as mensagens que o modelo classificou como pertencentes a uma determinada classe, quantas foram realmente classificadas corretamente. Uma precisão alta significa que o modelo está cometendo poucos falsos positivos.

Recall (Revocação): indica, entre todas as mensagens que realmente pertencem a uma determinada classe, quantas foram identificadas corretamente pelo modelo. Um recall alto significa que o modelo está deixando poucas mensagens daquela classe passarem despercebidas.

F1-Score: é a média harmônica entre Precision e Recall. Ele combina as duas métricas em um único valor e é útil quando queremos avaliar o equilíbrio entre identificar corretamente uma classe e evitar classificações incorretas.

2. Como interpretar a diagonal principal da Matriz de Confusão?

A diagonal principal da matriz de confusão representa as classificações que o modelo acertou. Cada valor nessa diagonal mostra quantas mensagens de uma determinada classe foram corretamente identificadas como pertencentes àquela mesma classe.

Por exemplo, se a matriz apresentar um valor 2 na posição correspondente à classe localizacao, significa que 2 mensagens que realmente eram de localização foram classificadas corretamente como localizacao.

Os valores que aparecem fora da diagonal representam erros de classificação, ou seja, casos em que o modelo confundiu uma intenção com outra.

3. Por que a acurácia isolada pode ser enganosa quando temos classes desbalanceadas?

A acurácia representa a proporção total de previsões corretas. Porém, quando as classes possuem quantidades muito diferentes de exemplos, ela pode dar uma impressão exagerada do desempenho do modelo.

Por exemplo, se 90% das mensagens pertencerem à classe localizacao e apenas 10% às outras classes, um modelo que sempre classificasse as mensagens como localizacao poderia alcançar 90% de acurácia, mesmo sendo incapaz de identificar corretamente as outras intenções.

Por isso, em situações de classes desbalanceadas, é importante analisar também Precision, Recall e F1-Score, além da matriz de confusão, para verificar o desempenho do modelo em cada classe individualmente.




Acuracia via Pipeline: 0.00%

Previsões:
Mensagem: Como solicitar minhas ferias?
Real: solicitar_ferias
Previsto: enviar_atestado
--------------------------------------------------
Mensagem: Quero agendar meu periodo de ferias
Real: solicitar_ferias
Previsto: obter_holerite
--------------------------------------------------



Respostas das perguntas:

1. Cole o código corrigido e a acurácia obtida.

O código corrigido utiliza X = df3['mensagem'], y = df3['intencao'], realiza o train_test_split, cria o Pipeline, treina o modelo e calcula a acurácia.

A acurácia deve ser verificada no resultado exibido pelo Colab. Como o conjunto de teste possui apenas 2 mensagens, a acurácia pode variar bastante.

2. Qual é a grande vantagem de utilizar o objeto Pipeline no Scikit-Learn?

A principal vantagem é agrupar todas as etapas do processamento em um único objeto. Neste laboratório, o Pipeline combina o TfidfVectorizer, responsável por transformar os textos em números, e o LogisticRegression, responsável pela classificação.

Isso deixa o código mais organizado, facilita o treinamento e reduz a possibilidade de erros.

3. Por que o Pipeline evita que erros de pré-processamento ocorram entre treino e teste?

O Pipeline garante que o mesmo processo de pré-processamento seja aplicado de forma consistente aos dados de treino e de teste. O TfidfVectorizer aprende o vocabulário usando apenas os dados de treinamento e depois utiliza esse conhecimento para transformar os dados de teste.

Assim, evita-se que informações do conjunto de teste sejam utilizadas durante o treinamento, reduzindo o risco de vazamento de dados (data leakage) e tornando a avaliação do modelo mais confiável.


FIM.
