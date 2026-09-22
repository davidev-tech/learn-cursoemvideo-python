# Interrupção de Laço: `break`

## Definição

- `break` é o comando que **interrompe um loop**, saindo dele imediatamente.
- Funciona tanto em `for` quanto em `while`.
- Quando executado, o fluxo do programa continua **após o laço**.

## Exemplo

```python
while True:
    if cond1:
        ...
    if cond2:
        ...
    if cond3:
        ...
    if cond4:
        ...
        break
    print("Pega")
```

### Explicação

- `while True` é um **loop infinito**: ele continuará repetindo até encontrar um `break`.
- Dentro do laço, temos várias verificações condicionais (`if`).
- O `break` está dentro de um dos `if`. Se aquela condição for verdadeira, o laço é encerrado.
- O `print("Pega")` está **dentro** do `while`, mas **fora** dos `if`. Ele só será executado se o `break` **não** for atingido naquela iteração.

## Observações importantes

- `break` interrompe apenas o **laço mais interno** em caso de loops aninhados.
- Em `while True`, o `break` é a forma mais comum de encerrar o loop.
- A indentação é essencial para indicar em qual bloco o `break` está.
- Se o `break` nunca for alcançado, o `while True` continuará para sempre.

---
