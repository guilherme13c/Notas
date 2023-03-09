#### Definição 1.1
Uma **Equação Diferencial Ordinária (ODE)** é uma equação que envolve uma função desconhecida, $y(x)$, suas derivadas até uma ordem $n$ e a variável independente $x$; ou seja, é uma equação da forma
$$f(x,y,y',y'',\ldots,y^{(n)})=0\tag{1}$$
#### Definição 1.2
A **ordem** de uma equação diferencial é a ordem da derivada mais alta que aparece na mesma.

#### Definição 1.3
Dizemos que uma ODE  de ordem $n$ é linear se ela é da seguinte forma
$$a_n(x)y^{(n)}+a_{n-1}(x)y^{(n-1)}+\ldots+a_1(x)y'+a_0(x)y=g(x),\tag{2}$$
onde os coeficientes $a_0(x),\ldots,a_n(x)$ são funções conhecida da variável $x$. Quando $g(x)$ for identicamente nula, dizemos que a equação $(2)$ é **homogênea**.
Se uma ODE de ordem $n$ não for do tipo $(2)$, dizemos que ela é **não-linear**.
As ODEs aparecem em várias aplicações e, a seguir, daremos alguns exemplos das mesmas.

### Exemplo 1.1
>Se chamarmos de $x(t)$ o número de bactérias no instante $t$, é comum supor que a taxa de variação de $x$ em cada instante seja proporcional à $x$, ou seja,
$$\frac{dx}{dt}=kx,\tag{3}$$
onde a constante de proporcionalidade, $k$, é positiva, o que nos conduz a uma ODE linear de primeira ordem homogênea.

No estudo do decaimento de massa de materiais radioativos, onde $x(t)$ é a massa do material no instante $t$, temos uma equação do tipo $(3)$, onde substituímos $k$ por $-k$.
