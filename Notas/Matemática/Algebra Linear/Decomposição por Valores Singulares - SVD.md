# SVD Completo

$$A_{m\times n}=U_{m\times m}\Sigma_{m\times n} V_{n\times n}^T$$
onde $U$ é uma matriz unitária $m\times m$, $\Sigma$ é uma matriz retangular diagonal $m\times n$ com números reais não negativos na diagonal, e $V^T$ é uma matriz unitária $n\times n$. As entradas diagonais de $\Sigma\;(\Sigma_{ii})$ são chamadas de valores singulares de $A$.

# SVD Reduzido

Como apenas os $r$ primeiros elementos da diagonal de $\Sigma$ são não nulos, podemos tomar esta submatriz, descartando as colunas $r+1,\ldots,m$ de $U$ e as linhas $r+1,\ldots,n$ de $V^T$. O resultado, denotado pelas mesmas letras, é

$$A_{m\times n}=U_{m\times r}\Sigma_{r\times r} V_{r\times n}^T$$

---

#  SVD em "pedaços"

Podemos escrever a decomposição como a soma de matrizes de posto 1
$$A=U\Sigma V^T=\sigma_1u_1v_1^T+\ldots+\sigma_ru_rv_r^T$$

---
## [[Autovalores e Autovetores|Autovalores]] e Valores Singulares

>###### Pergunta
> Existe alguma relação entre autovalores e valores singulares?
> $$A = U\Sigma V^T$$
> $$S=X\Lambda X^{-1}$$

>###### Resposta
>Sim. 2 [[Matrizes Simétricas|matrizes simétricas]].
>>$A_{n\times m}^TA_{m\times n}=S$
>>$A^TA=(U\Sigma V^T)^TU\Sigma V^T$
>>$=V\Sigma U^TU\Sigma V^T$
>>$=V\Sigma^2V^T$
>>$=\begin{bmatrix}|& &|\\ v_1&\cdots&v_r\\ |& &|\end{bmatrix}\begin{bmatrix}\sigma_1^2& \\ & \ddots\\ && \sigma_r^2\end{bmatrix}\begin{bmatrix}-&v_1^T&-\\ & \vdots &\\ -&v_r^T&-\end{bmatrix}$
>>$=Q\Lambda Q^T$
>>
>> Dessa forma, os autovalores de $S=A^TA$ são valores singulares de $A$ elevados ao quadrado e autovetores de $S$ são vetores singulares direitos de $A$.
>
>>$A_{m\times n}A_{n\times m}^T=S$
>>$AA^T=U\Sigma V^T(U\Sigma V^T)^T$
>>$=U\Sigma V^TV\Sigma U^T$
>>$=U\Sigma^2 U^T$
>>$=\begin{bmatrix}|& &|\\ u_1&\cdots&u_r\\ |& &|\end{bmatrix}\begin{bmatrix}\sigma_1^2& \\ & \ddots\\ && \sigma_r^2\end{bmatrix}\begin{bmatrix}-&u_1^T&-\\ & \vdots &\\ -&u_r^T&-\end{bmatrix}$
>>$=Q\Lambda Q^T$
>> Dessa forma, os autovalores de $S=AA^T$ são valores singulares de $A$ elevados ao quadrado e autovetores de $S$ são vetores singulares esquerdos de $A$.

## Decompondo A
 1. Calcule os autovetores $v$'s de $A^TA$
 2. Faça $\sigma_k=\sqrt{\lambda_k}$
 3. Então calcule: $${u_k=}{Av_k\over\sigma_k}$$
 
 ---
 # Geometria de SVD
 
 Vamos começar por uma matriz de rotação $R$:
 $$R(\theta)=\begin{bmatrix}\cos(\theta) & -\sin(\theta)\\ \sin(\theta) & \cos(\theta)\end{bmatrix}$$
 
 $$Rv=(U\Sigma V^T)v = U\Sigma(V^Tv)$$
 ![[pre-mult por V^t.png]]
  $$Rv= U\Sigma \mbox{x},\;\;\mbox{x}=V^Tv$$
  
  Agora vamos ver o que acontece quando usamos uma matriz de escala $\Sigma$:
  $$\Sigma(\sigma_1,\sigma_2)=\begin{bmatrix}\sigma_1&0\\ 0&\sigma_2\end{bmatrix}$$
  $$\Sigma \mbox{x}=\begin{bmatrix}\sigma_1&0\\ 0&\sigma_2\end{bmatrix}\begin{bmatrix}x_1\\x_2\end{bmatrix}=\begin{bmatrix}\sigma_1 x_1\\\sigma_2 x_2\end{bmatrix}$$
  ![[rotacao matriz.png]]
  $$Rv=Uy,\;\;y=\Sigma\mbox{x}$$
  ![[rotacao matriz2.png]]
  
  ---