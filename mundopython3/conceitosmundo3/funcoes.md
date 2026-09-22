# Funções em Python

## Objetivo das funções

As funções têm como objetivo permitir a **reutilização de uma parte do código**, sem que seja preciso reescrevê-la. Além disso, facilitam a **manutenção do código**, pois, como criamos pequenos blocos usando funções, podemos mexer somente nele quando necessário, sem precisar alterar várias partes do código.

Quando criamos uma função, estamos criando um **comando personalizado**.

---

## Definindo uma função

Para definir uma função no Python, usamos a estrutura `def`, seguida do nome da função, parênteses e dois-pontos:

```python
def funcao():
    # bloco de código
```

Definimos o que queremos dentro dela usando **indentação**.

### Exemplo

```python
def mostrar_linha():
    print("----------------")
```

Dessa forma, definimos uma função.

---

## Chamando uma função

Caso queira chamá-la em algum momento do código, basta digitar o nome seguido dos parênteses: `funcao()`.

### Exemplo

```python
mostrar_linha()
print("           SISTEMA DE ALUNOS           ")
mostrar_linha()
mostrar_linha()
print("        CADASTRO DE FUNCIONARIOS        ")
mostrar_linha()
mostrar_linha()
print("         ERRO DO SISTEMA         ")
mostrar_linha()
```

---

## Parâmetros e argumentos

Em funções, também podemos utilizar **passagem de parâmetros** e **argumentos**.

- **Parâmetros:** são as variáveis que vão dentro dos parênteses na hora em que definimos a função.
  ```python
  def funcao(parametro_1, parametro_2):
      ...
  ```
  Podemos ter mais de um parâmetro, separando-os por vírgula.

- **Argumentos:** são os valores definidos na hora em que chamamos a função no programa principal. Eles serão as entradas que ocuparão os espaços definidos pelos parâmetros.

### Exemplo

```python
def exibir_mensagem(msg):
    print("--------------------")
    print(msg)
    print("--------------------")

exibir_mensagem("SISTEMAS DE ALUNOS")
```

No exemplo mostrado, `msg`, na hora em que definimos a função, é o **parâmetro**, e `"SISTEMAS DE ALUNOS"` é o **argumento** passado na hora em que chamamos a função.

> **Observação:** quando definimos uma quantidade X de parâmetros na função, sempre que formos chamá-la e passar os argumentos, a quantidade de argumentos passados deve ser igual à quantidade de parâmetros definidos.

No Python, podemos misturar argumentos explícitos e não explícitos. No entanto, os **não explícitos devem vir primeiro**. A partir do momento em que explicitamos 1, devemos explicitar todos que vierem depois dele.

---

## Tipos de argumentos

- **Argumentos não explicitados** = *Positional Arguments* (Argumentos Posicionais).
- **Argumentos explicitados** = *Keyword Arguments* (Argumentos de Palavra-chave ou Nomeados).

Tanto quando definimos explicitamente o parâmetro `x = argumento_y` quanto quando usamos dicionários, temos argumentos nomeados.

---

## Empacotamento com `*`

Quando vamos alocar mais de um valor em um parâmetro, ou não sabemos quantos serão alocados, usamos o `*`.

### Exemplo

```python
def exibir_numeros(*num):
    print(num)

exibir_numeros(2, 1, 7)
```

Dessa forma, podemos alocar vários valores dentro de `num`. Assim, `num` deixa de ser uma variável simples e passa a ser uma **tupla**. Isso se chama **empacotamento**.

> **Observação:** quando fazemos esse empacotamento, o Python cria o espaço em formato de tupla.

---

## Desempacotamento

Para o **desempacotamento**, usamos o `*` na hora em que chamamos a função. No desempacotamento, ele pode ser usado em qualquer variável composta. No entanto, para dicionário, devemos usar **dois asteriscos** (`**`). Se não, ele pega apenas as chaves e as desempacota como argumentos posicionais, podendo gerar um resultado incorreto ou um erro de tipo caso queiramos calcular algo.

Queremos chave e valor; dessa forma, desempacotamos os pares como argumentos nomeados.

```python
# Para listas/tuplas:
*  -> espalha os elementos como argumentos posicionais

# Para dicionários:
*  -> espalha apenas as chaves
** -> espalha chave + valor como argumentos nomeados
```

---

## Observação importante sobre o `*`

É importante usar o `*` na hora de desempacotar estruturas compostas, pois, se não, ele aloca tudo de uma vez em um parâmetro. Podemos ter duas situações possíveis:

1. Caso a função esteja esperando os valores com o uso do empacotamento `*` e receba apenas um argumento sem `*`, ela entende que aquilo é uma lista e coloca a lista dentro de uma tupla.
2. Caso espere mais de um parâmetro, ele aloca tudo no primeiro parâmetro, gerando um erro e pedindo os argumentos dos parâmetros restantes.

Quando usamos o `*`, o asterisco atua como um **operador de espalhamento** (*spread*). Ele itera sobre a estrutura composta e passa cada elemento como um argumento individual para a função.
