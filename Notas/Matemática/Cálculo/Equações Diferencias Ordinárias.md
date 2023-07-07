#### Definição 1.1
Uma **Equação Diferencial Ordinária (EDO)** é uma equação que envolve uma função desconhecida, $y(x)$, suas derivadas até uma ordem $n$ e a variável independente $x$; ou seja, é uma equação da forma
$$f(x,y,y',y'',\ldots,y^{(n)})=0\tag{1}$$
#### Definição 1.2
A **ordem** de uma equação diferencial é a ordem da derivada mais alta que aparece na mesma.

#### Definição 1.3
Dizemos que uma EDO  de ordem $n$ é linear se ela é da seguinte forma
$$a_n(x)y^{(n)}+a_{n-1}(x)y^{(n-1)}+\ldots+a_1(x)y'+a_0(x)y=g(x),\tag{2}$$
onde os coeficientes $a_0(x),\ldots,a_n(x)$ são funções conhecida da variável $x$. Quando $g(x)$ for identicamente nula, dizemos que a equação $(2)$ é **homogênea**.
Se uma EDO de ordem $n$ não for do tipo $(2)$, dizemos que ela é **não-linear**.
As EDOs aparecem em várias aplicações e, a seguir, daremos alguns exemplos das mesmas.

### Exemplo 1.1
>Se chamarmos de $x(t)$ o número de bactérias no instante $t$, é comum supor que a taxa de variação de $x$ em cada instante seja proporcional à $x$, ou seja,
$$\frac{dx}{dt}=kx,\tag{3}$$
onde a constante de proporcionalidade, $k$, é positiva, o que nos conduz a uma EDO linear de primeira ordem homogênea.

No estudo do decaimento de massa de materiais radioativos, onde $x(t)$ é a massa do material no instante $t$, temos uma equação do tipo $(3)$, onde substituímos $k$ por $-k$.

### Exemplo 1.2
>A equação diferencial
>$$Q'+p(t)Q=g(t),\tag{4}$$
>onde $p(t)$ e $g(t)$ são funções contínuas num dado intervalo aberto $I$, é uma EDO de primeira ordem linear, ela aparece, por exemplo, em modelagem de misturas, onde $Q(t)$ descreve a quantidade de sal presente num recipiente no instante $t$.

Note que a equação $(3)$ é um caso particular de $(4)$ quando $p(t)$ é constante e $g(t)$ é identicamente nula.

### Exemplo 1.3
>A equação diferencial
>$$y'=r(1-\frac{y}{K})y$$
>onde $r$ e $K$ são constantes positivas, é chamada de equação de *Verhulst*, ou equação logística, ela aparece no contexto do crescimento ou declínio da população de uma espécie. Ela é uma EDO de primeira ordem não-linear.

Muitas equações diferenciais de segunda ordem aparecem em problemas de mecânica e resultam da Segunda Lei de Newton, a qual diz que a resultante de todas as forças, $f$, que atuam num corpo, é igual ao produto da massa do mesmo, $m$, pela sua aceleração. Como a aceleração é a derivada segunda da posição, $x$, em relação ao tempo, $t$. A força em geral depende de $t$, $x$ e da velocidade, $x'$ . Portanto a Segunda Lei de Newton pode ser colocada na seguinte forma
$$x''=\frac{f(t,x,x')}{m}\tag{5}$$
Se $f$ não depender explicitamente de $t$; ou seja, $f=f(x,v)$, podemos assumir que $v=v(x)$ e $x=x(t)$. Então da regra da cadeia, $\frac{dv}{dt}=\frac{dv}{dx}\frac{dx}{dt}=\frac{dv}{dx}$ e $(5)$ pode ser re-escrita como
$$v\frac{dv}{dx}=\frac{f(x,v)}{m}\tag{6}$$
que é uma equação diferencia de primeira ordem em $v$.

---
[[Funções|]][[Derivadas|]]