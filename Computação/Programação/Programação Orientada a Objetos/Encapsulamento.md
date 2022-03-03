[[Introdução a POO|]][[Classes e seus Métodos|]][[Classes e seus Atributos|]]

Encapsulamento é o mecanismo que coloca juntos os dados e suas funções associadas, mantendo-os controlados em relação ao seu nível de acesso. Assim, tal ferramenta proporciona [[Princípios Da POO#Abstração|abstração]], separa a visão interna da visão externa e protege a integridade dos dados do [[Objetos e Classes|Objeto]].

---
# Modificadores de Acesso
+ Public
+ Protected
+ Private

```C++
#include <string>

class Classe {
	public:
		std::string str = "string";
	protected:
		int num1 = 10;
	private:
		float num2 = 3.141592;
}
```

***Obs.:*** A checagem dos modificadores ocorre em tempo de compilação.

---
## Public
+ Permite que os membros sejam acessados de qualquer outra parte do código.
+ Deve ser utilizado com responsabilidade.
+ Não é recomendado.

## Protected
Permite que os membros sejam acessados apenas por outras classes derivadas ou por classes amigas (C++).

## Private
+ Permite que os membros sejam acessados somente por métodos da mesma classe.
+ Deve ser usado sempre que possível.
***Obs.:*** É o padrão quando não há declaração explícita.

---
# Acessando e Modificando Atributos
+ Acesso deve ser o mais restrito possível.
+ De preferência todos devem ser private.
+ Sempre usar métodos auxiliares

## Getters e Setters
+ Todos os atributos devem possuir `get` e `set`.
+ Atributos boleanos devem utilizar o prefixo `is` ao inves de `get`.

---