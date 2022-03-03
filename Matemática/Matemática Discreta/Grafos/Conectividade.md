[[Introdução a Grafos|]]
# Conectividade
Informalmente um grafo é **_conexo_** (conectado) se for possível [[Caminhamentos em Grafos#Caminho|caminhar]] de qualquer vértice para qualquer outro vértice através de uma sequência de arestas adjacentes.

#### Definição
Seja $G$ um grafo. Dois vértices $v$ e $w$ de $G$ estão **_conectados_** se, e somente se, existe um caminho de $v$ para $w$. Um grafo $G$ é conexo se, e somente se, dado um par qualquer de vértices $v$ e $w$ em $G$, existe um caminho de $v$ para $w.$ Simbolicamente,
$$G\mbox{ é conexo }\iff\forall\mbox{ vértices }v,w\in V(G),\exists\mbox{ um caminho de }v\mbox{ para } w.$$
Se a negação for tomada, é possível ver que um grafo não é conexo se e somente se existem dois vértices em $G$ que não estão conectados por qualquer caminho.

---
## Lemas
Seja $G$ um grafo.
1. Se $G$ é conexo, então quaisquer dois vértices distintos de $G$ podem ser conectados por um [[Caminhamentos em Grafos#Trajeto Simples|trajeto simples (simple path)]].
2. Se vértices $v$ e $w$ são parte de um circuito de $G$ e uma aresta é removida do circuito, ainda assim existe um trajeto de $v$ para $w$ em $G$.
3. Se $G$ é conexo e contém um circuito, então uma aresta do circuito pode ser removida sem desconectar $G$.

---
### Componente Conexo
Um componente conexo de um grafo é um subgrafo de maior tamanho possível.

#### Definição
Um grafo $H$ é um componente conexo de um grafo $G$ se e somente se:
1. $H$ é um subgrafo de $G$;
2. $H$ é conexo;
3. Nenhum subgrafo conexo $I$ de $G$ tem $H$ como um subgrafo e $I$ contém vértices ou arestas que não estão em $H$.

**_Obs._**: Um grafo pode ser visto como a união de seus componentes conexos.

---
### Componente Fortemente Conexo
Um grafo dirigido $G = (V, E)$ é fortemente conexo se cada dois vértices quaisquer são alcançáveis a partir um do outro.

Os componentes fortemente conexos de um grafo dirigido são conjuntos de vértices sob a relação “são mutuamente alcançáveis”.

Um grafo dirigido fortemente conexo tem apenas um componente fortemente conexo.

---