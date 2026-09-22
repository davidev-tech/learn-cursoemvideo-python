# Listas Compostas (Listas Aninhadas)

## Definição

Listas compostas são **listas dentro de listas**. Em Python, também são chamadas de **listas aninhadas**.

### Exemplo

```python
pessoas = [["João", 34], ["Maria", 25], ["Marco", 19]]
```

Como mostrado no exemplo, existe uma lista `pessoas` que dentro dela possui outras listas. Cada uma com o nome e a idade de pessoas diferentes.

## Características

As características permanecem as mesmas de uma lista padrão:

- São **mutáveis**.
- São delimitadas por **colchetes** `[ ]`.
- As buscas continuam sendo por **índices**, no entanto agora com **dois índices**:
  - o índice da lista principal;
  - os índices das listas internas.

### Exemplo de acesso

```python
pessoas = [["João", 34], ["Maria", 25], ["Marco", 19]]
print(pessoas[0][0])
```

O exemplo anterior busca o índice `0` na lista principal e encontra a primeira lista. Depois busca o índice `0` dentro dessa sublista, que nesse caso é `"João"`, e o exibe.

### Segundo exemplo

```python
pessoas[1]
```

Já no segundo exemplo, ele pega a lista do índice `1` e exibe ela toda:

```python
["Maria", 25]
```

## Observações importantes

- O primeiro índice acessa a **sublista**; o segundo acessa o **elemento** dentro da sublista.
- Como listas são mutáveis, também é possível alterar valores dentro das sublistas:

```python
pessoas[0][1] = 35
# Agora: [["João", 35], ["Maria", 25], ["Marco", 19]]
```

- `len(pessoas)` retorna `3` (quantidade de sublistas).
- `len(pessoas[0])` retorna `2` (quantidade de elementos na primeira sublista).
- O fatiamento também funciona normalmente:

```python
print(pessoas[0][:])   # ['João', 34]
print(pessoas[1:])     # [['Maria', 25], ['Marco', 19]]
```
