[[Princípios Da POO#Herança]][[Introdução a POO|]][[Classes e seus Atributos|]][[Classes e seus Métodos|]][[Objetos e Classes|]]
- É uma técnica para reutilizar características de uma classe na definição de outra classe.
- Determina uma hierarquia de classes.

---

- Classes mais genéricas: **superclasses** (pai)
- Classes especializadas: **subclasses** (filha)

![[Pasted image 20211208101433.png]]

---
# Herança

Os atributos e métodos são herdados por todos os objetos dos níveis mais baixos, considerando o modificador de acesso.

***Obs.:***	Membros _private_ são herdados, mas não são acessíveis pois pertencem somente ao escopo da classe.

Diferentes subclasses podem herdar as características de uma (ou mais) superclasses

---
## Benefícios

Reutilização de código:
- Compartilhar similaridades
- Preservar as diferenças

Facilita a manutenção do código:
- Maior legibilidade do código existente
- Quantidade menor de linhas de código
- Alterações em poucas partes do código

---
## Árvore de Herança
O conjunto de classes que herdam entre si recebe o nome de árvore de herança

Cada subclasse pode possuir:
- Uma única superclasse (_Java_): Herança Simples
- Várias superclasses (_C++_): Herança Múltipla

---
![[Pasted image 20211208102458.png]]

O modificador de acesso usado para declarar a superclasse determina o nível de acesso aos seus membros pela subclasse. Quando a classe é declarada como:

>#### Public
>Mantém os níveis de acesso da classe base

>#### Protected
>Membros Public e Protected $\implies$Protected

>#### Private
>Membros Public e Protected $\implies$Private

---
## Construtores e Destrutores
A classe derivada executa o construtor da classe base ***antes*** de executar o próprio.
- Chamado mesmo que implicitamente
- Pode estar explícito na lista de inicialização

A classe derivada executa o destrutor da classe base ***depois*** de executar o próprio.

---
# Herança Simples
## Sobrescrita de [[Classes e seus Métodos|Métodos]]
Métodos da superclasse podem ser sobrescritos na subclasse (_overriding_). Isso ocorre quando eles possuem a mesma assinatura e tipo de retorno.
Para sobrescrever métodos, devemos declará-los como _[[Herança#Métodos Virtuais|virtuais]]_.

***Obs.:*** Métodos _private_ não são sobrescritiveis. 

Não se pode restringir o acesso na sobrescrição de um método (Princípio de Substituição de Liskov):
- _Public_ $\implies$ _Public_
- _Protected_ $\implies$ _Protected, Public_ 

Atributos não são redefiníveis:
- Se um atributo de mesmo nome for definido na subclasse, a definição na superclasse é _ocultada_.
Membros estáticos não são redefinidos:
- Se um membro estático de mesmo nome for definido na subclasse, a definição na superclasse é _ocultada_.
- Como o acesso é feito pelo nome da classe, estar ou não _ocultado_ faz pouca diferença.

#### Métodos Virtuais
São resolvidos dinamicamente, isto é, apenas em tempo de execução sabemos exatamente qual função será chamada.

O comportamento base de uma classe pode ser sobrescrito em classes derivadas.

```Cpp
class Pessoa {
	public:
		virtual void meuNome() {
			cout << "Meu nome é PESSOA." << endl;
		}
};

class Estudante : public Pessoa {
	public:
		void meuNome() override {
			cout << "Meu nome é ESTUDANTE." << endl;
		}
};
```
---
# Herança Múltipla
Subclasse herda de mais de uma superclasse. 

***Obs.:*** Nem todas as linguagens permitem isso!

Problemas:
- Dificulta a manutenção do sistema
- Também dificulta o entendimento
- Reduz a modularização
- Pode gerar ambiguidade

```Cpp
class Animal {

};

class Herbivoro : public Animal {

};

class Carnivoro : public Animal {

};

class Onivoro : public Herbivoro, public Carnivoro {

};
```

## Críticas
Fere o [[Princípios Da POO#Encapsulamento|princípio do encapsulamento]]:
- Membros fazem parte de várias classes

Cria interdpendência entre classes:
- Mudanças em superclasses podem ser difíceis

Como resolver isso?
- Composição: técnica para criar um novo tipo não pela derivação, mas pela junção de outras classes de menor complexidade

---
# Composição x Herança
## Princípio da Abertura-Fechamento
- Aberto para extensão
	- Novos Campos
	- Novas operações
	- Novas invariantes
- Fechado para uso
	- Interface
	- Pré-condições
	- Pós-condições
	- Compilable

---