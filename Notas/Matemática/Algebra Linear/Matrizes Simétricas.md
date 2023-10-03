# Matrizes Simétricas

$$S = \begin{bmatrix} 0&1\\1&0\end{bmatrix} = S^T$$

> ###### Teorema
> Seja $S$ uma matriz real simétrica de ordem $n$. Todos [[Autovalores e Autovetores|autovalores]] são reais e possui $n$ autovalores ortogonais (mesmo se autovalores repetidos).
> #### [Demonstração](https://www.youtube.com/watch?v=gJhlkEBZsfI&t=0s)

---
# Aplicações

Matrizes simétricas aparecem em várias aplicações importantes (e.g., visão computacional, grafos, otimização).

---
# [[Autovalores e Autovetores#Decomposição Espectral|Decomposição Espectral]] De $S$

Como $S$ possui sempre $n$ autovetores independentes, existe decomposição espectral$$S=X\Lambda X^{-1}$$
onde colunas $x_i$ são autovetores. Como os autovetores são ortogonais, normalizando cada $x_i$, temos$$S=Q\Lambda Q^{-1}$$
Como $Q$ é quadrada, $Q^{-1}=Q^T$. Portanto, $$S = Q\Lambda Q^T$$

---
# Matrizes Definidas Positivas

São [[Matrizes Simétricas#Matrizes Simétricas|Matrizes Simétricas]] onde:

$(i)$ Todos $\lambda_i>0$;
$(ii)$ Energia $=x^TSx\;>0\;\,\forall x\not=0\,$;
$(iii)$ $S=A^TA$ (com colunas de $A$ independentes);
$(iv)$ Todos os menores principais líderes $>0$;
		i.e., $\det(A[:k,:k])>0, k=1,\ldots,n$
$(v)$ Todos os pivôs na eliminação $>0$.

***Obs.:*** As afirmações são equivalentes portanto a validate de qualquer uma garante a validate das demais.

## $QSQ^T$

É sempre simétrica e [[Matrizes Simétricas#Matrizes Definidas Positivas|definida positiva]], já que
$(Q^TSQ)^T=Q^TS^TQ=Q^TSQ$
e
$Q^TSQ=Q^{-1}SQ$ é similar a $S$.

---
# Matrizas Semidefinidas Positivas

$(i)$ Todos $\lambda_i\geq0$;
$(ii)$ Energia $=x^TSx\;\geq0\;\,\forall x\not=0\,$;
$(iii)$ $S=A^TA$ (colunas dependentes permitidas em $A$);
$(iv)$ Todos os menores principais líderes $\geq0$;
		i.e., $\det(A[:k,:k])>0, k=1,\ldots,n$
$(v)$ $r$ pivôs na eliminação $>0$, com $r\leq n$.

***Obs.:*** As afirmações são equivalentes portanto a validate de qualquer uma garante a validate das demais.

---