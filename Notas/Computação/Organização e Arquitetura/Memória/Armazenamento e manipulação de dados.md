# Alocação de [[Hierarquia de Memória|Memória]]

### Segmentos da memória
> ##### Código/Globais
> Guarda o código compilado do programa e outras variáveis.

> ##### Stack(Pilha)
> Espaço que variáveis dentro de funções são alocadas.

> ##### Heap
> Espaço estável (durável) de armazenamento;
> Programa aloca/desaloca porções de memória do heap durante a execução.

#### Stack
> + Porção contígua/sequential de memória;
> + ***LIFO*** (last-in-first-out);
> + Não é necessário gerenciar manualmente;
> + Possui limites no seu crescimento (varia de acordo com a linguagem do programa).

#### Heap
> + Espaço de memória de propósito geral;
> + Não impõe um padrão de alocação (podendo gerar fragmentação ao longo do tempo);
> + Gerenciamento ***explícito*** (alocação/desalocação manuais);
> + "Não" possui um limit de tamanho.

*Pilha* e *Heap* crescem um em direção ao outro. Assim, má alocação por parte do programador pode levar à ocorrência de problemas durante a alocação.

### Tipos de Alocação
#### Estática _$\longrightarrow$ Pilha_
> + Acesso/Manipulação sem alterar o endereço (variáveis globais);
> + O espaço de memória para as variáveis é conhecido em ***compile time***, ou seja, durante o desenvolvimento.

#### Dinâmica _$\longrightarrow$ Heap_
Maior controle na manipulação $\rightarrow$ Mais responsabilidade
> + Armazenamento de grandes quantidades de dados cujo tamanho máximo é desconhecido na implementação (não fixo);
> + Tamanho pode variar após o início da execução;
> + Não estão associadas a um escopo específico.

---