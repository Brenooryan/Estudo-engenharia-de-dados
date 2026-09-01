# 02 — Variáveis

> Curso **Python para Data Science** — [Alura](https://www.alura.com.br/)

Como guardar informações na memória para reutilizá-las depois — a base de qualquer análise de dados.

---

## Criando uma variável

Uma variável é criada no momento em que um valor é atribuído a ela. A estrutura é: nome da variável, sinal de igual (`=`) e o valor.

```python
idade = 5
print(idade)
```

```
5
```

O sinal `=` aqui **não** significa igualdade matemática: ele é o operador de atribuição, que guarda o valor da direita no nome da esquerda.

### Reatribuição

O valor de uma variável pode ser trocado a qualquer momento. O valor antigo simplesmente deixa de existir:

```python
idade = 10
print(idade)
```

```
10
```

### Exibir com `print()` ou só com o nome

Dentro de um notebook, escrever apenas o nome da variável na última linha da célula já mostra o valor:

```python
idade = 15
idade
```

```
15
```

A diferença é que isso só funciona para a **última** linha de uma célula. O `print()` funciona em qualquer lugar, inclusive dentro de laços e condicionais.

## Regras para nomear variáveis

Nomes que **não** podem ser usados:

- **Começar com número** — `10_notas`, `2_nomes_casa`
- **Ter espaço no meio** — `Nome escola`, `notas estudantes` (o certo é `nome_escola`)
- **Usar nomes de funções do Python** — `print`, `type` (funciona, mas quebra a função original)

Além disso, o Python diferencia maiúsculas de minúsculas. Cada um destes nomes é uma variável **diferente**:

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

Na prática, o padrão adotado é `snake_case`: tudo minúsculo com underline separando as palavras (`media_aluno`, `total_funcionarios`). Nome bom é nome que descreve o conteúdo — `m` não diz nada, `media_aluno` diz.

## Tipos de variáveis

Cada valor guardado pertence a uma classe, que depende do tipo de dado atribuído. A função [`type()`](https://docs.python.org/3/library/functions.html#type) revela essa classe:

```python
i = 5
type(i)      # int   — número inteiro

f = 9.8
type(f)      # float — número com casas decimais

s = "Breno"
type(s)      # str   — texto (string)
```

Os quatro tipos básicos vistos:

| Tipo | Classe | Exemplo | Observação |
|---|---|---|---|
| Inteiro | `int` | `15` | Números sem casa decimal |
| Decimal | `float` | `8.45` | Usa **ponto**, não vírgula |
| Texto | `str` | `'Fabricio'` | Sempre entre aspas |
| Booleano | `bool` | `True` / `False` | Maiúscula na primeira letra, sem aspas |

Ponto de atenção: `8.45` é um número, enquanto `'8.45'` é um texto. Parecem iguais na tela, mas só o primeiro entra em uma conta.

## Aplicação: transformando uma ficha em variáveis

Situação trabalhada — a ficha do aluno abaixo precisava virar código:

- Nome: Fabricio Daniel
- Idade: 15 anos
- Média do semestre: 8,45
- Situação de aprovação: verdadeira

Cada informação vira uma variável do tipo correspondente:

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

É exatamente isso que acontece em um conjunto de dados: cada coluna tem seu tipo, e o tipo determina o que é possível fazer com a informação.

### Versão com dado do usuário

Depois refiz o exercício coletando a média digitada e decidindo a situação a partir dela, em vez de deixá-la fixa:

```python
nome_aluno2 = 'Fabricio Daniel'
idade_aluno2 = 15
media_semestre = float(input("Digite a média do semestre: "))
sit_aprov = True

if media_semestre >= 6:
    sit_aprov = True
else:
    sit_aprov = False

print(nome_aluno2, idade_aluno2, media_semestre,
      'Aprovado' if sit_aprov else 'Reprovado')
```

---

## O que ficou de aprendizado

- Variável é criada pela atribuição; não existe declaração de tipo antes.
- O tipo é definido pelo dado atribuído e pode ser consultado com `type()`.
- Python diferencia maiúsculas de minúsculas nos nomes.
- Decimais usam ponto; booleanos são `True` e `False`, sem aspas.
- Nome descritivo em `snake_case` é o que mantém o código legível.

## Referências

- [Função `type()`](https://docs.python.org/3/library/functions.html#type)
- [Tipos built-in do Python](https://docs.python.org/3/library/stdtypes.html)
