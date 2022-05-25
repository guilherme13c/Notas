[[Introdução a Grafos|]]
# Coloração de Grafos
#### Definição
Uma coloração de um [[Introdução a Grafos#Grafo Simples|grafo simples]] é o assinalamento de uma cor a cada vértice do grafo tal que dois vértices adjacentes não têm a mesma cor.

#### Definição
O número cromático de um grafo é o menor número de cores necessárias à coloração deste grafo. O número cromático de um grafo $G$ é denotado por $\chi(G)$.

>###### Teorema
>O número cromático de um grafo planar é no máximo quatro.

---
# Coloração Crítica
Um grafo conexo é chamado cromaticamente $k$-crítico (chromatically $k$-critical) se o número cromático de $G$ é $k$, mas para cada aresta de $G$, o número cromático do grafo obtido pela eliminação dessa aresta de $G$ passa a ser $k-1$.

---
# Coloração de Arestas
Uma coloração de arestas de um grafo é um assinalamento de cores às arestas tal que arestas incidentes a um vértice em comum possuem cores diferentes.

O número cromático de aresta de um grafo é o menor número de cores que podem ser usadas numa coloração de arestas do grafo e é representado por $\chi^`(G)$.

---