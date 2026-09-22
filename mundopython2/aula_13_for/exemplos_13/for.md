# Estrutura de Repetição `for`

## Definição

- `for` é um laço de repetição com **variável de controle**.
- Repete uma ação um número determinado de vezes, de acordo com um intervalo/índice.
- Pode ser entendido como “repita para cada item do intervalo”.

## Sintaxe básica

```python
for variavel in range(inicio, fim):
    # bloco de código
```

- `range(inicio, fim)` gera uma sequência que vai de `inicio` até `fim - 1`.
- O `fim` **não** é incluído.

---

## Exemplo 1 — Repetição simples

```python
for c in range(1, 10):
    # ação
```

**Observação:** o intervalo vai de **1 a 9** (o 10 não é incluído). Portanto, a ação será repetida 9 vezes.

---

## Exemplo 2 — Repetição com condicional

Código corrigido:

```python
for c in range(0, 3):
    if moeda == True:
        print("Pegar moeda.")
    print("Passo")
    print("Pula")
print("passo")
print("Pega")
```

### Explicação

- O loop executa **3 vezes** (`c = 0, 1, 2`).
- Dentro do loop:
  - Verifica se `moeda` é `True`. Se for, imprime `"Pegar moeda."`.
  - Independentemente da condição, imprime `"Passo"` e `"Pula"`.
- Após o loop (fora dele), imprime `"passo"` e `"Pega"` **uma única vez**.

> **Dica:** `if moeda == True:` pode ser simplificado para `if moeda:`.

---

## Observações importantes

- A indentação é obrigatória em Python. O bloco do `for` deve estar recuado (geralmente 4 espaços).
- O `range` pode ter 1, 2 ou 3 argumentos:
  - `range(fim)` → de 0 até `fim - 1`.
  - `range(inicio, fim)` → de `inicio` até `fim - 1`.
  - `range(inicio, fim, passo)` → de `inicio` até `fim - 1`, pulando de `passo` em `passo`.
- `for` também pode percorrer strings, listas, tuplas, dicionários, etc.

---
