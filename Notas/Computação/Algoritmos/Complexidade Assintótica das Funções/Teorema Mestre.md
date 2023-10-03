O Teorema Mestre trata da resolução de equações de [[Recursão|recorrência]] da forma $$T(n)=aT(\frac{n}{b})+f(n),$$ onde $a\geq1$ e $b>1$ são constantes e $f(n)$ é uma função [[Comportamento Asintótico das funções|assintoticamente]] positiva.

Neste caso não vamos achar a forma fechada da [[Recursão|recorrência]], mas sim seu comportamento [[Comportamento Asintótico das funções|assintótico]].

---
> # Teorema
> Sejam constantes $a\geq 1$ e $b> 1$ e $f(n)$ uma função definida nos inteiros não-negativos pela [[Recursão|recorrência]]: $$T(n)=aT(\frac{n}{b})+f(n),$$ onde a fração $\frac{n}{b}$ pode significar $\lceil{\frac{n}{b}}\rceil$ ou $\lfloor{\frac{n}{b}}\rfloor$. A equação de [[Recursão|recorrência]] $T(n)$ pode set limitada assintoticamente da seguinte forma:
> 1. Se $f(n) = O(n^{\log_b a - \epsilon})$ para alguma constante $\epsilon> 0$, então $T(n)=\Theta(n^{\log_b a})$.
> 2. Se $f(n)=\Theta(n^{\log_b a})$, então $T(n)=\Theta(n^{\log_b a} \log n)$.
> 3. Se $f(n)=\Omega(n^{\log_b a+\epsilon})$ para alguma constante $\epsilon> 0$ e se $af(\frac{n}{b})\leq cf(n)$ para alguma constante $c<1$ e para $n$ suficientemente grande, então $T(n)=\Theta(f(n))$.
> ---
> ## Casos e Condições
> > #### $1^o$ Caso:
> > $$f(n)\prec n^{\log_ba}$$
> > $$\downarrow$$
> > $$f(n)=O(\frac{n^{\log_ba}}{n^\epsilon})$$
> > $$T(n)=\Theta(n^{\log_ba})$$
> > A função $f(n)$ tem uma taxa de crescimento ***menor*** que $n^{\log_ba}$ por um fator polinomial, i.e., $n^\epsilon$.
> 
> > #### $2^o$ Caso:
> > $$f(n)\sim n^{\log_ba}$$
> > $$\downarrow$$
> > $$f(n)=\Theta(n^{\log_ba})$$
> > $$T(n)=\Theta(n^{\log_ba}\log n)$$
> > As duas funções têm a ***mesma*** taxa de crescimento.
> 
> > #### $3^o$ Caso:
> > $$f(n)\succ n^{\log_ba}$$
> > $$\downarrow$$
> > $$f(n)=\Omega(n^{\log_ba}n^\epsilon)$$
> > $$T(n)=\Theta(f(n))$$
> > A função $f(n)$ tem uma taxa de crescimento ***maior*** que $n^{\log_ba}$ por um fator polinomial, i.e., $n^\epsilon$, e a condição de "regularidade" é satisfeita.
> > > ###### Condição de regularidade
> > > $$af(\frac{n}{b})\leq cf(n)\text{, para } c<1.$$ 

---
[[Comportamento Asintótico das funções|]][[Funções|]]