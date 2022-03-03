[[Funções Multiplictivas|]][[Classes de Equivalência|]][[Teorema Chinês do Resto|]][[Congruências e Aritmética Modular|]]
# A função $\phi$ de Euler
Definimos $\mathbb{Z}_n^*$ como o conjunto dos elementos invertíveis de $\mathbb{Z}_n$.
$\begin{align}\mathbb{Z}_6^*=\{\,\bar 1,\bar5\,\}\end{align}$
$\begin{align}\mathbb{Z}_7^*=\{\,\bar 1,\bar2,\bar3,\bar4,\bar5,\bar6\,\}\end{align}$

A função $\phi:\mathbb{N}\longrightarrow\mathbb{N}$ é definida por $\phi(n)=\vert\mathbb{Z}_n^*\vert$. Em outras palavras:
$$\phi(n)=\vert\{a\in\{1,\ldots,n\}:\mbox{mdc}(a,n)=1\}\vert$$
---
# Invertíveis e o [[Teorema Chinês do Resto]]
![[Pasted image 20220115181436.png]]

Iremos provar que se $m,n\in\mathbb{N}$ tem $\mbox{mdc}(m,n)=1$, e $a,b,c\in\mathbb{Z}$ são tais que $\begin{cases}c\equiv a \;\;(\mbox{mod }m)\\ c\equiv b \;\;(\mbox{mod }n)\end{cases}$, então $c$ é invertível $\mbox{mod }mn\iff a$ é invertível $\mbox{mod }m$ e $b$ é invertível $\mbox{mod }n$.

Assim, podemos concluir que $\phi(mn)=\phi(n)\cdot\phi(m)$, ou seja, que $\phi$ é multiplicativa.

>###### Prova
>$(i)\Rightarrow$ Existem $a^\prime, b^\prime\in\mathbb{Z}$ tais que $a\cdot a^\prime\equiv 1;\;(\mbox{mod }m)$  e $ab\cdot b^\prime\equiv 1;\;(\mbox{mod }n)$.
>Seja $c^\prime\in\mathbb{Z}$ tais que $\begin{cases}c^\prime\equiv a^\prime\;\;(\mbox{mod }m)\\c^\prime\equiv b^\prime\;\;(\mbox{mod }n)\end{cases}$ Então $\begin{cases}c\cdot c^\prime\equiv 1\;\;(\mbox{mod }m)\\ c\cdot c^\prime\equiv 1\;\;(\mbox{mod }n)\end{cases}$ 
>
>Assim, $m\vert c\cdot c^\prime-1$ e $n\vert c\cdot c^\prime-1$. Commo $\mbox{mdc}(m,n)=1, m\cdot n\vert c\cdot c^\prime-1\implies c\cdot c^\prime\equiv1\;\;(\mbox{mod }m\cdot n)\implies c$ é invertivel módulo $mn$.
> 
>$(ii)\Rightarrow$ Existe $c^\prime\in\mathbb{Z}$ tal que $c\cdot c^\prime\equiv\;\;(\mbox{mod }m\cdot n)$ 
>
>$\begin{align}c\cdot c^\prime\equiv1\;\;(\mbox{mod }m)\\ a\cdot c^\prime\equiv1\;\;(\mbox{mod }m)\end{align}\implies a$ é invertível módulo $m$ 
>
>$\begin{align}c\cdot c^\prime\equiv1\;\;(\mbox{mod }n)\\ b\cdot c^\prime\equiv1\;\;(\mbox{mod }n)\end{align}\implies b$ é invertível módulo $n$.

---
## Calculando $\phi$
Como $\phi$ é multiplicativa, se $n=p_1^{\alpha_1}\cdot\ldots\cdot p_k^{\alpha_k}$ com $p_1, \ldots,p_k$ distintos, então $\phi(n)=\phi(p_1^{\alpha_1})\cdot\ldots\cdot\phi(p_k^{\alpha_k})$.
- $$\phi(p)=p-1$$

- $$\phi(p^k)=p^k-p^{k-1}=p^k\cdot\frac{p-1}{p}$$

- $$\begin{align}\phi(n)=\phi(p_1^{\alpha_1})\cdot\ldots\cdot\phi(p_k^{\alpha_k})\\ \\=p_1^{\alpha_1}\cdot\frac{p_1-1}{p_1}\cdot p_2^{\alpha_2}\cdot\frac{p_2-1}{p_2}\cdot\ldots\cdot p_k^{\alpha_k}\cdot\frac{p_k-1}{p_k}\\ \\=n\cdot \prod_{p\vert n}\frac{p-1}{p}\end{align}$$
---