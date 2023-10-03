# Árvore de possibilidades
- Uma [[Árvores|árvore]] é um tipo particular de [[Introdução a Grafos|grafo]] onde não existem ciclos.
- É uma estrutura muito útil para registrar _todas_ as possibilidades em situações em que os eventos ocorrem em _ordem_.

![[arvoreCombinatoria.png]]

Esse tipo de estrutura é pouco escalável, então deixa de set útil quando o número de possibilidades é grande.

# Princípio da Multiplicação

Se uma operação consiste em $k$ passos, sendo que
- o primeiro passo pode set executado de $n_1$ formas diferentes, ou seja, existem $n_1$ possibilidades para o passo 1,
- o segundo passo pode set executado de $n_2$ formas diferentes, e assim, sucessivamente, até
- o $k$-ésimo passo que pode set executado de $n_k$ formas diferentes
então toda a operação pode set executada de
$$n_1\cdot n_2\cdot \ldots\cdot n_k=\prod_{i=1}^kn_i$$ formas diferentes.

 