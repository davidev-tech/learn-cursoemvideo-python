# Ajuda Interativa, Docstrings, Parâmetros Padrão, Escopo e Retorno

## Ajuda Interativa (`help()`)

Para usar a **ajuda interativa**, basta usar a função `help()`. No terminal, digitamos o comando sobre o qual temos dúvidas e ele mostra a documentação daquele comando. Para sair, usamos `q`, `quit` ou `exit`.

Também podemos usar `help(comando)` diretamente no código, para ser mais direto.

> O `help()` é uma função formatada para humanos (bonita e organizada).

### Exemplo

```python
help(print)
```

---

## `__doc__`

Uma segunda forma de acessar a documentação é pelo atributo `__doc__`:

```python
print(comando.__doc__)
```

O `.__doc__` é o atributo **cru** (string pura).

### Exemplo

```python
print(len.__doc__)
```

---

## Docstrings

**Docstrings** são documentações feitas pelo desenvolvedor sobre a sua função, ficando logo abaixo da linha de definição da função. O objetivo delas é ser uma espécie de manual para outros programadores ou até mesmo usuários.

### Exemplo

```python
def contador(i, f, p):
    """
    --> Faz uma contagem e mostra na tela.
    :param i: inicia a contagem.
    :param f: marca o fim da contagem.
    :param p: pontua a quantidade do salto.
    return: Sem retorno.
    """
    # código da função
```

Para ler a sua própria docstring enquanto programa, basta digitar `help(sua_funcao)` no console. O Python vai buscar exatamente o que você escreveu entre as aspas triplas `"""`.

---

## Default Parameters (Parâmetros Padrão)

**Default Parameters** é um método que utiliza um valor padrão (*default*) para evitar que a função dê erro ao requerer um argumento para um parâmetro que não recebeu argumento.

Basicamente, quando definimos `0` como valor padrão para os parâmetros na função abaixo, eles já possuem aquele valor, tornando a passagem do argumento opcional. Parâmetros obrigatórios vêm antes dos parâmetros opcionais.

### Exemplo

```python
def somar(a=0, b=0, c=0):
    s = a + b + c
    print(f"A soma vale {s}")

somar(3, 2, 5)
somar(5, 2)
somar(2)
somar()
```

### Resultados

| Chamada           | Saída               |
|-------------------|---------------------|
| `somar(3, 2, 5)`  | `A soma vale 10`    |
| `somar(5, 2)`     | `A soma vale 7`     |
| `somar(2)`        | `A soma vale 2`     |
| `somar()`         | `A soma vale 0`     |

---

## Escopo de Variáveis

O **escopo de variáveis** é o local onde a variável vai ou não existir. Ou seja, uma variável pode existir apenas dentro de uma função, sendo uma **variável local**, ou no programa principal, sendo uma **variável global**.

Para modificar uma variável global de dentro de uma função, usamos o comando:

```python
global variavel
```

Dessa forma, acessamos o endereço da variável global na memória, tornando possível modificar variáveis globais de dentro de uma função.

---

## Retornando Valores

Usamos o comando `return variavel` para retornar um valor da variável de dentro da função para o programa principal. Isso permite que o valor seja exibido diretamente ou que seja atribuído a uma variável do programa principal.

> **Correção importante:** o valor retornado não se torna automaticamente global. A variável original continua local. O que acontece é que o valor retornado pode ser atribuído a uma variável global no programa principal.

> **Observação:** assim que usamos o `return` em uma função, nada abaixo dele será lido, pois a função encerra ali.

### Exemplo

```python
def somar(a, b):
    return a + b

resultado = somar(3, 4)
print(resultado)  # 7
```
