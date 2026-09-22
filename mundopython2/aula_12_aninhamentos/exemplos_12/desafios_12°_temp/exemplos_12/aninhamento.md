# Condicionais com Múltiplas Opções (`elif`) e Aninhamento

## Múltiplas opções com `elif`

Para mais de duas opções de uma condição, usamos o `elif` (abreviação de `else if`).

> **Observação:** `elif` não é exatamente o mesmo que `else`. Ele combina `else` + `if`, permitindo testar uma nova condição caso a anterior seja falsa.

### Estrutura

```python
if condição:
    ...
elif condição:
    ...
else:
    ...
```

### Exemplo

```python
idade = 20

if idade < 12:
    print("Criança")
elif idade < 18:
    print("Adolescente")
else:
    print("Adulto")
```

---

## Aninhamento

Aninhamento é quando colocamos uma estrutura dentro de outra. Na programação, isso significa ter, por exemplo, um `if` dentro de outro `if`.

### Estrutura

```python
if condição:
    if condição:
        if condição:
            ...
else:
    ...
```

### Exemplo com indentação correta

```python
if condicao1:
    if condicao2:
        if condicao3:
            print("Todas as condições são verdadeiras")
        else:
            print("condicao3 é falsa")
    else:
        print("condicao2 é falsa")
else:
    print("condicao1 é falsa")
```

> **Atenção:** a indentação define a qual `if` cada `else` pertence. No exemplo acima, o `else` final está alinhado ao primeiro `if`, então pertence a ele.

---

## Observações importantes

- Em Python, a indentação é obrigatória e faz parte da sintaxe.
- O padrão mais comum é usar **4 espaços** por nível de indentação.
- Aninhamentos muito profundos podem dificultar a leitura do código; use com moderação.

---
