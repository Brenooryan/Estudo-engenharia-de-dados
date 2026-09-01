# Estudo — Coletando dados
**Data:** DD/MM/AAAA

**Projeto:** Python para Data Science — [Alura](https://www.alura.com.br/)

---

## ⌨️ A função `input()`

- Estudei a função [`input()`](https://docs.python.org/3/library/functions.html#input) como forma de coletar valores da pessoa usuária.
- Entendi que ela exibe uma mensagem, pausa a execução e espera algo ser digitado.
- Fixei que o valor digitado precisa ser atribuído a uma variável para não se perder.
- Compreendi que o texto dentro dos parênteses é opcional, mas é o que orienta quem está usando o programa.

```python
nome = input('Escreva seu nome: ')
```

## 📝 O retorno é sempre uma string

- Este é o ponto central do tema.
- Entendi que, independentemente do que for digitado, o `input()` devolve uma `str`.
- Fixei que digitar `2023` guarda o texto `'2023'`, e não o número.
- Confirmei isso usando `type()` sobre a variável coletada.

```python
ano_entrada = input('Escreva o ano de ingresso do(a) estudante: ')
type(ano_entrada)
```

```
<class 'str'>
```

## ⚠️ O risco de esquecer a conversão

- Entendi que tentar fazer conta com o texto pode gerar erro.
- Percebi um caso pior: `'2023' * 2` devolve `'20232023'`, porque multiplicar string repete o texto.
- Fixei que esse tipo de falha é silenciosa, já que o programa roda e entrega um resultado errado.
- Compreendi que conferir o tipo antes de calcular evita esse problema.

## 🔄 Convertendo tipos

- Aprendi as funções de conversão: [`int()`](https://docs.python.org/3/library/functions.html#int), [`float()`](https://docs.python.org/3/library/functions.html#float), [`str()`](https://docs.python.org/3/library/functions.html#func-str) e [`bool()`](https://docs.python.org/3/library/functions.html#bool).
- Entendi que posso envolver o `input()` na conversão, resolvendo tudo em uma linha.
- Fixei o critério de escolha: ano de ingresso é `int`, nota e média pedem `float`.

```python
ano_entrada = int(input('Escreva o ano de ingresso do(a) estudante: '))
type(ano_entrada)
```

```
<class 'int'>
```

## 🖨️ Formatando a saída com f-strings

- Aprendi a apresentar o resultado misturando texto e valores não textuais.
- Fixei a estrutura: um `f` antes das aspas e as variáveis entre chaves.
- Entendi que dentro das chaves cabe qualquer expressão, não apenas o nome de uma variável.
- Compreendi que a formatação de casas decimais também entra ali, como no `{media:.2f}`.

```python
nota_entrada = float(input('Digite a nota do teste de ingresso: '))
print(f'Ano de entrada: {ano_entrada} - nota do teste de ingresso: {nota_entrada}')
```

## 🧮 Exercício — calculadora com operação escolhida

- Coletei dois números e o sinal da operação.
- Converti os números para `float` e deixei o sinal como texto.
- Entendi que isso está correto, porque o sinal é um caractere e será comparado com `'+'`.

```python
x = float(input('Digite um número: '))
z = str(input(''))
y = float(input('Digite outro número: '))

if z == '+':
    print(x + y)
```

## 🔠 Exercício — frase em maiúsculas

- Juntei o que vi em strings com a coleta de dados.
- Apliquei o `upper()` sobre a frase digitada e guardei o resultado.
- Percebi que o `str()` ali é redundante, já que o `input()` devolve string, mas deixa o tipo explícito.

```python
frase = str(input('Digite uma frase: '))
frase = frase.upper()

print(frase)
```

## 💡 Conceitos que fixei

- `input()` sempre devolve `str`, mesmo quando o digitado parece número.
- Esquecer a conversão pode gerar erro ou, pior, um resultado errado sem aviso.
- A conversão pode envolver o `input()` na mesma linha.
- `int()`, `float()`, `str()` e `bool()` fazem a conversão entre tipos.
- `type()` confirma o que está realmente guardado antes do cálculo.
- f-string mistura texto e variáveis de forma direta e legível.

## 🧾 Resumo final

Hoje aprendi a receber dados de quem usa o programa. O `input()` sempre entrega texto, então a conversão para o tipo certo é parte obrigatória da coleta, e não um detalhe. Também passei a usar f-strings para montar a saída, combinando texto e variáveis em uma única linha.

## 🚧 Próximos passos

- Estudar estruturas condicionais com `if` e `else`.
- Entender o papel da indentação em Python.
- Conhecer o `elif` para encadear várias condições.
