# Dicionários em Python

## Definição

O **dicionário** é a terceira variável composta do Python.  
Pode ser declarado como:

```python
dados = dict()
# ou
dados = {}
```

Diferente das outras estruturas, em que as buscas são feitas por **índices**, no dicionário temos **etiquetas** ou **chaves**.

## Exemplo básico

```python
dados = {"nome": "Pedro", "idade": 25}
print(dados["nome"])
print(dados["idade"])
```

Enquanto nas estruturas anteriores as buscas eram realizadas pelos índices, aqui o uso das chaves facilita as buscas e a legibilidade do código.

## Inserir e deletar

Diferente das listas, aqui **não usamos `append`**. Inserimos a nova chave + valor diretamente no dicionário:

```python
dados = {"nome": "Pedro", "idade": 25}

dados["sexo"] = "m"

# Agora: dados = {"nome": "Pedro", "idade": 25, "sexo": "m"}
```

Para deletar, usamos o `del` padrão e indicamos a chave:

```python
del dados["idade"]

# Agora: dados = {"nome": "Pedro", "sexo": "m"}
```

> **Atenção:** a chave é uma string, então precisa estar entre aspas: `del dados["idade"]`.

## Quebra de linha

As estruturas de variáveis compostas não precisam ser fechadas na mesma linha, contanto que sejam fechadas.

```python
filme = {
    "titulo": "Star Wars",
    "ano": 1977,
    "diretor": "George Lucas"
}
```

## Comandos úteis

| Comando             | Descrição                                                                 |
|---------------------|---------------------------------------------------------------------------|
| `filme.values()`    | Pega somente os valores.                                                  |
| `filme.keys()`      | Pega somente as chaves.                                                   |
| `filme.items()`     | Pega os dois: chave e valor.                                              |
| `filme.copy()`      | Copia o dicionário, assim como `[:]` nas listas. No entanto, dicionários, diferente das listas, usam `.copy()` para copiar. |

> **Observação:** `keys()`, `values()` e `items()` retornam **visões dinâmicas** (*view objects*), não listas. Se precisar de uma lista, use `list(filme.keys())`, por exemplo.

## Loops com dicionários

O uso de loops também é possível com essa estrutura.

```python
for k, v in filme.items():
    print(f"O {k} é {v}.")
```

Usamos o método `items()` para pegar chave e valor ao mesmo tempo, em vez de `enumerate` nos dicionários.

> **Observação:** `enumerate` é mais usado em sequências (listas, strings, tuplas) para obter índice e valor. Em dicionários, `items()` já entrega chave e valor diretamente.

## Estruturas compostas mistas

Também é possível usar estruturas diferentes juntas, como dicionários dentro de listas.

```python
locadora = [
    {"titulo": "Star Wars", "ano": 1977, "diretor": "George Lucas"},
    {"titulo": "Avengers", "ano": 2012, "diretor": "Joss Whedon"},
    {"titulo": "Matrix", "ano": 1999, "diretor": "Wachowski"}
]

print(locadora[0]["ano"])     # Exibe 1977
print(locadora[2]["titulo"])  # Exibe Matrix
```

## Observações importantes

- Dicionários são **mutáveis**.
- As chaves devem ser **imutáveis** (strings, números, tuplas). Os valores podem ser de qualquer tipo.
- Acessar uma chave inexistente gera `KeyError`. Para evitar erro, use `.get()`:
  ```python
  print(dados.get("altura"))        # None
  print(dados.get("altura", 0))     # 0
  ```
- `.copy()` faz uma **cópia rasa**. Para cópia profunda, use `copy.deepcopy()`.
- “Joss whendo” → **Joss Whedon**
