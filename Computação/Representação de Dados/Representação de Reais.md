[[Bases Numéricas|]]
##### [Vídeo completo](https://www.youtube.com/watch?v=RuKkePyo9zk&t=846s)
# Fixed Point Representation
Na representação de ponto fixo, o ponto que separa as partes inteira e fracionária do número é fixado em uma posição dentro do registrador. Dessa forma, o tamanho de cada parte é fixo. A posição exata do ponto depende da forma como o sistema computacional foi desenhada.

Nessa forma de representar reais, os bits à esquerda do ponto representam as potências positivas de 2, enquanto os bits à direita representam as potências negativas.

![[Pasted image 20220402161411.png]]

A representação de ponto fixo simplifica o processamento de números reais, mas impõe limitações no tamanho (range) e na precisão do números que podem ser armazenados.

# Floating Point Representation
A representação de ponto flutuante se inspira na notação científica, mas em base 2. Nesse método, o número é separado em duas partes, chamadas **mantissa** e **expoente**. O número de bits do expoente determina as limitações de tamanho do número (range), enquanto o número de bits da mantissa define a precisão.

O número de bits alocados para cada parte (mantissa e expoente) e a ordem em que elas são apresentadas pode variar de sistema para sistema, mas atualmente o padrão é o definido pela [IEEE 754](http://mathcenter.oxford.emory.edu/site/cs170/ieee754/). 

![[Pasted image 20220402163858.png]]

| Arquitetura | Sinal | Expoente | Mantissa |
| ----------- | ----- | -------- | -------- |
| 32 bits     | 1 bit | 8 bits   | 23 bits  |
| 64 bits     | 1 bit | 11 bits  | 52 bits  | 

**_Obs._**: A mantissa tem a precisão de um bit a mais que seu tamanho (24 | 53 bits). Isso ocorre pois seu primeiro bit sempre será 1 (devido às regras de notação científica), então não precisamos armazená-lo.

O número armazenado é da forma:
$$\begin{cases}M\cdot 2^{E-b}\mbox{, se }B = 0\\ -M\cdot 2^{E-b}\mbox{, se }B = 1\end{cases}$$
onde $B$ é o bit de sinal, $M$ é a mantissa, $E$ é o expoente e $b$ é o _viés_ (_bias_) do expoente. 

O viés do expoente é um número que sempre subtraímos dele na hora de realizar processamento usando números representados por ponto flutuante. Fazemos isso para que também possamos utilizar números negativos no expoente.
O padrão IEEE 754 determina que o viés deve ser:$$2^{n-1}-1$$
onde $n$ é o número de bits do expoente.

**_Obs._**: o víes também é o número de possíveis expoentes negativos, ou o valor absoluto do expoente negativo de maior magnitude.