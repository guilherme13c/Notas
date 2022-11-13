As [[Linguagens Formais|linguagens]] livres-do-contexto podem ser entendidas como linguagens mais gerais que as regulares, sendo toda [[Autômatos Finitos e Linguagens Regulares|linguagem regular]] uma linguagen livre-do-contexto.
Toda linguagem livre-do-contexto pode ser gerada por alguma [[#Gramática Livre-do-Contexto (GLC)|gramática livre-do-contexto]], de forma que as gramáticas livres-do-contexto são geradoras das linguagens livre-do-contexto.

# Gramática Livre-do-Contexto (GLC)
#### DEfinição
Uma gramática livre-do-contexto é uma 4-tupla $(V, \Sigma, R, S)$, onde: 
1. V é um conjunto finito denominado **variáveis**, 
2. Σ é um conjunto finito, disjunto de $V$, denominado **terminais**, 
3. R é um conjunto finito de **regras**, com cada regra sendo uma variável e uma cadeia de variáveis e terminais, e 
4. $S ∈ V$ é uma **variável inicial** (ou **variável de partida**).

Às vezes uma gramática pode gerar a mesma cadeia de várias formas diferentes. Tal cadeia terá várias árvores sintáticas diferentes e, portanto, vários significados diferentes.

# Ambiguidade
#### Definição
Uma derivação de uma cadeia $w$ em uma gramática $G$ é uma **derivação mais à esquerda** se a cada passo a variável remanescente mais à esquerda é aquela que é substituída.

#### Definição
Uma cadeia $w$ é derivada ambiguamente na gramática livre-do-contexto $G$ se ela tem duas ou mais derivações mais à esquerda diferentes.

#### Definição
A gramática $G$ é ambígua se ela gera alguma cadeia ambiguamente.

#### Definição
Algumas gramáticas ambíguas podem ser convertidas em gramáticas não-ambíguas. Quando isso não é possível, dizemos que a gramática em questão é **inerentemente ambígua**.

# A forma normal de Chomsky (FNC)
Dizemos que uma gramática está na forma normal de Chomsky se toda regra teum uma das seguintes formas:
- $A\to BC$, onde $A,B,C$ são variáveis quaisquer, e $B$ e $C$ não são a variável de partida;
- $A\to a$, onde $A$ é uma variável, e $a$ é um terminal; ou
- $S\to\epsilon$, apenas se $S$ for a variável de partida.

###### Teorema
Qualquer linguagem livre-do-contexto é gerada por uma gramática livre-do-contexto na FNC.

### Convertendo grámaticas para a FNC
O seguinte [[Algoritmos|algoritmo]] converte qualquer gramática para a FNC:

A GLC original:
![[Pasted image 20221026202944.png]]

1. Introduza uma nova variável inicial
![[Pasted image 20221026202959.png]]
2. Remova todas as regras $\epsilon$
![[Pasted image 20221026203104.png]]
3. Remova todas as regras unitárias (i.e., da forma $X \to Y$)
![[Pasted image 20221026203202.png]]
4. Converta as regras remanescentes para a forma apropriada acrescentando variáveis e regras adicionais da forma $X → YZ$ ou $X → a$.
![[Pasted image 20221026203242.png]]

# Autômato com Pilha (AP)
Para reconhecer linguagens livres-do-contexto vamos precisar de máquinas mais poderosas que os [[Autômatos Finitos e Linguagens Regulares|autômatos finitos]].
Lembre-se de que o [[Linguagens Não-Regulares#Lema do Bombeamento|lema do bombeamento para linguagens regulares]] diz, essencialmente, que “autômatos finitos se perdem em contagens longas”. Mais precisamente, os autômatos finitos têm sérias limitações em “se lembrar” do que viram no passado. Isto sugere que podemos incluir algum tipo de memória nos AFs! Vamos adicionar à máquina uma memória extremamente simples, uma pilha, em que o último símbolo empilhado é o primeiro a ser desempilhado. Assim, chegamos aos autômatos com pilha:
![[Pasted image 20221026203603.png]]

**Notação:** dado um conjunto $A$, denotamos por $A_\epsilon$ o conjunto $A \cup \set{\epsilon}$.
#### DEfinição
Um **autômato com pilha** (AP) é uma 6-tupla $(Q, \Sigma, \Gamma, \delta, q_0, F)$, onde:
1. $Q$ é um conjunto finito de estados, 
2. $\Sigma$ é o alfabeto (finito) de entrada, 
3. $\Gamma$ é o alfabeto (finito) de pilha, 
4. $\delta : Q \times \Sigma_\epsilon \times \Gamma_\epsilon \to P(Q \times \Gamma_\epsilon)$ é a função de transição, 
5. $q_0 \in Q$ é o estado inicial, e 
6. $F ⊆ Q$ é o conjunto de estados de aceitação (ou estados finais).

Note que, pela definição da função transição $δ$, estamos considerando APs não-determinísticos.
(Pode-se mostrar que APs determinísticos são estritamente menos poderosos que os não-determinísticos)

# Equivalência entre Linguagens Livre-do-Contexto e Autômatos com Pilha
Uma linguagem é livre-do-contexto se, e somente se, algum autômato com pilha a reconhece.

###### Corolário
Toda linguagem regular é livre-do-contexto.

---
###### Teorema
A classe das linguagens livres-do-contexto é fechada sob união.

###### Teorema
A classe das linguagens livres-do-contexto é fechada sob concatenação.

###### Teorema
A classe das linguagens livres-do-contexto é fechada sob fecho de Kleene.

###### Teorema
A classe das linguagens livres-do-contexto **não** é fechada sob interseção.

###### Teorema
A classe das linguagens livres-do-contexto **não** é fechada sob complementação.

---