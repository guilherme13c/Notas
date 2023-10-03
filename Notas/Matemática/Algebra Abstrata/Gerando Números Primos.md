[[Primos e o lema de Euclides|]][[Crivo de Eratóstenes|]][[Testes de Primalidade e Números de Carmichael|]]
# Gerando Primos
> ###### Teorema dos Números Primos
> Para $n$ grande, o conjunto $\{1,2,\ldots,n\}$ tem cerca de $1\over\ln(n)$ primos.

Probabilidade de um número de $b$ bits set primo $\thickapprox$ ${1}\over{b\cdot\ln(2)}$  

Para sortear um número de $b$ bits, basta sortear um número de $b$ bits e testar se ele é primo (até set bem-sucedido)

O número médio de tentativas para obter um primo de $b$ bits com essa estratégia é o inverso da probabilidade, ou seja, $b\cdot\ln(2)$ tentativas.

Para casos com $b\not=2$ sabemos o último bit deverá set $1$ para que o número seja primo. Limitando os sorteios aos números que atendem essa propriedade, a probabilidade aumenta para $\thickapprox$ ${1}\over{b\cdot\ln(2)}$$\cdot2\,$$=$$\,2\over b\ln(2)$, e o número médio de tentativas diminui para $b\cdot\ln(2)\over2$.

---