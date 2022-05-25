[Aula 1](https://www.youtube.com/watch?v=hlaLh-chsyE)
[Aula 2](https://www.youtube.com/watch?v=UCuKFbxvRT4)

---
# PCA
É uma técnica de Análise de Dados para redução de dimensionalidade.
![[pca1.png]]
PCA tranforma um conjunto de variáveis possivelmente correlacionadas (ex. 100 ou 1000) em um conjunto menor de variáveis (ex. 10) chamadas **componentes principais**.

---
## Para que serve?
+ Visualização: normalmente é o primeiro passo ao analisar datasets de alta dimensionalidade
+ Acelerar treinamento de modelos de aprendizado de máquina

---
# Centrando os pontos
$$\begin{bmatrix}x_1\\ x_2\\ x_3\end{bmatrix}=\begin{bmatrix}\mu_1\\ \mu_2\\ \mu_3\end{bmatrix}+\begin{bmatrix}\begin{bmatrix}x_1\\ x_2\\ x_3\end{bmatrix}-\begin{bmatrix}\mu_1\\ \mu_2\\ \mu_3\end{bmatrix}\end{bmatrix}$$
$$\mbox{x}=\mu+[\mbox{x}-\mu]=\mu+\mbox{y}$$
Subtraindo a média de cada coordenada-variável, temos um novo vetor $\mbox{y}$ com média zero em cada coordenada.

A nuvem de pontos é deslocada rigidamente para a origem.

---
# Pré-processamento dos dados
Primeiro ***z-normalizamos*** os dados:
1. Seja $\mu={1\over m}\sum_{i=1}^m\mbox{x}^{(i)}$
2. Subtraia cada $\mbox{x}^{(i)}$ por $\mbox{x}^{(i)}-\mu$
3. Seja $\sigma^2_j={1\over m-1}\sum_i(x_j^{(i)})^2$
4. Substitua cada $x_j^{(i)}$ por ${x^{(i)}_j\over\sigma_j}$

Passos 3-4: garantem que atributos sejam tratados igualmente

---
# Decomposição Ortogonal
Dizer que o vetor $\mbox{x}_\mbox{w}$ é o vetor mais próximo a $\mbox{x}$ em $\mbox{W}$ equivale a dizer que a diferença $\mbox{x}-\mbox{x}_\mbox{w}$ é ortogonal a $\mbox{W}$.

>###### Teorema
>Seja $\mbox{w}$ um subspaço do $\mathbb{R}^n$ e $\mbox{x}$ um vetor em $\mathbb{R}^n$. Então podemos escrever $\mbox{x}$ de forma única como:
>$$\mbox{x}=\mbox{x}_\mbox{w}+\mbox{x}_{\mbox{w}^\bot}\;\;\;(1)$$
>Onde $\mbox{x}$ é o vetor mais próximo a $\mbox{x}$ em $\mbox{W}$ e $\mbox{x}_{\mbox{w}^\bot}$ está em $\mbox{W}^\bot$.

>#### Definição
>Equação $(1)$ é chamada decomposição ortogonal de $\mbox{x}$ com relação à $\mbox{W}$; vetor $\mbox{x}_\mbox{w}$ é a projeção ortogonala de $\mbox{x}$ em $\mbox{W}$.

---
# Projeção em plano ou hiperplano
Seja $W$ o espaço gerado por $\{v_1,\ldots,v_m\}$ e $A$ a matriz cujas colunas são $\{v_1,\ldots,v_m\}$. Para calcular a decomposição ortogonal de $\mbox{x}$ em relação a $W$:
1. Calcule a matriz $A^TA$ e o vetor $b=A^T\mbox{x}$
2. Resolva $A^TAc=b$ e encontre o vetor desconhecido $c$
3. O sistema é sempre consistente, escolha uma solução $c$:
	
	$\mbox{x}_W=Ac$,  pelo teorema da [[Autovalores e Autovetores#Decomposição Espectral|decomposição espectral]], resulta em $\mbox{x}_{W\bot}=\mbox{x}-\mbox{x}_W$
	$\iff x_W=A(A^TA)^{-1}A^Tx$
	
---
 
