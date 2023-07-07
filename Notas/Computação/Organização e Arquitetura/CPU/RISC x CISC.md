## RISC x CISC
### CISC
#### Complex Instruction Set Computer

- Conjunto de instruções alargado
- Instruções complexas
- Instruções altamente especializadas
- Existência de vários formatos de instruções
- Suporte de vários modos de endereçamento
- Suporte para operandos em memória
- Baseado na [[#microprogramação]]
##### Exemplos
- Intel 80x86
- Motorola 680x0

---
#### CISC - Microprogramação

![[Pasted image 20230616165546.png]]

1. Cada instrução [[#CISC]] decodificada em: instrução de máquina, tipo de endereçamento e endereços, registradores.
2. Envio de instruções pequenas (microcódigo) para o Nano-processador (processador no processador).
3. Execução.
- Execução de uma instrução [[#CISC]] demora vários ciclos de clock.

---
#### CISC - Vantages
- Programação de código de máquina mais fácil.
- Código executável pequeno => menor necessidade de memória. 
- Instruções memória-memória (carrega e armazena dados com a mesma instrução) => menor necessidade de registradores.

---
#### CISC - Desvantagnes

• Aumento de complexidade de processadores novos por causa da inclusão das instruções velhas.
• Muitas instruções especiais - menos usadas.
• Execução de varias instruções complexas mais lenta do que execução de uma sequencia equivalente.
• Alta complexidade.
- Pipelining muito difícil => frequência de clock reduzido.
• Tratamento de eventos externos (Interrupts) mais difícil.
• Execução de instruções simples demora mais do que necessário.

---
#### CISC - Conclusão

Ótimo para os primeiros computadores, quando a memória e os registradores eram caros, mas é menos aplicável aos computadores atuais, pois a memória é barata e nossa preferência passou a ser velocidade.

---
### RISC
#### Reduced Instruction Set Computer

• Menor quantidade de instruções
• Instruções mais simples
• Largura fixa de cada instrução
• Cada instrução demora um ciclo de clock (ou menos)
##### Exemplos:
- MIPS
- SPARC
- Apple iPhone (Samsung ARM1176JZF)
- Processadores novos da Intel (parcialmente)

---
#### RISC - Vantagens

• Menos transistores (área) para implementar lógica
• Instruções para acesso à memória (armazenar e
carregar dados) são separados
• Complexidade baixa
• Menos sujeito às falhas
• Tempo de decodificação reduzido

---
#### RISC – Desvantagens

• Mais registradores necessários
• Compilação de código de máquina mais
complicado
• Código mais complexo / maior

---
### RISC x CISC

#### CISC
• Redução do número de instruções por programa
• Aumento do número de ciclos por instrução

#### RISC
• Redução do número de ciclos por instrução
• Aumento de número de instruções por programa

---
