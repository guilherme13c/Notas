# Para que serve?
Em geral, a dificuldade no estudo da análise combinatória não está em ***como contar*** mas ***o que contar***.

Em Ciência da Computação, questões de contagem são importantes já que temos uma quantidade finita de recursos.

> #### Exemplos:
> - Qual a quantidade de memória que será utilizada por um determinado programa que faz [[Armazenamento e manipulação de dados#Dinâmica _ longrightarrow Heap_|alocação dinâmica de memória]]?
> - Quantos usuários um determinado sistema computacional tem capacidade de atender?
> - Quantas computações um determinado algoritmo executa? (Qual é o [[Comportamento Asintótico das funções|custo computacional]] em termos de tempo e espaço de um determinado [[Algoritmos|algoritmo]]?)

Além disso, contagem é a base da probabilidade e da estatística.

---
# Princípios de Contagem
- [[Princípio da Multiplicação#Princípio da Multiplicação|Princípio da Multiplicação]]
- [[Princípio da Adição]]

---
![[combinatoria.png]]

---
## Fórmula de Pascal
$$\begin{pmatrix}n+1\\ r\end{pmatrix}=\begin{pmatrix}n\\ r-1\end{pmatrix}+\begin{pmatrix}n\\ r\end{pmatrix},\;\;0<r\le n.$$

#### [Demonstração](https://drive.google.com/file/d/1eCS0oC7f9wgM0b8K5i9oVEFlSM2nODbV/view)

---

[[Princípio da Casa de Pombo|]][[Combinação|]][[Permutação|]]