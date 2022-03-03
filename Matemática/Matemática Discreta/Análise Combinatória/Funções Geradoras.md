# Introdução
A função geradora para a sequência infinita de números reais
$$a_0,a_1,a_2,\ldots,a_k,\ldots$$
é a função polinomial abaixo, com uma quantidade infinita de termos:
$$G(x)=a_0+a_1x+a_2x^2+\ldots+a_kx^k+\ldots=\sum_{k=0}^\infty a_kx^k$$

Observe que para cada termo $a_k$ da sequência existe o termo polinomial $a_kx^k$ correspondente.

A função geradora para ${a_k}$ dada na definição acima, às vezes é chamada de função geradora simples de ${a_k}$ para distingui-la de outros tipos de funções geradoras para essa sequência.

---
# Funções Geradoras e Sequências Finitas
Podemos definir funções geradoras para sequências finitas de números reais ao estendermos uma sequência finita $a_0,a_1,a_2,\ldots,a_n$ em uma sequência infinita definindo $a_{n+1}=0,\;\;a_{n+2}=0,\ldots$.

A função geradora $G(x)$ dessa sequência infinita ${a_n}$ é um polinômio de grau $n$, já que nenhum termo $a_jx^j$, para $j>n$ ocorre, ou seja,
$$G(x)=a_0+a_1x+a_2x^2+\ldots+a_nx^n.$$

---
## Problemas de [[Introdução à Análise Combinatória|Contagem]] e Funções Geradoras ou um Problema de Codificação
As funções geradoras podem ser usadas para resolver uma grande variedade de problemas de contagem. Em particular, elas podem ser usadas para contar o número de combinações de vários tipos.

Já estudamos técnicas para contar as [[Combinação|combinações]] de tamanho $r$ de um conjunto com $n$ elementos quando a repetição é permitida sendo que restrições adicionais podem existir.

Tais problemas são equivalentes a contar as soluções para equações da forma
$$e_1+e_2+\ldots+e_n=C,$$
onde $C$ é uma constante e cada $e_i$ é um número inteiro não negativo que pode estar sujeito a uma restrição específica.

As funções geradoras também podem ser usadas para resolver problemas de contagem desse tipo.
