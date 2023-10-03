# [[Algoritmos|Algoritmo]] Ingênuo de Fatoração
```Python
def fatoracao_prima(n):
	fatores = []
	
	for i in range(math.floor(math.sqrt(n)-2)):
		while (i+2 % n == 0):
			fatores.append(i+2)
			n = n // i+2;
			
	if n > 1:
		fatores.append(n)
	return fatores
```

Chamemos de $n_I$ o valor inicial de $n$.

No começo de uma dada iteração do laço, todos os fatores [[Primos e o lema de Euclides#Números Primos e Compostos|primos]] de $n$ são maiores ou iguais a $i$. 
Assim, quando adicionamos $i$ a $\mbox{fatores}$, $i$ é um número primo. 
Considerando que as duas linhas no laço `while` são executadas simultaneamente, $n_I$ é sempre igual a $n$ vezes o produto dos elementos de $\mbox{fatores}$.
Se um número $k$ é composto, então seu menor fator primo $p$ satisfaz $p\leq\sqrt{k}$.
Assim, se a penúltima linha é executada, $n$ não possui fatores menores ou iguais a $\sqrt{n}$, e portanto $n$ é primo.

## Número de Operações Aritméticas
> #### $O(\sqrt{n})\Longrightarrow$ [[Comportamento Asintótico das funções|Algoritmo Pseudopolinomial]]


### Obs
Ao invés de comparar $i$ com $\lfloor\sqrt{n}\rfloor$, podemos comparar $i\cdot i$ com $n$. Isso evitaria o uso de números de ponto flutuante, aumentando a precisão e simplificando a aritmética do algoritmo.