# Princípio da Adição

Se uma operação consiste em $k$ passos distintos, onde os passos são mutuamente disjuntos, sendo que
- o primeiro passo pode set executado de $n_1$ formas diferentes, ou seja, existem $n_1$ possibilidades para o passo 1,
- o segundo passo pode set executado de $n_2$ formas diferentes, e assim sucessivamente até
- o $k$-ésimo passo que pode set executado de $n_k$ formas diferentes
então toda a operação pode set executada de $$n_1+n_2+\ldots+n_k=\sum_{i=1}^k n_i$$
formas diferentes.

## Consequências

- $n(A-B)=n(a)-n(B)$
- $B\,\cup(A-B)=A$

# Elementos na União de [[Conjuntos]]
## Dois Conjuntos
$\mid A \cup B\mid\;=\;\mid A\mid+\mid B\mid-\mid A\,\cap B\mid$

## Três Conjuntos
$\mid A\cup B\cup C\mid\;=\;\mid A\mid+\mid B\mid+\mid C\mid-\mid A\cap B\mid-\mid A\cap C\mid-\mid B\cap C\mid+\mid A\cap B\cap C\mid$

## Princípio da Inclusão-Exclusão
Em sua forma geral, o princípio de inclusão-exclusão afirma que para conjuntos finitos $A_1,\ldots,A_n$ temos que
$$\biggm\lvert\bigcup_{i=1}^{n}A_i\biggm\rvert=\sum_{i=1}^n\lvert A_i\rvert-\sum_{1\leq i<j\leq n}^n\lvert A_i\,\cap\,A_j\rvert+\sum_{1\leq i<j\leq n}^n\lvert A_i\cap A_j\cap A_k\rvert-\dots+(-1)^{n-1}\cdot \lvert A_i\cap\ldots\cap A_k\rvert$$
$(i)$ \[Soma as cardinalidades dos conjuntos individuais]
$(ii)$ \[Subtrai o número de elementos que aparecem na interseção de dois conjuntos]
$(iii)$ \[Soma o número de elementos que aparecem na interseção de três conjuntos]
$(iv)$ \[Subtrai o número de elementos que aparecem na interseção de quatro conjuntos e, assim, sucessivamente]