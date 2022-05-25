# Biblioteca

Bibliotecas são conjuntos de implementações em uma determinada linguagem. Elas possuem interface e comportamento bem definidos, que devem estar presentes em sua documentação. Esses conjuntos auxiliam na reutilização de código em diferentes partes do programa.

---
# Biblioteca Padrão C++

Funcionalidades são utilizadas a partir do método `#include`:

```Cpp
#include <string>
#include <iostream>
```

A Biblioteca Padrão do C++ é definida em um espaço de nomes (namespace) chamado `std`.

```Cpp
#include <iostream>

int main() {
	std::cout << "Hello  world!" << std::endl;  // acessando o componente através
	return 0;								  						// do namespace
}
```

Também podemos fazer a importação de todos os componentes do namespace:

```Cpp
#include <iostream>

using namespace std;	// importando os componentes do namespace

int main() {
	cout<< "Hello world!" << endl;
	return 0;
}
```

---
## Standard Template Library - STL

- ***[[Biblioteca STL#Containers|Container]]:*** representa como os dados são armazenados;
- ***[[Biblioteca STL#Iteradores|Iterador]]:*** auxilia no acesso e manipulação ("[[Ponteiros em C e Cpp|ponteiros]]");
- ***[[Biblioteca STL#Algorithms|Algorithm]]:*** procedimento que pode ser aplicado aos dados.

#### Programação Genérica

- A mesma definição de função atua sobre diferentes tipos, o que provê maior liberdade e flexibilidade para a implementação.
- Polimorfismo Universal/Paramétrico, em que os tipos são passados como parâmetros.

##### Linguagens

Templates (C++), Genérics(Java).

```Cpp
template <typename T> class NodeG {
	T data;
	NodeG* next;
}
```

---
### Containers

São estruturas de dados que armazenam coleções nas quais todos os elementos são do mesmo tipo, sendo esse primitivo ou definido pelo programador.

Praticamente todos os [[Tipos Abstratos de Dados|TADs]] são containers.
O uso de tipos específicos na definição desses [[Tipos Abstratos de Dados|TADs]], a estrutúra fica muito rígida. Dessa forma, é comum utilizar tipos genéricos, para que possam ser reutilizados com mais facilidade.

Os containers possibilitam o acesso uniforme aos dados (contrato). Assim, a utilização dos [[Tipos Abstratos de Dados|TADs]] fica padronizada, indepente do tipo do elemento e de como está [[Armazenamento e manipulação de dados|armazenado]]. A recuperação dos dados fica, também, baseada em regras bem definidas, usando índice, valor ou propriedades do elemento, por exemplo.

---
#### Tipos de Containers
##### Sequenciais
Os containers sequenciais são aqueles que mantém a ordem dos elementos de acordo com a ordem em que foram inseridos.

###### Vector
É um array genérico e dinamicamente redimensionável. Possiblita o acesso individual aos elementos a partir de índices e a adição e remoção de itens ao final de forma eficiente, além de poder ser percorrido em uma ordem específica.

```Cpp
#include <vector>
#include <iostream>

int main() {
	std::vector<int> v = {7, 5, 16, 8};
	
	v.push_back(25);
	v.push_back(13);
	
	for (int n : v) {
		std::cout << n << std::endl;
	}
	return 0;
}
```

###### List
É uma lista duplamente encadeada, e por isso não possibilita acessar elementos usando índices. A adicão e remoção de elementos com posição conhecida é mais eficiente, já que não é precisso mover os demais elementos.

```Cpp
#include <iostream>
#include <list>

int main() {
	std::list<int> l = {7, 5, 16, 8}1;
	
	l.push_front(25);
	l.push_back(13);
	
	for (std::list<int>::iterartor it=l.begin(); it != l.end(); ++it) {
		std::cout << *it << std::endl;
	}
	
	return 0;
}
```

---
##### Associativos

Os containers associativos mantém uma organização interna, que independe da sequencia de insersão.

###### Set
Semelhante ao conceito matemático, guarda uma coleção de elementos distintos. Esses elementos devem ser comparáveis de acordo com algum critério.

```Cpp
#include <iostream>
#include <set>

int main() {
	std::set<int> s;
	
	for(int i = 10; i >= 1; i--) {
		s.insert(i);
	}
	
	s.insert(7);
	
	for(int i = 2; i <= 10; i += 2) {
		s.erase(i);
	}
	
	std::cout << "(" << s.size() << ")" << std::endl;
	for (int e : s) {
		std::cout << e << std::endl;
	}
	
	return 0;
}
```

###### Map
Array associativo ou dicionário, onde cada elemento possui uma chave única. Assim, o Map é formado por cunjuntos de pares <chave, valor>.

```Cpp
#include <iostream>
#include <string>
#include <map>

int main() {

	std::map<int,std::string> m;

	m.insert(std::pair<int,std::string>(2017123456, "Joao"));

	m[2016123456] = "Maria";
	m[2018123456] = "Carlos";
	m[2015123456] = "Jose";
	m[2014123456] = "Joana";

	std::map<int,std::string>::iterator it;
	for (it = m.begin(); it != m.end(); it++) {
		std::cout << it->first << ": " << it->second << std::endl;
	}

	m[2016123456] = "Douglas";
	std::cout << m[2016123456] << std::endl;
	
	return 0;
}
```

---
##### Adaptadores

- Stack
- Queue
- Priority queue

---
***Obs.:*** Containers armazenam os dados por valor, não por referência.

---

### Iteradores

São semelhantes aos ponteiros, sendo usados para acessar os elementos armazenados. Iteradores apontam para itens que estão em um container. Podemos iterar sobre os elementos, isto é, percorrê-los.

```Cpp
#include <iostream>
#include <vector>

int main() {
	
	std::vector<int> v;
	
	v.push_back(5);
	v.push_back(2);
	v.push_back(9);
	
	std::vector::iterator it;
	for (it = v.begin(); it != v.end(); ++it) {
		std::cout << *it << std::endl;
	}
	return 0;
}
```

### Algorithms
São [[Algoritmos|algoritmos]] a serem usados em intervalos (Range) de elementos.

***Range***: qualquer sequência que pode ser acessada por meio de iteradores ou ponteiros, como matrizes ou alguns containers. O range define o intervalo semi-aberto: `[first, last)`.

***Atenção:*** em containers, o `begin()` aponta para o primeiro elemento, e o `end()` para a posição após o último. 

```Cpp
#include <iostream>
#include <vector>
#include <algorithm>

int main() { 
	
	std::vector<int> v = {23, 7, 5, 16, 8, 1, 12, 20, 10}; 
	
	for(int &n : v) 
		std::cout << n << std::endl; 
	
	int max = *std::max_element(v.begin(), v.end()); 
	std::cout << "Max: " << max << std::endl; 
	
	std::cout << "Sort:" << std::endl; std::sort(v.begin(), v.end()); 
	for(int &n : v) 
		std::cout << n << std::endl; 
	
	return 0; 
}
```