# Estudo — Strings
**Data:** DD/MM/AAAA

**Projeto:** Python para Data Science — [Alura](https://www.alura.com.br/)

---

## 🔤 O que é uma string

- Entendi que string é um conjunto de caracteres formando um texto.
- Aprendi que ela é criada ao atribuir a uma variável um dado entre aspas.
- Fixei que aspas simples e aspas duplas produzem exatamente o mesmo resultado.
- Compreendi que a escolha entre elas é prática: uso aspas duplas quando o texto tem apóstrofo.

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

## 🛠️ Métodos

- Aprendi que método é uma função que pertence a um objeto e age sobre ele.
- Fixei a estrutura de chamada: `objeto.metodo()`.
- Entendi que existem métodos que não precisam dos parênteses.
- Compreendi que preciso conferir a documentação de cada caso.

## 👩‍🏫 Situação — tratando um nome para cadastro

- Recebi o nome de uma professora com problemas: espaços sobrando nas pontas, letra trocada no sobrenome e caixa inconsistente.
- Entendi que o texto precisava ser tratado antes de entrar no sistema.
- O objetivo era chegar em `'GEOVANA ALESSANDRA DIAS SANTOS'`.

```python
texto = '  Geovana Alessandra dias Sanyos '
```

## 🔡 `upper()` e `lower()`

- Aprendi que [`str.upper()`](https://docs.python.org/3/library/stdtypes.html#str.upper) converte a string para maiúsculas.
- Aprendi que [`str.lower()`](https://docs.python.org/3/library/stdtypes.html#str.lower) converte para minúsculas.
- Entendi que o `lower()` é muito usado para padronizar dados antes de comparar textos.
- Fixei o motivo: para o Python, `'Ana'` e `'ana'` são diferentes.

## ✂️ `strip()`

- Aprendi que [`str.strip()`](https://docs.python.org/3/library/stdtypes.html#str.strip) remove os espaços em branco do início e do fim da string.
- Entendi que ele não mexe nos espaços entre as palavras.
- Fixei que espaço invisível nas pontas é um problema comum em dado vindo de formulário.

## 🔁 `replace()`

- Aprendi que [`str.replace(antigo, novo)`](https://docs.python.org/3/library/stdtypes.html#str.replace) substitui um trecho por outro.
- Usei o método para corrigir o `y` de "Sanyos".
- Entendi que ele troca **todas** as ocorrências, não apenas a primeira.
- Fixei o risco: um `replace` mal escolhido pode alterar trechos que eu não queria mudar.

## ⚠️ Métodos não alteram a variável original

- Este foi o ponto que mais mudou meu entendimento.
- Entendi que os métodos **retornam** uma transformação, mas não a executam sobre o texto original.
- Percebi que, mesmo depois de rodar `upper()`, `strip()` e `replace()`, a variável continuava igual.
- Aprendi que isso acontece porque strings em Python são imutáveis.
- Fixei que cada método devolve uma string nova, e o resultado se perde se eu não guardar.

## 🔗 Encadeando métodos

- Aprendi que posso chamar um método sobre o resultado do anterior, na mesma linha.
- Entendi que a leitura é da esquerda para a direita.
- Fixei que preciso atribuir o resultado de volta à variável para a transformação valer.

```python
texto = texto.strip().replace('y', 't').upper()
texto
```

```
'GEOVANA ALESSANDRA DIAS SANTOS'
```

- Acompanhei a ordem: tira os espaços, corrige a letra e depois passa tudo para maiúsculas.

## 💡 Conceitos que fixei

- Aspas simples e duplas são equivalentes para criar strings.
- Método é chamado com `objeto.metodo()`.
- `upper()`, `lower()`, `strip()` e `replace()` cobrem boa parte da limpeza básica de texto.
- `replace()` troca todas as ocorrências encontradas.
- Strings são imutáveis: o método devolve uma cópia transformada.
- Sem reatribuir, a transformação é descartada.
- Métodos encadeados executam na ordem em que aparecem.

## 🧾 Resumo final

Hoje trabalhei texto sujo até deixá-lo pronto para cadastro. O aprendizado central foi a imutabilidade: os métodos de string não mudam a variável, apenas devolvem uma versão transformada. Sem a reatribuição, o trabalho todo se perde. Também fixei o encadeamento como forma de aplicar várias transformações em sequência.

## 🚧 Próximos passos

- Estudar a coleta de dados com `input()`.
- Entender por que o retorno do `input()` é sempre texto.
- Aprender as funções de conversão entre tipos.
- Conhecer as f-strings para formatar a saída.
