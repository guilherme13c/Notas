[[Árvores|]][[Introdução a Grafos|]]
# Árvore
#### Definição
Uma árvore (também chamada de árvore livre) é um grafo não dirigido acíclico e conexo.

---
# Floresta
#### Definição
Uma floresta é um grafo não dirigido acíclico podendo ou não set conexo.

---
# Árvore Geradora
#### Definição
Uma árvore geradora de um grafo $G$ é um grafo que contém cada vértice de $G$ e é uma árvore.

> ###### Proposição
> - Cada grafo conexo tem uma árvore geradora.
> - Duas árvores geradoras quaisquer de um grafo têm a mesma quantidade de arestas.

---
## Árvore Geradora Mínima
#### Definição
Um grafo com peso é um grafo onde cada aresta possui um peso representado por um número real. A soma de todos os pesos de todas as arestas é o peso total do grafo. Uma árvore geradora mínima para um grafo com peso é uma árvore geradora que tem o menor peso total possível dentre todas as possíveis árvores geradoras do grafo.

Se $G$ é uma aresta com peso e $e$ uma aresta de $G$ então:
- $w(e)$ indica o peso da aresta $e$, e
- $w(G)$ indica o peso total do grafo $G$.

### Algoritmo de Kruskal
Ideia básica:
- Seleciona a aresta de menor peso que conecta duas árvores de uma floresta.
- Repita o processo até que todos os vértices estejam conectados sempre preservando a invariante de se ter uma árvore.

### Algoritmo de Prim
 Ideia básica:
- Tomando como vértice inicial $A$, crie uma fila de prioridades classificada pelos pesos das arestas conectando $A$.
- Repita o processo até que todos os vértices tenham sido visitados.
 
---
