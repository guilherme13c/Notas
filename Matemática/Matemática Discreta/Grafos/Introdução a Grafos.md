# Definição
Um grafo $G$ consiste de dois conjuntos finitos:
1. Vértices $V(G)$
2. Arestas $E(G)$

Em geral, um grafo $G$ é representado como:
$$G=(V,E)$$
---

# Grafo Simples
#### Definição
Um grafo simples é um grafo que não possui laços nem arestas paralelas. Em um grafo simples, uma aresta com vértices (nós terminais) $u$ e $v$ é representada por $uv$.

---
# Grafo Dirigido
#### Definição
Um grafo dirigido ou digrafo ou direcionado $G$ consiste de dois conjuntos finitos:
1. Vértices $V(G)$
2. Arestas dirigidas $E(G)$, onde cada aresta é associada a um par ordenado de vértices chamados de nós terminais. Se a aresta $e$ é associada ao par $(u,v)$ de vértices, diz-se que $e$ é a aresta dirigida de $u$ para $v$.

Para cada grafo dirigido, existe um [[#Grafo Simples|grafo simples]] (não-dirigido) que é obtido removendo as direções das arestas e os _loops_.

---
# Grafo Completo ($K_n$)
#### Definição
Um grafo completo de $n$ vértices, denominado $K_n$, é um [[#Grafo Simples|grafo simples]] com $n$ vértices $v_1,v_2,\ldots,v_n$, cujo conjunto de arestas contém exatamente uma aresta para cada par de vértices distintos.

Nota: A letra $K$ representa a letra inicial da palavra _komplett_, "completo" em alemão.

![[Pasted image 20220131193548.png]]

---
## Quantidade de Grafos Distintos com $n$ Vértices
$$2^{n^2-n\over2}=2^{(\vert V\vert^2-\vert V\vert)\over 2}$$

---
# Grafo Ciclo ($C_n$)
#### Definição
Um grafo ciclo de $n$ vértices, denominado $C_n, n\geq3$ é um [[#Grafo Simples|grafo simples]] com $n$ vértices $v_1,v_2,\ldots, v_n$ e arestas $v_1v_2,v_2v_3,\ldots,v_nv_1$.

---
# Grafo Roda ($W_n$)
#### Definição
Um grafo roda, denominado $W_n$, é um [[#Grafo Simples|grafo simples]] com $n+1$ vértices que é obtido acrescentando um vértice ao [[#Grafo Ciclo|grafo ciclo]] $C_n, n\geq3$, e conectando este novo vértice a cada um dos $n$ vértices de $C_n$.

---
# Grafo Cubo-$n$ ($Q_n$)
#### Definição
Um grafo cubo-$n$ possui $2^n$ vértices, denominado $Q_n$, é um [[#Grafo Simples|grafo simples]] que representa os $2^n$ strings de $n$ bits. Dois vértices são adjacentes se, e somente se, os strings que eles representam diferem em exatamente uma posição.

O grafo $Q_{n+1}$ pode ser obtido a partir do grafo $Q_n$, usando o seguinte algoritmo:
1. Faça duas cópias de $Q_n$;
2. Prefixe uma das cópias de $Q_n$ com $0$ e a outra com $1$;
3. Acrescente uma aresta conectando os vértices que só diferem no primeiro bit.

---
# Grafo Bipartido
#### Definição
Um grafo bipartido é um grafo com vértices $v_1,v_2,\ldots,v_m$ e $w_1,w_2,\ldots,w_n$, que satisfaz as seguintes propriedades:
$$\forall\;i,k=1,2,\ldots,m\;\wedge\;\forall\;j,l=1,2,\ldots,n$$
1. $\forall$ as arestas do grafo, cada aresta conecta algum vértice $v_i$ a algum vértice $w_j$;
2. $\neg\exists$ uma aresta entre cada par de vértices $v_i$ e $v_k$;
3. $\neg\exists$ uma aresta entre cada par de vértices $w_j$ e $w_l$.

---
# Grafo Bipartido Completo ($K_{m,n}$)
#### Definição
Um grafo bipartido completo de $m,n$ vértices, denominado $K_{m,n}$ é um [[#Grafo Simples|grafo simples]] com vértices $v_1,v_2,\ldots,v_m$ e $w_1,w_2,\ldots,w_n$, que satisfaz as seguintes propriedades:
$$\forall\;i,k=1,2,\ldots,m\;\wedge\;\forall\;j,l=1,2,\ldots,n$$
1. $\exists$ uma aresta entre **cada par** de vértices $v_i$ e $w_j$;
2. $\neg\exists$ uma aresta entre cada par de vértices $v_i$ e $v_k$;
3. $\neg\exists$ uma aresta entre cada par de vértices $w_j$ e $w_l$.

---
# Grafo de Petersen
#### Definição
É um grafo não-dirigido [[#Grafo Cubo- n|cúbico]] com $10$ vértices e $15$ arestas, como ilustrado abaixo. É um grafo largamente utilizado como exemplo e contraexemplo para muitos problemas em teoria dos grafos.
![[Pasted image 20220131200439.png]]

---
# Multigrafo
#### Definição
Um multigrafo é um grafo que não possui laços mas pode ter arestas paralelas. Formalmente, um multigrafo $G=(V,E)$ consiste de um conjunto $V$ de vértices, um conjunto $E$ de arestas, e uma função $f$ de $E$ para $\{\{u,v\}\vert u,v\in V,u\not=v\}$. As arestas $e_1$ e $e_2$ são chamadas múltiplas ou paralelas se $f(e_1)=f(e_2)$.

---
# Pseudografo
#### Definição
Um pseudografo é um conjunto que pode ter laços e arestas paralelas. Formalmente, um pseudografo $G=(V,E)$ consiste de um conjunto $V$ de vértices, um conjunto $E$ de arestas, e uma função $f$ de $E$ para $\{\{u,v\}\vert u,v\in V\}$.

---
# Multigrafo Dirigido
#### Definição
Um multigrafo dirigido é um grafo que pode ter laços e arestas paralelas. Formalmente, um multigrafo dirigido $G=(V,E)$ consiste de um conjunto $V$ de vértices, um conjunto $E$ de arestas, e uma função $f$ de $E$ para $\{\{u,v\}\vert u,v\in V\}$. As arestas $e_1$ e $e_2$ são arestas múltiplas se $f(e_1)=f(e_2)$.

---
# Hipergrafo
#### Definição
Um hipergrafo $H(V,F)$ é definido pelo par de conjuntos $V$ e $F$, onde:
- V é um conjunto não vazio de vértices;
- $F$ é um conjunto de hiperarestas, representada por uma "família" de partes não vazias de $V$.
Um hipergrafo é um [[#Grafo Dirigido|grafo não-dirigido]] em que cada hiperaresta conecta um número arbitrário de vértices.

- Um hipergrafo é $k$-uniforme se cada aresta contém exatamente $k$ vértices;
- Um grafo "tradicional" é um hipergrafo $2$-uniforme;
- Em um hipergrafo, o grau de um vértice $v$ é a quantidade de arestas que contém o vértice $v$.

---
# Terminologia de Grafos
![[Pasted image 20220131202102.png]]

---
# Grafo Valorado
#### Definição
Um grafo valorado é um grafo em que cada aresta tem um valor associado. Formalmente, um grafo valorado $G=(V,F)$ consiste de um conjunto $V$ de vértices, um conjunto $E$ de arestas, e uma função $f$ de $E$ para $P$, onde $P$ representa o conjunto de valores (pesos) associados às arestas.

---
# Grafo Imersível
#### Definição
Um grafo é imersível em uma superfície $S$ se puder ser representado geograficamente em $S$ de tal forma que arestas se cruzem nas extremidades (vértices).

Um grafo planar é um grafo que é imersível no plano.

---
# Subgrafo
#### Definição
Um grafo $H = (V^` , E^`)$ é um subgrafo de $G = (V, E)$ se, e somente se:
- cada vértice de $H$ é também um vértice de $G$, ou seja, $V ^` \subseteq V$ ;
- cada aresta de $H$ é também uma aresta de $G$, ou seja, $E^`\subseteq E$ ; e
- cada aresta de $H$ tem os mesmos nós terminais em $G$, ou seja, se $(u, v) \in E^`$  então $(u, v) \in E$.

Um subgrafo $H$ de $G$ é um subgrafo próprio de $G$ se $H \not= G$.

#### Definição
Seja $V = (V, E)$ um [[#Grafo Simples|grafo simples]]. O subgrafo induzido por um subconjunto $V^` \subseteq V$ é o grafo $H_i = (V^` , E^`)$ onde $E^` \subseteq E$, mas as arestas que pertencem a $E^`$ são apenas aquelas que têm seus vértices em $V^`$.

---
# Grau de um Vértice
#### Definição
Seja $G$ um grafo e um vértice $v$ de $G$. O grau de $v$, denominado grau($v$) (deg($v$)), é igual ao número de arestas que são incidentes a $v$, com uma aresta que seja um laço contada duas vezes. O grau total de $G$ é a soma dos graus de todos os vértices de $G$.

Em um grafo dirigido o grau de um vértice $v$ é o número de arestas que saem dele (out-deg($v$)) mais o número de arestas que chegam nele (in-deg($v$)).

## Teorema do aperto de mão (handshaking):
Seja $G$ um grafo. A soma dos graus de todos os vértices de $G$ é duas vezes o número de arestas de $G$. Especificamente, se os vértices de $G$ são $v_1, v_2,\ldots, v_n$, onde $n$ é um inteiro positivo, então
$$\mbox{Grau de }G=\mbox{grau}(v_1)+\mbox{grau}(v_2)+\ldots+\mbox{grau}(v_n)=2\times\mbox{número de arestas de }G$$
>###### Corolário
>O grau total de um vértice é par.

---
# Grafo Regular
#### Definição
Um grafo é dito ser regular quando todos os seus vértices têm o mesmo grau.

---
# Características de um Grafo
## Teorema
Em qualquer grafo $G$ existe um número par de vértices de grau ímpar.

---