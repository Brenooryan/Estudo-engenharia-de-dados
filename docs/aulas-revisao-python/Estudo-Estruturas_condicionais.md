# Estudo — Estruturas condicionais
**Data:** DD/MM/AAAA

**Projeto:** Python para Data Science — [Alura](https://www.alura.com.br/)

---

## 🔀 `IF` — tomando decisões

- Entendi que `if` significa "se" e forma uma estrutura condicional.
- Aprendi que ele verifica se uma condição é verdadeira ou falsa.
- Fixei que o bloco de código só é executado quando a condição resulta em verdadeiro.

```python
if 2 < 7:
    print('Verdadeiro')
```

```
Verdadeiro
```

## 📐 Sintaxe obrigatória

- Aprendi que a linha da condição termina com dois pontos.
- Entendi que a indentação define o que está dentro do `if`.
- Fixei que o recuo não é estilo: em Python, ele faz parte da lógica da linguagem.
- Compreendi que outras linguagens fazem isso com chaves, e o Python usa o próprio recuo.

## ↔️ `ELSE` — o caso contrário

- Aprendi que o `else` complementa o `if`.
- Entendi que ele é executado quando a condição é avaliada como `False`.
- Fixei que o `else` não recebe condição, porque cobre todo o resto dos casos.

## 🎓 Situação — aprovação de estudantes

- Recebi a média de um estudante e precisei decidir entre aprovado e reprovado.
- A regra: média igual ou superior a 6.0 aprova.

```python
media = float(input('Digite a média: '))

if media >= 6:
    print('Aprovado')
else:
    print('Reprovado')
```

## ⚠️ Vários `if` independentes

- A instituição criou uma terceira situação: média entre 4.0 e 6.0 vai para recuperação.
- Minha primeira tentativa foi encadear três `if` separados.
- Entendi que funciona, mas cada `if` é avaliado de forma independente.
- Percebi que o Python testa todas as condições mesmo depois de já ter achado a resposta.
- Fixei o risco: se as condições não forem bem escritas, mais de um bloco executa e o programa imprime respostas contraditórias.

```python
media = float(input('Digite a média: '))

if media >= 6:
    print('Aprovado')
if 6.0 > media >= 4.0:
    print('Recuperação')
if media < 4.0:
    print('Reprovado')
```

## 🔗 Comparação encadeada

- Aprendi que posso escrever `6.0 > media >= 4.0` em uma única expressão.
- Entendi que isso significa "menor que 6 e maior ou igual a 4".
- Fixei que o Python entende essa forma naturalmente, sem precisar do `and`.

## 🪜 `ELIF`

- Aprendi que `elif` significa "senão, se" e é a união do `else` com o `if`.
- Entendi que ele permite verificar várias condições de forma encadeada.
- Fixei que as condições são avaliadas em ordem, de cima para baixo.
- Compreendi que, assim que uma resulta em verdadeiro, o restante da estrutura é ignorado.
- Entendi que o `else` final entra em ação quando nenhuma condição foi satisfeita.

```python
media = float(input('Digite a média: '))

if media >= 6:
    print('Aprovado')
elif 6.0 > media >= 4.0:
    print('Recuperação')
else:
    print('Reprovado')
```

- Percebi que essa versão é mais curta e mais segura que a anterior.
- Fixei o motivo: as três situações ficam mutuamente exclusivas por construção, e não por sorte na escrita.

## 🧮 Operadores de comparação

- Usei `>`, `<`, `>=`, `<=`, `==` e `!=` para montar as condições.
- Entendi que `==` compara dois valores e `!=` verifica se são diferentes.
- Fixei a confusão mais comum: `=` atribui um valor, `==` compara.
- Aprendi que usar `=` dentro de um `if` gera erro de sintaxe.

## 💡 Conceitos que fixei

- `if` executa um bloco só quando a condição é verdadeira.
- `else` cobre o caso contrário e não recebe condição.
- Dois pontos e indentação são exigência da linguagem.
- Vários `if` soltos são avaliados de forma independente.
- `elif` para na primeira condição verdadeira e ignora o resto.
- Python aceita comparação encadeada, como `6.0 > media >= 4.0`.
- `=` atribui, `==` compara.

## 🧾 Resumo final

Hoje entendi como fazer o programa decidir. O `if` executa um bloco quando a condição é verdadeira e o `else` cobre o restante. O aprendizado mais útil foi comparar as duas formas de tratar três situações: com `if` soltos, todas as condições são testadas e o risco de resposta dupla existe; com `elif`, a execução para na primeira verdadeira e a lógica fica correta por construção.

## 🚧 Próximos passos

- Estudar os operadores lógicos `and`, `or` e `not`.
- Entender o operador de pertencimento `in`.
- Conhecer a forma reduzida do `if/else` em uma linha.
