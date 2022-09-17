Suponha que desejamos selecionar $r$ objetos distintos de um [[Conjuntos|conjunto]] de $n$ elementos mas a ordem não é importante.
Neste caso, estamos contando o número de combinações de $r\;\;(r\le n)$ objetos distintos escolhidos de um conjunto de $n\;\;(n\ge1)$ elementos onde a ordem não é importante.

# Definição
Sejam $n$ e $r$ inteiros não negativos comm $r\le n$. Uma combinação $r$ de um conjunto de $n$ elementos é um subconjunto de $r$ dos $n$ elementos.

$C(n,r)$ representa o número de subconjuntos de tamanho $r$ que podem ser obtidos de um conjunto de $n$ elementos.

>## Formas de representar
>$$C(n,r)$$
>$$C_{n,r}$$
>$$_nC_r$$
>$$^nC_r$$
>$$\begin{pmatrix}n\\r\end{pmatrix}$$

Para cada combinação $C(n,r)$, existem $r!$ formas de [[Permutação|permutar]] os $r$ objetos.
 Ou ainda, para cada permutação $P(n,r)$ existem $r!$ arranjos com o mesmo conjunto de $r$ objetos distintos.
 
 Pelo [[Princípio da Multiplicação]] , o número de permutações de $r$ objetos distintos escolhidos de $n$ objetos é o produto da quantidade de formas de escolher os $r$ objetos, $C(n,r)$, pela quantidade de formas de arranjar os $r$ objetos, $r!$, ou seja,
 $$C(n,r)\cdot r!=P(n,r)$$
 Ou ainda
 $$C(n,r)={P(n,r)\over r!}={n!\over r!\cdot(n-r)!}$$
 
 ---
 # Combinação com repetição
 Quantas formas existem de escolher $r$ elementos sem considerar a ordem de um conjunto de $n$ elementos se repetição é permitida?
 
 ##### Estratégia:
- Considere cada um dos $n$ elementos como uma categoria de objeto do qual várias seleções podem ser feitas.
 
>###### Exemplo
>Suponha que um conjunto com os elementos $\{1,2,3,4\}$. Se três elementos devem ser escolhidos, então podemos ter:
> - $[3,3,1],[2,2,1],[1,2,4],\ldots$
> Como a ordem não importa, temos que $[3,3,1]=[3,1,3]=[1,3,3]$.

#### Definição
Uma combinação de $r$ elementos com repetição permmitida, ou multiconjunto de tamanho $r$, escolhida de um conjunto $X$ de $n$ elementos é uma seleção não ordenada de elementos de $X$ com repetição permitida.

Se $X={x_1,x_2,\ldots,x_n}$, escreve-se uma combinação de $r$ elementos com repetição permitida, ou multiconjunto de tamanho $r$, como
$$[x_{i_1},x_{i_2},\ldots,x_{i_r}]$$
tal que $x_{i_j}\in X$ e algum $x_{i_j}$ pode ser igual a um outro elemento.


## Fórmula
$$CR_{n,r}=C_{n+r-1,r}={(n+r-1)!\over r!\cdot(n-1)!}=\begin{pmatrix}n+r-1\\r\end{pmatrix}$$

---
[[Princípio da Casa de Pombo|]][[Tipos Abstratos de Dados|]][[Introdução à Análise Combinatória|]]