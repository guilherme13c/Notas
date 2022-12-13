As **Reduções de Tempo Polinomial** ou **Polynomial-time Reductions** são [[Algoritmos|algoritmos]] de [[Comportamento Asintótico das funções|complexidade temporal polinomial]] que transformam instâncias de um problema em instâncias de outro problema. 
Usamos a seguinte notação para indicar que um problema $X$ se reduz polinomialmente à um problema $Y$, ou seja, que existe um algoritmo polinomial que transforma instâncias de $X$ em instâncias de $Y$.
$$X\le_\text{p}Y$$
---
- Se $X\le_\text{p}Y$ e $Y$ pode ser resolvido em tempo polinomial, então $X$ também pode ser resolvido em tempo polinomial.
- Se $X\le_\text{p}Y$ e $X$ não pode ser resolvido em tempo polinomial, então $Y$ também não pode ser resolvido em tempo polinomial.
- Se $X\le_\text{p}Y$ e $Y\le_\text{p}X$, usamos a notação $X\equiv_\text{p}Y$. Nesse caso, $X$ pode ser resolvido em tempo polinomial se, e só se, $Y$ pode ser resolvido em tempo polinomial.

---

Podemos utilizar reduções para construir algoritmos. Dessa forma podemos transformar instâncias de um problema que não sabemos resolver em instâncias de um problema conhecido.

![[Pasted image 20221213141522.png]]
---

# Transitividade
É importante ressaltar que a redução por mapeamento é transitiva. Podemos observar isso de forma intuitiva:
Se existe um algoritmo que transforma instâncias de um problema $A$ em instâncias de um problema $B$ em tempo polinomial, e existe também um algoritmo que transforma instâncias de $B$ em instâncias de um problema $C$ em tempo polinomial, então podemos utilizar a composição desses algoritmos para transformar instâncias de $A$ em instâncias de $C$. Essa transformação será polinomial pois sua complexidade será o produto das complexidades dos algoritmos anteriores, que são polinomiais, e o produto de dois polinômios é também um polinômio.

---
