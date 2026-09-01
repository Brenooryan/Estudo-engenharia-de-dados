# 07 — Operadores

> Curso **Python para Data Science** — [Alura](https://www.alura.com.br/)

Operadores lógicos e de pertencimento para montar condições mais elaboradas — último tema estudado até aqui.

---

## Por que operadores lógicos

Na construção de comandos, às vezes a expressão condicional precisa de mais de uma verificação ao mesmo tempo. É aí que entram os operadores lógicos, quase sempre acompanhando o `if`.

Antes, três definições que ajudam a ler a documentação:

- **Expressão lógica** — uma declaração que pode ser avaliada como verdadeira ou falsa.
- **Operandos lógicos** — os elementos que estão sendo comparados.
- **Operadores lógicos** — o que combina várias expressões em uma só.

## `AND`, `OR`, `NOT`

- **`and`** — verifica se duas condições são verdadeiras. `x and y` resulta em `True` apenas se **ambas** forem verdadeiras.
- **`or`** — verifica se pelo menos uma é verdadeira. `x or y` resulta em `True` se **ao menos uma** delas for verdadeira, e `False` só quando as duas forem falsas.
- **`not`** — nega uma condição. `not x` resulta em `True` se `x` for falsa, e `False` se `x` for verdadeira.

Resumindo em tabela:

| `x` | `y` | `x and y` | `x or y` | `not x` |
|:---:|:---:|:---:|:---:|:---:|
| `True` | `True` | `True` | `True` | `False` |
| `True` | `False` | `False` | `True` | `False` |
| `False` | `True` | `False` | `True` | `True` |
| `False` | `False` | `False` | `False` | `True` |

### Testes feitos

Variáveis criadas para os testes — vale notar a atribuição múltipla, que dá o mesmo valor a duas variáveis de uma vez:

```python
t1 = t2 = True
f1 = f2 = False
```

**`and`** — as duas verdadeiras, expressão verdadeira:

```python
if t1 and t2:
  print('expressão verdadeira')
else:
  print('expressão falsa')
```

```
expressão verdadeira
```

**`or`** — uma verdadeira e uma falsa já basta:

```python
if t1 or f2:
  print('expressão verdadeira')
else:
  print('expressão falsa')
```

```
expressão verdadeira
```

**`not`** — inverte o valor, então `not True` cai no `else`:

```python
if not t1:
  print('expressão verdadeira')
else:
  print('expressão falsa')
```

```
expressão falsa
```

## `IN`

O `in` verifica se um elemento está presente em uma lista, tupla ou outra variável de conjunto. A expressão `x in y` resulta em `True` se `x` estiver dentro de `y`.

### Situação: conferindo a lista de aprovados

A escola distribuiu os nomes dos aprovados como um texto único, e era preciso conferir se alguns nomes estavam ali:

```python
lista = 'José da Silva, Maria Oliveira, Pedro Martins, Ana Souza, Carlos Rodrigues, Juliana Santos, Bruno Gomes, Beatriz Costa, Felipe Almeida, Mariana Fernandes, João Pinto, Luísa Nascimento, Gabriel Souza, Manuela Santos, Thiago Oliveira, Sofia Ferreira, Rafael Albuquerque, Isabella Gomes, Bruno Costa, Maria Martins, Rafaela Souza, Matheus Fernandes, Luísa Almeida, Beatriz Pinto, Mariana Rodrigues, Gabriel Nascimento, João Ferreira, Maria Albuquerque, Felipe Oliveira'

nome_1 = 'Mariana Rodrigues'
nome_2 = 'Marcelo Nogueira'
```

```python
if nome_1 in lista:
    print(f'O nome {nome_1} está na lista.')
else:
    print(f'O nome {nome_1} não está na lista.')
```

```
O nome Mariana Rodrigues está na lista.
```

```python
if nome_2 in lista:
    print(f'O nome {nome_2} está na lista.')
else:
    print(f'O nome {nome_2} não está na lista.')
```

```
O nome Marcelo Nogueira não está na lista.
```

Como `lista` é uma string, o `in` procura o trecho de texto dentro dela. Isso funciona, mas tem uma limitação: a busca é por sequência de caracteres, então um nome parcial como `'Maria'` também retornaria `True` por estar contido em `'Maria Oliveira'`.

## Operador ternário

Forma compacta de escrever um `if/else` em uma única linha, quando o objetivo é apenas escolher entre dois valores:

```python
maior = x if x > y else y
```

A leitura é: *use `x` se `x > y`, senão use `y`*. O resultado da expressão é atribuído diretamente à variável.

---

## Exercícios resolvidos

### 1. Maior de dois números

```python
x = float(input('Digite um número inteiro: '))
y = float(input('Digite um número inteiro: '))

maior = x if x > y else y

print(f'O maior número digitado foi: {maior}')
```

### 2. Crescimento da empresa

Três saídas possíveis, resolvidas com `if / elif / else`. O `else` cobre o caso do zero, sem precisar de comparação:

```python
num = float(input('Informe o percentual de crescimento da empresa: '))

if num > 0:
    print('A empresa teve crescimento.')
elif num < 0:
    print('A empresa teve declínio.')
else:
    print('A empresa não teve variação.')
```

### 3. Vogal ou consoante

Uso direto do `in` com uma string de vogais — bem mais enxuto do que cinco comparações com `or`:

```python
letra = input('Digite uma letra: ')

if letra in 'aeiou':
    print('A letra digitada é uma vogal.')
else:
    print('A letra digitada é uma consoante.')
```

### 4. Maior faturamento anual

Ternário aninhado combinado com `and`, para comparar três valores:

```python
ano1 = 90000
ano2 = 120000
ano3 = 150000

maior = ano1 if ano1 > ano2 and ano1 > ano3 else (ano2 if ano2 > ano3 else ano3)

print(f'O maior faturamento anual foi: {maior}')
```

### 5. Produto mais barato

Mesma lógica do anterior para achar o menor valor, mais um encadeamento para descobrir a qual produto ele pertence:

```python
produto1 = 'Oleo'
produto2 = 'Arroz'
produto3 = 'Feijão'

valor1 = float(input(f'Qual é o preço do {produto1}? '))
valor2 = float(input(f'Qual é o preço do {produto2}? '))
valor3 = float(input(f'Qual é o preço do {produto3}? '))

menor = valor1 if valor1 < valor2 and valor1 < valor3 else (valor2 if valor2 < valor3 else valor3)

if valor1 == menor:
    print(f'O produto mais barato é {produto1}')
elif valor2 == menor:
    print(f'O produto mais barato é {produto2}')
else:
    print(f'O produto mais barato é {produto3}')
```

### 6. Três números em ordem crescente

Aqui usei uma abordagem diferente: em vez de comparar par a par, joguei os valores em uma lista e ordenei com `sort()`.

```python
x = int(input('Digite um número inteiro: '))
y = int(input('Digite outro número inteiro: '))
z = int(input('Digite mais um número inteiro: '))

numeros = [x, y, z]

numeros.sort()
print(f'Os números digitados em ordem crescente são: {numeros[0]}, {numeros[1]}, {numeros[2]}')
```

O `sort()` ordena a lista no próprio lugar (diferente dos métodos de string, que devolvem uma cópia). Os colchetes com o índice — `numeros[0]` — acessam cada posição, e a contagem começa em zero.

---

## O que ficou de aprendizado

- `and` exige as duas condições verdadeiras; `or` se satisfaz com uma; `not` inverte o resultado.
- `in` verifica pertencimento e funciona também dentro de strings, procurando um trecho de texto.
- O ternário `valor_a if condição else valor_b` resolve escolhas simples em uma linha.
- Ternários aninhados funcionam para três valores, mas o `if/elif/else` costuma ser mais legível.
- `sort()` ordena a lista original, e o acesso por índice começa no zero.

## Referências

- [Operadores booleanos](https://docs.python.org/3/library/stdtypes.html#boolean-operations-and-or-not)
- [Testes de pertencimento](https://docs.python.org/3/reference/expressions.html#membership-test-operations)
