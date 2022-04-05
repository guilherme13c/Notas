[[Comportamento Asintótico das funções|]]
# Sequências Infinitas
Pode-se pensar numa sequência como uma lista de números escritos em uma ordem definida:
$$a_1,a_2,a_3,a_4,\ldots,a_n,\ldots$$
> ##### Notação
> A sequência ${a_1,a_2,a_3,\ldots}$ é também indicada por
> $$\set{a_n} \mbox{ ou } \set{a_n}^\infty_{n=1}$$

---
# Limite de Sequências
>#### Definição 1
> Uma sequência $\set{a_n}$ tem **limite** $L$ e escrevemos
> $$\lim_{n\to\infty}a_n=L \;\;\;\mbox{ ou }\;\;\; a_n\to L\mbox{ quando } n\to\infty$$
> e pudermos tornar os termos an tão próximos de L quanto quisermos ao fazer n suficientemente grande. Se existir, dizemos que a sequência **converge** (ou é **convergente**). Caso contrário, dizemos que a sequência **diverge** (ou é **divergente**). 

>#### Definição 2
>Uma sequência ${a_n}$ tem **limite** $L$ e escrevemos
>$$\lim_{n\to\infty}a_n=L \;\;\;\mbox{ ou }\;\;\; a_n\to L\mbox{ quando } n\to\infty$$
>se, para cada $\varepsilon>0$ existir um número inteiro correspondente $N$ tal que
>$$n>N \implies \vert a_n-L\vert<\varepsilon$$

>###### Teorema 1
>Se existe uma [[Funções|função]] $f(x), x\in\mathbb{R}$ tal que $a_n=f(n)$ então:
>$$\lim_{n\to\infty}a_n=\lim_{x\to\infty}f(x),n\in\mathbb{N},x\in\mathbb{R}$$

> ###### Teorema 2
> Se $a_n$ é uma sequência crescente e existe $M$ tal que $a_n<M,\forall n\in\mathbb{N}$, então:
> $$\lim_{n\to\infty}a_n\leq M$$
> Análogo para sequências descrescentes limitadas inferiormente por $N$:
> $$\lim_{n\to\infty}a_n\geq N$$