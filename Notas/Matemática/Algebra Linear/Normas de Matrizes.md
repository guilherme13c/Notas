# [Distância Estatística](https://www.youtube.com/watch?v=CPFej2oVWlg)
Precisamos de uma distância diferente da euclidiana para detectar anomalias em dados.

Vamos começar vendo matrizes de dados estatísticos: matrizes com $n$ items e $k$ colunas ou variáveis.

---
# Norma-S
Seja $S$ uma [[Matrizes Simétricas|matriz simétrica]] e [[Matrizes Simétricas#Matrizes Definidas Positivas|definida positiva]]

Defina:
+ Norma-S:		$\|x\|_s=x^TSx=\Sigma_{i,j}x_ix_jS_{ij}$

---
# Normas Matriciais
## Norma Matricial: Definição
A norma de uma matriz é uma função $\|\star\|$ do conjunto de todas matrizes reais (de todas ordens finitas) para $\mathbb{R}$ que satisfaz as seguintes propiedades:
> $(i)$ $\|A\|\ge0$ e $\|A\|=0\iff A=0$
> $(ii)$ $\|\alpha A\|=|\alpha|\|A\|\;\;$ para todo $\alpha$ escalar.
> $(iii)$ $\|A+B\|\le\|A\|+\|B\|\;\;$ para matrizes do mesmo tamanho.
> $(iv)$ $\|AB\|\le\|A\|\cdot\|B\|\;\;$ tara todas matrizes conformáveis.

---
## Norma de Frobenius
A mais simples norma matricial.

+ Empilhe as colunas da matriz como um vetor e calcule a sua norma [[Normas de Vetores#Norma L2 e Lp|L2]]
$$A=\begin{bmatrix}1.3&5.9&-1.8\\1.7&6.1&9.7\end{bmatrix}\rightarrow\|A\|_F=\sqrt{(1.3)^2+(5.9)^2+(-1.8)^2+(1.7)^2+(6.1)^2+(9.7)^2}$$
$$\|A\|_F=\|B\|,\;B=\begin{bmatrix}1.3\\1.7\\5.9\\6.1\\-1.8\\9.7\end{bmatrix}$$
$$\|A\|_F=\sqrt{\sum_{i,j}|a_{ij}|^2}$$

#### Outras descrições úteis
$$\|A\|_F=\sqrt{\sum_{i,\,j}|a_{ij}|^2}=\sqrt{\sum_{j=1}^m\|a_j\|_2^2}=\sqrt{\sum_{i=1}^n\|b^T_i\|^2_2}=\mbox{trace}(A^TA)$$

---
## Normas Induzidas
Uma norma qualquer para vetores do $R^n$ induz uma norma no espaço das matrizes $m\times n$.

Seja $C =$ conjunto dos $x$ em $R^n$ tais que $\|x\|=1$
Seja $A$ uma matriz $m\times n$ qualquer
Então
$$\|A\|=\mbox{max}_{\mbox{x}\in C}\{\|A\mbox{x}\|\}$$

### Norma Espectral (induzida pela Norma Vetorial Euclidiana)
$$\|A\|_2=\max_{\|x\|_2=1}\|A\mbox{x}\|_2=\sqrt{\lambda_\max},$$
onde $\lambda_\max$ é o maior número $\lambda$ tal que $A*A-\lambda I$ é [[Decomposição por Valores Singulares - SVD|singular]].

### Norma-1 Matricial (induzida pela Norma-1 Vetorial)
Máximo dentre as somas dos valores absolutos de coluna.

$$A=\begin{bmatrix}2&-3&1\\2&0&-1\\1&4&5\end{bmatrix}$$
$$\|A\|_1=\max((2+2+1),(3+0+4),(1+1+5))=7$$

### Norma-$\infty$ (induzida Pela Norma-$\infty$ Vetorial)
Máximo dentre as somas dos valores absolutos de linha.

$$A=\begin{bmatrix}2&-3&1\\2&0&-1\\1&4&5\end{bmatrix}$$
$$\|A\|_\infty=\max((2+3+1),(2+0+1),(1+4+5))=10$$

---