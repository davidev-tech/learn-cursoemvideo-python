# Bibliotecas em Python

## O que são bibliotecas?

Bibliotecas são conjuntos de funcionalidades prontas que não vêm nativamente na linguagem. Essas funcionalidades não nativas devem ser importadas por meio de bibliotecas, que já possuem funcionalidades desejadas desenvolvidas para funções específicas dentro do sistema.

## Importação de bibliotecas

A importação de bibliotecas em Python ocorre por meio do comando `import` + nome do módulo ou biblioteca.  
**Obs.:** essas importações devem ocorrer logo no início do programa.

### Formas de importação

- `import biblioteca` → importa toda a biblioteca (módulo).
- `from biblioteca import item_especifico` → importa apenas um item específico.
- `from biblioteca import item1, item2` → importa múltiplos itens específicos, separados por vírgula.

### Exemplos

```python
import math
from math import sqrt
from math import sqrt, pow
```

## Biblioteca `math`

A biblioteca `math` é a biblioteca matemática do Python.

### Funções da `math`

| Função      | Descrição                                                       |
|-------------|-----------------------------------------------------------------|
| `ceil`      | Arredonda o valor para cima.                                    |
| `floor`     | Arredonda o valor para baixo.                                   |
| `trunc`     | Trunca o número, eliminando a parte decimal.                    |
| `pow`       | Calcula potência.                                               |
| `sqrt`      | Calcula raiz quadrada.                                          |
| `factorial` | Calcula fatorial.                                               |

**Observação:** nem todas são funções de arredondamento. `ceil`, `floor` e `trunc` arredondam/truncam; `pow`, `sqrt` e `factorial` são funções matemáticas diversas.

### Exemplos de uso

```python
import math

print(math.sqrt(9))       # 3.0
print(math.pow(2, 3))     # 8.0
print(math.factorial(5))  # 120

from math import sqrt, pow

print(sqrt(16))           # 4.0
print(pow(2, 4))          # 16.0
```

## Bibliotecas externas

Para usar bibliotecas externas, primeiro é necessário instalá-las na máquina. Só depois disso é possível importá-las normalmente, como nos exemplos anteriores.

---
