[[Primos e o lema de Euclides|]][[Ciclos e o Pequeno Teorema de Fermat|]][[Exponenciação Binária|]]
# Testes de Primalidade
## Teste de Fermat
Seja $1<a<n$:
- Se $a^{n-1}\not\equiv1\;\;(\mbox{mod }n)$, então $a$ é testemunha da não-primalidade de $n$.
- Se $n$ é composto mas $a^{n-1}\equiv1\;\;(\mbox{mod }n)$, então $n$ é _pseudoprimo_ em base $a$.

#### Definição: Número de Carmichael
$n$ é um número de Carmichael se $n$ é composto e $a^{n-1}\equiv1\;\;(\mbox{mod }n)$ para todo $a\in\mathbb{N}$ tal que $\mbox{mdc}(a,n)=1$. 

###### Teorema de Korselt
Um número $n$ é de Carmichael se e somente se
- $n=p_1\cdot p_2\cdot\ldots\cdot p_k$ para $p_1,p_2,\ldots,p_k$ primos distintos $(k\geq 2)$ e
- $p_j-1\vert n-1$ para todo $j=1,2,\ldots,k$

---

## Teste de Miller
>#### Fatos
>1. Se $n$ é primo e $1<a<n$, então $a^{n-1}\equiv1\;(\mbox{mod }n)$.
>2. Se $n$ é primo e $x^2\equiv1\;(\mbox{mod }n)$, então $x\equiv1\;(\mbox{mod }n)$ ou $x\equiv-1\;(\mbox{mod }n)$.

Se $n$ é ímpar e $n-1=2^t\cdot q$ com $q$ ímpar, então:
- ou $a^q\equiv1\;(\mbox{mod }n)$
- ou $a^{2^i\cdot q}\equiv-1\;(\mbox{mod }n)$ para algum $i=0,\ldots,t-1$

#### Algoritmo
```python
def miller(a, n):
	# Sejam t, q tais que n-1=(2**t)*q com q ímpar
	r = (a**q) % n # <-- usar exponenciação binária
	if (r % n == 1):
		return "inconclusivo"
	for i in range(t):
		if (r % n == n-1):
			return "inconclusivo"
		r = r * r % n
	return "composto"
```

>###### Teorema (Rabin)
>Se $n$ é composto, pelo menos 75% dos $1<a<n-1$ são testemunhas de Miller da não-primalidade de $n$.

## Teste de Miller-Rabin
```python
def millerRabin(n, k):
	# n>=5, ímpar # k -> número de iterações
	for i in range(k):
		a = random(1, n) # sorteia a tal que 1<a<n-1
		if (miller(a, n) == "composto"):
			return "composto"
	return "provavelmente primo"
	# chance de errar <= (1/4)**k
```

---