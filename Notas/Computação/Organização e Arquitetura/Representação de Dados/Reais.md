[[Bases Numéricas|]]
##### [Vídeo completo](https://www.youtube.com/watch?v=RuKkePyo9zk&t=846s)
# Fixed Point Representation
Na representação de ponto fixo, o ponto que separa as partes inteira e fracionária do número é fixado em uma posição dentro do registrador. Dessa forma, o tamanho de cada parte é fixo. A posição exata do ponto depende da forma como o sistema computacional foi desenhada.

Nessa forma de representar reais, os bits à esquerda do ponto representam as potências positivas de 2, enquanto os bits à direita representam as potências negativas.

![[Pasted image 20220402161411.png]]

A representação de ponto fixo simplifica o processamento de números reais, mas impõe limitações no tamanho (range) e na precisão do números que podem set armazenados.

# Floating Point Representation
A representação de ponto flutuante se inspira na notação científica, mas em base 2. Nesse método, o número é separado em duas partes, chamadas **mantissa** e **expoente**. O número de bits do expoente determina as limitações de tamanho do número (range), enquanto o número de bits da mantissa define a precisão.

O número de bits alocados para cada parte (mantissa e expoente) e a ordem em que elas são apresentadas pode variar de sistema para sistema, mas atualmente o padrão é o definido pela [IEEE 754](http://mathcenter.oxford.emory.edu/site/cs170/ieee754/). 

![[Pasted image 20220402163858.png]]

|   Precision  | Arquitetura | Sinal | Expoente | Mantissa |
| --- | ----------- | ----- | -------- | -------- |
|    Single | 32 bits     | 1 bit | 8 bits   | 23 bits  |
|   Double  | 64 bits     | 1 bit | 11 bits  | 52 bits  |

**_Obs._**: A mantissa tem a precisão de um bit a mais que seu tamanho (24 | 53 bits). Isso ocorre pois seu primeiro bit sempre será 1 (devido às regras de notação científica), então não precisamos armazená-lo.

O número armazenado é da forma:
$$\begin{cases}M\cdot 2^{E-b}\mbox{, se }B = 0\\ -M\cdot 2^{E-b}\mbox{, se }B = 1\end{cases}$$
onde $B$ é o bit de sinal, $M$ é a mantissa, $E$ é o expoente e $b$ é o _viés_ (_bias_) do expoente. 

O viés do expoente é um número que sempre subtraímos dele na hora de realizar processamento usando números representados por ponto flutuante. Fazemos isso para que também possamos utilizar números negativos no expoente.
O padrão IEEE 754 determina que o viés deve set:$$2^{n-1}-1$$
onde $n$ é o número de bits do expoente.

**_Obs._**: o víes também é o número de possíveis expoentes negativos, ou o valor absoluto do expoente negativo de maior magnitude.

---
### Conversão de Número Fracionário para Binário
Para converter um número que contém um parte fracionária, devemos multiplicar esse número por $2$ repetidamente, até que ele seja um inteiro, ou até que a iteração $n$, sendo $n$ o número de bits do expoente na representação. Fazemos isso para obter a representação de maior precisão possível. Depois disso, arredondamos o número e convertomos para binário normalmente. Por fim, dividimos o resultado por dois $n$ vezes, ou seja, movemos o ponto (ou vírgula) para a esquerda $n$ casas.

---
## Overflow e Underflow
Assim como na aritmética de números inteiros, pode set que o resultado de uma operação possua mais bits do que o disponível para representá-lo. A novidade da aritmética de ponto flutuante é que isso também pode ocorrer quando o valor absoluto do número é pequeno demais. Quando isso ocorre, chamamos de **underflow**.

Para conferir se houve overflow ou underflow em uma operação, podemos verificar se o expoente do resultado está dentro do intervalo válido, ou seja:
$$b > E > -b+1$$ onde $b$ é o viés.

## Double Precision
Para minimizar as ocorrências de *overflow* e *underflow* podemos utilizar o padrão de precisão dupla, ou seja, 64 bits em arquiteturas de 32 bits. Esse padrão funciona da mesma forma, o que muda é a quantidade de bits que representa cada parte do número.

[[Condições de Overflow ou Underflow|Sobre implementação de exceções no caso de overflow/underflow.]]

# Aritmética
## Adição
![[Pasted image 20220922104945.png]]

Para somar dois *floats* devemos seguir os seguintes passos:
1. Transformamos o número com menor expoente até que seu expoente seja igual ao do outro número,
2. Somamos os significados normalmente,
3. Normalizamos à notação científica no resultado e verificamos *overflow* e *underflow*,
4. Arredondamos a soma caso seja necessário.

![[Pasted image 20220922104825.png]]![[Pasted image 20220922104901.png]]

## Multiplicação
A multiplicação de *floats* também leva 4 passos:
1. Somamos os expoentes do multiplicando e do multiplicador para obter o expoente do produto,
2. Multiplicamos os significados do multiplicando e do multiplicador,
3. Normalizamos à notação científica e verificamos se houve *overflow* ou *underflow*,
4. Arredondamos o produto caso seja necessário.

![[Pasted image 20220922105115.png]]![[Pasted image 20220922105130.png]]

# Valores Especiais
![[Pasted image 20220922105726.png]]

---
# Links úteis
- [Float Converter](https://www.h-schmidt.net/FloatConverter/IEEE754.html)
- [Binary-decimal Converter](https://www.rapidtables.com/convert/number/decimal-to-binary.html)
- [Aritmética em FP](http://weitz.de/ieee/)
---