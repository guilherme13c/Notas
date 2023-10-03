# Definição
Um arranjo ordenado de objetos sem repetição
+ A ordem é importante.
+ Pode-se aplicar o [[Princípio da Multiplicação]].

# Casos
## Caso 1
Seja um conjunto com $n$ elementos. Quantas permutações existem considerando todos os elementos e que não há repetição?

Aplicando-se o princípio da multiplicação, temos:
$$n\cdot (n-1)\cdot (n-2)\cdot\ldots\cdot1=n!$$

## Caso 2
Seja um conjunto com $n$ elementos. Quantas permutações existem considerando $r\;\;(1\le r\le n)$ elementos desse conjunto e que não há repetição?

Aplicando-se o princípio da multiplicação, temos:
$$n\cdot(n-1)\cdot\ldots\cdot(n-r+1)=\prod_{i=n-r+1}^{n}i={n!\over (n-r)!}$$

## Caso Genérico
Dado um conjunto com $n\;\;(n\ge1)$ elementos e um valor de $r\;\;(1\le r\le n)$, existem
$$P(n,r)={n!\over(n-r)!}$$

## Permutação com repetição
$$P^{n_1,n_2,\ldots, n_k}_n={n!\over n_1!n_2!\cdot\ldots\cdot n_k!}$$
onde $n$ é o número de elementos do conjunto e $n_1,n_2,\ldots,n_k$ são os números de vezes que cada elemento se repeat.

[[Princípio da Casa de Pombo|]][[Tipos Abstratos de Dados|]][[Introdução à Análise Combinatória|]]