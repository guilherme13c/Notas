Como vimos, os [[Linguagens Livres-do-Contexto#Autômato com Pilha (AP)|autômatos com pilha]] são ainda mais poderosos que os [[Autômatos Finitos e Linguagens Regulares#Autômato Finito (AF)|autômatos finitos]], podendo reconhecer ainda mais [[Linguagens Formais|linguagens]]. Porém, APs não conseguem reconhecer todas as linguagens. Ou seja, existem linguagens não-livres-do-contexto, que estão além do poder dos autˆomatos com pilha e, equivalentemente, além do poder das gram´aticas livres-do-contexto.

# Lema do Bombeamento para linguagens livres-do-contexto
Se $A$ é uma linguagem livre do contexto, então existe um número $p$, chamado de comprimento de bombeamento, tal que, se $s$ é uma cadeia qualquer em $A$ de comprimento pelo menos $p$, então $s$ pode ser dividida em cinco partes $s = uvxyz$ satisfazendo as seguintes condições: 
1. para cada $i ≥ 0, uv^i xy^i z ∈ A,$ 
2. $|vy| > 0$, e 
3. $|vxy| ≤ p$.
