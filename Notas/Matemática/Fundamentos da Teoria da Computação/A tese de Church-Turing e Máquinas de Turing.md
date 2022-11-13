Vimos que as [[Linguagens Livres-do-Contexto e Autômatos com Pilha|liguagens livre-do-contexto]] são mais gerais que as [[Autômatos Finitos e Linguagens Regulares#Linguagens Regulares|linguagens regulares]], e que muitas [[Linguagens Formais|linguagens]] de interesse (como linguagens de programação) são linguagens livres-do-contexto. Porém, vimos que nem toda linguagemé livre-do-contexto, como, por exemplo, $L = \{ww | w \in \{0, 1\}^* \}.$ Por essa razão, autômatos com pilha são ainda muito restritos para servirem como um modelo de computação geral. Aqui vamos estudar um modelo ainda mais poderoso que os autômatos com pilha, as **máquinas de Turing**.

# Máquina de Turing (MT)
Lembre-se de que o [[Linguagens Não-Livres-do-Contexto#Lema do Bombeamento para linguagens livres-do-contexto|lema do bombeamento para linguagens livres-do-contexto]] diz, essencialmente, que gramáticas livres-do-contexto não têm controle sobre quantas vezes uma regra recursiva pode ser usada. Isto se reflete no reconhecedor para linguagens livres-do-contexto: os autômatos com pilha até conseguem “se lembrar” do que já viram, mas apenas “da última coisa que já viram”. Isto sugere que para aumentar o poder de computação de APs, podemos melhorar o tipo de **memória** que eles utilizam. Vamos adicionar à máquina uma memória de acesso irrestrito, uma **fita**, que pode ser lida e escrita em qualquer posição.

Assim, chegamos à máquina de Turing (MT):
![[Pasted image 20221027080230.png]]

## Principais diferenças entre autˆomatos finitos e máquinas de Turing: 
1. MTs podem tanto **ler** quanto **escrever** na fita. 
2. A **cabeça de leitura** pode se mover tanto para a esquerda quanto para a direita. 
3. A fita é infinita. 
4. Os estados especiais para rejeitar e aceitar fazem efeito imediatamente (e não apenas quando a cadeia de entrada tiver sido completamente consumida).

#### Definição
Uma máquina de Turing é uma 7-tupla $(Q, \Sigma, \Gamma, \delta, q_0, q_{aceita}, q_{rejeita})$, onde 
1. $Q$ é o conjunto (finito) de estados, 
2. $\Sigma$ é o alfabeto (finito) de entrada sem o símbolo em branco t, 
3. $\Gamma$ é o alfabeto (finito) da fita, onde $t \in \Gamma$ e $\Sigma ⊆ \Gamma$, 
4. $\delta : Q \times \Gamma \to Q \times \Gamma \times \{E, D\}$ é a [[Funções|função]] de transição, 
5. $q_0 \in Q$ é o estado inicial, 
6. $q_{aceita} \in Q$ é o estado de aceitação, e 
7. $q_{rejeita} \in Q$ é o estado de rejeição, tal que $q_{rejeita} \neq q_{aceita}$.

Note que, pela definição da função transição $\delta$, estamos considerando MTs determinísticas.

### Configuração da Máquina de Turing
A medida em que uma MT computa, ela altera sua **configuração** (ou **configuração instantˆanea**), que é a combinação de três itens: 
1. seu estado atual, 
2. o conteúdo atual da fita, e 
3. a posição do cabeçote de leitura/escrita. A configuração de uma MT contém toda a informação necessária para ela continuar sua computação.

Representamos uma configuração como $$uqv$$ quando a MT: 
1. está no estado $q \in Q$, 
2. o conteúdo atual da fita é $uv \in \Gamma^∗$ , sendo que todo símbolo ap´os o último de $v$ é branco, e 
3. a cabeça de leitura/escrita está apontando para o primeiro símbolo de $v$

#### Definição
Dizemos que uma configuração $C_1$ **origina** uma configuração $C_2$ se a MT puder ir legitimamente de $C_1$ a $C_2$ em um único passo.
Formalmente, sejam $a, b, c \in \Gamma,\space u, v \in \Gamma^*$ , e $q_i , q_j \in Q$. Dizemos que: 

A configuração $uaq_ibv$ **origina** $uq_jacv$ se na função de transição $\delta(q_i, b) = (q_j, c, E)$;
A configuração $uaq_ibv$ **origina** $uacq_jv$ se na função de transição $\delta(q_i, b) = (q_j, c, D)$.

##### Casos especiais de mudança de configuração: 
- Quando a cabeça está na _extremidade esquerda da fita_, a configuração $q_ibv$ origina $q_jcv$ se na função de transição temos o comando $\delta(q_i, b) = (q_j, c, E)$ para a cabeça se mover para a esquerda (pois a MT não pode ir para a esquerda do início da fita). 
- Quando a cabeça está na _extremidade direita da fita_, note que a configuração $uaq_i$ equivale a $uaq_i\sqcup$, pois à direita do último símbolo da fita têm apenas espaços em branco, e podemos realizar a mudança de configuração normalmente (seja a instrução para a cabeça se mover para a esquerda ou para a direita).

A configuração inicial de $M$ sobre a entrada $w$ é $$q_0w,$$pois a máquina está no estado inicial $q_0$ com a cabeça no início da fita. 

- Em uma **configuração de aceitação**, o estado é $q_{aceita}$. 
- Em uma **configuração de rejeição**, o estado é $q_{rejeita}$. 

Configurações de aceitação e de rejeição são **configurações de parada** e, portanto, não originam configurações subsequentes.

## Computação na Máquina de Turing
#### Definição
Uma máquina de Turing $M$ aceita a entrada $w$ se existe uma sequência de configurações $C_1, C_2, \ldots , C_k$ tal que: 
1. $C_1$ é a configuração inicial de $M$ sobre $w$, 
2. cada $C_i$ origina $C_{i+1}$, 
3. $C_k$ é uma configuração de aceitação. O conjunto de cadeias que $M$ aceita é a **linguagem de $M$**, ou a **linguagem reconhecida por $M$**, e é denotada por $L(M)$.

#### Definição
Uma linguagem é **Turing-reconhecível** se alguma máquina de Turing a reconhece. 

*Obs:* Alguns livros chamam as linguagens Turing-reconhecíveis de **linguagens recursivamente enumeráveis.**

## Reconhecedoras e Decisoras
Note que quando uma MT $M$ processa uma cadeia $w$, há 3 possibilidades: 
1. $M$ aceita $w$ (i.e., para em $q_{aceita}$); 
2. $M$ rejeita $w$ (i.e., para em $q_{rejeita}$); 
3. $M$ entra em **loop** (i.e., não para nunca).

#### Definição
Máquinas de Turing que podem entrar em loop são chamadas de **reconhecedoras**.

Elas aceitam toda cadeia de entrada $w \in L(M)$, mas não há garantias de que vão rejeitar toda cadeia $w \not\in L(M)$.

#### Definição
Máquinas de Turing que nunca entram em loop são preferíveis, pois elas fornecem uma resposta definitiva para toda cadeia de entrada: 
- aceita, caso $w \in L(M)$, ou 
- rejeita, caso $w \not\in L(M)$. 
Tais máquinas são chamadas de **decisoras**, pois elas decidem definitivamente se cada cadeia pertence ou não à linguagem.

### Linguagens Turing-decidíveis
#### Definição
Uma linguagem é **Turing-decidível**, ou simplesmente **decidível**, se alguma máquina de Turing a decide.

Note que toda linguagem Turing-decidível também é Turing-reconhecível.

# Variantes da Máquina de Turing
Existem variações da MT contendo novos recursos. Veremos agora que essas variantes (pelo menos as que citaremos) são equivalentes à versão original da MT.

### Máquina de Turing com cabeçote imóvel
Se adicionarmos a possibilidade de, em uma transição, manter o cabeçote de leitura/escrita na mesma posição, teremos o mesmo poder computacional.

### Máquina de Turing Multifita
Se adicionarmos mais fitas de memória à MT original, também não ganhamos mais poder computacional. Isso ocorre pois cada fita tem tamanho arbitrário, assim sendo possível simular $n$ fitas em uma única fita, desde que $n$ não seja infinito.

### Máquina de Turing Não-Determinista
Podemos também adicionar não-determinismo à MT preservando o poder computacional da máquina.

# A Tese de Church-Turing
O conceito de **computação** é hoje consolidado pela **Tese de Church-Turing**:

- “Se uma função é efetivamente computável, então ela é computável por meio de uma máquina de Turing.” 
Uma formulação alternativa, mas equivalente, da tese é: 
- “O conceito intuitivo de ‘algoritmo’ equivale aos algoritmos de máquinas de Turing.”

#### Definição
“ _Computação efetiva_ (e *algoritmos*) é nada mais, nada menos, do que exatamente aquilo que as Máquinas de Turing são capazes de fazer.”

A Tese de Church-Turing dificilmente pode ser demonstrada verdadeira, porém é amplamente aceita, uma vez que existem fortes evidências a seu favor.

# Gramáticas Irrestritas (GI)
#### Definição
Uma **gramática irrestrita** é uma 4-tupla $(V, \Sigma, R, S)$, onde: 
1. $V$ é um conjunto finito denominado variáveis, 
2. $\Sigma$ é um conjunto finito, disjunto de V, denominado terminais, 
3. $R$ é um conjunto finito de regras, com cada regra sendo uma cadeia não vazia de variáveis e terminais e uma cadeia possivelmente vazia de variáveis e terminais, e 
4. $S \in V$ é uma variável inicial (ou variável de partida).

### Notações
- Dizemos $uxv$ origina $uwv$ com a notação: $$uxv\implies uwv$$
- Dizemos $u$ deriva $v$ com a notação: $$u \overset{*}{\implies} v$$
---
