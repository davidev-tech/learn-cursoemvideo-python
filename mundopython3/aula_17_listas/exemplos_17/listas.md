# Listas em Python

## Definição

Listas, assim como tuplas, são **variáveis compostas** que guardam valores, e seus valores são percorridos por **índice**. No entanto, diferente das tuplas, elas são **mutáveis** e recebem **colchetes** no início e no fim: `[]`.

Também podem ser declaradas como:

```python
dados = list()
```

## Exemplo de mutabilidade

```python
lanches = ["Hambúrguer", "Refrigerante", "Batata Frita", "Sorvete"]
lanches[0] = "Macarronada"
# Agora: lanches = ["Macarronada", "Refrigerante", "Batata Frita", "Sorvete"]
```

O valor do índice `0`, que era `"Hambúrguer"`, é **substituído** por `"Macarronada"`.

## Comandos úteis

| Comando                         | Descrição                                                                 |
|---------------------------------|---------------------------------------------------------------------------|
| `lista.append(elemento)`        | Adiciona um novo elemento no **final** da lista.                          |
| `lista.insert(indice, elemento)`| Adiciona o novo elemento em um **índice especificado**.                   |
| `del lista[indice]`             | Deleta o elemento da lista na **memória**.                                |
| `del lista`                     | Deleta a **lista toda** da memória.                                       |
| `lista.pop(indice)`             | Remove um elemento da lista pelo **índice**.                              |
| `lista.pop()`                   | Remove o **último** elemento da lista.                                    |
| `lista.remove(item)`            | Remove o elemento pelo **valor** (primeira ocorrência).                   |
| `lista.sort()`                  | Ordena os valores (crescente).                                            |
| `lista.sort(reverse=True)`      | Ordena os valores no **sentido inverso** (decrescente).                   |
| `len(lista)`                    | Verifica o comprimento da lista, ou seja, quantos elementos tem dentro.   |

> **Observação:** `sort()` modifica a lista original. Se quiser preservar a lista original, use `sorted(lista)`, que retorna uma nova lista ordenada.

## Cuidado com remoções inválidas

Caso tente remover um elemento da lista que **não existe**, a linguagem gera um **erro** (geralmente `ValueError` ou `IndexError`). Para evitar tais problemas, é sempre bom verificar antes.

### Exemplo de verificação segura

```python
lanches = ["Hambúrguer", "Refrigerante", "Batata Frita"]

if "Pizza" in lanches:
    lanches.remove("Pizza")
else:
    print("Item não encontrado")
```
