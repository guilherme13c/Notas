# Regressão Linear
[[Normas de Vetores|]][[Funções|]][Aula](https://www.youtube.com/watch?v=4qwuwMbsUZA)

A regressão linear é o método usado para estimar uma relacão linear em um conjunto de dados coletados. Essa relação pode ser descrita como a reta $r$:

$$r:y=\beta_1\cdot x+\beta_0$$
Como os dados coletados possuem ***resíduo*** $(\epsilon)$, a reta que melhor representa a relação $r$ é aquela que minimiza os resíduos.

Forma matricial:
$$\begin{bmatrix}1&x_n\end{bmatrix}\begin{bmatrix}\beta_0\\ \beta_1\end{bmatrix}=y_n+\epsilon_n$$
$$\begin{bmatrix}1&x_1\\1&x_2\\\vdots&\vdots\\1&x_n\end{bmatrix}\begin{bmatrix}\beta_0\\ \beta_1\end{bmatrix}=\begin{bmatrix}y_1\\y_2\\\vdots\\y_n\end{bmatrix}+\begin{bmatrix}\epsilon_1\\\epsilon_1\\\vdots\\\epsilon_n\end{bmatrix}$$
$$A\mbox{x}=b+e$$
$$e=A\mbox{x}-b$$
Expressão analítica:
$$\hat{\beta_1}={\sum_i(x_i-\bar{x})(y_i-\bar{y})\over\sum_i(x_i-\bar{x})^2}$$
$$\hat{\beta_0}=\bar{y}-\hat{\beta_1}\bar{x}$$
onde $\bar x$ e $\bar y$ são, respectivamente, as médias dos valores de $x$ e $y$.

---
## Código de Regressão Linear
```python
import numpy as np
import matplotlib.pyplot as plt

SPAN = 500

X = []
Y = []

class Point:
	def __init__(self):
		self.x = np.random.randint(0, SPAN)
		self.y = np.random.normal(scale=SPAN/3) + self.x * 2
		
		X.append(self.x)
		Y.append(self.y)

# gerando pontos aleatorios
for i in range(30):
	p = Point()

# plotando pontos aleatórios
plt.scatter(X, Y)

# calculando médias das coordenadas dos pontos
mu_x = np.mean(X)
mu_y = np.mean(Y)

# calculo Beta1
num = sum((x - mu_x) * (y - mu_y) for x, y in zip(X, Y))
den = sum ((x - mu_x)**2 for x in X)

Beta1 = num / den

# calculo Beta0
Beta0 = mu_y - (Beta1 * mu_x)

# configurando o gráfico e plotando a reta de regressão
Xspace = np.linspace(0, SPAN, SPAN)
Yspace = Xspace * Beta1 + Beta0

plt.plot(Xspace, Yspace, color='red')

for x, y in zip(X, Y):
	plt.scatter(x, x * Beta1 + Beta0, color='g', marker='x')
	plt.plot([x,x], [x * Beta1 + Beta0, y], color='g', alpha=0.5)

plt.grid(True, alpha=0.3)
plt.show()
```
![[regressao_linear1 1.png]]

---
# Regressão Linear Múltipla
[Aula](https://www.youtube.com/watch?v=vYXuiGyjYoA)

#### Ampliando o Modelo Anterior
Chegamos na conclusão, anteriormente, que uma relação linear entre dois fatores pode ser estimada por uma equação de reta da forma
$$r:y=\beta_0 + x\cdot\beta_1$$
onde $x$ representa um fator e $y$ representa outro.
Em casos onde um fator ($y$) é dependente de mais de um fator ($x,z,t,\ldots$), podemos incrementar a equação de reta anterior para uma equação da forma
$$y=\beta_0+\beta_1\cdot f_1+\beta_2\cdot f_2+\ldots+\beta_m\cdot f_m=\beta_0+\sum_{i=1}^m(\beta_i\cdot f_i)$$
onde $n$ é o número de fatores e cada $f_i$ é um fator, sendo $\beta_i$ o seu coeficiente (ponderador).

Forma matricial:
$$y_1\approx\beta_0+\beta_1\cdot f_{1_1}+\beta_2\cdot f_{2_1}+\ldots+\beta_n\cdot f_{m_1}=\beta_0+\sum_{i=1}^m(\beta_i\cdot f_{i_1})$$
$$y_2\approx\beta_0+\beta_1\cdot f_{1_2}+\beta_2\cdot f_{2_2}+\ldots+\beta_n\cdot f_{m_2}=\beta_0+\sum_{i=1}^m(\beta_i\cdot f_{i_2})$$
$$\vdots$$
$$y_n\approx\beta_0+\beta_1\cdot f_{1_n}+\beta_2\cdot f_{2_n}+\ldots+\beta_n\cdot f_{m_n}=\beta_0+\sum_{i=1}^m(\beta_i\cdot f_{i_n})$$
$$\begin{bmatrix}y_1\\y_2\\ \vdots\\y_n\end{bmatrix}\approx\begin{bmatrix}\beta_0\\\beta_0\\\vdots\\\beta_0\end{bmatrix}+\begin{bmatrix}\beta_1\cdot f_{1_1}\\\beta_1\cdot f_{1_2}\\\vdots\\\beta_1\cdot f_{1_n}\end{bmatrix}+\begin{bmatrix}\beta_2\cdot f_{2_1}\\\beta_2\cdot f_{2_2}\\\vdots\\\beta_2\cdot f_{2_n}\end{bmatrix}+\cdots+\begin{bmatrix}\beta_m\cdot f_{m_1}\\\beta_m\cdot f_{m_2}\\\vdots\\\beta_m\cdot f_{m_n}\end{bmatrix}$$
$$\begin{bmatrix}y_1\\y_2\\ \vdots\\y_n\end{bmatrix}\approx\beta_0\begin{bmatrix}1\\1\\\vdots\\1\end{bmatrix}+\beta_1\begin{bmatrix}f_{1_1}\\f_{1_2}\\\vdots\\ f_{1_n}\end{bmatrix}+\beta_2\begin{bmatrix}f_{2_1}\\f_{2_2}\\\vdots\\f_{2_n}\end{bmatrix}+\cdots+\beta_m\begin{bmatrix}f_{m_1}\\f_{m_2}\\\vdots\\f_{m_n}\end{bmatrix}$$
$$\begin{bmatrix}y_1\\y_2\\ \vdots\\y_n\end{bmatrix}\approx\begin{bmatrix}1&f_{1_1}&f_{2_1}&\cdots&f_{m_1}\\1&f_{1_2}&f_{2_2}&\cdots&f_{m_2}\\\vdots&\vdots&\vdots&\ddots&\vdots\\1&f_{1_n}&f_{2_n}&\cdots&f_{m_n}\end{bmatrix}\cdot\begin{bmatrix}\beta_1\\\beta_2\\\vdots\\\beta_m\end{bmatrix}$$
$$Y\approx Xb$$
***Obs.:*** É importante destacar que a matriz $X$ não é necessariamente quadrada. Se ela não for, o sistema não terá solução.

---