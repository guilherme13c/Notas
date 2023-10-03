# Séries
#### Definição

Uma **série** é a soma de todos os elementos de uma [[Sequências Infinitas|sequência infinita]].

## Soma de Progressão Geométrica (PG)

$\begin{cases}{\large S_n={c(1-r^n)\over 1-r}, \mbox{ se } r\not=1}\\{\large S_n={c\cdot n}, \mbox{ se } r=1}\end{cases}$

$r^n\begin{cases}=1, \mbox{ se } r=1\\=\pm1, \mbox{ se } r=-1\\ \to0, \mbox{ se } r\in(-1,1)\\\to\infty, \mbox{ se } r>1\\\mbox{diverge}, \mbox{ se } r< -1\\\end{cases}$

> ### Soma de Série Geométrica
>  A sequência $r^n$ converge se, e somente se, $r\in(-1,1)$:
> $${\color{white}\sum_{n=1}^\infty{c\cdot r^{n-1}}={c\over 1-r}, \mbox{ se } r\in(-1,1)}$$

> #### Definição
> Dada uma série $\sum_{n=1}^\infty a_n=a_1+a_2+a_3+\cdots$, denote por $S_n$ sua $n$-ésima soma parcial:
> $$S_n=\sum_{i=1}^n a_i=a_1+a_2+\cdots+a_n$$
> Se a sequência $\set{S_n}$ for convergente e $\lim_{n\to\infty}S_n=S$ existir como um número real, então a série $\sum a_n$ é chamada **convergente**, e escrevemos
> $$a_1+a_2+\cdots+a_n+\cdots=S \mbox{ ou } \sum_{n=1}^\infty a_n=S$$
> O número $s$ é chamado a soma da série. Se a sequência $\set{S_n}$ é divergente, então a série é chamada **divergente**.

> ###### Teorema
> Se a série $\sum_{n=1}^\infty a_n$ for convergente, então $\lim_{n\to\infty}a_n=0$.

> # Teste de Divergência
> Se $\lim_{n\to\infty}a_n$ não existir ou se $\lim_{n\to\infty}a_n\not=0$, então a série $\sum_{n=1}^\infty a_n$ é divergente.

## Teste da Integral
Suponha que $f$ seja uma função contínua, positiva e decrescente em $[1,\infty)$ e seja $a_n=f(n)$. Então a série $\sum_{n=1}^\infty$ é convergente se, e somente se, a integral imprópria $\int_1^\infty f(x)\;dx$ for convergente. Em outras palavras: 

+ (i) Se $\int_1^\infty f(x) \;dx$ for convergente, então $\sum_{n=1}^\infty a_n$ é convergente.
+ (ii) Se $\int_1^\infty f(x) \;dx$ for divergente, então $\sum_{n=1}^\infty a_n$ é divergente.

## Estimativa de Resto para o [[#Teste da Integral]]
Suponha que $f(k)=a_k$, onde $f$ é uma função contínua, positiva, decrescente para $x\geq n$ e $\sum a_n$ é convergente. Se $R_n=S-S_n$, então
$$\int_{n+1}^\infty f(x)\;dx\leq R_n\leq\int_n^\infty f(x)\;dx$$
Dessa forma é possível estimar a precisão da soma parcial $S_n$ como aproximação para $S$. Isso pode set utilizado em computadores para reduzir a necessidade de computação sem grande perda de precisão.

> ### $p$-séries
> A série $p$ $\sum_{n=1}^\infty {1\over n^p}$ é convergente se $p> 1$ e divergente se $p\leq1$.

## Teste da Comparação
Sejam $a_k,b_k,k=1,2,3,\ldots$, sequências de termos não negativos tais que $a_k\leq b_k\;\forall k\in\mathbb{N}$:
1. Caso $\sum_{k=1}^\infty b_k$ convirja, $\sum_{k=1}^\infty a_k$ converge também.
2. Caso $\sum_{k=1}^\infty a_k$ divirja, $\sum_{k=1}^\infty b_k$ diverge também.

## Teste da Comparação no Limit
Sejam $a_k,b_k,k\in\mathbb{N}$ sequências de termos positivos. Suponha que existe $\lim_{k\to\infty}{a_k\over b_k}$ ou que $\lim_{k\to\infty}{a_k\over b_k}=\infty$:

