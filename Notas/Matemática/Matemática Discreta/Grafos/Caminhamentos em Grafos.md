[[Introdução a Grafos|]]
# Caminho
Seja $G$ um grafo não dirigido, $n\geq1$, e $v$ e $w$ vértices de $G$.

**_Caminho (walk)_**: Um caminho de $v$ para $w$ é uma sequência alternada de vértices e arestas adjacentes de $G$. Um caminho tem a forma:
$$(v=)v_0e_1v_2e_2v_2\ldots v_{n-1}e_nv_n(=w)$$
ou ainda
$$v_0[v_0,v_1]v_1[v_1,v_2]v_2\ldots v_{n-1}[v_{n-1},v_n]v_n$$
onde $v_0=v$ e $v_n=w$.

---
- No caso de arestas múltiplas, deve-se indicar qual delas está sendo usada.
- Vértices $v_0$ e $v_n$ são extremidades do caminho.
- Tamanho (comprimento) do caminho: número de arestas do mesmo, ou seja, número de vértices menos um.
- O **_caminho trivial_** de $v$ para $v$ consiste apenas do vértice $v$.
- Se existir um caminho $c$ de $v$ para $w$, então $w$ é alcançável a partir de $v$ via $c$.

---
## Caminho Fechado
**_Caminho Fechado (closed walk)_**: [[#Caminho|Caminho]] que começa e termina no mesmo vértice.

Um caminho fechado com pelo menos uma aresta é chamado de **_ciclo_**.

---
## Trajeto
**_Trajeto (path)_**: [[#Caminho|Caminho]] de $v$ para $w$ sem arestas repetidas.
$$(v=)v_0e_1v_2e_2v_2\ldots v_{n-1}e_nv_n(=w)$$
onde todas as arestas $e_i$ são distintas, ou seja, $e_i\not=e_k$, para qualquer $i\not=k$.

---
### Trajeto Simples
**_Trajeto Simples (simple path)_**: [[#Caminho]] de $v$ para $w$ sem vértices e arestas repetidos.

---
### Circuito
**_Circuito (circuit)_**: [[#Trajeto]] fechado, ou seja, um [[#Caminho|caminho]] onde não há aresta repetida e os vértices inicial e final são idênticos:
$$(v=)v_0e_1v_2e_2v_2\ldots v_{n-1}e_nv_n(=w)$$
onde toda aresta $e_i,1\leq i\leq n$, é distinta e $v_0=v_n$.

---
#### Circuito Simples / Ciclo Simples
**_Circuito Simples (simple circuit)_**: [[#Caminho]] onde não há arestas e vértices repetidos, exceto os vértices inicial e final que são idênticos.

---
# Terminologia de Caminhos
![[Pasted image 20220201182935.png]]

---
# Fecho Transitivo Direto
O fecho transitivo direto (FTD) de um vértice $v$ é o conjunto de todos os vértices que podem set alcançados por algum caminho iniciado em $v$.

# Fecho Transitivo Inverso
O fecho transitivo inverso (FTI) de um vértice $v$ é o conjunto de todos os vértices a partir dos quais se pode atingir $v$ por algum caminho.

---