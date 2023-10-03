# Multiplicação Entre Matriz e Vetor
$$\begin{bmatrix}a_{11}&a_{12}\\ a_{21}&a_{22} \end{bmatrix} \begin{bmatrix}x_1\\ x_2 \end{bmatrix} = \lambda\begin{bmatrix}x_1\\x_2 \end{bmatrix}$$
$$\Rightarrow AX=\lambda X$$
$$\Rightarrow AX-\lambda X = \bar{0}$$
$$\Rightarrow AX-\lambda IX = \bar{0}$$
$$\Rightarrow (A-\lambda I)X = \bar{0}$$
$$\Rightarrow \begin{bmatrix}a_{11}-\lambda && a_{12}\\ a_{21} && a_{22}-\lambda\end{bmatrix}\begin{bmatrix} x_1\\ x_2 \end{bmatrix} = \begin{bmatrix} 0\\ 0\end{bmatrix}$$

As soluções $\lambda$ são chamadas de **autovalores**.

O vetor nulo não é um autovetor, então precisamos que $\\ \det{(A-\lambda I)}=0$ seja verdadeiro.

Para calcular os autovetores, substituímos os autovalores $\lambda_1,\ldots,\lambda_k$ em $A-\lambda I$:
$$AX-\lambda_iX=\bar{0}\;,\;\;(1\leq i\leq k)$$
$$\Rightarrow(A-\lambda_i I)X=\bar{0}$$

As soluções $X$ e seus múltiplos escalares são chamadas de **autovetores**, e cada autovetor $X$ é relativo a um autovalor $\lambda$.

***Obs.:*** Ao multiplicar um autovetor $v$ de $A$ por $A$, o resultado é multiplo de $v$:
$$vA=v\lambda$$

---
## Traço, determinante e autovalores
> ###### $(i)$
> O traço, que é a soma da diagonal da matriz, é igual à soma dos autovalores.
> $$tr(A)=\sum_{i=1}^{n}a_{ii}=\sum_{i=1}^{m}{\lambda_i}$$

> ###### $(ii)$
> A determinante é igual ao produto dos autovalores
> $$det(A)=\prod_{i=1}^{m}{\lambda_i}$$

---
## Potência da matriz

Se $X$ é autovetor de $A$, então $X$ é autovetor de $B = A^2$. Se $\lambda$ é autovalor de $A$, então $\lambda^k$ é autovalor de $A^k$.

$$\forall k\in\mathbb{Z},A^kX=\lambda^kX$$

***Intuitivamente:*** Se uma transformação linear $A$ conserva a direção do autovetor $X$, então aplicar essa mesma transformação novamente conservará a direção de $X$ novamente.

---
# Autovetores e a Matriz

Se uma matriz $A_{n\times n}$ possui $n$ autovetores independentes, então um vetor $v_{n\times 1}$ pode set escrito como a combinação dos autovetores.

$v=c_1x_1+\cdots+c_nx_n$
$Av=c_1\lambda_1x_1+\cdots+c_n\lambda_nx_n$

---
# Matrizes Similares

Para toda matriz $M$ invertível:
+ $B=M^{-1}AM$ tem os mesmos autovalores de $A$.
+ $B$ e $A$ são matrizes similares.

---
# Decomposição Espectral

Seja uma matriz $A_{n\times n}$ com $n$ autovetores independentes:
$$A\begin{bmatrix}&& \\ X_1&\cdots&X_n\\ &&\end{bmatrix}=\begin{bmatrix}&& \\ AX_1&\cdots&AX_n\\ &&\end{bmatrix}=\begin{bmatrix}&& \\ \lambda_1X_1&\cdots&\lambda_nX_n\\ &&\end{bmatrix}$$
$$A\begin{bmatrix}&& \\ X_1&\cdots&X_n\\ &&\end{bmatrix}=\begin{bmatrix}&& \\ X_1&\cdots&X_n\\ &&\end{bmatrix}\begin{bmatrix}\lambda_1& & \\ &\ddots& \\ &&\lambda_n\end{bmatrix}$$
$$AX=X\Lambda$$
$$AXX^{-1}=X\Lambda X^{-1}$$
$$A=X\Lambda X^{-1}\mbox{onde }\Lambda\mbox{, é chamada de matriz de autovalores.}$$

## Diagonalização de Matriz
Uma forma de calcular $A^k$ eficiente é:

$$A^k=X\Lambda^kX^{-1}$$

---
# Calculo de autovalores ([[Algoritmos|Algoritmo]] QR)
Em matrizes triangulares, os autovalores se encontram na diagonal. Por exemplo:
Os autovalores da matriz $A=\begin{bmatrix}1&2&3\\0&4&5\\0&0&6\end{bmatrix}$ são: $\lambda_1=1,\lambda_2=4,\lambda_3=6$.
Dessa forma, é simples e rápido calcular os autovalores dessas matrizes.
## [[#Matrizes Similares]]
Para matrizes $A$ não triangulares, podemos transformá-las em matrizes triangulares de forma a preservar os autovalores. Para tal podemos utilizar uma matriz triangular $B$ que seja similar a $A$.
$$B=M^{-1}AM$$
$$BX=\lambda X$$
$$BX=(M^{-1}AM)X$$
$$M\underbrace{BX}_{\lambda X}=\underbrace{MM^{-1}}_IAMX$$
$$\lambda\;\underbrace{MX}_Y=A\underbrace{MX}_Y$$
$$\lambda Y=AY$$
Podemos usar qualquer matriz $M$ para tal transformação, desde que $M$ seja invertível. Dessa maneira, vamos utilizar $M=Q$, de forma que $Q$ é ortonormal e $A=QR$, com $R$ triangular.
$$B=\underbrace{Q^TA}_RQ$$
$$B=RQ$$
Esse processo pode set repetido diversas vezes, sendo que cada iteração dexia $B$ mais próxima de uma matriz triangular. Dessa forma, após várias iterações desse algoritmo, teremos aproximações dos autovalores de $A$ na diagonal de $B$.

> ###### Algoritmo $QR$
> Seja $A_0=A$.
> - Obtenha $A_0=Q_0R_0$
> - Defina $A_1=Q_0^TA_0Q_0$
> - Obtenha $A_1=Q_1R_1$
> - Defina $A_2=Q_1^TA_1Q_1$
> $\vdots$
>
Repita até obter uma matriz aproximadamente triangular superior.

---
