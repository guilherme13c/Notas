[[Introdução a POO|]][[Objetos e Classes|]][[Classes e seus Métodos|]]

Suportam os [[Princípios Da POO|conceitos]] de:
+ Encapsulamento
+ Herança
+ Polimorfismo

---
# Tipos de Componentes
+ Membros de instância
+ Membros de classe (estáticos)
+ Procedimentos de inicialização
+ Procedimentos de destruição

## Membros de Instância
+ [[Armazenamento e manipulação de dados|Espaço de memória]] alocado para cada objeto
+ Somente são chamados através do objeto]

## Membros de Classe (estáticos)
+ Espaço de memória único para todos objetos
+ Podem ser chamados mesmo sem um objeto

---
# Instanciação de Objetos
Criação do objeto, alocação de memória para o mesmo, e criação/retorno da referência para ele.

---
# Atributos de Instância
## Valores Padrão
+ Tipos numéricos: valor 0 (zero)
+ Tipo boleano: valor 0 (false)

***Obs.:*** Não se deve confiar nessa inicialização.

Os demais atributos não são inicializados "automaticamente", e ponteiros apontam para lixo de memória.

Os atributos definem o **estado** do objeto.

---
# Atributos Estáticos
+ Não estão associados a uma instância
+ São compartilhados pelas instâncias e ocupam um espaço único na memória
+ Geralmente utilizados para constantes

---
