# Processos e Threads

- *Thread*: fluxo de controle de instruções;
- [[Processos|Processo]]: espaço de [[Hierarquia de Memória|memória]] e recursos alocados a ele associados;
- Se um processo tem mais de uma thread, elas compartilham quase todos os recursos e memória, com exceção apenas para o que identifica cada *thread*:
	- contador de programa;
	- registradores;
	- pilha de execução.

![[Pasted image 20231006093201.png]]

---

## Vantagens do multi-threading

- Maior capacidade de resposta;
- Compartilhamento de recursos;
- Economia quando comparado com multi-processos;
- Facilidade de expressão;
- Aproveitamento de [[CPU|arquiteturas]] multiprocessadas (multi-core, *hyperthreading*).

---

# Threads de usuário x kernel

- Implementações com compromissos diferentes;
- *Threads* no nível de usuário (bibliotecas):
	- mais leves, pois o *overhead* se limita ao programa;
	- se o kernel não reconhece, pode ser ineficiente.
- *Threads* de kernel:
	- melhor integradas ao escalonador do S.O.;
	- mais *overhead*.
- Mapeamento entre os dois níveis varia entre sistemas e tem compromissos diferentes.

---

## Mapeamento muitos-para-um

- Muitas *threads* de usuário mapeadas para uma única *thread* de kernel:
	- Ocorre, p.ex., quanto o S.O. não reconhece threads, apenas processos;
- Se uma thread faz uma chamada do S.O. bloqueante, todo o processo é suspenso:
	- mesmo que outras *threads* pudessem executar;
	- Para evitar isso, bibliotecas precisam transformar chamadas bloqueantes em não bloqueantes.

---

## Mapeamento um-para-um

- Kernel reconhece *threads* e cada *thread* de usuário é na verdade uma *thread* de kernel;
- Mapeamento é simples, mas "pesado":
	- toda troca de *threads* envolve mudança para modo protegido.

---


