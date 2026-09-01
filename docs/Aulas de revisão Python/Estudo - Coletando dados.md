# 05 — Coletando dados

> Curso **Python para Data Science** — [Alura](https://www.alura.com.br/)

Recebendo informação de quem usa o programa, convertendo tipos e formatando a saída.

---

## A função `input()`

Em algumas aplicações é preciso coletar valores da pessoa usuária. A função [`input()`](https://docs.python.org/3/library/functions.html#input) exibe uma mensagem, pausa a execução até que algo seja digitado e devolve o que foi escrito.

```python
nome = input('Escreva seu nome: ')
nome
```

```
'Breno'
```

O texto dentro dos parênteses é opcional, mas é o que orienta a pessoa sobre o que digitar.

## O retorno é sempre uma string

Este é o ponto central do tema. Independentemente do que for digitado, o `input()` devolve uma `str`:

```python
ano_entrada = input('Escreva o ano de ingresso do(a) estudante: ')
type(ano_entrada)
```

```
<class 'str'>
```

Ou seja, mesmo digitando `2023`, o valor guardado é o texto `'2023'`. Tentar fazer uma conta com ele resultaria em erro — ou, pior, em um comportamento silencioso e errado: `'2023' * 2` devolve `'20232023'`, porque multiplicar string repete o texto.

## Convertendo tipos

Para trabalhar com o dado como número, é preciso converter o resultado:

| Função | Converte para | Exemplo |
|---|---|---|
| [`int()`](https://docs.python.org/3/library/functions.html#int) | Inteiro | `int('2023')` |
| [`float()`](https://docs.python.org/3/library/functions.html#float) | Decimal | `float('8.45')` |
| [`str()`](https://docs.python.org/3/library/functions.html#func-str) | Texto | `str(15)` |
| [`bool()`](https://docs.python.org/3/library/functions.html#bool) | Booleano | `bool(1)` |

A conversão pode ser feita já na coleta, envolvendo o `input()`:

```python
ano_entrada = int(input('Escreva o ano de ingresso do(a) estudante: '))
type(ano_entrada)
```

```
<class 'int'>
```

Escolher entre `int()` e `float()` depende do dado: ano de ingresso é inteiro, nota e média pedem `float`, porque aceitam casas decimais.

## Formatando a saída com f-strings

Para apresentar o resultado misturando texto e valores não textuais, usa-se a f-string: um `f` antes das aspas e as variáveis entre chaves `{}`.

```python
nota_entrada = float(input('Digite a nota do teste de ingresso: '))
print(f'Ano de entrada: {ano_entrada} - nota do teste de ingresso: {nota_entrada}')
```

```
Ano de entrada: 2023 - nota do teste de ingresso: 8.5
```

Dentro das chaves é possível colocar qualquer expressão, não apenas o nome de uma variável — inclusive contas e formatação de casas decimais, como o `{media:.2f}` visto no tema anterior.

## Exercícios feitos

### Calculadora com operação escolhida

Coleta de dois números e do sinal da operação, com o resultado saindo pelo condicional:

```python
x = float(input('Digite um número: '))
z = str(input(''))
y = float(input('Digite outro número: '))

if z == '+':
    print(x + y)
```

Note que `x` e `y` foram convertidos para `float`, mas `z` permaneceu texto — é exatamente o que se quer, já que o sinal é um caractere e será comparado com `'+'`.

### Frase em maiúsculas

Junção do que foi visto em strings com a coleta de dados:

```python
frase = str(input('Digite uma frase: '))
frase = frase.upper()

print(frase)
```

O `str()` aqui é redundante, já que o `input()` já devolve uma string — mas deixa explícito o tipo esperado.

---

## O que ficou de aprendizado

- `input()` sempre devolve `str`, mesmo quando o que se digita parece número.
- A conversão pode envolver o `input()` na mesma linha: `float(input('...'))`.
- `int()`, `float()`, `str()` e `bool()` fazem as conversões entre tipos.
- `type()` é útil para conferir o que realmente está guardado antes de calcular.
- f-string mistura texto e variáveis de forma direta e legível.

## Referências

- [Função `input()`](https://docs.python.org/3/library/functions.html#input)
- [Formatted string literals](https://docs.python.org/3/reference/lexical_analysis.html#f-strings)
