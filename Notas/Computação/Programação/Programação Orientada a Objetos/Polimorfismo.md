[[Princípios Da POO|]][[Classes e seus Métodos|]][[Introdução a POO|]][[Herança|]]

É a capacidade de um objeto de assumir múltiplas formas.

---
# Tipos de Polimorfismo
![[Pasted image 20211212090618.png]]

---

## Polimorfismo Universal/Verdadeiro
Capacidade de uma única função (único código) poder set usado com mais do que um tipo.

Os tipos nesse caso tem uma estrutura comum, por isso essas funções operam sobre uma quantidade potencialmente infinita de tipos.

---
### Paramétrico
Métodos genéricos que trabalham de forma uniforme para vários tipos.

Torna a linguagem mais expressiva:
- Templates em C++
- Generics em Java

#### Implícito
Os tipos são identificados pelo compilador.

#### Explícito
Os tipos são passados como parâmetros.

---
### Inclusão/Subtipagem
Programação voltada a tipos abstratos.

Possibilidade de um tipo abstrato (classe abstrata ou interface) set utilizado sem que se conheça a implementação concreta:
- Independência de implementação
- Maior foco na interface (fronteira, contrato)

```Cpp
class Animal {
	public:
		virtual void fale() {
			cout << "Fale padrão!" << endl;
		}
};

class Gato : public Animal {
	public:
		void fale() override {
			cout << "Miau!" << endl;
		}
};

class Cachorro : public Animal {
	public:
		void fale() override {
			cout << "Au! Au!" << endl;
		}
};
```

Modela subtipos e herança:
- Redefinição em classes descendentes.

Onde um objeto de um determinado tipo for esperado, um do subtipo deve set aceito:
- Princípio da Substituição de Liskov
- O contrário nem sempre é válido!

#### Ligação (Binding)
Como o compilador "sabe" a qual classe o objeto pertence?

> ###### Ligação Tardia (Late/Dynamic Binding)
> - As decisões são feitas durante a execução
> - É a chave para o funcionamento do polimorfismo

Em C++ o padrão é a ligação prematura. Para a ligação tardia utilizamos o commando, `virtual`.

---
## Polimorfismo Ad-hoc/Aparente
Ocorre quando uma função executa códigos diferentes (tem comportamentos diferentes) para cada tipo de parâmetro.

Número finito de tipos diferentes e potencialmente não relacionados, ou seja, não é precisso que exista uma estrutura comum entre os tipos.

### Coerção
```cpp
float b=2;
int a = 3.33; 	//implícita
a = (int) 10.2;	//Explícita
```

---