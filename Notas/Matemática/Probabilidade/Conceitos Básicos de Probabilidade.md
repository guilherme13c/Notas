[[Conceitos Básicos de Probabilidade|]][[Introdução à Análise Combinatória|]]
# Teoria da Probabilidade
Probabilidade de um evento $E$:
$$p(E)={|E|\over|S|}$$
Supondo que todos os resultados são igualmente possíveis.

## Determinando Probabilidades
Seja $S$ o espaço amostral de um experimento com um número finito ou contável de resultados.

Atribuímos uma probabilidade $p(s)$ para cada resultado $s$.

Duas condições devem set respeitadas:
1. $0\le p(s)\le 1$, para cada $s\in S$;
2. $\sum\limits_{s\in S}p(s)=1$.

Se o espaço amostral é infinito, $\sum\limits_{s\in S}p(s)$ é uma série infinita convergente.

Quando há $n$ resultados possiveis, $x_1, x_2,\ldots,x_n$, as duas condições ficam:
1. $\forall i:i\le n\;,0\le p(x_i)\le 1$;
2. $\sum\limits_{i=1}^{n}p(x_i)=1$.

---
# Probabilidade de Combinação de Eventos
Considere $E$ como um evento em um espaço amostral $S$.

A probabilidade do evento $\bar{E}$, chamado de evento complementar de $E$, é dada por
$$p(\bar{E})=1-p(E)=1-{|E|\over|S|}.$$

Considere $E_1$ e $E_2$ como eventos no espaço amostral $S$.

Temos que
$$p(E_1\cup E_2)=p(E_1)+p(E_2)-p(E_1\cap E_2)$$
pelo princípio da Inclusão-Exclusão.

---