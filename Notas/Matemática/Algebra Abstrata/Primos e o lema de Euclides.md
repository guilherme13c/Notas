## Teorema de Bézout
Dados $a,b\in\mathbb{Z}$, existem $x,y\in\mathbb{Z}$ tais que $ax+by=\mbox{mdc}(a,b)$.

---
## Lema de Euclides
###### Versão 1
Sejam $n,a,b\in\mathbb{Z}$. Se $n\mid ab$ e $\mbox{mdc}(n,a)=1$, então $n\mid b$.

###### Versão 2
Sejam $a,b\in\mathbb{N}$ e $p$ primo. Se $p\mid ab$, então $p\mid a$ ou $p\mid b$.

---

# Números Primos e Compostos
>## Número Composto
>#### Def:
>Um $n\in\mathbb{N}$ é composto se $n>1$ e existem naturais $a,b<n$ com $n = ab$.

>## Número Primo
>#### Def:
>Um $n\in\mathbb{N}$ é primo se $n>1$ e $n$ não é composto.
>###### Fato 1
>Se $p$ é primo, seus únicos divisores são $1$ e $p$.
>###### Fato 2
>Se $p$ é um primo e $p\mid a_1a_2\cdots a_k$ para $k \geq 1$ e $a_1,a_2,\cdots,a_k\in\mathbb{N}$, então $p\mid a_i$ para algum $1\leq i\leq k$.

---

# Infinitude dos Primos
###### Demonstração
Suponha que existem apenas $k\in\mathbb{N}$ primos $p_1,p_2,\dots,p_k$.
$$n=p_1p_2\dots p_k + 1$$
Note que, para todo $1\leq i\leq k$, $p_i\not\mid n$.
$$(p_i\mid n, p_i\mid p_1,p_2,\dots,p_k\Rightarrow p_i\mid1).$$
Qual a fatoração prima de $n$? Absurdo! $\square$