[[Funções|]][[Teorema Fundamental da Aritmética|]][[Máximo Divisor Comum - MDC e Mínimo Múltiplo Comum - MMC|]]
# Funções Multiplicativas
Uma função $f:\mathbb{N}\longrightarrow\mathbb{Z}$ é dita set multiplicativa se $f(1)=1$ e, para quaisquer $m, n\in\mathbb{N}$ tais que $\mbox{mdc}(m,n)=1$, temos que $f(m\cdot n)=f(m)\cdot f(n)$.

> ###### Fato
> Se $f$ é multiplicativa e $a = p_1^{\alpha_1}\cdot \ldots \cdot p_k^{\alpha_k}$ com $p_1,\ldots,p_k$ distintos. Então:
> $f(a)=f(p_1^{\alpha_1})\cdot\ldots\cdot f(p_k^{\alpha_k})$ 

## Exemplos
#### 1)
Dado $k\in\mathbb{N}$, seja $D(k)$ o conjunto de divisres positivos de $k$ e $d(k)=\vert D(k)\vert$.

No caso geral, as funções $f$ e $g$ abaixo são inversas se $\mbox{mdc}(m,n)=1$.
$$f:D(m)\times D(n)\longrightarrow D(m\cdot n)$$
$$(d_1,d_2)\longmapsto d_1\cdot d_2$$$$g:D(m\cdot n)\longrightarrow D(m)\times D(n)$$$$d\longmapsto \Bigg(\mbox{mdc}(m,n), \frac{d}{\mbox{mdc}(d,m)}\Bigg)$$
#### 2)
Dado $k\in\mathbb{N}$, seja $\sigma(k)$ a soma dos divisores positivos de $k$.

Se $m,n\in\mathbb{N}$ com $\mbox{mdc}(m,n)=1$,
$$\begin{align}
\sigma(m,n)=\sum_{d\vert m\cdot n}d=\sum_{d_1\vert m}\sum_{d_2\vert n}d_1\cdot d_2\\\\
=\Bigg(\sum_{d_1\vert m}d_1\Bigg)\Bigg(\sum_{d_2\vert m}d_2\Bigg)\\\\
=\sigma(m)\cdot\sigma(n)
\end{align}$$
---
# Convolução de Dirichlet
Se $f$ e $g$ são multiplicativas, podemos definir a **convolução de Dirichlet**.
$$(f\star g)(k)=\sum_{d\vert k}f(d)\cdot g\Bigg(\frac{k}{d}\Bigg),$$
que também é multiplicativa, pois se $m,n\in\mathbb{N}$ tem $\mbox{mds}(m,n)=1$, então
$$\begin{align}
(f\star g)(m\cdot n)=\sum_{d\vert m\cdot n}f(d)\cdot g\Bigg(\frac{m\cdot n}{d}\Bigg)\\\\
=\sum_{d_1\vert m}\sum_{d_2\vert n}f(d_1\cdot d_2)\cdot g\Bigg(\frac{m\cdot n}{d_1\cdot d_2}\Bigg)\\\\
=\sum_{d_1\vert m}\sum_{d_2\vert n}f(d_1)\cdot f(d_2)\cdot g\Bigg(\frac{m}{d_1}\Bigg)\cdot g\Bigg(\frac{n}{d_2}\Bigg)\\\\
=\underbrace{\Bigg[\sum_{d_1\vert m}f(d_1)\cdot g\Bigg(\frac{m}{d_1}\Bigg)\Bigg]}_{(f\star g)(m)}\cdot \underbrace{\Bigg[\sum_{d_2\vert n}f(d_2)\cdot g\Bigg(\frac{m}{d_1}\Bigg)\Bigg]}_{(f\star g)(m)}
\end{align}$$
---