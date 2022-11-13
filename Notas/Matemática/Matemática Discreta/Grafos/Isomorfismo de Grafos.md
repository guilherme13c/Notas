[[Introdução a Grafos|]]
# Isomorfismo
#### Definição
Sejam os grafo $G$ e $G^\prime$ com [[Conjuntos]] de vértices $V(G)$ e $V(G^\prime)$ e com conjuntos de arestas $E(G)$ e $E(G^`),$ respectivamente. O grafo $G$ é isomorfo ao grafo $G^`$ se e somente se existem correspondências um-para-um
$$g:V(G)\to V(G^`)$$
$$h:E(G)\to E(G^`)$$
que preservam as funções aresta-vértice de $G$ e $G^`$ no sentido que
$$\forall v\in V(G)\wedge e\in E(G)$$
$v$ é um nó terminal de $e\iff g(v)$ é um nó terminal de $h(e)$.

---
Isomorfismo de grafos é uma [[Relações de Equivalência|relação de equivalência]] no conjunto de grafos.

---
Existe um [[Algoritmos|algoritmo]] que aceita como entrada os grafos $G$ e $G^`$ e produz como resultado uma afirmação se estes grafos são isomorfos ou não?
- Sim. Gere todas as funções $g$ e $h$ e determine se elas preservam as funções aresta-vértice de $G$ e $G^`$.
- Se $G$ e $G^`$ têm cada um $n$ vértices e $m$ arestas, o número de funções $g$ é $n!$ e o número de funções $h$ é $m!$, o que dá um número total de $n!\cdot m!$ funções.

---
## Invariantes para Isomorfismo de Grafos
>###### Teorema
>Cada uma das seguintes propriedades é uma invariante para isomorfismo de dois grafos $G$ e $G^`$, onde $n,m$ e $k$ são inteiros não negativos:
>1. Tem $n$ vértices;
>2. Tem $m$ arestas;
>3. Tem um vértice de [[Introdução a Grafos#Grau de um Vértice|grau]] $k$;
>4. Tem $m$ vértices de [[Introdução a Grafos#Grau de um Vértice|grau]] $k$;
>5. Tem um [[Caminhamentos em Grafos#Circuito|circuito]] de tamanho $k$;
>6. Tem um [[Caminhamentos em Grafos#Circuito Simples Ciclo Simples|circuito simples]] de tamanho $k$;
>7. Tem $m$ [[Caminhamentos em Grafos#Circuito Simples Ciclo Simples|circuitos simples]] de tamanho $k$;
>8. É [[Conectividade#Definição|conexo]];
>9. Tem um [[Circuitos Euleriano & Hamiltoniano#Caminhamentos em Grafos Circuito Euleriano|circuito Euleriano]];
>10. Tem um [[Circuitos Euleriano & Hamiltoniano#Caminhamentos em Grafos Circuito Circuito Hamiltoniano|circuito Hamiltoniano]].
>
>Isto significa que se $G$ é isomorfo a $G^`$ então se $G$ tem uma destas propriedades $G^`$ também tem.

---
# [[#Isomorfismo|Isomorfismo]] de [[Introdução a Grafos#Grafo Simples|Grafo Simples]]
#### Definição
Se $G$ e $G^`$ são grafos simples (sem arestas paralelas e sem laços) então $G$ é isomorfo a $G^`$ se e somente se existe uma correspondência $g$ um-para-um do conjunto de vértices $V (G)$ de $G$ para o conjunto de vértices $V (G^`)$ de $G^`$ que preserva a função aresta–vértice de $G$ e de $G^`$ no sentido que
$$\forall \mbox{ vértices } u,v\in G$$ $uv$ é uma aresta de $G\iff\{g(u),g(v)\}$ é uma aresta de $G^`$ .

---