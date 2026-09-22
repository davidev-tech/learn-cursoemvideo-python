# Estruturas Condicionais e Fluxo de Execução

## Fluxo sequencial

Todo sistema é composto por algoritmos sequenciais, executados de cima para baixo e da esquerda para a direita, seguindo um passo a passo para atingir um determinado objetivo.

## Fluxo condicional

Em sistemas mais complexos, o fluxo informacional depende de **estruturas condicionais**, como:

- `if` → **se**
- `else` → **senão**

Ou seja, podemos ter fluxos de algoritmos diferentes de acordo com as condições atendidas.

### Exemplo conceitual

```text
Se determinada condição for atendida, faça isso:
    ...
    ...
    ...

Senão, faça isso:
    ...
    ...
    ...
```

## Blocos de código e indentação

Quando uma condição é atendida, o sistema entra dentro do bloco de código daquela condição.

O que está escrito dentro do bloco de condição deve estar **indentado**, ou seja, deve ter um recuo e não ficar alinhado igualmente à sua condição.

> **Observação:** em Python, a convenção é usar **4 espaços** por nível de indentação (ou uma tabulação). O importante é manter a consistência.

## Exemplo em Python

```python
idade = 18

if idade >= 18:
    print("Maior de idade")
else:
    print("Menor de idade")
```

---