Seja $\rho = \lim_{k\to\infty}{a_k\over b_k}, \rho\geq0$ ou $\rho=\infty$.
1. Se $\rho>0$ e finito, então ou ambas $\sum_{k=1}^\infty a_k$ e $\sum_{k=1}^\infty b_k$ convergem, ou ambas divergem.
2. Se $\rho=0$ e $\sum_{k=1}^\infty b_k$ converge, então $\sum_{k=1}^\infty a_k$ converge.
3. Se $\rho=\infty$ e $\sum_{k=1}^\infty b_k$ diverge, então $\sum_{k=1}^\infty a_k$ diverge.

---
# Séries Alternadas
$b_k>0:$
$\sum^\infty_{k=1}(-1)^{k-1}b_k$ ou $\sum^\infty_{k=1}(-1)^k b_k$
$b_1-b_2+b_3-\ldots$ ou $-b_1+b_2-b_3+\ldots$

## Teorema (Teste das [[#Séries Alternadas]])
Seja ${b_k}$ uma sequência de termos positivos, decrescente e com $\lim_{n\to\infty}b_n=0$. Então, as séries alternadas $\sum^\infty_{k=1}(-1)^{k-1}b_k$ e $\sum^\infty_{k=1}(-1)^k b_k$ são convergentes.


## Teste da Razão
> $(i)$ Se ${\lim_{n\to\infty}\vert {a_{n+1}\over a_n}\vert=L<1}$, então a série $\sum_{n=1}^{\infty}a_n$ é absolutamente convergente.
> $(ii)$ Se ${\lim_{n\to\infty}\vert {a_{n+1}\over a_n}\vert=L> 1}$ ou se ${\lim_{n\to\infty}\vert {a_{n+1}\over a_n}\vert=\infty}$, então a série $\sum_{n=1}^{\infty}a_n$ é divergente.
> $(iii)$ Se ${\lim_{n\to\infty}\vert {a_{n+1}\over a_n}\vert=1}$, o [[#Teste da Razão]] é inconclusivo.

## Teste da Raiz
> $(i)$ Se ${\lim_{n\to\infty}\sqrt[n]{\vert a_n\vert}=L<1}$, então a série $\sum_{n=1}^{\infty}a_n$ é absolutamente convergente.
> $(ii)$ Se ${\lim_{n\to\infty}\sqrt[n]{\vert a_n\vert}=L> 1}$ ou se ${\lim_{n\to\infty}\sqrt[n]{\vert a_n\vert}=\infty}$, então a série $\sum_{n=1}^{\infty}a_n$ é divergente.
> $(iii)$ Se ${\lim_{n\to\infty}\sqrt[n]{\vert a_n\vert}=1}$, o [[#Teste da Raiz]] é inconclusivo.

---

# Séries de Potências
Uma **série de potências** é uma série da forma
$$\sum_{n=0}^{\infty}c_n x^n=c_0+c_1x+c_2x^2+c_3x^3+\ldots+c_nx^n+\ldots$$
onde $x$ é uma variável e $c_n$'s são constantes chamadas **coeficientes** da série. A soma da série é uma função
$$f(x)=c_0+c_1x+c_2x^2+c_3x^3+\ldots+c_nx^n+\ldots$$
cujo domínio é p conjunto de todos os $x$ para os quais a série converge. Observe que $f$ se assemelha a um polinômio.

Em geral, a série da forma
$$\sum_{n=0}^\infty c_n(x-a)^n=c_0+c_1(x-a)+c_2(x-a)^2+\ldots$$
é denominada **série de potências em $(x-a)$** ou **série de potências centrada em $a$** ou **série de potências em torno de $a$.**

> ## Teorema
> Para uma dada série de potências $\sum_{n=0}^{\infty}c_n (x-a)^n$, existem apenas três possibilidades:
> $(i)$ A série converge apenas quando $x=a$
> $(ii)$ A série converge para todo $x$
> $(iii)$ Existe um número positivo $R$ tal que a série converge se $\vert x-a \vert<R$ e diverge se $\vert x-a \vert> R$
> 
> Esse número $R$ no caso $(iii)$ é chamado de **Raio de Convergência**.