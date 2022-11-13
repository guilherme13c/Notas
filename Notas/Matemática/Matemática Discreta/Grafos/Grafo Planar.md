[[Introdução a Grafos|]]
# Grafo Planar
Um grafo é dito ser planar se puder ser desenhado no plano sem que haja arestas se cruzando.

---
# Fórmula de Euler
>###### Teorema
>Seja $G$ um grafo planar simples com $e$ arestas e $v$ vértices. Seja $r$ o número de regiões na representação planar de $G$. Temos que
$$r=e-v+2$$
>###### Corolário 1
>Se $G$ é um grafo simples conexo e planar com $e$ arestas e $v$ vértices, sendo $v \geq 3$, então $e \leq 3v - 6$.
>
>**_Obs._**: Podemos usar o corolário para mostrar que o grafo não é planar, mas não para mostrar que ele é.

### Grau de uma Região
#### Definição
Grau de uma região $(\mbox{deg}(R))$: número de arestas no limite de uma região. Toda aresta que tem um vértice de grau 1 contribui com dois para o grau da região.

>###### Corolário 2
>Se $G$ é um grafo simples conexo e planar, então $G$ tem um vértice de grau menor ou igual a 5.

>###### Corolário 3
>Se $G$ é um grafo simples conexo e planar com $e$ arestas e $v$ vértices, sendo que $v \geq 3$ e nenhum circuito de comprimento três, então
>$$e\leq 2v-4.$$

---