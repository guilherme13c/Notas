[[Reduções de Tempo Polinomial|]][[P vs. NP|]][[Intodução a Intratabilidade|]][[Conjuntos|]]
#### definição
Um problema $Y$ é dito $\mathbf{NP}$-completo quando $Y\in\mathbf{NP}$ com a propriedade que para todo problema $X\in\mathbf{NP}$, $X\le_\text{p}Y$.

## Proposição
Suponha que $Y\in\mathbf{NP}\text{-completo}$. Então, $Y\in\mathbf{P}\iff \mathbf{P}=\mathbf{NP}$.
### Demonstração
$\mathbf{P}=\mathbf{NP}\implies Y\in\mathbf{P}$, pois $Y\in\mathbf{NP}$.

Suponha que $Y\in\mathbf{P}$.
- Considere qualquer problema $X\in\mathbf{NP}$. Como $X\le_\text{p}Y$, temos que $X\in\mathbf{P}$.
- Isso implica $\mathbf{NP}\subseteq\mathbf{P}$.
- Já sabemos que $\mathbf{P}\subseteq\mathbf{NP}$, então $\mathbf{P}=\mathbf{NP}$.

---

# Como provar que um problema $Y\in\mathbf{NP}\text{-completo}$
1. Mostre que $Y\in\mathbf{NP}$.
2. Escolha um problema $\mathbf{NP}\text{-completo}$.
3. Demonstre que $X\le_\text{p}Y$.

---
