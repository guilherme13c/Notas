# Definição
Dada uma [[Relações de Equivalência|relação de equivalência]] $\sim$ num conjunto $A$, a classe de equivalência de um $a\in A$ é o conjunto $\bar a=\{x\in A:x\sim a\}$

>## Proposição
>Seja $\sim$ uma relação de equivalência em $A$ e $a,b\in A$. Então ou $\bar a=\bar b$ ou $\bar a\cap \bar b = \emptyset$.
>## Prova
>($(ii)\to$Simetria, $(iii)\to$Transitividade)
>Suponha que existe $x\in\bar a\cap\bar b$. Assim, $$x\sim a\mbox{ e } x\sim b$$
>$$\Downarrow (ii)$$
>$$a\sim x\mbox{ e }x\sim b$$
>$$\Downarrow$$
>$$a\sim b \xRightarrow{(ii)}b\sim a$$
>+ $y\in\bar a\Rightarrow y\sim a\xRightarrow[(iii)]{a\sim b}y\sim b\Rightarrow y\in\bar b$.
>+ $y\in\bar b\Rightarrow y\sim b\xRightarrow[(iii)]{b\sim a} y\sim a\Rightarrow y\in\bar a$.$\square$

---
# Partições
Dada $\sim$ em $A$, considere $A/_\sim=\{\bar a:a\in A\}$. Vimos que esses conjuntos particionam $A$, isto é, todo $a\in A$ está em alguma classe de equivalência e nenhum elemento está em duas classes diferentes.

Assim, podemos pensar em classes de equivalência como partições.

![[relacoes1.png]]
$\mathbb{Q}=(\mathbb{Z}\times\mathbb{N})/_\sim$

---
# Propriedades das Classes de Equivalência
Seja $A$ um conjunto e $R$ uma relação de equivalência em $A$ e $a$ e $b$ elementos de $A$:
1. Se $aRb$, então $[a]=[b]$
2. $[a]\cap[b]=\emptyset\;\;\;\vee\;\;\;[a]=[b]$

---
