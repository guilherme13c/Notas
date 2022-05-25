[[Algebra Booleana|]]

Exceto em casos especiais ou em tabelas da verdade particularmente esparsas, o uso de Mapas de Karnaugh se torna inviável para mais de 6 variáveis. Por isso, se faz necessário um algoritmo mais sistemático.
O método de Quine-McCluskey é capaz de encontrar a representação mínimizada de qualquer [[Formas Canônicas de Funções Booleanas|Função Booleana]] através de um procedimento sistemático que produz todos os primos implicantes e então seleciona o conjunto mínimo de primos que cobre a função. O método encontra os primos implicantes ao aplicar o Teorema da Unificação repetidamente.

# [[Algoritmos|Algoritmo]] de Quine-McCluskey
## Encontrando Primos Implicantes
O primeiro passo do algoritmo é listar todos os elementos que compõe o *on-set* e o *don't-care-set* em termos dos índices de seus mintermos, representados como números binários. Então, os elementos são agrupados de acordo com a quantidade de $1$s na sua representação binária. Isso torna mais fácil a comparação de pares.

Como exemplo, vamos utlizar a função $F=\sum m(4,5,6,8,9,,10,13)+d(0,7,15)$:

|     coluna 1     |     coluna 2     |coluna 3     | 
|:----------------:|:----------------:| :---: |
| 0000$\checkmark$ |     0-00$*$      | 01--$*$    |
|                  |     -000$*$      |     |
| 0100$\checkmark$ |                  |-1-1$*$     |
| 1000$\checkmark$ | 010-$\checkmark$ |     |
|                  | 01-0$\checkmark$ |     |
| 0101$\checkmark$ |     100-$*$      |     |
| 0110$\checkmark$ |     10-0$*$      |     |
| 1001$\checkmark$ |                  |     |
| 1010$\checkmark$ | 01-1$\checkmark$ |     |
|                  | -101$\checkmark$ |     |
| 0111$\checkmark$ | 011-$\checkmark$ |     |
| 1101$\checkmark$ |     1-01$*$      |     |
|                  |     $\space$     |     |
| 1111$\checkmark$ | -111$\checkmark$ |     |
|                  | 11-1$\checkmark$ |     |
$\checkmark$ Implicante
$*$ Primo Implicante

A primeira coluna contém os mintermos do *on-set* e do *don't-care-set*, isto é, pontos no [[Introdução a Grafos#Grafo Cubo- n Q_n|Espaço Booleano]]. Por exemplo, cada um destes representa um produto de 4 variáveis (mintermo). Como resultado da aplicação do método, a segunda coluna vai conter implicantes que formam arestas no Espaço Booleano: produtos de 3 variáveis. Após mais uma iteração do método, a terceira coluna vai conter implicantes que representam planos no Espaço Booleano: produtos de 2 variáveis.
Lembrando que, para aplicar o Teorema da Unificação, devemos comparar os elementos de grupos vizinhos em pares, e quando eles diferirem de apenas um bit, isso significa que os mintermos que esses números representam são adjacentes no Espaço Booleano $n$-dimensional.

## Encontrando A Cobertura Mínima
O segundo passo do método é encontrar a menor coleção de primos implicantes que cobre completamente o *on-set*. Isso pode ser obtido através do pontuário de primos implicantes.

![[Pasted image 20220523164028.png]]