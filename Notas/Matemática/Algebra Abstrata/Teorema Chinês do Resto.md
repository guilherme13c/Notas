[[Congruências e Aritmética Modular|]][[Primos e o lema de Euclides|]][[Critérios de Divisibilidade|]]
# Sistemas de Congruências
$\begin{cases}x\equiv2\;\;(\mbox{mod }3)\\x\equiv3\;\;(\mbox{mod }5)\\x\equiv2\;\;(\mbox{mod }7)\end{cases}\Rightarrow\begin{cases}x\equiv8\;\;(\mbox{mod }15)\\ x\equiv2\;\;(\mbox{mod }7)\end{cases}\Rightarrow x\equiv23\;\;(\mbox{mod }105)$ 

---
# Teorema do Resto Chinês
> Se $a,b\in\mathbb{Z}$ e $\mbox{mdc}(m,n)=1$ , o sistema $$\begin{cases}x\equiv a\;\;(\mbox{mod }m)\\ x\equiv b\;\;(\mbox{mod }n)\end{cases}$$ tem solução. Além disso, se $c\in\mathbb{Z}$ é uma solução do sistema, então $x\in\mathbb{Z}$ resolve o sistema se, e somente se, $x\equiv c\;\;(\mbox{mod  } mn)$.

---
## Visualização do Teorema
![[Aula 13.2-Teorema Chinês do Resto - Intuição e demonstração.mp4]]

---
## Simplificando [[#Sistemas de Congruências]]

No sistema de congruências
$$\begin{cases}x\equiv a\;\;(\mbox{mod }m)\\ x\equiv b\;\;(\mbox{mod }n)\end{cases}$$
a solução $x=c$ pode set encontrada pela equação
$$c=m\alpha b+n\beta a$$
onde $m>n$, $\alpha$ e $\beta$ são os valores obtidos como coeficientes para a fatoração pelo [[Primos e o lema de Euclides#Teorema de Bézout|teorema de Bézout]] usando o [[Máximo Divisor Comum - MDC e Mínimo Múltiplo Comum - MMC#Algoritmos Algoritmo Estendido de Euclides|algoritmo estendido de euclides]] com $m$ e $n$ como parâmetros.

---