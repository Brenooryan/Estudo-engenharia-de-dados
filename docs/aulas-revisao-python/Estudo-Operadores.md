# Estudo — Operadores
**Data:** DD/MM/AAAA

**Projeto:** Python para Data Science — [Alura](https://www.alura.com.br/)

---

## 🧠 Por que operadores lógicos

- Entendi que às vezes a expressão condicional precisa de mais de uma verificação ao mesmo tempo.
- Aprendi que os operadores lógicos são o que permite combinar essas verificações.
- Fixei que eles aparecem quase sempre acompanhando o `if`.
- Compreendi três termos da documentação: expressão lógica é a declaração que pode ser verdadeira ou falsa, operandos são os elementos comparados e operadores são o que combina tudo em uma expressão só.

## 🔗 `AND`

- Aprendi que o `and` verifica se duas condições são verdadeiras.
- Fixei que `x and y` resulta em `True` apenas se **ambas** forem verdadeiras.
- Entendi que basta uma condição falsa para a expressão inteira ser falsa.

```python
t1 = t2 = True
f1 = f2 = False

if t1 and t2:
  print('expressão verdadeira')
else:
  print('expressão falsa')
```

```
expressão verdadeira
```

- Notei também a atribuição múltipla `t1 = t2 = True`, que dá o mesmo valor a duas variáveis de uma vez.

## 🔀 `OR`

- Aprendi que o `or` verifica se pelo menos uma das condições é verdadeira.
- Fixei que `x or y` resulta em `True` se ao menos uma delas for verdadeira.
- Entendi que ele só é falso quando as duas condições são falsas.

```python
if t1 or f2:
  print('expressão verdadeira')
else:
  print('expressão falsa')
```

```
expressão verdadeira
```

## 🚫 `NOT`

- Aprendi que o `not` nega uma condição.
- Fixei que `not x` é `True` quando `x` é falso, e `False` quando `x` é verdadeiro.
- Entendi que ele inverte o resultado, então `not True` cai no `else`.

```python
if not t1:
  print('expressão verdadeira')
else:
  print('expressão falsa')
```

```
expressão falsa
```

## 📊 Tabela verdade que montei

| `x` | `y` | `x and y` | `x or y` | `not x` |
|:---:|:---:|:---:|:---:|:---:|
| `True` | `True` | `True` | `True` | `False` |
| `True` | `False` | `False` | `True` | `False` |
| `False` | `True` | `False` | `True` | `True` |
| `False` | `False` | `False` | `False` | `True` |

## 🔍 `IN` — pertencimento

- Aprendi que o `in` verifica se um elemento está presente em um conjunto.
- Fixei que `x in y` resulta em `True` se `x` estiver dentro de `y`.
- Entendi que ele funciona com listas, tuplas e também com strings.

## 📋 Situação — conferindo a lista de aprovados

- A escola distribuiu os nomes dos aprovados como um texto único.
- Precisei verificar se alguns nomes estavam nessa lista.
- Usei o `in` dentro de um `if` para fazer a checagem.

```python
nome_1 = 'Mariana Rodrigues'

if nome_1 in lista:
    print(f'O nome {nome_1} está na lista.')
else:
    print(f'O nome {nome_1} não está na lista.')
```

```
O nome Mariana Rodrigues está na lista.
```

- Entendi que, como a lista é uma string, o `in` procura o trecho de texto dentro dela.
- Fixei a limitação disso: um nome parcial como `'Maria'` também retornaria `True`, por estar contido em `'Maria Oliveira'`.

## ⚡ Operador ternário

- Aprendi a forma compacta de escrever um `if/else` em uma única linha.
- Fixei a estrutura: `valor_a if condição else valor_b`.
- Entendi a leitura: use `x` se a condição for verdadeira, senão use `y`.
- Compreendi que o resultado da expressão é atribuído diretamente à variável.

```python
maior = x if x > y else y
```

## 🧮 Exercício — maior de dois números

- Coletei dois números e usei o ternário para guardar o maior deles.

```python
x = float(input('Digite um número inteiro: '))
y = float(input('Digite um número inteiro: '))

maior = x if x > y else y

print(f'O maior número digitado foi: {maior}')
```

## 📈 Exercício — crescimento da empresa

- Tratei três saídas possíveis com `if / elif / else`.
- Entendi que o `else` cobre o caso do zero sem precisar de comparação.

```python
num = float(input('Informe o percentual de crescimento da empresa: '))

if num > 0:
    print('A empresa teve crescimento.')
elif num < 0:
    print('A empresa teve declínio.')
else:
    print('A empresa não teve variação.')
```

## 🔤 Exercício — vogal ou consoante

- Usei o `in` com uma string de vogais.
- Fixei que isso ficou bem mais enxuto que cinco comparações ligadas por `or`.

```python
letra = input('Digite uma letra: ')

if letra in 'aeiou':
    print('A letra digitada é uma vogal.')
else:
    print('A letra digitada é uma consoante.')
```

## 💰 Exercício — maior faturamento anual

- Combinei ternário aninhado com `and` para comparar três valores.

```python
ano1 = 90000
ano2 = 120000
ano3 = 150000

maior = ano1 if ano1 > ano2 and ano1 > ano3 else (ano2 if ano2 > ano3 else ano3)

print(f'O maior faturamento anual foi: {maior}')
```

## 🛒 Exercício — produto mais barato

- Usei a mesma lógica para achar o menor valor.
- Depois encadeei condições para descobrir a qual produto ele pertence.

```python
menor = valor1 if valor1 < valor2 and valor1 < valor3 else (valor2 if valor2 < valor3 else valor3)

if valor1 == menor:
    print(f'O produto mais barato é {produto1}')
elif valor2 == menor:
    print(f'O produto mais barato é {produto2}')
else:
    print(f'O produto mais barato é {produto3}')
```

- Percebi que ternário aninhado funciona, mas o `if/elif/else` fica mais legível.

## 🔢 Exercício — três números em ordem crescente

- Aqui usei uma abordagem diferente das comparações par a par.
- Coloquei os valores em uma lista e ordenei com `sort()`.
- Entendi que o `sort()` ordena a lista no próprio lugar, diferente dos métodos de string.
- Fixei que os colchetes com índice acessam cada posição e que a contagem começa em zero.

```python
numeros = [x, y, z]

numeros.sort()
print(f'Os números digitados em ordem crescente são: {numeros[0]}, {numeros[1]}, {numeros[2]}')
```

## 🔢 Exercício — turnos

- Aqui utilizei uma variavel resp para armazenar a `string()`.
- Utilizei o `if()` para iniciar uma condição.
- Usei o `in()` para verificar se a variável resp pertence a uma das condições.
- Utilizei o `elif` adicionar mais condições ao código.

```python
resp = (input('Qual turno você esta?'))

if resp in ('manha', 'Manha'):
    print('Bom dia')
elif resp in ('tarde', 'Tarde'):
    print('Boa tarde')
elif resp in ('noite', 'Noite'):
    print('Boa noite')
else:
    print('Invalido!')
```

## 🔢 Exercício — Verifica numero par

- Aqui utilizei uma variavel num para armazenar um `int()`.
- Utilizei o `if()` para iniciar uma condição.
- Usei o operador módulo `%` para criar um condição que quando o `num() / 2 der resto 0`, ele é par.

```python
num = int(input('Digite um número inteiro: '))

if num % 2 == 0:
    print('O número digitado é par.')
else:
    print('O número digitado é ímpar.')
```

## 🔢 Exercício — Verifica decimal

- Aqui utilizei uma variavel num para armazenar um `float()`.
- Utilizei o `if()` para iniciar uma condição.
- Usei o operador módulo `%` para criar um condição que quando o `num / 1` e resto diferente `!=` de 0, ele é decimal.

```python
num = float(input('Digite um número: '))

if num % 1 != 0:
    print('O número digitado é decimal.')
else:
    print('O número digitado é inteiro.')
```

## 💡 Conceitos que fixei

- `and` exige as duas condições verdadeiras.
- `or` se satisfaz com uma condição verdadeira.
- `not` inverte o resultado da condição.
- `in` verifica pertencimento e também procura trecho dentro de string.
- Buscar nome dentro de uma string casa com partes do texto, e isso pode dar falso positivo.
- O ternário resolve escolhas simples em uma linha.
- Ternário aninhado funciona, mas o `if/elif/else` é mais legível.
- `sort()` altera a lista original, e o índice começa em zero.

## 🧾 Resumo final

Hoje aprendi a montar condições mais elaboradas. Os operadores lógicos combinam verificações em uma única expressão, o `in` checa se um elemento está dentro de um conjunto e o ternário resume um `if/else` simples em uma linha. Nos exercícios percebi que quase sempre existe mais de um caminho para o mesmo resultado, e que o mais curto nem sempre é o mais legível.

## 🚧 Próximos passos

- Estudar estruturas de repetição.
- Entender o laço `while` e sua condição de parada.
- Estudar o laço `for` e a função `range()`.
- Entender a diferença entre repetir enquanto uma condição é verdadeira e percorrer um conjunto de elementos.
- Estudar estruturas de dados, começando por listas.
- Entender índices positivos e negativos no acesso aos elementos.
- Ver como percorrer uma lista item a item com um laço `for`.
