# Tratamento de Exceções em Python

## Definição

**Exception (exceção)** é um erro que **não ocorre de forma frequente** e **não é um erro sintático**. Ou seja, o código está escrito corretamente, mas algo inesperado acontece durante a execução.

Um exemplo comum é o **erro de tipo**: definimos que uma entrada deve ser de um tipo, mas o usuário envia outro tipo de dado, resultando em `TypeError` no terminal.

Para lidar com essas situações, devemos **tratar os dados**. Em Python, temos dois comandos principais para isso:

- **`try`** → “tente alguma coisa”.
- **`except`** → “se não, aconteceu uma exceção”.

Também podemos usar um `else` após o `except` e um `finally` para finalizar tudo.

> **Observações:**
> - `else` e `finally` são **opcionais**.
> - O `try` deve vir acompanhado de pelo menos um `except`.
> - Podemos ter **vários `except`** para um mesmo `try`.

---

## Estrutura completa

```python
try:
    # código que pode gerar exceção
except TipoDeErro:
    # tratamento da exceção
else:
    # executa se não houve exceção
finally:
    # executa sempre, com ou sem exceção
```

---

## Papel de cada bloco

| Bloco     | Apelido                    | Quando executa                                                                 |
|-----------|----------------------------|--------------------------------------------------------------------------------|
| `try`     | O “laboratório”            | Contém o código que corre risco de dar problema.                               |
| `except`  | O “plano de contingência”  | Só roda se algo der errado no `try`.                                           |
| `else`    | O “caminho feliz”          | Só roda se o `try` foi um sucesso absoluto (zero erros).                       |
| `finally` | O “protocolo de encerramento” | Roda **sempre**, não importa se deu erro ou não. Ideal para fechar conexões com banco de dados (PostgreSQL) ou arquivos. |

---

## Exemplo

```python
try:
    num = int(input("Digite um número: "))
    print(10 / num)
except ValueError:
    print("Você não digitou um número inteiro.")
except ZeroDivisionError:
    print("Não é possível dividir por zero.")
else:
    print("Tudo certo!")
finally:
    print("Encerrando o programa...")
```

---

## LBYL vs EAFP

### LBYL (*Look Before You Leap*) — usando `if`

Use para:

- Validar formato;
- Verificar tamanho de string;
- Checar se campos estão vazios (sanitização).

**Exemplo:**

```python
if isinstance(valor, int) and valor != 0:
    resultado = 10 / valor
```

### EAFP (*Easier to Ask Forgiveness than Permission*) — usando `try`

Use para:

- Operações de rede;
- Leitura de arquivos;
- Conversões de tipo (`float` / `int`);
- Qualquer interação com Banco de Dados.

**Exemplo:**

```python
try:
    resultado = 10 / int(valor)
except (ValueError, ZeroDivisionError):
    resultado = None
```

---

## Validação híbrida

> “O ideal para sistemas robustos é a **validação híbrida**: usar o `if` para filtrar o que é previsível e `try/except` para capturar o imprevisível. Isso garante que o banco de dados receba dados limpos e que o sistema sobreviva a falhas de infraestrutura.”

---

## Principais tipos de exceção

| Exceção              | Quando ocorre                                                     |
|----------------------|-------------------------------------------------------------------|
| `ValueError`         | Conversão inválida (ex: `int("abc")`).                            |
| `TypeError`          | Operação com tipo errado (ex: `"2" + 2`).                         |
| `ZeroDivisionError`  | Divisão por zero.                                                 |
| `FileNotFoundError`  | Arquivo não encontrado.                                           |
| `KeyError`           | Chave inexistente em dicionário.                                  |
| `IndexError`         | Índice fora do intervalo em lista/tupla.                          |

---
- “se não acontece uma exceção” → **se acontecer uma exceção** (reescrito para ficar coerente)
- “apos” → **após**
- “varios” → **vários**
- “try deve vir acompanhado de um except” → mantido, destacando que é **pelo menos um**.
- Adicionada tabela-resumo dos blocos e dos tipos de exceção.
- Adicionados exemplos de código para `try/except/else/finally` e para LBYL/EAFP.

Pode enviar a próxima anotação.
