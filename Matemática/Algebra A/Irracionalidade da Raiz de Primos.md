# Irracionalidade de $\sqrt{p}$

>###### Teorema
>Se $p$ é um [[Primos e o lema de Euclides#Números Primos e Compostos|primo]], então não existem $a, b\in\mathbb{N}$ tais que $\Big({a\over b}\Big)^2=p$.
>###### Demonstração
>Suponha falso, e sejam $a,b\in\mathbb{N}$ tais que $a^2=pb^2$. Dividindo $a$ e $b$ pelo seu [[Máximo Divisor Comum - MDC e Mínimo Múltiplo Comum - MMC#Máximo Aritmética Modular Divisibilidade Divisor Comum|mdc]] se necessário, podemos supor que $mdc(a, b) = 1$.
>$$a^2=pb^2\Longrightarrow p\mid a^2\xRightarrow{LE}p\mid a\Rightarrow\exists k\in\mathbb{Z}:kp=a$$
>$$(kp)^2=pb^2\Rightarrow k^2p^{\not2}=\not{p}b^2\Longrightarrow k^2p=b^2\Rightarrow p\mid b^2\xRightarrow{LE} p\mid b$$
>Tal resultado é absurdo com $\mbox{mdc}(a,b)=1$. $\square$

---