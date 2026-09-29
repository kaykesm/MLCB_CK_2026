# Resultados - Aula 07

## LAB 1 - Regressão Logística

**Teste:**
"Quero fazer uma transferencia de 500 reais"

**Output:**
{'status': 'FALLBACK'}

**Teste da extração de valor:**
500.0

## LAB 2 - Naive Bayes

**Teste:**
"Urgente: servidor caiu no protocolo INC-9982"

**Output:**
{'status': 'FALLBACK'}

**Teste da extração de protocolo:**
INC-9982

## LAB 3 - Decision Tree

**Teste:**
"Quero rastrear o pedido BR987654321"

**Output:**
{'status': 'SUCESSO', 'intencao': np.str_('rastrear_pedido'), 'confianca': np.float64(1.0), 'codigo_rastreio': 'BR987654321'}

**Teste da extração do código de rastreio:**
BR987654321
