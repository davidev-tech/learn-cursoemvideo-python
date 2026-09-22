# Modularização em Python

## Definição

**Modularização** é o ato de modularizar, ou seja, decompor problemas complexos em subproblemas independentes.

Surgiu com o propósito de:

- dividir sistemas grandes em partes menores;
- facilitar a legibilidade e a manutenção;
- manter o código mais organizado;
- ocultar detalhes de implementação;
- permitir a reutilização de um módulo em outros projetos.

## Como utilizar

Para utilizar modularização, colocamos as funções em um arquivo diferente e seguimos o mesmo padrão de importação que já existe.

No arquivo principal, podemos usar:

```python
import nome_arquivo
```

ou

```python
from nome_arquivo import nome_funcao
```

Depois, basta chamar a função dentro do arquivo principal.

### Exemplo

**Arquivo `uteis.py`:**

```python
def soma(a, b):
    return a + b
```

**Arquivo principal:**

```python
import uteis

print(uteis.soma(2, 3))  # 5
```

Ou, importando diretamente a função:

```python
from uteis import soma

print(soma(2, 3))  # 5
```

---

## Namespace (Espaço de Nomes)

Quando usamos `import uteis`, criamos um **“caminho”**. Isso evita que, se você tiver uma função `soma()` no seu programa e outra `soma()` no módulo, elas entrem em conflito.

Nesse caso, você usará:

```python
uteis.soma()
```

Assim, o nome da função fica associado ao módulo de origem.

---

## Single Responsibility Principle (SRP)

**Single Responsibility Principle** (Princípio da Responsabilidade Única): um módulo deve ter uma **“razão única para existir”**.

### Exemplo

Um módulo `matematica.py` não deve ter funções para “imprimir boletos”.

Isso mantém a modularização **saudável**.
