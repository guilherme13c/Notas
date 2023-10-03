[[Caminhamentos em Grafos#Circuito|]][[Introdução a Grafos|]]
# [[Caminhamentos em Grafos#Circuito|Circuito]] Euleriano
#### Definição
Seja $G$ um grafo. Um circuito Euleriano é um circuito que contém cada aresta e cada vértice de $G$. É uma sequência de vértices e arestas adjacentes que começa e termina no mesmo vértice de $G$, passando pelo menos uma vez por cada vértice e exatamente uma única vez por cada aresta de $G$.

> ###### Teorema
> Se um grafo possui um circuito Euleriano, então cada vértice do grafo tem [[Introdução a Grafos#Grau de um Vértice|grau]] par.

O contrapositivo desse teorema é equivalente ao original:
> Se algum vértice de um grafo tem grau ímpar, então o grafo não possui um circuito Euleriano.

> ###### Teorema
> Se cada vértice de um grafo não vazio tem grau par e o grafo é conexo, então o grafo tem um circuito Euleriano.

---
## [[Caminhamentos em Grafos#Trajeto|Trajeto]] Euleriano
#### Definição
Seja $G$ um grafo e sejam $v$ e $w$ dois vértices de $G$. Um trajeto Euleriano de $v$ para $w$ é uma sequência de arestas e vértices adjacentes que começa em $v$, termina em $w$ e passa por cada vértice de $G$ pelo menos uma vez e passa por cada aresta de $G$ exatamente uma única vez.

###### Corolário
Seja $G$ um grafo e dois vértices $v$ e $w$ de $G$. Existe um trajeto Euleriano de $v$ para $w$ se e somente se $G$ é conexo e $v$ e $w$ têm grau ímpar e todos os outros vértices de $G$ têm grau par.

---
# [[Caminhamentos em Grafos#Circuito|Circuito]] Hamiltoniano
#### Definição
Dado um grafo $G$, um circuito Hamiltoniano para $G$ é um circuito simples que inclui cada vértice de $G$, ou seja, uma sequência de vértices adjacentes e arestas distintas tal que cada vértice de $G$ apacere exatamente uma única vez.

## Determinando se um Grafo possui um Circuito Hamiltoniano
Se $G$ tem um circuito Hamiltoniano, então $G$ tem um subgrafo $H$ que:
1. $H$ contém cada vértice de $G$;
2. $H$ é conexo;
3. $H$ tem o mesmo número de arestas e de vértices;
4. Cada vértice de $H$ tem grau 2.

---
