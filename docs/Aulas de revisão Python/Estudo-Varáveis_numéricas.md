# 03 — Variáveis numéricas

> Curso **Python para Data Science** — [Alura](https://www.alura.com.br/)

Operações com `int` e `float` aplicadas a um caso real de folha de pagamento.

---

## `int` e `float`

- **`int`** — números inteiros, sem casa decimal: `5`, `16`, `3000`
- **`float`** — números com casa decimal, separada por **ponto**: `8.45`, `6250.0`

Um detalhe que vale registrar: a divisão com `/` sempre devolve um `float`, mesmo quando o resultado é exato. `10 / 2` resulta em `5.0`, não `5`.

## Operadores aritméticos usados

| Operador | Operação | Exemplo |
|:---:|---|---|
| `+` | Soma | `5 + 16` |
| `-` | Subtração | `12500 - 3000` |
| `*` | Multiplicação | `16 * 6000` |
| `/` | Divisão | `184500 / 22` |

## Situação trabalhada

Uma tabela com os cargos de uma escola, a quantidade de pessoas em cada um e o salário correspondente:

| Cargo | Quantidade | Salário |
|---|---|---|
| Segurança | 5 | 3000 |
| Docente | 16 | 6000 |
| Diretoria | 1 | 12500 |

Três respostas eram necessárias: o total de empregados, a diferença entre o menor e o maior salário, e a média ponderada da faixa salarial.

### Passo 1 — guardar os dados

```python
q_seguranca = 5
s_seguranca = 3000

q_docente = 16
s_docente = 6000

q_diretoria = 1
s_diretoria = 12500
```

O prefixo `q_` para quantidade e `s_` para salário mantém o código organizado quando o número de variáveis cresce.

### Passo 2 — total de funcionários

```python
total_funcionarios = q_seguranca + q_docente + q_diretoria
print(total_funcionarios)
```

```
22
```

### Passo 3 — diferença salarial

```python
dif_sal = s_diretoria - s_seguranca
print(dif_sal)
```

```
9500
```

### Passo 4 — média ponderada

Este foi o ponto principal do exercício. A média simples dos três salários daria um resultado errado, porque ignora que existem 16 docentes e apenas 1 pessoa na diretoria. O peso de cada salário é a quantidade de pessoas que o recebem.

Então o cálculo é feito em duas etapas: primeiro o gasto total de cada cargo, depois a soma dividida pelo total de funcionários.

```python
sal_seguranca = q_seguranca * s_seguranca
sal_docente = q_docente * s_docente
sal_diretoria = q_diretoria * s_diretoria

soma_sal = sal_diretoria + sal_docente + sal_seguranca

media_sal = soma_sal / total_funcionarios

print(f"{media_sal:.2f}")
```

```
5795.45
```

Para comparação: a média simples dos três valores seria 7166,67 — quase 1400 a mais do que a realidade da folha. É um bom lembrete de que a escolha da métrica muda a conclusão.

## Formatando casas decimais

A divisão devolveu um número com várias casas decimais. Como se trata de dinheiro, o resultado foi limitado a duas casas dentro de uma f-string:

```python
print(f"{media_sal:.2f}")
```

A sintaxe é `{variavel:.2f}` — o `.2` indica a quantidade de casas e o `f` indica formato de ponto flutuante. A formatação afeta apenas a exibição: a variável continua guardando o valor completo.

---

## O que ficou de aprendizado

- `int` e `float` se misturam livremente nas operações; o resultado vira `float`.
- Divisão com `/` sempre retorna `float`.
- Média ponderada exige multiplicar cada valor pelo seu peso antes de dividir pelo total.
- `{valor:.2f}` controla as casas decimais na exibição, sem alterar o dado original.
- Quebrar o cálculo em variáveis intermediárias facilita conferir onde um erro apareceu.

## Referências

- [Operadores numéricos](https://docs.python.org/3/library/stdtypes.html#numeric-types-int-float-complex)
- [Format Specification Mini-Language](https://docs.python.org/3/library/string.html#format-specification-mini-language)
