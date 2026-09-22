# Manipulação de Arquivos em Python

## Visão geral

Manipular arquivos é uma etapa essencial em sistemas que precisam **persistir dados** (guardar informações mesmo depois que o programa é fechado). No contexto do projeto final (Mundo 3), o sistema precisa:

- **Verificar se o arquivo existe** (se não existir, criá-lo vazio).
- **Cadastrar uma nova pessoa**, acrescentando uma linha ao final do arquivo.
- **Listar todas as pessoas**, lendo o arquivo inteiro e exibindo os dados na tela.

---

## 1. O que significa “abrir um arquivo”?

Quando fazemos:

```python
open('dados.txt', 'r')
```

o Python pede ao sistema operacional um **canal de comunicação** com aquele arquivo. Essa comunicação é representada por um objeto (o *file handle*). Toda operação de leitura ou escrita usa esse objeto.

> **Importante:** depois de usar, é preciso fechar esse canal com `.close()` para liberar recursos.

A forma mais segura e idiomática é usar o **gerenciador de contexto** `with`, que fecha automaticamente, mesmo se ocorrer erro.

### Estrutura básica

```python
with open('arquivo.txt', 'r') as arquivo:
    conteudo = arquivo.read()
# Aqui o arquivo já está fechado automaticamente
```

---

## 2. Modos de abertura

| Modo  | Significado     | Comportamento                                                                 |
|-------|-----------------|-------------------------------------------------------------------------------|
| `'r'` | Leitura         | Dá erro se o arquivo não existe.                                              |
| `'w'` | Escrita         | Cria o arquivo se não existe; **apaga o conteúdo** se já existe.              |
| `'a'` | Append          | Cria o arquivo se não existe; escreve **sempre no final**, sem apagar o conteúdo. |
| `'r+'`| Leitura e escrita | Não apaga o conteúdo inicial.                                              |

> Para o **cadastro**, o modo `'a'` é perfeito: abre, escreve uma nova linha e fecha, sem perder os registros anteriores.

---

## 3. Como organizar os dados no arquivo?

É preciso um formato que permita, depois, **ler e separar** os campos. Uma opção simples é usar `;` (ponto e vírgula) como separador.

### Exemplo de arquivo

```text
João;25
Maria;30
```

Na leitura, lê-se **linha por linha** e usa-se `.split(';')` para separar os campos.

---

## 4. Lógica das funções principais

### a) `arquivoExiste(nome)`

- Verifica se o arquivo existe.
- Pode ser feito com `os.path.exists(nome)` (módulo `os`) ou `Path(nome).exists()` (`pathlib`).
- Não é necessário abrir o arquivo — basta retornar `True` ou `False`.

```python
import os

def arquivoExiste(nome):
    return os.path.exists(nome)
```

### b) `criarArquivo(nome)`

- Se o arquivo não existe, cria um arquivo **vazio**.
- Usa-se `'w'` ou `'a'` e fecha em seguida.
- Use `encoding='utf-8'` para aceitar acentos (João, José, etc.).

```python
def criarArquivo(nome):
    with open(nome, 'w', encoding='utf-8') as f:
        pass
```

### c) `cadastrar(arq, nome, idade)`

- Abre no modo `'a'` (append).
- Escreve uma linha formatada.
- Converte a idade para string e adiciona `\n` no final, para que cada cadastro fique em uma linha separada.

```python
def cadastrar(arq, nome, idade):
    with open(arq, 'a', encoding='utf-8') as f:
        f.write(f'{nome};{idade}\n')
```

### d) `lerArquivo(arq)`

- Abre no modo `'r'`.
- Se o arquivo não existir, tratar com `try/except FileNotFoundError` ou chamar `criarArquivo` antes.
- Ler todas as linhas com `.readlines()` (devolve uma lista) ou iterar direto sobre o objeto arquivo com `for linha in arquivo:`.
- Para cada linha: remover `\n` com `.strip()` e separar com `.split(';')`.
- Exibir formatado, por exemplo:

```python
def lerArquivo(arq):
    try:
        with open(arq, 'r', encoding='utf-8') as f:
            for linha in f:
                nome, idade = linha.strip().split(';')
                print(f'{nome:<30}{idade:>3} anos')
    except FileNotFoundError:
        print("Arquivo não encontrado.")
```

---

## 5. Pontos que costumam gerar confusão

- **Esquecer o `encoding`:** use `encoding='utf-8'` em qualquer `open()` que lida com texto em português.
- **Esquecer o `\n`:** sem ele, todos os registros grudam na mesma linha. Na leitura, o `strip()` resolve.
- **Abrir com `'w'` para cadastrar:** isso apaga tudo. Para acrescentar, é `'a'`.
- **Não fechar o arquivo:** com `with`, você nunca mais erra nisso.

---

## Resumo rápido

| Operação          | Modo ideal | Cuidado principal                  |
|-------------------|------------|-------------------------------------|
| Ler arquivo       | `'r'`      | Tratar `FileNotFoundError`          |
| Criar arquivo     | `'w'`      | Apaga conteúdo se já existir        |
| Cadastrar/append  | `'a'`      | Sempre escreve no final             |
| Ler e escrever    | `'r+'`     | Não apaga o conteúdo inicial        |

---
