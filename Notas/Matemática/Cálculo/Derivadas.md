[[Funções|]]
# Definição
$$f^`(x) = \lim_{h\to0}{f(x+h)-f(x)\over h}$$

A derivada de uma função $f$ pode ser entendida como a função que descreve a taxa de variação (inclinação) de $f$.

---
## Notações
#### Diferenciação como função
$f^`(x)=y^`={\mbox{d}y\over\mbox{d}x}={\mbox{d}f\over\mbox{d}x}={\mbox{d}\over\mbox{d}x}f(x)=Df(x)=D_xf(x)$

#### Diferenciação em valor
${\mbox{d}x\over\mbox{d}y}\Biggm]_{x=a}$ ou ${\mbox{d}x\over\mbox{d}y}\Biggm|_{x=a}$

---
>###### Teorema
>Se $f$ for diferenciável em $a$, então $f$ é contínua em $a$.
>
> ---
>***Obs.:*** A reciproca dessa afirmação é falsa.

---
# Regras de Diferenciação
>###### Função constante
>$${d\over dx}(c)=0$$

>###### Função potência
>$${d\over dx}(x^n)=nx^{n-1}$$ e $${d\over dx}(x)=1$$

>###### Múltiplo Constante
>$${d\over dx}[c\cdot f(x)]=c\cdot{d\over dx}f(x)$$

>###### Soma e Diferença
>$${d\over dx}[f(x)+g(x)]={d\over dx}f(x)+{d\over dx}g(x)$$
>
>$${d\over dx}[f(x)-g(x)]={d\over dx}f(x)-{d\over dx}g(x)$$

>###### Número $e$
>$e$ é um número real tal que $\lim_{h\to0}{e^h-1\over h}=1$ ou $e=\lim_{x\to0}(1+x)^{1\over x}$ ou $e=\lim_{n\to\infty}\bigg(1+{1\over n}\bigg)^n$

>###### Função exponencial natural
>$${d\over dx}(e^x)=e^x$$

>###### Produto
>$${d\over dx}[f(x)\cdot g(x)]=f(x)\cdot{d\over dx}[g(x)]+g(x)\cdot{d\over dx}[f(x)]$$

>###### Quociente
>$${d\over dx}\bigg[{f(x)\over g(x)}\bigg]={g(x){d\over dx}[f(x)]-f(x){d\over dx}[g(x)]\over[g(x)]^2}$$

---
## Derivadas de Funções Trigonométricas
>###### Seno
>$${d\over dx}(\sin x)=\cos x$$

>###### Cosseno
>$${d\over dx}(\cos x)=-\sin x$$

>###### Tangente
>$${d\over dx}(\tan x)=\sec^2 x$$

>###### Cossecante
>$${d\over dx}(\mbox{cossec }x)=-\mbox{cossec }x \mbox{ cotan }x$$

>###### Secante
>$${d\over dx}(\sec x)=\sec x\; \tan x$$

>###### Cotangente
>$${d\over dx}(\mbox{cotan }x)=-\mbox{cossec}^2\,x$$

---
## Regra da Cadeia
>$${d\over dx}f(g(x))=f^`(g(x))\cdot g^`(x)$$

---
>$${d\over dx}(a^x)=a^x\ln a$$

---
## Derivadas de Funções Trigonométricas Inversas
>$${d\over dx}(\sin^{-1}x)={1\over\sqrt{1-x^2}}$$

>$${d\over dx}(\tan^{-1}x)={1\over1+x^2}$$

>$${d\over dx}(\cos^{-1}x)=-{1\over\sqrt{1-x^2}}$$

>$${d\over dx}(\mbox{cossec}^{-1}x)=-{1\over x\sqrt{x^2-1}}$$

>$${d\over dx}(\sec^{-1})={1\over x\sqrt{x^2-1}}$$

>$${d\over dx}(\mbox{cotan}^{-1}x)=-{1\over 1+x^2}$$

---
## Funções Logaritmicas
>###### Diferenciação Logaritmica
>1. Tome o logaritmo natural em ambos os lados de uma equação $y=f(x)$ e use as Leis dos Logaritmos para simplificar.
>2. Diferencie implicitamente em relação a $x$.
>3. Resolva a equação resultante para $y^`$

>$${d\over dx}(\log_ax)={1\over x\ln a}$$

>$${d\over dx}(\ln x)={1\over x}$$

>$${d\over dx}(\ln u)={1\over u}{du\over dx}$$

>$${d\over dx}[\ln g(x)]={g^`(x)\over g(x)}$$

>$${d\over dx}\ln\lvert x\rvert={1\over x}$$

---
# Diferenciação Implícita
Seja a equação a seguir
$$x^2+y^2=25$$

Para encontrarmos uma equação tangente à equação dada vamos _criar_ uma variável $t$ e duas funções $f(t)$ e $g(t)$ tais que $f$ descreva o valor de $x$ e $g$ descreva o de $y$:
$$f(t)^2+g(t)^2=5^2$$

Dessa forma, podemos diferenciar a equação em ambos os lados e aplicar a Regra da Soma:
$${d(f(t)^2+g(t)^2)\over dt}=0$$
$${d\over dt}f(t)^2+{d\over dt}g(t)^2=0$$
$$2f(t){df\over dt}+2g(t){dg\over dt}=0$$
$$2f(t)\cdot f^`(t)+2g(t)\cdot g^`(t)=0$$
$$2x\cdot dx+2y\cdot dy=0$$
$$x\cdot dx=-y\cdot dy$$
$$-1={y\cdot dy\over x\cdot dx}$$
$${dy\over dx}=-{x\over y}$$

---