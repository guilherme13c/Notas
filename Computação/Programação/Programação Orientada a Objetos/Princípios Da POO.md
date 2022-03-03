[[Introdução a POO|]][[Objetos e Classes|]]

# Abstração
>#### Elimine o irrelevante, enfatize o essencial.

A representação computacional do objeto real deve se concentrar nas características que são relevantes para o problema.

São criados somente os atributos e métodos necessários para o problema em mãos.

---
# [[Encapsulamento]]
>#### Esconda o desnecessário.

O objeto deve esconder seus dados e os detalhes de sua implementação.

## [[Classes e seus Atributos|Atributos]] e [[Classes e seus Métodos|Métodos]]
+ Atributos não devem ser manipulados diretamente.
+ Os atributos somente devem ser alterados ou consultados através dos métodos do objeto.

Um sistema orientado a objetos baseia-se no **contrato** e não na implementação interna.

Proteção da estrutura interna (integridade)
> Modificadores de acesso (C++):
> ```C++
> public, protected, private
> ```

---
# [[Herança]]
>#### Modele a semelhança.

Objetos devem ser organizados de forma hierárquica no sistema, o que facilita a implementação de herança.

Objetos herdam atributos e métodos de seus antecedentes na hierarquia.

## [[Herança#Árvore de Herança|Estrutura Hierárquica]]
+ A classe que forneceu os elementos herdados é chamada de **superclasse**.
+ A classe herdeira é chamada de **subclasse**.
+ A subclasse pode herdar os métodos e atributos de suas superclasses.
+ A subclasse pode definir novos atributos e métodos específicos.

---
# [[Polimorfismo]]
>#### Mesma função, comportamentos diferentes.

Capacidade da linguagem de tratar tipos diferentes de forma homogênea.

Um método pode assumir "diferentes formas", apresentar diferentes comportamentos.

---
# Modularidade
O sistema deve ser composto de objetos altamente coesos e fracamente acoplados.

Separação de responsabilidades
+ Limites lógicos entre os componentes
+ Melhora a manutenibilidade
+ Aumenta a estabilidade, reduz efeitos colaterais

Um programa orientado a objetos é um conjunto de objetos que colaboram entre si para a solução de um problema.

---
# Mensagens
Comunicação entre objetos
+ Envio/Recebimento de mensagens
+ Forma de invocar um comportamento

---