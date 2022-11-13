[[Introdução a POO|]][[Princípios Da POO|]]
# O Princípio da Subistituição
Se $S$ é subtipo de $T$, então $S$ deve poder ser usado em qualquer situação em que $T$ pode ser usado.

---
## A Lei da [[Herança]]
Se $S$ é subtipo de $T$, então:
- Pré-condições em $S$ não podem ser mais restritivas que em $T$;
- Pós-condições em $S$ não podem ser mais relaxadas que em $T$;
- Invariantes de $T$ têm de ser preservadas em $S$.
 
---
## Overriding do Operador de Igualdade (=)
Sabemos que a [[Introdução a Relações|relação]] de igualdade é uma [[Relações de Equivalência|relação de equivalência]]. Dessa forma, quado se tenta sobrescrever o operador de igualdade em uma linguagem orientada a objetos, devemos preservar suas [[Propriedades de Relações|propriedades]] (reflexividade, simetria e transitividade).

Uma das coisas que pode ser feita para garantir a preservação dessas propriedades é um conferência dos tipos dos elementos. Em C++, usamos o arquivo de cabecalho `<typeinfo>`:

```Cpp
// Point.cpp

#include <typeinfo>

bool operator == (const Point &lhs, const Point &rhs) {
	bool t_lhs = typeid(lhs) == typeid(Point);
	bool t_rhs = typeid(rhs) == typeid(Point);
	if (t_lhs && t_rhs) {
		return lhs.x == rhs.x && lhs.y == rhs.y;
	} else {
		return false;
	}
}
```

Essa solução preserva as propriedades da relação de igualdade, mas quebra o princípio de substituição de Liskov. Para resolver ambos problemas simultaneamente, podemos usar a composição ao invés da herança, e criar um método conversor (caso seja preciso).

---