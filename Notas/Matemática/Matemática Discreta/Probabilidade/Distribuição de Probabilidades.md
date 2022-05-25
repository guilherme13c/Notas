[[Conceitos Básicos de Probabilidade|]][[Introdução à Análise Combinatória|]]

# Variável Aleatória
É uma variável quantitativa, cujo resultado (valor) depende de fatores aleatórios.

#### Definição
É uma função do espaço amostral de um experimento para o conjunto dos números reais.

#### Distribuição de um Variável Aleatória
A distribuição de uma variável aleatória $X$ em um espaço amostral $S$ é o conjunto de pares $(r,p(X=r))$ para todo $r\in X(S)$ no qual $p(X=r)$ é a probabilidade de $X$ assumir o valor $r$.

---
# Distribuição de Probabilidade
A distribuição de probabilidade é uma descrição de um fenômeno aleatório em termos das probabilidades de eventos.

## Distribuição Uniforme
Seja $S$ um conjunto com $n$ elementos.

A distribuição uniforme atribui a probabilidade ${1\over n}$ a cada elemento de $S$.

O experimento de selecionar um elemento a partir de um espaço amostral com umma distribuição uniforme é chamado de seleção aleatória de um elemento de $S$.

Quando há $n$ resultados associativos ao evento $E$, i.e., $E=\{a_1,a_2,\ldots,a_n\}$, então $p(E)=\sum\limits_{i=1}^n p(a_i)$.

## Distribuição Binomial
Indicamos por $b(k;n,p)$ a probabilidade de $k$ sucessos em $n$ testes de Bernoulli independentes com probabilidades de sucesso $p$ e probabilidade de fracasso $q=1-p$. A distribuição binomial $$b(k;n,p)=\begin{pmatrix}n\\k\end{pmatrix}\,p^kq^{n-k}.$$

---