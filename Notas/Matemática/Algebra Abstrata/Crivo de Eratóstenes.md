# Crivo/Peneira De Erastóstenes
O crivo de Erastóstenes é um algoritmo para encontrar primos menores que um número específico.

```Python
def crivo(M):
	ehPrimo = [true, true, true, ..., true] # array de tamanho M + 1 onde todas as posicoes sao `true`
	ehPrimo[0] = false
	ehPrimo[1] = false
	
	for i in range(math.floor(math.sqrt(M)-2)):
		if ehPrimo[i]:
			for j in range(i*i, M+1, step=i):
				ehPrimo[j] = false
	return ehPrimo
```

O [[Algoritmos|algoritmo]] nunca marca $\mbox{ehPrimo[ }j\mbox{ ]} = \mbox{false}$ se $j$ é [[Primos e o lema de Euclides#Números Primos e Compostos|primo]], pois só marca múltiplos não triviais de $i$.
Se $n\leq \mbox{M}$ é [[Primos e o lema de Euclides#Números Primos e Compostos|composto]], então seja $i$ o menor fator primo de $n$. Já vimos que $i^2\leq n$ e, portanto, $i\leq\sqrt{\mbox{M}}$. Logo, na iteração correspondente a $i$ do loop externo, $n$ será marcado como composto.

## [[Comportamento Asintótico das funções|Complexidade do Crivo]]

`Assistir à aula 5.2 para encontrar a explicação`

$${M\over2}+{M\over3}+{M\over5}+{M\over7}+\cdots$$
$$\leq {M\over2}+{M\over3}+M\Big({1\over p_3}+{1\over p_4}+\cdots+{1\over p_n}\Big)$$
$$\leq {M\over2}+{M\over3}+{M\over{c'}}\Big(\sum_{i=3}^{M}{1\over{i\cdot\log i}} \Big)$$
$$leq {M\over2}+{M\over3}+{M\over{c'}}\int_2^M{1\over x\cdot \ln x} dx$$
$$=O(M\cdot \log\log M)$$
