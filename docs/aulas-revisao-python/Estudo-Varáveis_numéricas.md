# Estudo — Variáveis numéricas
**Data:** DD/MM/AAAA

**Projeto:** Python para Data Science — [Alura](https://www.alura.com.br/)

---

## 🔢 `int` e `float`

- Estudei os dois tipos numéricos usados no dia a dia: `int` e `float`.
- Entendi que `int` guarda números inteiros, como `5`, `16` e `3000`.
- Entendi que `float` guarda números com casa decimal, separada por ponto.
- Fixei que os dois se misturam livremente nas operações.
- Aprendi que a divisão com `/` sempre devolve um `float`, mesmo quando o resultado é exato.

## ➗ Operadores aritméticos

- Usei `+` para soma, `-` para subtração, `*` para multiplicação e `/` para divisão.
- Entendi que a ordem de precedência segue a matemática: multiplicação e divisão antes de soma e subtração.
- Fixei que parênteses forçam a ordem quando preciso mudar esse comportamento.

## 🏫 Situação — folha de pagamento da escola

- Recebi uma tabela com cargo, quantidade de pessoas e salário correspondente.
- Precisei calcular o total de empregados, a diferença entre o menor e o maior salário, e a média ponderada da faixa salarial.

| Cargo | Quantidade | Salário |
|---|---|---|
| Segurança | 5 | 3000 |
| Docente | 16 | 6000 |
| Diretoria | 1 | 12500 |

## 🗂️ Guardando os dados

- Criei uma variável para cada informação da tabela.
- Entendi que prefixos ajudam a organizar quando o número de variáveis cresce.
- Fixei o padrão que usei: `q_` para quantidade e `s_` para salário.

```python
q_seguranca = 5
s_seguranca = 3000

q_docente = 16
s_docente = 6000

q_diretoria = 1
s_diretoria = 12500
```

## 👥 Total de funcionários

- Somei as três quantidades para obter o total de pessoas empregadas.

```python
total_funcionarios = q_seguranca + q_docente + q_diretoria
print(total_funcionarios)
```

```
22
```

## 📉 Diferença salarial

- Subtraí o menor salário do maior para encontrar a amplitude da faixa.

```python
dif_sal = s_diretoria - s_seguranca
print(dif_sal)
```

```
9500
```

## ⚖️ Média ponderada

- Entendi que a média simples dos três salários daria um resultado errado.
- Compreendi o motivo: ela ignora que existem 16 docentes e apenas 1 pessoa na diretoria.
- Fixei que o peso de cada salário é a quantidade de pessoas que o recebem.
- Aprendi a fazer o cálculo em duas etapas: primeiro o gasto de cada cargo, depois a soma dividida pelo total.

```python
sal_seguranca = q_seguranca * s_seguranca
sal_docente = q_docente * s_docente
sal_diretoria = q_diretoria * s_diretoria

soma_sal = sal_diretoria + sal_docente + sal_seguranca

media_sal = soma_sal / total_funcionarios

print(f"{media_sal:.2f}")
```

```
5795.45
```

- Comparei os dois resultados: a média simples daria 7166,67, quase 1400 acima da realidade da folha.
- Fixei que a escolha da métrica muda a conclusão da análise.

## 🎯 Formatando casas decimais

- Aprendi a limitar as casas decimais dentro de uma f-string.
- Entendi a sintaxe `{variavel:.2f}`: o `.2` define a quantidade de casas e o `f` indica ponto flutuante.
- Fixei que a formatação afeta apenas a exibição, e a variável continua guardando o valor completo.

## 🧩 Organização do cálculo

- Entendi a vantagem de quebrar a conta em variáveis intermediárias.
- Fixei que isso facilita conferir onde um erro apareceu.
- Compreendi que um cálculo longo escrito em uma linha só é difícil de depurar.

## 💡 Conceitos que fixei

- `int` e `float` se misturam nas operações e o resultado vira `float`.
- Divisão com `/` sempre retorna `float`.
- Média ponderada exige multiplicar cada valor pelo seu peso antes de dividir.
- Média simples e média ponderada levam a conclusões diferentes.
- `{valor:.2f}` controla as casas decimais só na exibição.
- Variáveis intermediárias tornam o cálculo mais fácil de conferir.

## 🧾 Resumo final

Hoje apliquei operações aritméticas em um caso real de folha de pagamento. O ponto principal foi entender que a média correta ali é a ponderada, porque cada salário representa um número diferente de pessoas. Também aprendi a formatar o resultado com duas casas decimais, sem alterar o valor guardado na variável.

## 🚧 Próximos passos

- Estudar strings e como o Python trata texto.
- Conhecer os métodos de limpeza e padronização de texto.
- Entender o conceito de imutabilidade das strings.
