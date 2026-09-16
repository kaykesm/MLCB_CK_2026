# Resultados - Aula 06

## Demo - Teste 1

**Frase:** "Quero comprar uma casa com três quartos."

- **Intenção:** comprar_imovel
- **Confiança:** 74.8%
- **Status da Decisão:** IDENTIFICADO (comprar_imovel)

## Demo - Teste 2

**Frase:** "Estou procurando um apartamento para alugar."

- **Intenção:** 2via_boleto_contrato
- **Confiança:** 39.1%
- **Status da Decisão:** UNCERTAIN (Fallback Acionado)

## Demo - Teste 3

**Frase:** "O banheiro do apartamento está com vazamento."

- **Intenção:** 2via_boleto_contrato
- **Confiança:** 39.1%
- **Status da Decisão:** UNCERTAIN (Fallback Acionado)

## Demo - Teste 4

**Frase:** "Preciso da segunda via do meu boleto."

- **Intenção:** 2via_boleto_contrato
- **Confiança:** 55.4%
- **Status da Decisão:** IDENTIFICADO (2via_boleto_contrato)

## LAB01 - Decision Tree

No LAB01, o classificador Logistic Regression foi substituído pelo Decision Tree, mantendo o mesmo pré-processamento e a vetorização por embeddings GloVe.

### Teste 1

**Frase:** "Quero comprar uma casa com três quartos."

- **Intenção:** comprar_imovel
- **Confiança:** 100.0%
- **Status da Decisão:** IDENTIFICADO (comprar_imovel)

### Teste 2

**Frase:** "Estou procurando um apartamento para alugar."

- **Intenção:** 2via_boleto_contrato
- **Confiança:** 40.0%
- **Status da Decisão:** UNCERTAIN (Fallback Acionado)

### Teste 3

**Frase:** "O banheiro do apartamento está com vazamento."

- **Intenção:** 2via_boleto_contrato
- **Confiança:** 40.0%
- **Status da Decisão:** UNCERTAIN (Fallback Acionado)

### Teste 4

**Frase:** "Preciso da segunda via do meu boleto."

- **Intenção:** 2via_boleto_contrato
- **Confiança:** 100.0%
- **Status da Decisão:** IDENTIFICADO (2via_boleto_contrato)

### Resultado

O modelo Decision Tree foi treinado e integrado com sucesso ao fluxo NLU. A interface Gradio continuou funcionando e realizando a classificação das intenções. Nos testes realizados, algumas frases foram classificadas com alta confiança, enquanto outras acionaram o fallback por apresentarem confiança abaixo do limiar definido.


## LAB02 - Alteração do Limiar de Confiança

No LAB02, o limiar de confiança foi alterado de 50% para 65%. A mensagem visual também foi atualizada para informar explicitamente o percentual de corte utilizado pelo modelo.

### Teste 1

**Frase:** "Quero comprar uma casa com três quartos."

- **Intenção:** comprar_imovel
- **Confiança:** 100.0%
- **Status da Decisão:** IDENTIFICADO (comprar_imovel) - Confiança mínima: 65%

### Teste 2

**Frase:** "Estou procurando um apartamento para alugar."

- **Intenção:** 2via_boleto_contrato
- **Confiança:** 40.0%
- **Status da Decisão:** UNCERTAIN (Fallback Acionado) - Abaixo do corte de 65%

### Teste 3

**Frase:** "Preciso da segunda via do meu boleto."

- **Intenção:** 2via_boleto_contrato
- **Confiança:** 100.0%
- **Status da Decisão:** IDENTIFICADO (2via_boleto_contrato) - Confiança mínima: 65%

### Resultado

O novo limiar de confiança de 65% foi aplicado com sucesso. Nos testes, classificações com confiança igual ou superior ao limiar foram aceitas, enquanto a classificação com 40.0% de confiança acionou o fallback. A interface também passou a exibir explicitamente o corte de 65% no status da decisão.
