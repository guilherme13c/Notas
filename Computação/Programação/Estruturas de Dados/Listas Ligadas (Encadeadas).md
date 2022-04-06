# Listas Ligadas/Encadeadas

São um tipo de [[Tipos Abstratos de Dados#Estruturas de dados|estrutura de dados]] parecido com vetores.
Funcionam como uma corrente, onde cada elemento aponta para o próximo/anterior. Dessa forma, é possível alocar apenas a quantidade de memória necessária e inserir elementos no meio da lista se torna mais simples do que em vetores.

```Cpp
struct Node {
	int value;
	int *nextNode;
};

struct LinkedList {
	Node *head;
	Node *tail;
	
	void pushNode(int val) {
		Node *node = new Node;
		node->nextNode = nullptr;
		node->value = val;
		
		if (head == nullptr) {
			head = node;
			tail = node;
		} else {
			tail->nextNode = &node;
			tail = &node;
		}
	}
	
	void removeNode(int val) {
		Node *current = head;
		Node *previous = nullptr;
		
		while (current != nullptr) {
			if (current->value == val) {
				if (previous == nullptr) {
					head = current->next;
				} else if (current->nextNode == nullptr) {
					previous->next = nullptr;
					tail = previous;
				} else {
					previous->next = current->next;
				}
				delete current;
				return 0;
			}
			
			previous = current;
			current = current->next;
		}
	}
};

int main() {
	LinkedList list;
	
	lista.pushNode(1);
	lista.pushNode(2);
	lista.pushNode(3);
	
	lista.removeNode(2);
	lista.removeNode(1);
	lista.removeNode(3);
	
	return 0;
}
```