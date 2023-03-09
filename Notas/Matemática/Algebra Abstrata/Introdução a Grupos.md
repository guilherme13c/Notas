[[Introdução a Relações|]][[Propriedades de Relações|]]
# Grupos
#### Definição
Um grupo é um par ordenado $(G,*)$, onde $G$ é um conjunto e $*$ é uma operação, com $*:G\times G\to G$ é uma operação que satisfaz as seguintes propriedades:
1. **_Associatividade_**: Se $a,b,c\in G$, então $(a*b)*c=a*(b*c)$
2. Existe um elemento especial $e$, chamado **_elemento neutro_**, tal que $g*e=e*g=g$ para todo $g\in G$.
3. **_Inverso à esquerda_**: Para todo $g\in G$, existe $g^`\in G$ com $g^`*g=e$.

---
## Geradores
#### Definição
$S$ é um conjunto de geradores de $G$ se e somente se $S\subset G$ e todo elemento de $G$ é da forma
$$s_k*\ldots*s_2*s_1$$
onde cada $s_k$ é um elemento de $S$ ou inverso de um elemento de $S$.

## Diagramas e Tabelas de Cayley
![[Pasted image 20220221174209.png]]

![[Pasted image 20220221174236.png]]

---

## Ordem de um Elemento
Se $(G,*)$ é um grupo, definimos para $g\in G$ e $k\in \mathbb{Z}$,
$$g^k=\begin{cases}\overbrace{g*\ldots*g}^{k \mbox{ vezes}}\mbox{ se }k>0\\ e\;\;\;\;\;\;\;\;\;\;\;\;\mbox{ se }k=0\\ \underbrace{g^{-1}*\ldots*g^{-1}}_{\vert k\vert\mbox{ vezes}}\mbox{ se }k<0\end{cases}$$
#### Definição
A ordem de um elemento $g\in G$ é o menor $n\in\mathbb{N}$ tal que $g^n=e$.
**_Notação_**: $\mbox{ord}(g)$.

---
## Subgrupos Gerados
Dado um grupo $(G,*)$ e um conjunto $S\subset G$, o subgrupo de $G$ gerado por $S$ é o conjunto que contém todos os elementos da forma
$$s_1*\ldots*s_k,k\in\mathbb{N}\cup\set{0}$$
onde cada $s_i$ pertence a $S$ ou é o inverso de um elemento de $S$.

**_Obs_**.: $\langle S\rangle$ é sempre subgrupo.  

O subgrupo gerado por um único elemento tem a forma especial.
$$\langle g\rangle=\{g^k:k\in\mathbb{Z}\}$$
Como $g^i=g^j$ se e somente se $i=j\;(\mbox{mod ord}(g))$, então se $\mbox{ord}(g)<\infty$ ,
$$\langle g\rangle=\set{g^0,\ldots,g^{\mbox{ord}(g)-1}}$$
$$\Longrightarrow \mbox{ord}(g)=\vert \langle g\rangle\vert$$

---