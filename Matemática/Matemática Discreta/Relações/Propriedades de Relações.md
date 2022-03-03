# Propriedades de Relações
## Reflexividade
$R$ é **reflexiva** se, e somente se, $\forall x\in A, xRx$.
-> Cada elemento é relacionado com ele mesmo, ou ainda, há uma aresta laço em cada vértice no grafo dirigido da relação.

## Simetria
$R$ é **simétrica** se, e somente se, $\forall x,y\in A$ se, $xRy$ então $yRx$.
-> Se um primeiro elemento é relacionado com um segundo, então o segundo é relacionado com o primeiro, ou ainda, para cada aresta de "ida" há uma aresta de "volta" no grafo dirigido da relação.

## Transitividade
$R$ é **transitiva** se, e somente se, $\forall x,y,z\in A$, se $xRy$ e $yRz$ então, $xRz$.
-> Se um primeiro elemento é relacionado com um segundo e o segundo é relacionado com um terceiro, então o primeiro é relacionado com o terceiro, ou ainda, se há aresta de um primeiro vértice para um segundo e de um segundo para um terceiro, então há uma aresta do primeiro para o terceiro no grafo dirigido da relação.

## Anti-simetria
$R$ é **anti-simétrica** se, e somente se, $\forall x, y \in A$, se $xRy \wedge yRx$ então $x = y$.
-> Se um primeiro elemento é relacionado com um segundo e o segundo é relacionado com o primeiro, então os dois elementos são idênticos, ou ainda, para cada aresta de “ida” não há uma aresta de “volta” no grafo dirigido da relação.

## Irreflexividade
$R$ é **irreflexiva** sse, $\forall x \in A, x\not Rx$.
-> Cada elemento não é relacionado com ele mesmo, ou ainda, não há aresta laço em cada vértice no grafo dirigido da relação.

## Assimetria
$R$ é **assimétrica** se, e somente se, $\forall x, y \in A$, se $xRy$ então $y\not Rx$.
-> Se um primeiro elemento está relacionado com um segundo, então o segundo não está relacionado com o primeiro, ou ainda, para cada aresta de “ida” não há uma aresta de “volta” nem aresta laço no grafo dirigido da relação. Uma relação assimétrica é anti-simétrica e irreflexiva.

***Obs.:*** os elementos $x, y$ e $z$ não precisam ser distintos!

> Se uma relação é simétrica, transitiva e reflexiva simultaneamente, dizemos que esta é uma [[Relações de Equivalência|Relação de Equivalência]].

---
# Verificando Propriedades de Relações Através de um Programa

Seja uma relação binária $R$ definida em um conjunto finito $A$ com $n$ elementos.

É possível verificar através de um programa cada uma dessas seis propriedades.

#### Possível implementação
- Representar $R$ por uma matriz booleana (matriz binária ou matriz zero-um) quadrada de tamanho $n$.
- A linha corresponde ao primeiro elemento do par ordenado e a coluna ao segundo elemento do par ordenado (consequentemente a mtriz não é simétrica).

-> Se todas as entradas na diagonal principal da matriz forem $1$ (verdadeiro) a relação é reflexiva.
-> Se todas as entradas na diagonal principal da matriz forem $0$ (falso) a relação é irreflexiva.

-> Se a [[Matrizes Simétricas|matriz for simétrica]], a relação também é simétrica.

---
[[Introdução a Relações|]][[Algoritmos|]]