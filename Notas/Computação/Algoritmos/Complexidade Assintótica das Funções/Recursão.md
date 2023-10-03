# Definições recursivas
Toda definição que utilize a si mesma é considerada uma ***definição recursiva***.
> #### Exemplos:
> > ###### Números Naturais
> > a) 1 é um número natural
> > b) o successor de um número natural é um número natural
> 
> > ###### Função fatorial
> > a) $0! = 1$.
> > b) se $n > 0$ então $n! = n (n - 1)!$

---
# O poder da recursão
A recursão permite definir um conjunto infinito de objetos através de um commando finito.

Um problema recursivo $P$ pode set espresso como $$P \equiv \mathcal{P}[S_i,P],$$ onde $\mathcal{P}$ é a composição de commandos $S_i$ e do próprio $P$.

## O problema da terminação
É importante definir uma condição para a terminação da recursão. Caso essa etapaseja feita de forma incorreta, o processo recursivo pode se tornar interminável, causando problemas. Por esse motivo, algoritmos recursivos são perigosos, já que computadores possuem memória finita, a má implementação pode levar o programa a extrapolar o seu devido espaço de armazenamento, conflitando com as demais atividades que ocorrem simultaneamente na máquina.

---
[[Algoritmos|]][[Armazenamento e manipulação de dados|]]