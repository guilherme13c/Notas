# Bases
#### Definição
Dado $B>1$, a representação do número $n\in\mathbb{N}$ em base $B$ é uma sequência de $k\in\mathbb{N}$ dígitos $d_0,\space d_1,\cdots,\space d_{k-1}$ tais que
+ $n={\sum_{i=0}^{k-1}}\nolimits d_iB^i=d_{k-1}B^{k-1}+\cdots+d_1B+d_0$
+ $0\le d_i<B$ e $d_{k-1}>0$

>#### Proposição
>Dado $B>1$, todo $n\in\mathbb{N}$ tem uma única representação em base $B$.
>
>###### Unicidade
>$d_{k-1}B^{k-1}+\cdots+d_1B+d_0=n=d^`_{k^`-1}B^{k^`-1}+\cdots+d^`_1B+d^`_0$
>$\cancel{d_{k-1}B^{k-1}}+\cdots+\cancel{d_1B}+d_0\equiv \cancel{d^`_{k^`-1}B^{k^`-1}}+\cdots+\cancel{d^`_1B}+d^`_0\;\;\;(\mbox{ mod }B\;)$
>$d_0\equiv d_0^`\;\;\;(\mbox{ mod }B\;)$
>$\implies B\mid d_0^`-d_0\implies d_0=d_0^`$

---
[[Critérios de Divisibilidade|]][[Congruências e Aritmética Modular|]]