# 06 — Estruturas condicionais

> Curso **Python para Data Science** — [Alura](https://www.alura.com.br/)

Fazendo o programa tomar decisões: executar um bloco de código apenas quando uma condição for verdadeira.

---

## `IF`

`if` significa "se". Ele verifica se uma condição é verdadeira ou falsa e executa o bloco correspondente. A sintaxe:

```python
if condição:
    # faça algo
```

Dois detalhes de sintaxe que o Python exige:

- os **dois pontos** ao final da linha da condição;
- a **indentação** (recuo) das linhas seguintes — é ela que define o que está dentro do `if`. Em outras linguagens isso seria feito com chaves; em Python, o recuo é obrigatório e faz parte da lógica.

```python
if 2 < 7:
    print('Verdadeiro')
```

```
Verdadeiro
```

## `ELSE`

O `else` complementa o `if` e é executado quando a condição é avaliada como `False`:

```python
if condição:
    # código caso seja verdade
else:
    # código caso seja falso
```

### Situação: aprovação de estudantes

Recebendo a média, o algoritmo decide entre **Aprovado** e **Reprovado**. A regra: média igual ou superior a 6.0 aprova.

```python
media = float(input('Digite a média: '))

if media >= 6:
    print('Aprovado')
else:
    print('Reprovado')
```

O `else` não leva condição — ele cobre todo o resto dos casos.

## Vários `if` independentes

A instituição criou uma terceira situação: quem tem média entre 4.0 e 6.0 vai para **Recuperação**. A primeira tentativa foi encadear três `if` separados:

```python
media = float(input('Digite a média: '))

if media >= 6:
    print('Aprovado')
if 6.0 > media >= 4.0:
    print('Recuperação')
if media < 4.0:
    print('Reprovado')
```

Funciona, mas com dois problemas:

1. Cada `if` é avaliado de forma independente, então o Python testa as três condições mesmo depois de já ter encontrado a resposta.
2. Se as condições não forem escritas com cuidado, mais de um bloco pode ser executado e o programa imprime duas respostas contraditórias.

Vale registrar a comparação encadeada usada aqui: `6.0 > media >= 4.0` é uma forma enxuta de escrever "menor que 6 **e** maior ou igual a 4", e o Python entende naturalmente.

## `ELIF`

`elif` significa "senão, se" — é a união do `else` com o `if`. Permite verificar várias condições de forma encadeada:

```python
if condição1:
    # faça algo
elif condição2:
    # faça outra coisa
elif condição3:
    # faça mais alguma coisa
else:
    # faça algo diferente
```

O interpretador avalia as condições em ordem. Assim que uma resulta em `True`, o bloco correspondente é executado e **todo o restante da estrutura é ignorado**. Se nenhuma for verdadeira, o `else` entra em ação.

O mesmo caso das médias, reescrito:

```python
media = float(input('Digite a média: '))

if media >= 6:
    print('Aprovado')
elif 6.0 > media >= 4.0:
    print('Recuperação')
else:
    print('Reprovado')
```

Além de mais curto, este código é mais seguro: as três situações são mutuamente exclusivas por construção, e não por sorte na escrita das condições.

## Operadores de comparação usados

| Operador | Significado |
|:---:|---|
| `>` | Maior que |
| `<` | Menor que |
| `>=` | Maior ou igual a |
| `<=` | Menor ou igual a |
| `==` | Igual a |
| `!=` | Diferente de |

Confusão comum que vale anotar: `=` atribui um valor, `==` compara dois valores. Usar `=` dentro de um `if` gera erro de sintaxe.

---

## O que ficou de aprendizado

- `if` executa um bloco só quando a condição é verdadeira; `else` cobre o caso contrário.
- Dois pontos e indentação não são estilo — são exigência da linguagem.
- Vários `if` soltos são avaliados de forma independente e podem disparar mais de uma resposta.
- `elif` encadeia as condições, para a execução na primeira verdadeira e evita esse risco.
- Python aceita comparação encadeada, como `6.0 > media >= 4.0`.
- `=` atribui, `==` compara.

## Referências

- [Estrutura `if`](https://docs.python.org/3/tutorial/controlflow.html#if-statements)
- [Operadores de comparação](https://docs.python.org/3/library/stdtypes.html#comparisons)
