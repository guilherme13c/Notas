[[Intodução a Intratabilidade|]][[Reduções de Tempo Polinomial|]]
#### $\mathbf{P}$
$\mathbf{P}$ é o [[Conjuntos|conjunto]] de [[Decidibilidade|problemas de decisão]] para os quais existe algum [[Algoritmos|algoritmo]] de [[Comportamento Asintótico das funções|complexidade]] temporal polinomial. 

#### certificador
Um algoritmo $C(s,t)$ é um **certificador** para o problema $X$ se: $\forall s: s\in X \iff \exists t: C(s,t)=\text{sim}$.

#### $\mathbf{NP}$
$\mathbf{NP}$ é o conjunto de problemas de decisão para os quais existe um [[#certificador]] de complexidade polinomial.
- $C(s,t)$ é um algoritmo de complexidade polinomial.
- O certificado $t$ é de tamanho polinomial: $\vert t\vert \le p(\vert s\vert)$ para algum polinômio $p(\cdot)$.

