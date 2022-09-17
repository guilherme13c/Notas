[[Relações de Equivalência|]]
# Relações em Conjuntos
## Relação Binária
- Sejam os [[conjuntos]] $A$ e $B$.
- Uma relação binária de $A$ para $B$ é um subconjunto de $A\times B$.
- Dado um par ordenado $(x, y)$ em $A\times B$, $x$ está relacionado com $y$ por $R$ , escrito $xRy$, se, e somente se, $(x,y)\in R$.
- O termo _binário_ é usado para indicar uma relação entre dois conjuntos.

#### Notação
- "$x$ está relacionado com $y$":
$$xRy\iff(x,y)\in R$$
- "$x$ não está relacionado com $y$":
$$x\not Ry\iff(x,y)\not\in R$$
---
# Matriz de uma Relação
Uma relação entre conjuntos finitos pode ser representada por uma matriz binária (matriz zero-um).

Seja $R$ uma relação binária de $A = \{a_1, a_2,\ldots,a_m\}$ para $B=\{b_1,b_2,\ldots,b_n\}$, sendo que podemos ter também $A=B$.

A relação $R$ pode ser representada pela matriz $M_R=[m_{ij}]$, onde:
$$m_{ij}=\begin{cases}1\mbox{ se }(a_i,b_j)\in R\\0\mbox{ se }(a_i,b_j)\not\in R\end{cases}$$
---
# Diagrama de Seta de uma Relação
Suponha que $R$ é uma relação de um conjunto $A$ para um conjunto $B$. O "diagrama de seta" para $R$ é obtido da seguinte forma:

1. Represente os elementos de $A$ numa região e os elementos de $B$ como pontos em outra região.
2. Para cada $x$ em $A$ e $y$ em $B$, desenhe uma seta de $x$ para $y$ se, e somente se, $x$ é relacionado com $y$ por $R$. Simbolicamente:

	-> Desenhe uma seta de $x$ para $y\iff xRy\iff(x,y)\in R$.

![[Pasted image 20220104182010.png]]

---
# O inverso de uma Relação
Seja $R$ uma relação de $A$ para $B$. A relação inversa $R^{-1}$ de $B$ para $A$ é definida como:
$$R^{-1}=\{(x,y)\in B\times A\vert(x,y)\in R\}.$$
Essa definição pode ser re-escrita operacionalmente como
$$\forall x\in X,y\in Y,(y,x)\in R^{-1}\iff(x,y)\in R$$
---
# [[Introdução a Grafos|Grafo]] Dirigido de uma Relação
#### Definição (relação binária):
Uma relação binária no conjunto $A$ é uma relação binária de $A$ para $A$.

Neste caso, o diagrama de seta é modificado e torna-se um grafo dirigido, ou seja, o conjunto $A$ é desenhado somente uma vez e uma seta é desenhada para cada par de pontos relacionados entre si.

![[Pasted image 20220104181935.png]]

---
# Relações $n$-árias
#### Definição
Dados os conjuntos $A_1,A_2,\ldots,A_n$, uma relação $n$-ária $R$ em $A_1\times A_2\times\ldots\times A_n$ é subconjunto de $A_1\times A_2\times\ldots\times A_n$.

Relações envolvendo dois, três e quatro conjuntos são chamadas de binárias, ternárias e quaternárias, respectivamente.

---
>###### Número de Relações em um Conjunto com $n$ Elementos $= 2^{n^2}$

---