# Máximo [[Critérios de Divisibilidade|Divisor]] Comum

>#### Definição
> Sejam $a$ e $b$ inteiros tal que ambos não sejam simultaneamente nulos. O maior inteiro $d$ tal que $d \mid a$ e $d \mid b$ é chamado de ***máximo divisor comum*** de $a$ e $b$. O máximo divisor comum de $a$ e $b$ é denotado por $mdc(a,b)$ ou $gcd(a,b)$.

---

## [[Algoritmos|Algoritmo]] de Euclides
$D(a,b) = \{d\in\mathbb{Z}:d\mid a \text{ e } d\mid b\}$ e $mdc(a,b) = \begin{cases} max(a,b)\mbox{, se }a\neq 0\mbox{ ou }b\neq0 \\  0 \mbox{ se } a = b = 0\end{cases}$
Fato: $\forall\,a\in\mathbb{N}\,\cup\{0\}, mdc(a,0)=0$.
>###### Teorema:
>Sejam $a,b,q,r\in\mathbb{Z}$ tais que $a=qb+r$. Então $mdc(a,b)=mdc(b,r)$.
```python
def euclides(a, b):
	if (b == 0):
		return b
	r = a % b
	q = (a-r)/b
	return euclides(b,r)
```
***Obs.:*** A função é [[Recursão|recursiva]].

### Complexidade do [[Algoritmos|Algoritmo]]

A complexidade Algoritmo de Euclides é proporcional ao número de digitos dos números de entrada na base 2.
###### Teorema:
O $mdc(a,b)$ usa no máximo $2\,\lfloor(\log_2b)+1\rfloor$ chamadas recursivas.
>###### Prova:
>Mostraremos que a cada duas chamadas, o segundo parâmetro cai pela metade.
>***Obs.:***  $r'\leq {b\over 2}$
> + Se $r\leq {b\over 2}$, então $r'\leq r<{b\over 2}$.
> + Se $r>{b\over 2}$, então $r<b<2r \Longrightarrow q'=1 \mbox{ e } r'=b-r < {b\over 2}$ .

---

## [[Algoritmos|Algoritmo]] Estendido de Euclides

A forma estendida do algoritmo de Euclides retorna não só o valor do $mdc(a,b)$, mas retorna também a expressão desse em termos de $a$ e $b$. Ou seja, o retorno vem na forma $x, y, mdc(a,b)$, onde $ax+by=mdc(a,b)$.

```Python
def euclides(a, b):
	if (b == 0):
		return a, 1, 0
	r = a % b
	q = (a-r)/b
	g, x_, y_ = euclides(b,r) 
	return g, y_, x_-q*y_
```
***Obs.:*** A função é [[Recursão|recursiva]].

---

# Mínimo Múltiplo Comum

>#### Definição
>O ***mínimo múltiplo comum*** dos inteiros positivos $a$ e $b$ é o menor inteiro positivo que é divisível por ambos $a$ e $b$. O mínimo múltiplo comum de $a$ e $b$ é denotado por $mmc(a,b)$ ou $lcm(a,b)$.

---

>###### Teorema
>Sejam $a$ e $b$ inteiros positivos. Então: $$ab=mdc(a,b)\times mmc(a,b)$$

---

#### Propriedades:

$$(i)\; \text{Para }b > 0 \text{ e } a \geq b,\,mdc(a,b) = mdc(a-b,b).$$

---