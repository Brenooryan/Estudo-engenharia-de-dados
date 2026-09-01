# 01 — Introdução ao Python

> Curso **Python para Data Science** — [Alura](https://www.alura.com.br/)

Primeiro contato com a linguagem e com o ambiente de estudo, terminando no primeiro código executado.

---

## Google Colaboratory

O [Google Colaboratory](https://colab.research.google.com/) (Colab) é um ambiente de notebooks que roda no navegador, sem instalação de nada na máquina. O código é executado nos servidores do Google e o arquivo fica salvo no Google Drive.

Um notebook é organizado em **células**, e existem dois tipos:

| Tipo | Para que serve |
|---|---|
| **Código** | Recebe comandos em Python e mostra o resultado logo abaixo da célula |
| **Texto** | Recebe anotações escritas em Markdown (títulos, listas, links, negrito) |

Isso é o que torna o notebook útil em Data Science: análise e explicação ficam no mesmo arquivo, na ordem em que o raciocínio acontece.

**O que testei na prática:**

- criar células novas de código e de texto;
- mover uma célula de posição dentro do notebook;
- executar uma célula com `Shift + Enter` (executa e vai para a próxima) ou pelo botão de play;
- reexecutar células fora de ordem — e perceber que a ordem de execução importa, porque o notebook guarda o estado do que já foi rodado.

## Primeiro código: a função `print()`

A função [`print()`](https://docs.python.org/3/library/functions.html#print) exibe na tela o valor que for colocado entre parênteses.

```python
print("Hello Word")
```

```
Hello Word
```

O texto precisa estar entre aspas (simples ou duplas). Sem aspas, o Python entenderia que é o nome de uma variável e devolveria um erro.

### Imprimindo números

Números **não** levam aspas:

```python
print(10)
```

```
10
```

A diferença é importante: `10` é um número com o qual dá para fazer contas, e `"10"` seria um texto.

### Imprimindo vários valores de uma vez

O `print()` aceita mais de um valor, separados por vírgula. Ele exibe todos na mesma linha, inserindo automaticamente um espaço entre eles:

```python
print('Breno', 24)
```

```
Breno 24
```

Aqui foram misturados um texto e um número na mesma chamada, sem precisar converter nada.

---

## O que ficou de aprendizado

- Notebook é dividido em células independentes, e o resultado aparece logo abaixo de cada uma.
- Célula de texto serve para documentar; célula de código serve para executar.
- `print()` é a forma de mostrar informação na tela.
- Texto vai entre aspas; número vai sem aspas.
- Vírgula dentro do `print()` permite exibir vários valores de tipos diferentes de uma vez.

## Referências

- [Documentação oficial do Python](https://docs.python.org/3/)
- [Função `print()`](https://docs.python.org/3/library/functions.html#print)
