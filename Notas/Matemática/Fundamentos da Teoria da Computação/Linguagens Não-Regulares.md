Sabemos que os [[Autômatos Finitos e Linguagens Regulares#Autômato Finito (AF)|autômatos finitos]] são capazes de reconhecer toda e qualquer [[Linguagens Formais|linguagem]] regular. Contudo, existem linguages que não podem ser reconhecidas pelos autômatos finitos, chamadas de linguagens não-regulares.

Para demonstrar que uma dada linguagem não pertence ao conjunto de linguagens regulares, podemos utilizar o [[#Lema do Bombeamento]].

# Lema do Bombeamento
Se $A$ é uma linguagem regular, então existe um número $p$ (o *comprimento de bombeamento*) tal que, se $s$ é qualquer cadeia de $A$ de comprimento no mínimo $p$, então $s$ pode ser dividida em três subcadeias $$s=xyz$$
satisfazendo as seguintes condições:
1. para cada $i\geq0,\space xy^iz\in A$,
2. $\vert y\vert > 0$, e
3. $\vert xy\vert\leq p$.