# Laço de Repetição `while not`

## Definição

- `while not` pode ser traduzido como **“enquanto não”**.
- O laço continua executando **enquanto a condição for falsa** (ou seja, enquanto ela **não** for atendida).
- Em outras palavras: o loop para quando a condição se torna verdadeira.

> `not` é um operador lógico de negação. Portanto, `while not condição` é equivalente a `while condição == False`.

## Sintaxe

```python
while not condição:
    # bloco de código
```

## Exemplo

```python
while not condição:
    if cond1:
        ...
    if cond2:
        ...
    if cond3:
        ...
    print("Pega")
```

### Explicação

- Enquanto `condição` for falsa, o bloco dentro do `while` será repetido.
- Dentro do laço, são feitas três verificações condicionais (`if`).
- O `print("Pega")` está **dentro** do `while`, então será executado **a cada iteração**, após as verificações.
- Quando `condição` se tornar verdadeira, o laço é encerrado e o programa segue para depois do `while`.

## Observações

- A indentação é obrigatória em Python. O bloco do `while` deve estar recuado (geralmente 4 espaços).
- Cuidado com loops infinitos: se a condição nunca se tornar verdadeira, o `while not` continuará para sempre.
- O exemplo acima usa `if` sem condições reais, apenas para ilustrar a estrutura.

---
