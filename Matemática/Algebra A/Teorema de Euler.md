[[Função phi de Euler|]][[Funções Multiplictivas|]][[Classes de Equivalência|]][[Congruências e Aritmética Modular|]]
# Teorema de Euler
- $\mathbb{Z}$ tem $\phi(n)$ invertíveis
- Se $a,b\in\mathbb{Z_n}$ são invertíveis, então $a\cdot b$ é invertível, pois dados $a^`,b^`\in\mathbb{Z}_n$ com $a\cdot a^`=\bar 1$ e $b\cdot b^`=\bar 1$, temos que
$$a\cdot \cancel{b \cdot b^`}\cdot a^`\cdot=\cancel{a\cdot a^`}=\bar1$$
$a\in\mathbb{Z}_n^*$, $\{\,\underbrace{a^0,a^1,a^2,a^3,\ldots,a^{\phi(n)}}_{\phi(n)+1\mbox{ elementos}}\}\in\mathbb{Z}_n^*$.

---
## Enunciado
Seja $n\in\mathbb{N}$ e $a\in\mathbb{Z}_n^*$. Então $a^{\phi(n)}=\bar1$.

(Versão com congruências: Seja $n\in\mathbb{N}$ e $a\in\mathbb{Z}$ com $\mbox{mdc}(a,n)=1$. Então $a^{\phi(n)}\equiv1\;\;(\mbox{mod }n)$).

#### Prova
![[Pasted image 20220115193324.png]]

---
***Obs.:*** O Teorema de Euler não se aplica se a base e o módulo não forem primos entre si ($\mbox{mdc}(b, m) \neq 1$).

---