[[Algebra Booleana|]]
# Introdução
Existem duas formas canônicas para representar qualquer função booleana, sendo estas:
- **Forma normal disjuntiva**, **Soma-de-Produtos** ou **Expansão de mintermos**
- **Forma normal conjuntiva**, **Produto-de-Somas** ou **Expansão de maxtermos**
Vale destacar que essas formas não são ótimas, e a grande vantagem de seu uso é que são únicas, podendo set utilizadas para mostrar que duas funções $F_1$ e $F_2$ são equivalentes por possuir formas canônicas iguais.

---

# Forma Normal Disjuntiva
Para obter a Soma de Produtos de uma função $F$, podemos utilizar sua tabela da verdade.
Considade a função $F(x_1,x_2)=x_1$:

| $x_1$ | $x_2$ | $F$ |
| --- | --- | --- |
| $0$   | $0$   | $0$   |
| $0$   | $1$   | $0$   |
| ${\color{cyan}1}$   | ${\color{cyan}0}$   | ${\color{cyan}1}$  |
| ${\color{cyan}1}$   | ${\color{cyan}1}$   | ${\color{cyan}1}$   |

Nas linhas da tabela onde o valor da função é $1$ (linhas coloridas), obtemos o **mintermo** (produto das entradas $x_1$ e $x_2$ negando as entradas com o valor $0$). Depois disso, somamos cada mintermo desses:

$F(x_1,x_2)=(x_1\bar{x_2})+(x_1x_2)$

# Forma Normal Conjuntiva
Para obter o Produto de Somas de uma função $F$, também podemos utilizar sua tabela da verdade.
Considere a mesma função do exemplo anterior:

| $x_1$             | $x_2$             | $F$               |
| ----------------- | ----------------- | ----------------- |
| ${\color{cyan}0}$ | ${\color{cyan}0}$ | ${\color{cyan}0}$ |
| ${\color{cyan}0}$ | ${\color{cyan}1}$ | ${\color{cyan}0}$ |
| $1$               | $0$               | $1$               |
| $1$               | $1$               | $1$               |

Nas linhas onde o valor de $F$ é $0$ (linhas coloridas), obtemos o **maxtermo** (a soma das entradas $x_1$ e $x_2$ negando as entradas com o valor $1$). Depois disso, multiplicamos cada maxtermo desses:

$F(x_1,x_2)=(x_1+x_2)(x_1+\bar{x_2})$

---

## Fomas Canônicas e as leis de De Morgan

Podemos também usar uma forma canônica para obter a outra da negação da função usando as leis de De Morgan. Por exemplo, conhecendo o Produto de Somas de $F$, podemos aplicar a lei de De Morgan e obter a Soma de Produtos de $\bar{F}$.

## Mapeando uma Forma Normal para outra

$F(A,B,C)=\sum m(1,3,5,6,7)=\prod M(0,2,4)$
$\bar{F}(A,B,C)=\sum m(0,2,4)=\prod M(1,3,5,6,7)$

onde $m(i,j,k)$ são os mintermos das linhas $i,j,k$ da tabela da verdade. De forma análoga, $M(i,j,k)$ são os maxtermos.

---