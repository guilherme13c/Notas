# Autômato Finito (AF)
#### Definição
**Autômatos finitos** são bons modelos para computadores com uma quantidade muito limitada de memória.

# Autômato Finito Determinístico (AFD)
#### Definição
Um autômatos finito (determinístico) é uma 5-tupla $(Q, \Sigma, \delta, q_0, F)$, onde:

- $Q$ é um conjunto finito de estados,
- $\Sigma$ é um conjunto finito chamado de alfabeto,
- $\delta : Q \times \Sigma \to Q$ é uma função de transição,
- $q_0 \in Q$ é o estado inicial, e
- $F \subseteq Q$ é o conjunto de estados de aceitação (ou estados finais).

---

Autômatos finitos podem ser representados como [[Introdução a Grafos|grafos]], onde cada nó representa um estado e cada aresta representa uma transição. Um nó com borda dupla representa um estado de aceitação.

##### Exemplo
![[Pasted image 20220917151300.png]]

---

### [[Linguagens Formais|Linguagem]] Reconhecida
#### Definição
Se $A$ é o conjunto de todas as cadeias que uma máquina $M$ aceita, dizemos que $A$ é a linguagem reconhecida pela máquina $M$.

Denotamos a linguagem de uma máquina $M$ por $L(M) = A$.

---

# Minimização de Automatos Finitos
#### Definição
Um AFD mínimo para uma linguagem é aquele que, dentre todos os AFDs equivalentes para a mesma linguagem, possui o menor número de estados.

Pode-se demonstrar que o AFD mínimo para uma linguagem é único (desconsiderando trocas de nomes dos estados, que não alteram o funcionamento do AFD).

## Algoritmo para minimizar um AFD
O algoritmo de minimização de AFDs é baseado no conceito de estados equivalentes, ou seja, que se comportam identicamente.

#### Definição
Dois estados $e$ e $e^\prime$ são equivalentes se o resultado final (aceitação ou rejeição) do processamento de qualquer cadeia $w ∈ Σ^*$ é o mesmo se iniciado a partir $e$ ou a partir de $e^\prime$ .

Mais formalmente, dois estados $e$ e $e^\prime$ são equivalentes se $∀w ∈ Σ^∗ : w$ é aceita a partir de $e ⇔ w$ é aceita a partir de $e^\prime$.

O algoritmo de minimização funciona ao unir todos os estados equivalentes entre si (o que não altera o funcionamento do autômato, uma vez que estados equivalentes se comportam de maneira idêntica para toda cadeia). Já estados não-equivalentes não podem ser unidos e permanecem separados.
A questão central do algoritmo de minimização é, então, determinar quais estados de um AFD são equivalentes.

Para determinar quais estados não são equivalentes, o algoritmo:
1. Inicialmente assume que todos os estados são equivalentes entre si e os agrupa.
2. Iterativamente identifica cadeias $w ∈ Σ^∗$ que atestam que alguns estados não são equivalentes e separa estes estados.
3. Quando nenhum estado mais pode ser separado, sabe-se que somente os estados equivalentes permanecem juntos e com eles se constrói o autômato equivalente minimizado.

---

# Linguagens Regulares
#### Definição
Uma linguagem é chamada de linguagem regular se algum autômato finito a reconhece.

# Operações Regulares
Sejam $A$ e $B$ linguagens. Definimos as operações regulares **união**, **concatenação**, e **fecho de Kleene** (ou estrela) da seguinte forma:
- União: $A ∪ B = \set{x | x ∈ A \text{ ou } x ∈ B}$.
- Concatenação: $A ◦ B = \set{xy | x ∈ A \text{ e } y ∈ B}$. 
- Estrela (ou fecho de Kleene): $A^* = \set{x_1x_2 \ldots x_k | k ≥ 0 \text{ e cada } x_i ∈ A}$.\

###### Teorema
A classe de linguagens regulares  é fechada sob a operação de união.

###### Teorema
A classe de linguagens regulares  é fechada sob a operação de concatenação.

###### Teorema
A classe de linguagens regulares  é fechada sob a operação de fecho de Kleene.

# Expressões Regulares
Expressões regulares são geradores para as linguagens regulares. Uma expressão regular pode ser descrita com uma cadeia de símbolos e operações.
#### Definição
$R$ é uma expressão regular se $R$ for
1. $a$, para algum $a$ no alfabeto $\Sigma$,
2. $\epsilon$,
3. $\emptyset$,
4. $(R_1 \cup R_2)$, onde $R_1$ e $R_2$ são expressões regulares,
5. $(R_1 ◦ R_2)$, onde $R_1$ e $R_2$ são expressões regulares,
6. $(R^*_1)$, onde $R_1$ é uma expressão regular.

---
# Não-determinismo

Não-determinismo é um conceito extremamente útil que tem grande impacto sobre a teoria da computação.

Até agora lidamos com computação determinística: quando a máquina está em um estado e lê um símbolo, existe exatamente uma única opção para o próximo estado.

Em uma computação não-determinística, quando a máquina está em um estado e lê um símbolo, podem existir várias $(0, 1, 2, 3, . . .)$ escolhas para o próximo estado.

Note que o não-determinismo é uma generalização do determinismo. Todo autômato finito determinístico (AFD) é automaticamente um autômato finito não-determinístico (AFN) também.

![[Pasted image 20220917154151.png]]

Há ao menos 3 interpretações de uma computação não-determinista:
- **Oráculo**: em cada ponto em que há mais de uma possibilidade, a máquina “adivinha” um caminho que leva à aceitação da cadeia (se tal escolha existe) e segue este caminho. 
  
  Ou seja: se existe um caminho que leve à aceitação da cadeia, a máquina “adivinha” tal caminho e aceita a cadeia; se tal caminho não existe, a máquina rejeita a cadeia.
  
- **Paralelismo**: em cada ponto em que há mais de uma possibilidade, a máquina se divide em múltiplas cópias, e cada uma continua computando normalmente.
  
   Ou seja: uma cadeia é aceita se, e somente se, pelo menos uma cópia da máquina aceita a cadeia.

- **Backtracking**: em cada ponto em que há mais de uma possibilidade, a máquina escolhe uma que ainda não foi testada e prossegue. Caso a escolha leve à rejeição da cadeia, a máquina retorna ao ponto da última escolha em aberto e faz uma nova opção. 
  
   Ou seja: se, e somente se, existe uma maneira de aceitar a cadeia, a máquina vai encontrá-la pois ela tenta todas as computações alternativas possíveis.

###### Teorema
Todo autômato finito não-determinístico (AFN) tem um autômato finito determinístico (AFD) equivalente.

#### Corolário
Uma linguagem é regular se, e somente se, algum AFN a reconhece.

###### Teorema
A classe de linguagens regulares é fechada sob a operação de união.

###### Teorema
A classe de linguagens regulares é fechada sob a operação de concatenação.

###### Teorema
A classe de linguagens regulares é fechada sob a operação de fecho de Kleene.

###### Teorema
A classe de linguagens regulares é fechada sob complemento.

###### Teorema
A classe de linguagens regulares é fechada sob a operação de interseção.