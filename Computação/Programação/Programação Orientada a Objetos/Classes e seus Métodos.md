[[Classes e seus Atributos|]][[Princípios Da POO|]][[Objetos e Classes|]][[Introdução a POO|]]

São procedimentos que podem modificar ou apenas acessar os valores dos atributos
+ Instância
+ Classe

Controle de visibilidade
+ Determinar que métodos disponíveis para acesso
+ Permite definir o contrato da classe
+ Relacionado ao encapsulamento

---
# Construtores
Método chamado durante a instanciação
+ Classe declara zero ou mais construtores
+ Possui o construtor padrão (sem parâmetros)

Métodos construtores devem sempre possuir o mesmo nome da Classe, sendo diferenciaveis pela lista de parâmetros.

Métodos nunca declaram o tipo de retorno.

## Overloading (sobrecarga)
Dois ou mais métodos podem possuir o mesmo nome ([[Princípios Da POO#Polimorfismo|Polimorfismo]]). Para isso, eles devem possuir listas de parâmetros diferentes (a ordem dos parâmetros importa).

---
# Destrutores
Método chamado para a finalização
+ Libera os [[Armazenamento e manipulação de dados|recursos]] alocados na execução

Devem possuir o mesmo nome da Classe
+ Semelhante aos construtores
+ Devem ser precedidos por `~`

---