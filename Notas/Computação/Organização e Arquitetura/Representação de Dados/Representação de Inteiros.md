# Notação Numérica Posicional
A [[#Notação Numérica Posicional]] é a forma mais simples de representar inteiros na memória. Nesse sistema, os números são representados na memória em sua forma [[Bases Numéricas|binária]] como uma sequência de bits.

Com 4 bits:$$(0101)_2=(5)_{10}$$

Nessa notação, só é possível representar números positivos ($n \geq 0$). Para solucionar esse problema, podemos usar o bit mais significativo para indicar se o sinal:

$$(0101)_2 = (5)_{10}\;\;\mbox{ e }\;\;(1101)_2 = (-5)_{10}$$

| binário | decimal |
| ------- | ------- |
| $1111$  | $-7$    |
| $1110$  | $-6$    |
| $1101$  | $-5$    |
| $1100$  | $-4$    |
| $1011$  | $-3$    |
| $1010$  | $-2$    |
| $1001$  | $-1$    |
| $1000$  | $-0$    |
| $0000$  | $+0$    |
| $0001$  | $+1$    |
| $0010$  | $+2$    |
| $0011$  | $+3$    |
| $0100$  | $+4$    |
| $0101$  | $+5$    |
| $0110$  | $+6$    |
| $0111$  | $+7$    |


Após esse ajuste, outros problemas surgem. Um deles é o fato de existirem duas representações distintas para o $0$.

- $(0)_{10}=(0000)_2$
- $(-0)_{10}=(1000)_2$

Outro problema é a incoerência da aritmética quando usamos essa nova notação:
$$\begin{equation}
\frac{
    \begin{array}[b]{r}
      \left( 0101 \right)_2\\
      + \left( 1101 \right)_2
    \end{array}
  }{
    \left( 1{\color{cyan} 0010} \right)_2
  }
\end{equation}$$
Ou em decimal:
$$\begin{equation}
\frac{
    \begin{array}[b]{r}
      \left( 5 \right)_{10}\\
      + \left( (-5) \right)_{10}
    \end{array}
  }{
    \left( {\color{cyan} 2} \right)_{10}
  }
\end{equation}$$

Para solucionar tais problemas, foi criada a notação de [[#Ones Complement|complemento de um (ones complement)]].

---
# Ones Complement

O método de complemento de um consiste em inverter todos os bits dos números negativos, exceto o bit indicador de sinal.

| binário | decimal |
| ------- | ------- |
| $1000$  | $-7$    |
| $1001$  | $-6$    |
| $1010$  | $-5$    |
| $1011$  | $-4$    |
| $1100$  | $-3$    |
| $1101$  | $-2$    |
| $1110$  | $-1$    |
| $1111$  | $-0$    |
| $0000$  | $+0$    |
| $0001$  | $+1$    |
| $0010$  | $+2$    |
| $0011$  | $+3$    |
| $0100$  | $+4$    |
| $0101$  | $+5$    |
| $0110$  | $+6$    |
| $0111$  | $+7$    |

Como podemos ver, os resultados aritméticos utilizando o complemento de um resultam em uma unidade a menos que o valor correto (e.g.  $6+(-2)=3$).

Para fazer a matemática funcional, podemos nos livrar do $(-0)$ e subtrair uma unidade do valor de cada representação (e.g.  $(1000)_2 \mbox{ representava }(-7)_{10},\mbox{ mas agora passa a representar }(-8)_{10}$). Essa mudança origina o método de [[#Twos Complement|complemento de dois (twos complement)]].

---
# Twos Complement

| binário | decimal |
| ------- | ------- |
| $1111$  | $-8$    |
| $1110$  | $-7$    |
| $1101$  | $-6$    |
| $1100$  | $-5$    |
| $1011$  | $-4$    |
| $1010$  | $-3$    |
| $1001$  | $-2$    |
| $1000$  | $-1$    |
| $0000$  | $+0$    |
| $0001$  | $+1$    |
| $0010$  | $+2$    |
| $0011$  | $+3$    |
| $0100$  | $+4$    |
| $0101$  | $+5$    |
| $0110$  | $+6$    |
| $0111$  | $+7$    |

Na notação de complemento de dois, a matemática passa a funcionar da forma correta e o $0$ só possui uma representação. Contudo, para obtermos o inverso aditivo de um número precisamos, além de inverter o bit de sinal, subtrair uma unidade, o que torna essa inversão mais cara.

---

# Operações em [[#Twos Complement]]
## Negação
Para negar um número em complemento de dois: inverter todos os bits e somar 1
 ![[Pasted image 20220922110110.png]]

## Mudança de representação
 Converter números de $n$ bit em números com mais de $n$ bits: copiar o mais significante bit (o bit de sinal) nos outros bit
 ![[Pasted image 20220922110147.png]]

## Adição
![[Pasted image 20220922110800.png]]

Pode ocorrer **overflow** (resultado maior que palavra do computador).
[[Condições de Overflow ou Underflow|Sobre implementação de exceções no caso de overflow/underflow.]]

## Multiplicação
Existem diferentes algoritmos para multiplicar dois número no hardware, sendo a mais básica:

![[Pasted image 20220922111100.png]]

Existe também uma forma mais otimizada:

![[Pasted image 20220922111231.png]]

## Divisão
Para a divisão de dois números, também existe mais de um algorimo:

![[Pasted image 20220922111328.png]]

Ou uma versão mais otimizada, que pode utilizar o mesmo hardware da multiplicação otimizada:
![[Pasted image 20220922111358.png]]

---