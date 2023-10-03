Um sistema operacional é um programa que realiza a interface entre o hardware e o usuário, fazendo a gestão dos recursos e apresentando eles de forma mais simples e compreensível para os usuários.
Entre as responsabilidades do sistema operacional, estão o gerenciamento de [[Hierarquia de Memória|memória]][[Memória Cache|]], de privilégios, dos dispositivos (mouse, teclado, monitor, etc.), o sistema de arquivos e o sistema de processos.

---

# Estrutura do S.O.

No passado, os sistemas operacionais eram escritos em um único programa, usando linguagem de máquina. Contudo, o aumento da complexidade levou ao uso de linguagens de mais alto nível. Isso resultou em implementações mais rápidas e legíveis, além do ganho de portabilidade e otimização com os compiladores modernos. Outra característica que mudou foi a organização interna da implementação, introduzindo as estruturas em:
- [[#Enfoque em camadas|Camadas]];
- [[#Enfoque em módulos|Módulos]];
- [[#Estrutura em micro-kernel|Micro-kernel]]; e
- [[#Máquinas Virtuais]].

---
## Enfoque em camadas

- O S.O. é dividido em níveis, sendo cada nível construído sobre os inferiores, e o nível 0 sendo o hardware;
- A modularidade torna cada nível mais fácil de construir, pois pode usar as funções dos níveis inferiores;
- Existe uma dificuldade em se definir apropriadamente cada camada;
- Pode inserir overhead (custo adicional) quando uma operação usar muitas camadas.
![[Pasted image 20231003192837.png]]![[Pasted image 20231003192914.png]]
###### Exemplo:
- [MS-DOS](https://en.wikipedia.org/wiki/MS-DOS)
- [Unix](https://en.wikipedia.org/wiki/Unix)

---
## Estrutura em micro-kernel

- Sistemas complexos com muitas funcionalidades dentro do kernel;
- Manter o menor kernel possível e mover o resto para o espaço do usuário;
- Tarefas executadas por [[Processos|processos]] que trocam mensagens entre si;
- Menos código em modo protegido;
- Mais fácil de estender;
- Custo de comunicação por meio do espaço do kernel.
![[Pasted image 20231003193322.png]]
###### Exemplo:
- [Mach](https://en.wikipedia.org/wiki/Mach_(kernel))

---
## Enfoque em módulos

- Organização comum da maioria dos S.O. atuais;
- Kernel não é exatamente monolítico;
- Enfoque [[Introdução a POO|orientado a objetos]];
- Cada componente básico separado;
- Cada um conversa com os demais por interfaces bem definidas;
- Módulos podem ser carregados sobre demanda.
![[Pasted image 20231003193412.png]]
###### Exemplo:
- [Solaris](https://en.wikipedia.org/wiki/Oracle_Solaris)

---
## Máquinas Virtuais

- Extensão do [[#Enfoque em camadas|enfoque em camadas]] e [[#Estrutura em micro-kernel|micro-kernel]];
- Um S.O. pode ser colocado sobre uma outra camada que o separa do hardware;
- Uma máquina virtual é uma abstração;
- O nível de abstração pode variar;
- Diversos S.O. podem executar de forma protegida uns dos outros;
![[Pasted image 20231003193444.png]]
###### Exemplos:
- [IBM mainframes](https://en.wikipedia.org/wiki/IBM_mainframe)

---
