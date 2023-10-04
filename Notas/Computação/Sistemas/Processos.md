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
