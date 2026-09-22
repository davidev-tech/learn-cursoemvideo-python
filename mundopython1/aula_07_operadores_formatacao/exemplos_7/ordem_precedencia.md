# Ordem de Precedência dos Operadores Aritméticos

| Ordem | Operador(es)         | Descrição                                      |
|-------|----------------------|------------------------------------------------|
| 1º    | `()`                 | Parênteses — maior prioridade                  |
| 2º    | `**`                 | Potência                                       |
| 3º    | `*`, `/`, `//`, `%`  | Multiplicação, divisão, divisão inteira e resto |
| 4º    | `+`, `-`             | Adição e subtração                             |

---

## Observações

- Operadores na mesma ordem têm a mesma precedência e são avaliados da **esquerda para a direita**.
- A exceção é o `**` (potência), que é avaliado da **direita para a esquerda**.
- Use parênteses para deixar a ordem de avaliação explícita e evitar ambiguidades.
