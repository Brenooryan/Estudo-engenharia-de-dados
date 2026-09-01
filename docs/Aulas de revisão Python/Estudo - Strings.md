# 04 — Strings

> Curso **Python para Data Science** — [Alura](https://www.alura.com.br/)

Trabalhando com texto e usando métodos para tratar dados sujos antes de inseri-los em um sistema.

---

## O que é uma string

String é um conjunto de caracteres formando um texto. Ela é criada ao atribuir a uma variável um dado entre aspas simples (`'`) ou duplas (`"`) — as duas formas produzem exatamente o mesmo resultado:

```python
s1 = 'Alura'
s2 = "Alura"

print(s1, s2)
print(type(s1), type(s2))
```

```
Alura Alura
<class 'str'> <class 'str'>
```

A escolha entre um tipo de aspas e outro é prática: quando o texto contém um apóstrofo, usar aspas duplas evita conflito (`"L'Oréal"`).

## Métodos

Métodos são funções que pertencem a um objeto e agem sobre ele. A estrutura é:

```
objeto.metodo()
```

Existem métodos que não precisam dos parênteses — é preciso conferir a documentação de cada caso.

## Situação trabalhada

Chegou o nome de uma professora para cadastro, mas com problemas: espaços sobrando nas pontas, letra trocada no sobrenome e caixa inconsistente.

```python
texto = '  Geovana Alessandra dias Sanyos '
```

O objetivo era chegar em:

```
'GEOVANA ALESSANDRA DIAS SANTOS'
```

### [`str.upper()`](https://docs.python.org/3/library/stdtypes.html#str.upper)

Converte a string para maiúsculas.

```python
texto.upper()
```

```
'  GEOVANA ALESSANDRA DIAS SANYOS '
```

### [`str.lower()`](https://docs.python.org/3/library/stdtypes.html#str.lower)

Converte a string para minúsculas. Muito usado para padronizar dados antes de comparar textos, já que `'Ana'` e `'ana'` são diferentes para o Python.

```python
texto.lower()
```

### [`str.strip()`](https://docs.python.org/3/library/stdtypes.html#str.strip)

Remove os espaços em branco do início e do fim da string. Não mexe nos espaços entre as palavras.

```python
texto.strip()
```

```
'Geovana Alessandra dias Sanyos'
```

### [`str.replace(antigo, novo)`](https://docs.python.org/3/library/stdtypes.html#str.replace)

Substitui **todas** as ocorrências de um trecho por outro. Aqui foi usado para corrigir o `y` de "Sanyos":

```python
texto.replace('y', 't')
```

```
'  Geovana Alessandra dias Santos '
```

Atenção: por trocar todas as ocorrências, um `replace` mal escolhido pode alterar trechos indesejados do texto.

## Observação importante: métodos não alteram a variável

Este foi o ponto que mais mudou meu entendimento. Os métodos **retornam** uma transformação, mas não a executam sobre o texto original:

```python
texto
```

```
'  Geovana Alessandra dias Sanyos '
```

Mesmo depois de rodar `upper()`, `strip()` e `replace()`, a variável continuou exatamente como estava. Isso acontece porque strings em Python são imutáveis — cada método devolve uma string nova, e o resultado se perde se não for guardado.

## Encadeando métodos e guardando o resultado

Como cada método devolve uma string, é possível chamar o próximo em sequência, na mesma linha. E para que a transformação valha de fato, o resultado é atribuído de volta à variável:

```python
texto = texto.strip().replace('y', 't').upper()
texto
```

```
'GEOVANA ALESSANDRA DIAS SANTOS'
```

A leitura é da esquerda para a direita: tira os espaços, depois corrige a letra, depois passa tudo para maiúsculas. Cada método atua sobre o resultado do anterior.

---

## O que ficou de aprendizado

- Aspas simples e duplas são equivalentes para criar strings.
- Método é chamado com `objeto.metodo()`.
- `upper()`, `lower()`, `strip()` e `replace()` cobrem boa parte da limpeza básica de texto.
- Strings são imutáveis: o método devolve uma cópia transformada e não altera a original.
- Sem reatribuir (`texto = texto.strip()`), a transformação é descartada.
- Métodos podem ser encadeados, executando na ordem em que aparecem.

## Referências

- [Métodos de string](https://docs.python.org/3/library/stdtypes.html#string-methods)
