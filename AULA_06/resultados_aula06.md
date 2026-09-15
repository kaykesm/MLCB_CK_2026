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
