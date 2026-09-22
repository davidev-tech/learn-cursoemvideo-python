# Tuplas em Python

## Definição

Tuplas são **variáveis compostas**. Enquanto variáveis simples guardam apenas 1 valor, as tuplas podem guardar mais de 1 valor.

### Comparação

| Variável Simples | Variável Composta (Tupla) |
|------------------|----------------------------|
| `bebida = "agua"` | `bebidas = ("agua", "suco", "refrigerante", "chá", "café", "leite")` |

## Acesso aos valores

- Podemos acessar **todos** os valores da tupla apenas referenciando a variável (`bebidas`).
- Ou acessar um item **específico** de acordo com o índice: `0`, `1`, `2`, `3`, `4`...
- O **fatiamento** em variáveis compostas também é possível.

### Exemplos

```python
print(bebidas)        # ('agua', 'suco', 'refrigerante', 'chá', 'café', 'leite')
print(bebidas[0])     # 'agua'
print(bebidas[2:])    # ('refrigerante', 'chá', 'café', 'leite')
```

## Imutabilidade

As tuplas são **imutáveis**. Após definir os valores dentro de uma tupla, **não é possível** fazer qualquer alteração, seja:

- Remover um elemento
- Adicionar um elemento
- Substituir um elemento por outro

### Estrutura de definição

Usam **parênteses** no início e no final: `( )`

## Comandos úteis

| Comando              | Descrição                                                                 |
|----------------------|---------------------------------------------------------------------------|
| `len(tupla)`         | Verifica o comprimento de uma String ou variável composta: quantos elementos existem naquela estrutura. |
| `tupla.index(item)`  | Verifica em qual índice aquele item aparece **primeiro**.                 |
| `tupla.count(item)`  | Verifica **quantas vezes** aquele item aparece.                           |
| `del(tupla)`         | Deleta a tupla da memória, como se nunca tivesse existido.                |
| `sorted(tupla)`      | Retorna uma **lista** com os elementos em ordem alfabética.               |

> **Observação:** `sorted()` **não altera** a tupla original (ela é imutável). Ele retorna uma nova lista ordenada. Se quiser o resultado como tupla, use `tuple(sorted(tupla))`.

## Cuidado com índices inexistentes

Caso procure o índice de um elemento que **não existe**, a linguagem irá gerar um **erro** (`ValueError`). Portanto, é sempre bom verificar antes da busca.

### Exemplo de verificação segura

```python
bebidas = ("agua", "suco", "refrigerante")

if "cha" in bebidas:
    print(bebidas.index("cha"))
else:
    print("Item não encontrado")
```

---
