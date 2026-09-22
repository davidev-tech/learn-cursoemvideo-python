# Pacotes em Python

## Definição

**Pacotes** são pastas que contêm vários **módulos**, ou seja, vários arquivos.

Podemos ter pacotes dentro de pacotes (**subpacotes**). Cada pasta de pacote — incluindo a principal e as subpastas — deve conter obrigatoriamente um arquivo `__init__.py` para que o pacote funcione como um pacote regular.

> **Observação:** em Python 3.3+, existem os *namespace packages*, que não exigem `__init__.py`. Porém, no modelo tradicional (e no contexto de aulas), o `__init__.py` é exigido.

## Importação

Na hora de importar, usamos importações mais específicas:

```python
from pacote import modulo
```

Ou seja: **vá ao pacote e importe esse módulo**.

### Exemplo

```python
from uteis import matematica
from uteis.subpacote import estatistica
```

## Relação entre módulo e pacote

- Um **módulo** pode possuir várias funções.
- Um **pacote** pode possuir vários módulos.

## Hierarquia de organização

```text
Função (Lógica)
   └── Módulo (Arquivo .py)
         └── Pacote (Pasta com __init__.py)
               └── Biblioteca (Conjunto de Pacotes)
```

## Exemplo de estrutura de pastas

```text
projeto/
├── main.py
└── pacote/
    ├── __init__.py
    ├── modulo1.py
    └── subpacote/
        ├── __init__.py
        └── modulo2.py
```

### Importando no arquivo principal

```python
from pacote import modulo1
from pacote.subpacote import modulo2
```
