# Estudo — Variáveis
**Data:** DD/MM/AAAA

**Projeto:** Python para Data Science — [Alura](https://www.alura.com.br/)

---

## 📦 Variáveis — guardando informação

- Entendi que variável é um nome que aponta para um valor guardado na memória.
- Aprendi que ela é criada no momento em que recebe um valor, sem declaração prévia.
- Fixei a estrutura: nome da variável, sinal de igual e o valor.
- Compreendi que trabalhar com variáveis é essencial em Data Science, porque lido com muitos dados ao mesmo tempo.

```python
idade = 5
print(idade)
```

```
5
```

## 🟰 O sinal de igual

- Entendi que o `=` não significa igualdade matemática.
- Fixei que ele é o operador de atribuição: guarda o valor da direita no nome da esquerda.
- Aprendi que a leitura correta é "recebe", e não "é igual a".

## 🔁 Reatribuição

- Aprendi que o valor de uma variável pode ser trocado a qualquer momento.
- Entendi que o valor antigo simplesmente deixa de existir.
- Fixei que a variável sempre guarda apenas o último valor atribuído.

```python
idade = 10
print(idade)
```

```
10
```

## 👀 Exibir o valor

- Aprendi que, no notebook, escrever só o nome da variável já mostra o valor.
- Entendi que isso funciona apenas na última linha da célula.
- Fixei que o `print()` funciona em qualquer posição, inclusive dentro de condicionais e laços.

## 🚫 Nomes que não posso usar

- Aprendi que o nome não pode começar com número, como `10_notas`.
- Aprendi que o nome não pode ter espaço, como `Nome escola`.
- Entendi que usar nomes de funções do Python, como `print` ou `type`, quebra a função original.
- Fixei que o padrão adotado é `snake_case`: tudo minúsculo com underline separando as palavras.
- Compreendi que nome descritivo é o que mantém o código legível: `media_aluno` diz muito mais que `m`.

## 🔠 Maiúsculas e minúsculas

- Entendi que o Python diferencia maiúsculas de minúsculas nos nomes.
- Fixei que `idade`, `Idade` e `IDADE` são três variáveis diferentes.
- Aprendi que o underline também pode compor nomes válidos, como `_idade` e `_idade_`.

```python
idade = 1
Idade = 2
IDADE = 3
_idade = 4
_idade_ = 5
print(idade, Idade, IDADE, _idade, _idade_)
```

```
1 2 3 4 5
```

## 🏷️ Tipos de variáveis

- Entendi que cada variável pertence a uma classe, definida pelo tipo do dado atribuído.
- Aprendi a consultar essa classe com a função [`type()`](https://docs.python.org/3/library/functions.html#type).
- Fixei os quatro tipos básicos: `int`, `float`, `str` e `bool`.
- Compreendi que `int` é número inteiro e `float` é número com casa decimal.
- Fixei que decimal em Python usa **ponto**, não vírgula.
- Entendi que booleano aceita apenas `True` ou `False`, com inicial maiúscula e sem aspas.

```python
i = 5
type(i)      # int

f = 9.8
type(f)      # float

s = "Breno"
type(s)      # str
```

- Fixei um ponto de atenção: `8.45` é número e `'8.45'` é texto, e só o primeiro entra em uma conta.

## 🧾 Aplicação — ficha do aluno em variáveis

- Trabalhei a situação de transformar a ficha de um estudante em variáveis.
- Entendi que cada informação da ficha vira uma variável do tipo correspondente.
- Fixei que isso é o mesmo que acontece em um conjunto de dados: cada coluna tem seu tipo.
- Compreendi que o tipo determina o que consigo fazer com aquele dado depois.

```python
nome_aluno = "Fabricio Daniel"
idade_aluno = 15
media_aluno = 8.45
situacao_aprovado = True

print(nome_aluno, idade_aluno, media_aluno, situacao_aprovado)
```

```
Fabricio Daniel 15 8.45 True
```

- Refiz o exercício coletando a média digitada e decidindo a situação a partir dela, em vez de deixá-la fixa.

## 💡 Conceitos que fixei

- Variável é criada pela atribuição, sem declaração de tipo.
- O `=` atribui um valor, não compara.
- A variável guarda apenas o último valor recebido.
- Nome não começa com número nem tem espaço.
- Python diferencia maiúsculas de minúsculas.
- O tipo é definido pelo dado e consultado com `type()`.
- Decimal usa ponto; booleano é `True` ou `False`, sem aspas.
- Número entre aspas vira texto e deixa de servir para cálculo.

## 🧾 Resumo final

Hoje entendi que variável é o mecanismo básico para guardar e reutilizar informação. O tipo não é declarado por mim: ele vem do dado atribuído, e posso conferi-lo com `type()`. Também fixei as regras de nomenclatura e percebi, na prática da ficha do aluno, que transformar dados em variáveis com o tipo correto é o primeiro passo de qualquer análise.

## 🚧 Próximos passos

- Estudar operações aritméticas com `int` e `float`.
- Entender a diferença entre média simples e média ponderada.
- Aprender a formatar casas decimais na exibição de resultados.
