# Estudo — Estruturas de repetição
**Data:** 16/09/2026

**Projeto:** Python para Data Science — [Alura](https://www.alura.com.br/)

---

## 🔁 Por que usar laços

- Entendi que executar o mesmo bloco de comandos várias vezes à mão não é viável.
- Trabalhei a situação de coletar e imprimir a média de duas notas de 3 estudantes.
- Compreendi o problema quando imaginei a mesma tarefa para 100 estudantes.
- Fixei a mudança de raciocínio: não é repetir o mesmo código 100 vezes, e sim executar o mesmo código 100 vezes.
- Aprendi que isso é construído com laços de repetição.

## ⏳ `WHILE` — repetir enquanto a condição for verdadeira

- Estudei o `while` como estrutura que repete um bloco enquanto uma condição for verdadeira.
- Fixei a estrutura: `while condição:` seguido do bloco indentado.
- Entendi que a condição é testada antes de cada volta do laço.

```python
contador = 1

while contador <= 10:
    print(contador)
    contador += 1
```

```
1 2 3 4 5 6 7 8 9 10
```

## ➕ O contador e o `+=`

- Aprendi que o contador precisa ser criado antes do laço.
- Entendi que `contador += 1` é a forma curta de escrever `contador = contador + 1`.
- Fixei que esse incremento é o que faz a condição eventualmente se tornar falsa.
- Compreendi o risco: sem incrementar o contador, a condição nunca muda e o laço roda para sempre.

## 🎓 `while` aplicado às médias

- Coloquei a coleta das notas e o cálculo da média dentro do `while`.
- Entendi que tudo que está indentado dentro do laço se repete a cada volta.
- Fixei que o incremento fica no fim do bloco, para fechar o ciclo.

```python
contador = 1

while contador <= 3:
    nota_1 = float(input('Digite a 1° nota: '))
    nota_2 = float(input('Digite a 2° nota: '))

    print(f'Média: {(nota_1+nota_2)/2}')
    contador += 1
```

## 🔂 `FOR` — percorrer um conjunto

- Estudei o `for` como estrutura que itera sobre um conjunto de elementos.
- Fixei a estrutura: `for elemento in conjunto:`.
- Entendi que o bloco é executado uma vez para cada elemento do conjunto.
- Aprendi que, ao chegar no fim do conjunto, o laço é interrompido sozinho.
- Fixei a principal diferença para o `while`: aqui não preciso criar nem incrementar contador manualmente.

## 🔢 `range()`

- Aprendi que o conjunto pode ser gerado pela função [`range()`](https://docs.python.org/3/library/functions.html#func-range).
- Entendi que ela gera uma sequência de números inteiros.
- Fixei a estrutura: `range(inicio, fim, passo)`.
- Aprendi que, se `inicio` não for informado, o valor padrão é 0.
- Aprendi que, se `passo` não for informado, o valor padrão é 1.
- Fixei o ponto que mais confunde: o `fim` **não** entra na sequência, por isso `range(1, 11)` vai de 1 a 10.

```python
for contador in range(1, 11):
    print(contador)
```

```
1 2 3 4 5 6 7 8 9 10
```

- Refiz o exercício das médias com `for`, e o código ficou menor que a versão com `while`.

```python
for contador in range(1, 4):
    nota_1 = float(input('Digite a 1° nota: '))
    nota_2 = float(input('Digite a 2° nota: '))

    print(f'Média: {(nota_1+nota_2)/2}')
```

## ⚖️ Quando usar `for` e quando usar `while`

- Entendi que uso `for` quando sei quantas repetições vão acontecer.
- Entendi que uso `while` quando a quantidade é indeterminada e depende de uma condição.
- Fixei os exemplos práticos: ler 15 notas é `for`, ler temperaturas até aparecer -273 é `while`.

---

## 🧮 Exercícios resolvidos

### 1) Laço com verificação de número inteiro ou decimal

- Usei um `for` com `range()` para repetir a coleta e classificar cada número digitado.
- Apliquei `num1 % 1 == 0` para identificar se o número é inteiro.

```python
for i in range(1, 3):
    num1 = float(input('Digite um número: '))

    if num1 % 1 == 0:
        print(f'{num1} é inteiro.')
    else:
        print(f'{num1} é decimal.')
```

### 2) Crescimento de colônias de bactérias

- Usei `while` porque a quantidade de dias era desconhecida.
- Fixei que a condição de parada é o momento em que a colônia A alcança a B.
- Entendi o papel do `dias += 1` como contador de voltas do laço.

```python
pa_atual = 4
taxa_a = 0.3

pb_atual = 10
taxa_b = 0.15

dias = 0

while pb_atual >= pa_atual:
    pa_atual += pa_atual * taxa_a
    pb_atual += pb_atual * taxa_b
    dias += 1

print(f"A colonia A ultrapassa o país B em {dias} dias.")
```

### 3) Validação de 15 notas

- Combinei `for` e `while` pela primeira vez.
- Entendi a divisão de papéis: o `for` controla as 15 leituras e o `while` repete enquanto a nota for inválida.
- Fixei que esse é o padrão clássico de validação de entrada.

```python
for i in range(15):
    nota = float(input('Digite a nota: '))

    while nota < 0 or nota > 5:
        print('Nota inválida!')
        nota = float(input('Digite a nota novamente: '))

    print(f'Nota válida: {nota}')
```

### 4) Média de temperaturas até -273°C

- Usei `while` com condição de parada baseada em um valor sentinela.
- Entendi que o valor -273 serve apenas para encerrar a leitura.

```python
temp = 0
cont = 0
while temp != -273:
    temp = float(input('Digite a temperatura: '))

    cont = cont + 1
    média = temp / cont

print(f'A média das temperaturas é: {média}')
```

### 5) Fatorial

- Usei um acumulador iniciado em 1 e multipliquei a cada volta.
- Fixei o `fatorial *= i` como versão curta de `fatorial = fatorial * i`.
- Entendi por que o `range` vai até `num + 1`: o fim é exclusivo.

```python
num = int(input('Digite um número inteiro: '))

fatorial = 1

for i in range(1, num + 1):
    fatorial *= i

print(f'O fatorial de {num} é: {fatorial}')
```

### 6) Tabuada

- Usei `for` com `range(1, 11)` e montei a linha com f-string.
- Entendi que dá para calcular dentro das chaves da f-string, com `{num * i}`.

```python
num = int(input('Digite um número inteiro: '))

for i in range(1, 11):
    print(f'{num} x {i} = {num * i}')
```

### 7) Número primo

- Contei quantos divisores exatos o número tem.
- Fixei a lógica: se o total de divisores for exatamente 2, o número é primo.
- Entendi a ligação com dados: números primos aparecem em criptografia e segurança.

```python
num = int(input('Digite um número inteiro: '))

divisores = 0

for i in range(1, num + 1):
    if num % i == 0:
        divisores += 1

if divisores == 2:
    print(f'O número {num} é primo.')
else:
    print(f'O número {num} não é primo.')
```

### 8) Distribuição de idades por faixa

- Criei um contador para cada faixa etária.
- Usei `while` porque a quantidade de clientes não era informada.
- Entendi um detalhe importante da estrutura: a primeira leitura fica **antes** do laço e a próxima no **fim** do bloco.
- Fixei o motivo: assim, se a primeira idade já for negativa, o programa não entra no laço.
- Percebi que o `elif` dispensa escrever o limite inferior de cada faixa, porque as condições são testadas em ordem.

```python
idade = int(input('Digite a idade: '))

while idade >= 0:
    if idade <= 25:
        cont1 += 1
    elif idade <= 50:
        cont2 += 1
    elif idade <= 75:
        cont3 += 1
    elif idade <= 100:
        cont4 += 1

    idade = int(input('Digite a idade: '))
```

### 9) Apuração de eleição

- Juntei quase tudo do tema: `for` para os 20 votos, `while` para validar, `if/elif` para contabilizar.
- Calculei o percentual de cada resultado e formatei com duas casas decimais.
- Fixei o uso de `{(cand1/20)*100:.2f}%` dentro da f-string.

---

## ⚠️ Pontos para revisar

- **Exercício 2:** usei `0.3` e `0.15` como taxas, mas o enunciado pede 3% e 1,5%, que seriam `0.03` e `0.015`. A lógica do laço está certa, só os valores mudam.
- **Exercício 4:** calculei `média = temp / cont` dentro do laço, o que divide apenas a última temperatura. O correto é acumular a soma (`soma += temp`) e dividir no fim, fora do laço.
- **Exercício 9:** mapeei `voto == 5` como branco e `6` como nulo, mas o enunciado define 5 como nulo e 6 como branco.

## 💡 Conceitos que fixei

- Laço serve para executar o mesmo código várias vezes, não para escrevê-lo várias vezes.
- `while` repete enquanto a condição for verdadeira.
- O contador do `while` precisa ser incrementado, ou o laço nunca termina.
- `contador += 1` é a forma curta de `contador = contador + 1`.
- `for` percorre um conjunto e termina sozinho ao chegar no fim.
- `range(inicio, fim, passo)` gera a sequência, e o `fim` não entra nela.
- Quantidade conhecida pede `for`; quantidade indeterminada pede `while`.
- `for` com `while` dentro é o padrão para validar entrada de dados.
- Acumulador (`soma`, `fatorial`) é criado antes do laço e atualizado a cada volta.

## 🧾 Resumo final

Hoje aprendi a repetir blocos de código em vez de duplicá-los. O `while` roda enquanto uma condição for verdadeira e depende de mim para alterar essa condição; o `for` percorre um conjunto gerado normalmente pelo `range()` e se encerra sozinho. Nos exercícios pratiquei contadores, acumuladores, validação de entrada com laço aninhado e leitura com valor sentinela — padrões que aparecem o tempo todo em tratamento de dados.

## 🚧 Próximos passos

- Estudar estruturas de dados, começando por listas.
- Entender índices positivos e negativos no acesso aos elementos.
- Aprender a particionar listas com `lista[inicio:fim]`.
- Conhecer os métodos `append()`, `extend()` e `remove()`.
- Estudar dicionários e o conceito de chave-valor.
- Ver como percorrer listas e dicionários com `for`.
