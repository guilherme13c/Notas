# Ponteiros e alocação
Ponteiros são variáveis que armazenam endereços de [[Armazenamento e manipulação de dados|memória]], ou seja, _"apontam"_ para outras variáveis.
> ***Obs.:*** Endereços de [[Armazenamento e manipulação de dados|memória]] normalmente são descritos por números em [[Bases Numéricas|hexadecimal(base 16)]]

Ponteiros são armazenados na [[Armazenamento e manipulação de dados#Stack|Pilha]] e normalmente apontam para endereços na [[Armazenamento e manipulação de dados#Heap|Heap]], mas podem também apontar para endereços na [[Armazenamento e manipulação de dados#Stack|Pilha]].

$$\text{Pilha} \longrightarrow \text{Heap}$$
$$\text{ou}$$
$$\text{Pilha} \longrightarrow \text{Pilha}$$
---
# Operadores em C/C++ [[Armazenamento e manipulação de dados#Dinâmica _ longrightarrow Heap_|(Link)]]
> #### Referência ***&***
> & `var` $\longrightarrow$ Endereço de memória da variável `var`.

> #### Deferência ***\* ***
> \* `var` $\longrightarrow$ Conteúdo do endereço apontado por `var`.

---
## Ponteiro para Ponteiro
Nada mais é do que um ponteiro que aponte para um espaço de [[Armazenamento e manipulação de dados|memória]] referente a outro ponteiro, e.g.:

```C
int main() {
	int *p1, **p2, x=1;
	
	p1 = &x;
	p2 = &p1;
	
	return 0;
}
```

Enquanto `p2` aponta para o endereço de `p1`, `p1` aponta para o endereço de `x`, ou seja: $$\text{p2}\rightarrow\text{p1}\rightarrow\text{\&x}$$

---
## C
> Alocação: **malloc**
> Realocação: **realloc**
> Liberação: **free**

~~~C
int main() {
	char *str;
	
	str = (char *) malloc(10);
	
	strcpy(str, "Exemple");
	printf("%s", str);
	
	str = (char *) realloc(str, 25);
	
	strcat(str, ": Hello World");
	printf("%s", str);
	
	free(str);
	
	return 0;
}
~~~
---
## C++
> Alocação: **new**
> Liberação: **delete**

Exemplo em C++:
~~~Cpp
int main() {
	int *a = nullptr;
	int b = 10;
	
	a = new int;
	
	a = &b;
	cout << a << *a << endl;
	
	*a = 20;
	cout << a << *a << endl;
	
	delete a;
	
	return 0;
}
~~~
ou para vetores:
~~~Cpp
int main() {
	int *p = new int[10];

	p[0] = 99;
	
	delete[] p;
	
	return 0;
}
~~~
---
## Ponteiros para estruturas (structs)
```Cpp
int main() {
	struct data {
		int dia;
		int mes;
		int ano;
	};
	
	struct data d1;
	struct data *ptr = &d1;
	int i = 0;
	
	cout << d1.dia << d1.mes << d1.ano << endl;
	cout << ptr->dia << ptr->mes << ptr->ano << andl;
	
	return 0;
}
```
---
## Passagem de parâmetros
> #### Valor
> + ***Parâmetro formal*** (recebido na função) é uma ***cópia*** do ***parâmetro real*** (passado na chamada).
> + Variáveis são completamente independentes.

> #### Referência
> ***Parâmetro formal*** (recebido na função) é uma ***referência*** ao ***parâmetro real*** (passado na chamada).
> + Modificações refletem no parâmetro real.
