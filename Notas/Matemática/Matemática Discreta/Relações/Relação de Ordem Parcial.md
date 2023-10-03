[[Introdução a Relações|]][[Relações de Equivalência|]][[Propriedades de Relações|]]
# Relações de Ordem Parcial
> #### Definição
> Seja $R$ uma relação binária definida no conjunto $A$. $R$ é uma relação de ordem parcial se, e somente se, $R$ é reflexiva, anti-simétrica e transitiva.

Um conjunto $A$ com uma relação de ordem parcial $R$ é um conjunto parcialmente ordenado ou _poset_ (_partially ordered set_) e é indicado por $$(A,R).$$sendo $A$ o conjunto e $R$ a relação.

Os elementos de $A$ são chamados de elementos do _poset_.

---
## Poset
Em alguns _posets_, temos relações definidas por operadores (símbolos) tais como:
- $\leq$ (menor ou igual a)
- $\subseteq$ (subconjunto)
- $\vert$ (divide)

Seria interessante ter um símbolo "genérico" a set usado quando falamos de um relação de ordem parcial em um _poset_ arbitrário, ao invés de falarmos de uma relação $R$ específica, i.e, $(A, R)$.

O símbolo $\preceq$ é usado para referenciar uma relação de ordem parcial genérica e é lido como "menor ou igual a".$$(A, \preceq)$$
***Obs.:*** A notação $a\prec b$ significa $a\preceq b$, mas $a\neq b$, i.e., os elementos são distintos.

Quando $a$ e $b$ forem elementos do _poset_ $(A,\preceq)$ não é necessário nem que $a\preceq b$ nem que $b\preceq a$.

---
### Elementos comparáveis no poset $(A, \preceq)$
> #### Definição
> Os elementos $a$ e $b$ de um _poset_ $(A, \preceq)$ são comparáveis se $a\preceq b$ ou $b\preceq a$. Quando nem $a\preceq b$ nem $b\preceq a$ , os elementos $a$ e $b$ são incomparáveis.

---
# Conjunto Totalmente Ordenado
> #### Definição
> Se $(A, \preceq)$ for um poset e quaisquer dois elementos de $A$ forem comparáveis, $A$ é chamado de um conjunto totalmente ordenado ou linearmente ordenado, e será chamada de ordem total ou ordem linear. Um conjunto totalmente ordenado também é chamado de cadeia.

---
# Ordem Lexicográfica
Seja $\Sigma$ um conjunto formado por símbolos (elementos) com uma relação de ordem parcial.

Pode-se, então, definir uma ordem lexicográfica ou ordem de “dicionário” no conjunto $\Sigma^*$.
- $\Sigma^*$ é o conjunto de todos os strings de tamanho $0, 1, 2, \ldots$

---
# Diagrama de Hasse
Grafo dirigido de uma relação:
![[Pasted image 20220110180007.png]]
Note que:
- Existe um laço ("loop") em cada vértice;
- Todas as arestas apontam para a mesma direção, ou seja, para cima;
- Toda vez que há uma aresta de um vértice para um segundo e de um segundo para um terceiro, então há uma aresta do primeiro vértice para o terceiro vértice.

-> É possível associar um grafo mais simples com uma relação de ordem parcial em um conjunto finito chamado Diagrama de Hasse.

![[Pasted image 20220110180411.png]]
## Algoritmo para obter o Diagrama de Hasse
Elimine:
1. Os laços em todos os vértices;
2. Todas as arestas que existem por causa da propriedade de transversividade;
3. A direção em todas as arestas.

## Algoritmo reverso
Para obter o grafo original a partir do Diagrama de Hasse basta reverter os passos do algoritmo anterior.

---
# Elementos maximais e minimais
> #### Definição
> Um elemento $a$ de um poset é chamado maximal se ele não for menor do que nenhum elemento do poset. Ou seja, não existe nenhum elemento $b \in A$ tal que $a\prec b$.

> #### Definição
> Um elemento $a$ de um poset é chamado minimal se ele não for maior do que nenhum elemento do poset. Ou seja, não existe nenhum elemento $b \in A$ tal que $b \prec a$.

Observe que nas duas definições está implícito que os elementos $a$ e $b$ são comparáveis.

Elementos maximal e minimal são fáceis de identificar usando um diagrama de Hasse:
- Else são os elementos “de baixo” e “de cima” no diagrama.
- É importante observar que pode haver mais de um elemento maximal/minimal.

Elementos de posets que têm propriedades extremais são importantes para muitas aplicações:
- Em sistemas distribuídos, podem identificar o primeiro elemento (e.g., processo que gerou uma disseminação) ou o último elemento (e.g., última transação válida) de uma cadeia causal.
- Em uma execução de um programa, podem identificar o primeiro commando de uma sequência que causou um error ou o último módulo afetado (do ponto de vista lógico) que deve set alterado por conta de uma mudança de requisito.

---
# Maior/Menor Elementos do poset $(A,\preceq)$
Algumas vezes, existe um elemento em um poset que é o maior/menor de todos.
> #### Definição
> Um elemento $a$ é o maior elemento de um poset se $b \preceq a$ para todo elemento $b \in A$ (esse elemento é único, se existir).

> #### Definição
> Um elemento $a$ é o menor elemento de um poset se $a \preceq b$ para todo elemento $b \in A$ (esse elemento é único, se existir).

---