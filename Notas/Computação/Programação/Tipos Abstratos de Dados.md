# [[Algoritmos#Algoritmos|Algoritmos]]
+ Sequência de ações executáveis;
+ Transformam uma entrada em uma saída;
+ Trabalham sobre [[#Estruturas de dados]].

# Estruturas de dados
+ Informações que representam uma situação real;
+ Absatração da realidade;
+ Suportam as operações dos algoritmos.

---
## Diferença entre Programa e Algoritmo
+ Um programa é uma realização concreta de um algoritmo abstrato, baseado em representações de dados específicas.
+ Programs precisam ser implementados em uma linguagem que pode ser entendida e seguida pelo computador. Ex.: C, C++, Java, Python, ...

---
# Tipos Abstratos de Dados (TAD's)
+ Generalização de tipos primitivos;
+ Encapsula diversos elementos (membros):
	+ Conjuntos de **valores**;
	+ Conjuntos de **operações** sobre esses valores.
+ Código com perspectivas diferentes:
	+ Usuário x Programador;
	+ Acesso às operações disponibilizadas;
	+ Conhece a específicação, não a implementação.
+ Desvincular a especificação da sua implementação
	+ Ocultação de Informações
+ *Especificação*:
	+ O que representa
	+ Quais operações podem ser realizadas
+ *Implementação*:
	+ Como deve ser implementada

---
# TAD's em C++
Em C++, utilizamos estruturas (structs) para implementar os tipos abstratos de dados.

```Cpp
#include <iostream>
#include <cmath>

using namespace std;

struct Ponto3D {
	float x;
	float y;
	float z;
	
	float calcularDistancia(Ponto3D *p2) {
		float dx = p2->x - this->x;
		float dy = p2->y - this->y;
		float dz = p2->z - this->z;
		return sqrt(dx*dx + dy*dy + dz*dz);
	}
};

int main() {
	Ponto3D *p1 = new Ponto3D;
	p1->x = 0;
	p1->y = 0;
	p1->z = 0;
	
	Ponto3D *p2 = new Ponto3D;
	p2->x = 5;
	p2->y = 5;
	p2->z = 5;
	
	cout << p1->calcularDistancia(p2) << endl;
	
	delete p1;
	delete p2;
	
	return 0;
}
```

---
# Uso dos TAD's
Os Tipos Abstratos de Dados podem ser usados para implementar a Programação Orientada a Objetos (POO / OOP).
