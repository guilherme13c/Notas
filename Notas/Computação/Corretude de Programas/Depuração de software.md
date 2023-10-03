- Verificação e Validação: Estabelecimento da existência de falhas (errors) em um programa.
- Depuração (Debugging): Relacionado à localização e reparação de falhas.

---
## Quando ocorrem os errors
- Tempo de **_compilação_**.
- Tempo de **_ligação_**.
- Tempo de **_execução_**.

---
## Tipos de Errors
- Errors de **_sintaxe_**: quando a sintaxe de linguagem não está sendo respeitada.
- Errors de **_semântica_**: quando alguma declaração é usada/realizada de forma indevida.
- Errors de **_lógica_**: manifestam-se em tempo de execução. Esses errors normalmente são imprevisíveis, só ocorrem com entradas específicas e são dependentes da plataforma ou do software.

---
# Depuração de Software

Depuração é a técnica que possibilita manipular a execução do programa de diversas formas e verificar o estado atual do sistema.

> #### Passos para depurar o código
> 1. Reproduzir o problema: Determinar as condições e Estabilizar a execução
> 2. Identificar o local e provável causa: Observar o comportamento, Conceber uma hipótese e Executar um experimento
> 3. Corrigir o error: Considerar a real razão do problema
> 4. Validar a solução: Cuidado com possíveis efeitos colaterais!
---
## Ferramentas de depuração
- GNU Debugger (_**GDB**_): Utilizar a flag de compilação **_-g_**.
- **_Valgrid_** para encontar errors de alocação de memória.

---