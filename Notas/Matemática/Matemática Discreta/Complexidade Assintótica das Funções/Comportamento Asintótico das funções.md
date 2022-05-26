# Notação Big-$O$
A notação Big-$O$ traz um limite superior para o crescimento de uma função.
>#### Definição
>Sejam $f$ e $g$ funções do conjunto dos inteiros ( $\mathbb{Z}$) ou do conjunto dos reais ( $\mathbb{R}$) para o conjunto dos reais ( $\mathbb{R}$). Dizemos que $f(x)$ é $O(g(x))$ se existem constantes $C$ e $k$ tais que $$|f(x)|\leq C\,|g(x)|$$ sempre que $x > k$. [Lê-se "$f(x)$ é 'big-oh'  de $g(x)$."]

***Observação:***	Intuitivamente, a definição de que $f(x)$ é $O(g(x))$ diz que $f(x)$ cresce mais lentamente que algum múltiplo fixo de $g(x)$ quando $x$ cresce sem limitações.

## Big-$O$ para algumas funções importantes
>###### Teorema 1:
>Seja $f(x) = a_nx^n+a_{n-1}x^{n-1}+a_{n-2}x^{n-2}+\dots+a_1x+a_0$, onde $a_0, a_1, \dots , a_{n-1}, a_n$ são números reais. Então $f(x)$ é $O(x^n)$.

>###### Teorema 2:
>Assuma que $f_1(x)$ é $O(g_1(x))$ e que $f_2(x)$ é $O(g_2(x))$. Então $(f_1+f_2)(x)$ é $O(g(x))$, onde $g(x) = (\max(|g_1(x)|,\,|g_2(x)|))$ para todo $x$.

>###### Corolário 1:
>Assuma que $f_1(x)$ e $f_2(x)$ são ambas $O(g(x))$. Então $(f_1+f_2)(x)$ é $O(g(x))$.

>###### Teorema 3:
>Assuma que $f_1(x)$ é $O(g_1(x))$ e $f_2(x)$ é $O(g_2(x))$. Então $(f_1f_2)(x)$ é $O(g_1(x)g_2(x))$.
---
# Notação Big-$\Omega$
>#### Definição
>Sejam $f$ e $g$ funções do conjunto dos inteiros ( $\mathbb{Z}$) ou do conjunto dos reais ( $\mathbb{R}$) para o conjunto dos reais ( $\mathbb{R}$). Dizemos que $f(x)$ é $\Omega(g(x))$ se existem constantes $C$ e $k$ com $C$ positivo tais que $$|f(x)|\geq C\,|g(x)|$$ sempre que $x > k$. [Lê-se "$f(x)$ é 'big-Omega'  de $g(x)$."]
---
# Notação Big-$\Theta$
>#### Definição
>Sejam $f$ e $g$ funções do conjunto dos inteiros ( $\mathbb{Z}$) ou do conjunto dos reais ( $\mathbb{R}$) para o conjunto dos reais ( $\mathbb{R}$). Dizemos que $f(x)$ é $\Theta(g(x))$ se $f(x)$ é $O(g(x))$ e $\Omega (g(x))$. Quando $f(x)$ é $\Theta(g(x))$, dizemos que $f$ é big-Theta de $g(x)$, que $f(x)$ é da ordem $g(x)$ e que $f(x)$ e $g(x)$ são da mesma ordem. [Lê-se "$f(x)$ é 'big-Theta'  de $g(x)$."]
---
>###### Teorema 4:
>Seja $f(x) = a_{n}x^{n}+a_{n-1}x^{n-1}+\dots+a_{1}x+a_{0}$, onde $a_0, a_1, \dots, a_n$ são números reais com $a_n \neq 0$. Então $f(x)$ é da ordem de $x^n$.
---
> ***OBS.:***
>>###### $(i)$
>>$$f(x) = g(x) \longrightarrow f = \Theta(g) ,\, g=\Theta(f).$$
>
>>###### $(ii)$
>>$$\text{Sejam } a,b\in \mathbb{R}\text{ e as funções
}f(x)=a^x\text{ e } g(x)=b^x\text{, então }$$
>>$$a>b \longrightarrow g=O(f).$$

---
# Notação Little-$o$
>#### Defenição
>Sejam $f(x)$ e $g(x)$ funções do conjunto dos inteiros positivos ($\mathbb{Z_+}$) para o conjunto dos reais ($\mathbb{R}$). Dizemos que $f(n)$ é $o(g(x))$ se, para toda e qualquer constante real $c > 0$, existe uma constante inteira $x_o \geq 1$ tal que $0\leq f(n)<cg(n)$.

Em relação matemática, $f(x)=o(g(x))$ significa:
$$\lim_{x\to \infty}\frac{f(x)}{g(x)}=0$$

---
# Notação Little-$\omega$
>#### Definição
>Sejam $f(x)$ e $g(x)$ funções do conjunto dos inteiros positivos ($\mathbb{Z_+}$) para o conjunto dos reais ($\mathbb{R}$). Dizemos que $f(x)$ é $\omega{g(x)}$ se, para toda e qualquer constante real $c > 0$, existe uma constante inteira $x_o\geq 1$, tal que $f(x) > cg(x) \geq 0$ para todo inteiro $x\geq x_o$.

Em relação matemática, $f(x)=\omega(g(x))$ significa:
$$\lim_{x\to \infty}\frac{f(x)}{g(x)}=\infty$$

---
# Hierarquia de funções
>$$1\prec \log{\log{n}} \prec \log{n} \prec n^{\epsilon} \prec n^{c} \prec n^{\log{n}} \prec c^n \prec n^n \prec c^{c^n}$$onde $\epsilon$ e $c$ são constantes arbitrárias com $0 < \epsilon < 1 < c$.
---
### Obs.:
Se $f(x)\in\Theta (g(x))$, então $f(x)\not\in o(g(x)) e f(x)\not\in\omega(g(x))$.

---

[[Funções|]]
[Vídeo sobre o assunto](https://www.youtube.com/watch?v=Q_1M2JaijjQ)