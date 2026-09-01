# Estudo — Introdução ao Python
**Data:** DD/MM/AAAA

**Projeto:** Python para Data Science — [Alura](https://www.alura.com.br/)

---

## 🐍 Python — a linguagem de estudo

- Conheci o Python como a linguagem que vou usar na trilha de dados.
- Entendi que ela é interpretada, ou seja, o código é executado linha por linha.
- Fixei que não preciso declarar tipos: a própria linguagem identifica o tipo do dado.
- Compreendi que a leitura do código é próxima do inglês comum, o que reduz a curva inicial.

## 🖥️ Google Colaboratory — ambiente de trabalho

- Estudei o [Google Colaboratory](https://colab.research.google.com/) como ambiente de notebooks rodando no navegador.
- Entendi que não preciso instalar nada na máquina, porque a execução acontece nos servidores do Google.
- Fixei que o arquivo fica salvo no Google Drive e pode ser compartilhado como um documento.
- Compreendi que o notebook é a ferramenta padrão em Data Science porque une código, resultado e explicação no mesmo arquivo.

## 🧱 Células — a unidade do notebook

- Aprendi que o notebook é dividido em células independentes.
- Entendi que a célula de código recebe comandos em Python e mostra o resultado logo abaixo.
- Entendi que a célula de texto recebe anotações escritas em Markdown.
- Testei criar, mover e apagar células dentro do notebook.
- Fixei que `Shift + Enter` executa a célula e avança para a próxima.

## ⚠️ Ordem de execução

- Entendi que o notebook guarda o estado do que já foi executado.
- Aprendi que posso rodar as células fora de ordem, mas isso muda o resultado.
- Fixei que uma variável criada em uma célula continua existindo nas outras.
- Compreendi que, se eu pular uma célula, a seguinte pode falhar por falta do dado anterior.

## 🖨️ `print()` — primeiro comando

- Executei meu primeiro código em Python com a função [`print()`](https://docs.python.org/3/library/functions.html#print).
- Entendi que ela exibe na tela o valor colocado entre parênteses.
- Fixei que texto precisa estar entre aspas, simples ou duplas.

```python
print("Hello Word")
```

```
Hello Word
```

- Entendi que, sem as aspas, o Python leria aquilo como nome de variável e devolveria erro.

## 🔢 Imprimindo números

- Aprendi que número não leva aspas dentro do `print()`.

```python
print(10)
```

```
10
```

- Fixei a diferença: `10` é um número que entra em contas, `"10"` é um texto.

## ➕ Vários valores no mesmo `print()`

- Aprendi que o `print()` aceita mais de um valor, separados por vírgula.
- Entendi que ele exibe todos na mesma linha e insere um espaço automático entre eles.

```python
print('Breno', 24)
```

```
Breno 24
```

- Fixei que posso misturar texto e número na mesma chamada, sem converter nada.

## 💡 Conceitos que fixei

- O notebook é dividido em células independentes.
- Célula de código executa, célula de texto documenta.
- A ordem de execução importa, porque o notebook guarda estado.
- `print()` é a forma de mostrar informação na tela.
- Texto vai entre aspas, número vai sem aspas.
- A vírgula dentro do `print()` exibe vários valores de tipos diferentes.

## 🧾 Resumo final

Hoje entendi como funciona o ambiente onde vou estudar. O Colab organiza o trabalho em células, executa cada uma separadamente e mantém na memória tudo o que já foi rodado. Meu primeiro comando foi o `print()`, que exibe valores na tela e aceita texto, número ou vários valores de uma vez.

## 🚧 Próximos passos

- Estudar variáveis e como guardar valores na memória.
- Entender as regras de nomenclatura de variáveis.
- Conhecer os tipos básicos: `int`, `float`, `str` e `bool`.
- Aprender a verificar o tipo de um dado com `type()`.
