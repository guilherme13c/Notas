[[Polimorfismo|]][[Princípios Da POO|]][[Introdução a POO|]]
# Sobrecarga
- Operador ou função com _assinaturas_ diferentes.
```cpp
#include <iostream>

int sum(int a, int b) {
	std::cout << "Sum of ints\n";
	return a + b;
}

double sum (double a, double b) {
	std::cout << "Sum of doubles\n";
	return a + b;
}

int main() {
	sum(1, 2) << std::endl;
	sum(1.1, 2.1) << std::endl;
	sum(1, 2.1) << std::endl;//Erro
}
```
O compilador "sabe" qual função invocar checando o tipo dos parâmetros. No código do exemplo, a última chamada é ambígua, assim o compilador não "sabe" qual função deve chamar, então levanta um error de compilação.

---
# Sobrecarga de Operadores
## Leitura de Streams
```Cpp
// fraction.h
#ifndef DATA_H
#define DATA_H

struct Fraction {
	int, num, den;
};

std::istream& operator >> (std::istream& is, Fraction& dt);
#endif
```

```Cpp
// fraction.cpp
#include <iostream>
#include "fraction.h"

std::istream& operator >> (std::istream& is, Fraction& dt) {
	is >> dt.num >> dt.den;
	return is;
}
```

```Cpp
// main.cpp
#include <iostream>
#include "fraction.h"

int main() {
	Fraction f;
	std::cin >> f;
}
```

## Escrita de Streams
```Cpp
// fraction.h
#ifndef DATA_H
#define DATA_H

struct Fraction {
	int, num, den;
};

std::istream& operator >> (std::istream &is, Fraction &dt);
std::istream& operator << (std::istream &out, Fraction const &dt);
#endif
```

```Cpp
// fraction.cpp
#include <iostream>
#include "fraction.h"

std::istream& operator >> (std::istream &is, Fraction &dt) {
	is >> dt.num >> dt.den;
	return is;
}
std::istream& operator << (std::istream &out, Fraction const &f) {
	return out << "(" << f.num << "/" << f.dem << ")";
}
```

```Cpp
// main.cpp
#include <iostream>
#include "fraction.h"

int main() {
	Fraction f;
	std::cin >> f;
	std::cout << f;
}
```

## Operação de Comparação
```Cpp
// fraction.h
#ifndef DATA_H
#define DATA_H

struct Fraction {
	int, num, den;

	// Método Integrado `inline`
	inline bool operator < (const Fraction &f) const {
		const double commonDen = den * f.den;
		return (num * f.den)/commonDen < (f.den * den)/commonDen;
	}
};

std::istream& operator >> (std::istream &is, Fraction &dt);
std::istream& operator << (std::istream &out, Fraction const &dt);
#endif
```
Com uma das comparações definidas, é fácil implementar as demais comparações
![[Pasted image 20220108130851.png]]

---

> ##### Método Integrado **Inline**
> Ao usar a palavra 'inline' antes de definir uma função, o compilador escreve o corpo da função no local onde ela seria chamada. Ao evitar a chamada, o código pode se tornar mais eficiente.
> ![[Pasted image 20220108130646.png]]
---