# Árvores
São um tipo de [[Tipos Abstratos de Dados#Estruturas de dados|estrutura de dados]] hierárquica, onde os elementos são organizados em níveis. Se assemelha com as [[Listas Ligadas (Encadeadas)|listas ligadas]].

## Elementos De Uma [[Árvores|Árvore]]

O primeiro nó da hierarquia é chamado de ***raiz***, os nós que não possuem filhos são ***folhas***. O filho de um nó é a raiz de uma ***subárvore***.

# Árvore Binária

É um tipo específico de [[Árvores#Árvores|árvore]] onde cada nó possui no máximo dois nós filhos.

# Árvores Binárias de Pesquisa

São [[#Árvore Binária|árvores binárias]] com regras de organização específicas. O elementos menores que a raiz da subárvore ficam à esquerda da mesma, já os maiores ficam à direita. Essas regras são válidas para todas as subárvores de uma árvore binária de pesquisa.

Os métodos relacionados com as árvores costumam ser [[Recursão|recursivos]].

```Cpp
//BST.hpp

#ifndef BST_H
#define BST_H

#include <iostream>
using namespace std;

struct NodeT {
	int data;
	NodeT* esq;
	NodeT* dir;
};

struct BST {
	NodeT* root =  nullptr;
	
	void insertNodeHelper(NodeT* root, int data);
	
	void insertNode(int data);
	void removeNode(int data);
	void display();
}

#endif
```

---

```Cpp
//BST.cpp

#include "BST.hpp"

NodeT* createNode(int data) {
	NodeT* aux = new NodeT;
	aux->data = data;
	aux->esq = nullptr;
	aux->dir = nullptr;
	
	return aux;
}

void BST::insertNodeHelper(NodeT* n, int data) {
	if (data < n->data) {
		if (n->esq == nullptr) {
			n->esq = createNode(data);
		} else {
			insertNodeHelper(n->esq, data);
		}
	} else if (data > n->data) {
		if (n->dir == nullptr) {
			n->dir = createNode(data);
		} else {
			insertNodeHelper(n->dir, data);
		}
	}
}

void BST::insertNode(int data) {
	if (root != nullptr) {
		insertNodeHelper(root, data);
	} else {
		root = createNode(data);
	}
}
```

---

```cpp
//main.cpp

#include "BST.hpp"

int main() {
	BST bst;
	
	bst.insertNode(5);
	bst.insertNode(2);
	bst.insertNode(7);
	bst.insertNode(6);
	
	return 0;
}
```
---
## Caminhamento Central

```cpp
void inorder(NodeT* n) {
	if (n == nullptr) {
		return;
	}
	
	inorder(n->esq);
	cout << n->data << " ";
	inorder(n->dir);
}

void BST::display() {
	inorder(root);
	cout << endl;
}
```