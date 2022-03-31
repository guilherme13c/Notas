# Introdução
A algebra booleana, ou algebra de Boole, fornece as operações e regras para que se trabalhe com o conjunto $B=\set{0,1}$. 

## Operações
As operações básicas para trabalharmos com sistemas booleanos são [[#Complemento]], [[#Soma]] e [[#Produto]].

### Complemento
O complemento é definido como $\bar{1}=0$ e $\bar{0}=1$.

| $x$ | $\bar x$ |
|:---:|:--------:|
|  1  |    0     |
|  0  |    1     |

### Soma
A soma booleana também é conhecida como **OU** ou **OR** e é representada com $+$, $\mbox{ou}$, $\mbox{or}$.

| $x$ | $y$ | $x + y$ |
|:---:|:---:|:-------:|
|  1  |  1  |    1    |
|  1  |  0  |    1    |
|  0  |  1  |    1    |
|  0  |  0  |    0    |

### Produto
O produto booleano também é conhecido como **E** ou **AND** e é representado com $\cdot$, $\mbox{e}$, $\mbox{and}$.

| $x$ | $y$ | $x\cdot y$ |
|:---:|:---:|:----------:|
|  1  |  1  |     1      |
|  1  |  0  |     0      |
|  0  |  1  |     0      |
|  0  |  0  |     0      |


# Funções Booleanas
Seja $B=\set{0,1}$. Então $B^n=\set{(x_1,x_2,\ldots,x_n)\;|\; x_i\in B \mbox{ para } 1\leq i \leq n}$ é o conjunto de todas as possíveis $n$-tuplas de $0$s e $1$s. A variável $x$ é chamada de **Variável Booleana** se ela apenas assume valores de $B$, ou seja, se seus valores possíveis são $0$ e $1$. Uma função de $B^n$ para $B$ é chamada de **[[Funções|Função]] booleana de grau $n$**.

> ## Número de funções booleanas de grau $n$
> Para uma função booleana com $n$ entradas, existem $2^{2^n}$ possíveis funções.


# Identidades Booleanas
| Identidade                                               | Nome                     |
| -------------------------------------------------------- | ------------------------ |
| $\bar{\bar x} = x$                                       | Lei do duplo complemento |
| $$x+x=x$$ $$x\cdot x=x$$                                 | Leis de Idempotência     |
| $$x+0=x$$ $$x\cdot 1 = x$$                               | Leis de Identidade       |
| $$x+1=1$$ $$x\cdot 0 = 0$$                               | Leis de Dominância       |
| $$x+y=y+x$$ $$xy=yx$$                                    | Leis de Comutatividade   |
| $$x+(y+z)=(x+y)+z$$ $$x(yz)=(xy)z$$                      | Leis Associativas        |
| $$x+yz=(x+y)(x+z)$$ $$x(y+z)=xy+xz$$                     | Leis Distributivas       |
| $$\bar{xy}=\bar x+\bar y$$ $$\bar{(x+y)}=\bar x \bar y$$ | Leis de De Morgan        |
| $$x+xy = x$$ $$x(x+y)=x$$                                | Leis de Absorção         |
| $$x+\bar x = 1$$                                         | Propriedade Unitária     |
| $$x\bar x=0$$                                            | Propriedade Zero                         |

# Dualidade
As identidade na tabela acima vêm em pares (exceto a lei de duplo complemento e as propriedades unitária e zero). Para explicar essa relação, usamos o conceito de dual. O **dual** de uma expressão booleana é obtido trocando as somas e adições (onde há $+$ colocamos $\cdot$, e onde há $\cdot$ colocamos $+$) e $0$s e $1$s (onde há $0$ colocamos $1$, e onde há $1$ colocamos $0$).

> ## Princípio da dualidade
> O dual de uma função booleana $F$ representada por uma expressão é a função representada pelo dual da expressão. Essa função dual, representada por $F^d$, não depende da expressão booleana particular usada para representar $F$. Uma identidade entre as funções representadas por expressões booleanas permanece válida quando tomamos o dual de ambos os lados da identidade.