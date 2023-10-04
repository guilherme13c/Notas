#### DEFINIÇÃO
Um processo pode ser visto como um programa em execução, ou seja, um fluxo de controle de execução de [[caminho de dados|instruções]].

---
## Bloco de Controle de Processo (PCB)

Estrutura que armazena as informações associadas a cada processo:
- [[#Diagrama de estados de processo|Estado do processo]];
	- Novo: acabou de ser criado;
	- Executando: CPU está executando as instruções;
	- Em espera: aguardando algum evento;
	- Pronto: esperando pela CPU; ou
	- Terminado: completou a execução;
- Contador de Programa;
- Conteúdo dos registradores da CPU;
- Informações de escalonamento da CPU;
- Informações da gerência de memória;
- Informações de contabilidade;
- Informações sobre estado de eventos de entrada e saída.

![[Pasted image 20231004082254.png]]

---

## Etapas de um processo

- [[#Criação de processos|Criação]]:
	- Inicialização do [[#Bloco de Controle de Processo (PCB)|PCB]];
	- Definição de imagem na [[Hierarquia de Memória|memória]].
- Execução:
	- Escalonamento pelo núcleo;
	- Comunicação entre processos;
	- Acesso a dispositivos.
- Terminação:
	- Liberação de recursos.

![[Pasted image 20231004082918.png]]

---

### Criação de processos

Um processo (pai) cria outros (filhos), que por sua vez podem criar ainda outros:
- Estabelece uma [[Árvores|árvore]] de processos;
- Filhos podem ser cópias do processo pai ou derivados de outros programas;
- Diversos níveis de compartilhamento são possíveis entre níveis da árvore (pais e filhos);
- Execução de pais e filhos pode ser concorrente ou pais podem esperar pelos filhos.

###### Exemplo:
- Unix:
![[Pasted image 20231004083708.png]]

---

### Terminação de processos

Ao terminar seu processamento, processo pede ao S.O. para retirá-lo do sistema:
- O pedido pode ser bem comportado ou causado por erros de execução;
- O processo criador (pai) é informado de seu fim;
- Os recursos são liberados pelo S.O.

---

## Diagrama de estados de processo

![[Pasted image 20231004084239.png]]

---

# Escalonamento de processos

- Aumentar a utilização do processador;
- Paralelismo aparente e transparente;
- O S.O. decide quem, quando e como.

![[Pasted image 20231004085336.png]]

---
 
## Filas de escalonamento

- Fila de jobs (conjunto de todos os processos):
	- Sistemas batch.
- Fila de processos prontos (todos os processos presentes em memória, prontos e esperando pela CPU):
	- Podem haver diferentes filas de prontos, com níveis de prioridades diferentes.
- Filas de dispositivos (processos aguardando pela resposta de um dispositivo de E/S).

---

## Escalonadores

- Escalonadores de longo prazo (de jobs):
	- Seleciona os processos a serem inseridos na fila de prontos (entrar no sistema);
	- Importante em sistemas compartilhados.
- Escalonadores de curto prazo (de CPU):
	- Seleciona o processo a receber a CPU a cada instante.
- Escalonamento de médio prazo:
	- Alguns sistemas podem retirar processos da fila de prontos temporariamente.
##### Obs.:
Processos podem ser descritos como:
- I/O bound (intensivos em E/S):
	- Passa mais tempo esperando por E/S que computando;
	- Muitas rajadas curtas de processamento.
- CPU bound (intensivos em processamento):
	- Passa mais tempo em processamento;
	- Períodos longos de processamento, na CPU.

---

## Troca/chaveamento de contexto (context switch)

- Mudança do processo em execução;
- O S.O. deve salvar o estado do processo atual e carregar o estado do novo;
- É um overhead;
- Tempo gasto depende da estrutura do hardware e do processo no S.O.

![[Pasted image 20231004093642.png]]

---

# Cooperação entre processos

- Processos independentes não podem afetar ou ser afetados pela execução de outros;
- Vantagens da cooperação entre processos:
	- Compartilhamento de informações;
	- Aumento da velocidade de processamento;
	- Modularidade
	- Conveniência

---

## Comunicação entre processos (IPC)

A troca de informações entre dois fluxos de execução (duas regiões de memória) pode ocorrer por meio de:
- Memória compartilhada (**shmem**):
	- Dois fluxos "enxergam" a mesma memória;
	- Primitivas são dependentes do tipo de S.O.
	- Princípios são os mesmos aplicados às *[[|threads]]*
- Troca de mensagens (**send/receive**):
	- Toda informação tem que fluir de um processo para outro;
	- Canais de comunicação podem ter diversas semânticas;
	- Exemplo mais importante: *sockets* (Redes)

![[Pasted image 20231004095234.png]]

### Decisões de implementação

- Como os canais são criados/estabelecidos?
- Quem é o destinatário: um processo ou um buffer?
- Um canal pode ligar mais de dois processos?
- Quantos canais podem ligar um mesmo par?
- Qual a capacidade do canal?
- As mensagens são de tamanho fixo ou variável?
- Cada canal é uni- ou bi-direcional?
- Qual o comportamento de send/receive se:
	- o canal está cheio, ou
	- as chamadas não ocorrem ao mesmo tempo?

---

#### Comunicação direta

- Processos identificam o outro explicitamente:
	- *send(P, msg)*: envia mensagem para o processo *P*;
	- *receive(Q, msg)*: recebe mensagem do processo *Q*.
		- recepção pode usar máscara (e.g.: *Q=any*).
- Propriedades de canal de comunicação direta:
	- Estabelecimento é automático;
	- Cada canal liga exatamente um par de processos;
	- Existe apenas um canal entre cada par;
	- Canais são usualmente bi-direcionais.

---

#### Comunicação indireta

- Mensagens são originadas e direcionadas para caixas de correio (ports = portas/portos)
	- Cada caixa tem um identificador único;
	- Processos só se comunicam se compartilharem uma caixa de correio;
	- Caixas de correio são recursos independentes que precisam ser criados e destruídos.
- Propriedades dos canais:
	- Estabelecimento vinculado ao compartilhamento;
	- Um canal pode ligar vários processos;
	- Cada par de processos pode ter vários canais;
	- Canais podem ser uni- ou bi-direcionais.

---

#### Sincronização de primitivas

- Troca de mensagens:
	- Bloqueante (síncrona)
	- Não bloqueante (assíncrona)
- Cada primitiva (*send*/*receive*) pode se comportar de uma forma. O mais comum é:
	- *send* assíncrono (retorna imediatamente);
	- *receive* síncrono (bloqueia até a mensagem chegar).

---

#### Controle de espaço no canal

- Implementação da fila de mensagens associadas a um canal enquanto em transito:
	- Capacidade zero: o canal não guarda mensagens, o transmissor deve fazê-lo, esperando pelo receptor (*rendezvous*);
	- Capacidade limitada: *send* é assíncrono enquanto a capacidade não é alcançada;
	- Capacidade ilimitada: *send* nunca espera.

---
