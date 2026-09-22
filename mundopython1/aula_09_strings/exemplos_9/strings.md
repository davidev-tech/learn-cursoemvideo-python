# Strings em Python

## Definição

- Uma **cadeia de caracteres** é o mesmo que uma **String**.
- Exemplo: `"Engenharia de Software"`
- Toda cadeia de texto em Python fica entre **aspas simples** (`'texto'`) ou **aspas duplas** (`"texto"`).

## Atribuição

```python
faculdade = "Engenharia de Software"
```

> **Observação:** sem as aspas, o Python interpretaria `Engenharia de Software` como nomes de variáveis/erro, e não como texto.

## Armazenamento na memória

O computador não guarda a string inteira em um único espaço; de forma simplificada, cada caractere ocupa uma posição na memória. Cada uma dessas posições é chamada de **índice**.

- Até caracteres como **espaço** ocupam um índice.
- A contagem dos índices começa em **0**.

### Exemplo com `"Engenharia de Software"`

| Índice | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 | 16 | 17 | 18 | 19 | 20 | 21 |
|--------|---|---|---|---|---|---|---|---|---|---|----|----|----|----|----|----|----|----|----|----|----|----|
| Caractere | E | n | g | e | n | h | a | r | i | a | ␣ | d | e | ␣ | S | o | f | t | w | a | r | e |

> `␣` representa um espaço.

## Técnicas de manipulação de Strings

### Fatiamento

- `texto[indice]` → acessa o caractere que está na posição indicada.

### Análise

- `len()` → retorna o comprimento da string.
- `count()` → conta quantas vezes um caractere ou trecho aparece.
- `find()` → retorna o índice da primeira ocorrência de um trecho.

### Transformação

- `replace()` → substitui parte do texto.
- `upper()` → transforma em maiúsculas.
- `lower()` → transforma em minúsculas.
- `capitalize()` → deixa a primeira letra maiúscula.
- `title()` → deixa as primeiras letras de cada palavra maiúsculas.
- `strip()` → remove espaços no início e no fim.

### Junção

- `join()` → junta elementos de uma sequência usando uma string como separador.

---
