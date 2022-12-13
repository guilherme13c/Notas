[[Intodução a Intratabilidade|]][[Reduções de Tempo Polinomial|]]
#### $\mathbf{P}$
$\mathbf{P}$ é o [[Conjuntos|conjunto]] de [[Decidibilidade|problemas de decisão]] para os quais existe algum [[Algoritmos|algoritmo]] de [[Comportamento Asintótico das funções|complexidade]] temporal polinomial. 

#### certificador
Um algoritmo $C(s,t)$ é um **certificador** para o problema $X$ se: $\forall s: s\in X \iff \exists t: C(s,t)=\text{sim}$.

#### $\mathbf{NP}$
$\mathbf{NP}$ é o conjunto de problemas de decisão para os quais existe um [[#certificador]] de complexidade polinomial.
- $C(s,t)$ é um algoritmo de complexidade polinomial.
- O certificado $t$ é de tamanho polinomial: $\vert t\vert \le p(\vert s\vert)$ para algum polinômio $p(\cdot)$.

#### $\mathbf{exp}$
$\mathbf{EXP}$ é o conjunto de problemas de decisão para os quais existe um algoritmo de complexidade exponencial.

---
# Proposições

## $\mathbf{P}\subseteq\mathbf{NP}$
### Demonstração
Considere qualquer problema $X\in \mathbf{P}$.
- Por definição, existe um algoritmo polinomial $A(s)$ que resolve $X$.
- Certificado $t=\varepsilon$, certificador $C(s,t)=A(s)$ .

## $\mathbf{NP}\subseteq\mathbf{EXP}$
### Demonstração
Considere qualquer problema $X\in \mathbf{NP}$.
- Por definição, existe um certificador polinomial $C(s,t)$ para $X$, onde o certificado $t$ satisfaz $\vert t\vert \le p(\vert s\vert)$ para algum polinomio $p(\cdot)$.
- Para resolver a instância $s$, rode o algoritmo $C(s,t)$ em todas as strings $t$ com $\vert t\vert\le p(\vert s\vert)$.
- Retorne $\text{sim}$ se, e só se, $C(s,t)$ retorna $\text{sim}$ para qualquer um desses certificados em potencial.

## $\mathbf{P}\neq\mathbf{EXP}$
$\mathbf{P}\neq\mathbf{EXP}\implies$ ou $\mathbf{P}\neq\mathbf{NP}$, ou $\mathbf{NP}\neq\mathbf{EXP}$, ou ambos.

---
# $\mathbf{P}=\mathbf{NP}$?
Problemas de decisão são tão fáceis quanto problemas de certificação?

