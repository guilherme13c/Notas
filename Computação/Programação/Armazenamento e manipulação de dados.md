# Hierarquia de memória
 Quanto mais "próxima" da CPU, menor o tempo para acessá-la e maior o seu custo. Então, memória de nível superior ("distante" da CPU), possui mais espaço, mas é mais lenta quando comparada com a memória de nível inferior ("próxima da CPU").

 ### Princípio da localidade
> ###### Temporal
> + Dados ascessados recentemente têm mais chance de serem usados novamente do que dados usados há mais tempo.
> + Manter os dados e instruções usados recentemente no topo da Hirarquia, onde o ascesso é mais veloz.

>  ###### Espacial
> + Probabilidade de ascesso maior para dados e instruções em ***endereços próximos***  àqueles acessados recentemente.
> + Variáveis são armazenadas próximas umas às outras
> + Vetores e matrizes armazenados em sequência

### Memória Virtual
A maior demanda por memória principal levou ao uso de parte da memória secundária para armazenar dados quando a memória principal está cheia.
Tal processo é realizado automaticamente pela Unidade de Gerência de Memória (UGM) presente nos processadores. Assim, todo dado que é acessado é antes buscado pela UGM na memória principal. Se esse dado não estiver lá, a UGM vai buscar na memória secundária. Ao encontrar, faz-se uma cópia do dado na memória principal e libera-se o acesso ao dado.
Tal processo tem impacto no custo de acesso, tornando o acesso ao dado mais lento.

---
# Alocação de Memória

### Segmentos da memória
>##### Código/Globais
>Guarda o código compilado do programa e outras variáveis.

>##### Stack(Pilha)
>Espaço que variáveis dentro de funções são alocadas.

>##### Heap
>Espaço estável (durável) de armazenamento;
>Programa aloca/desaloca porções de memória do heap durante a execução.

#### Stack
>+ Porção contígua/sequencial de memória;
>+ ***LIFO*** (last-in-first-out);
>+ Não é necessário gerenciar manualmente;
>+ Possui limites no seu crescimento (varia de acordo com a linguagem do programa).

#### Heap
>+ Espaço de memória de propósito geral;
>+ Não impõe um padrão de alocação (podendo gerar fragmentação ao longo do tempo);
>+ Gerenciamento ***explícito*** (alocação/desalocação manuais);
>+ "Não" possui um limite de tamanho.

*Pilha* e *Heap* crescem um em direção ao outro. Assim, má alocação por parte do programador pode levar à ocorrência de problemas durante a alocação.

### Tipos de Alocação
#### Estática _$\longrightarrow$ Pilha_
>+ Acesso/Manipulação sem alterar o endereço (variáveis globais);
>+ O espaço de memória para as variáveis é conhecido em ***compile time***, ou seja, durante o desenvolvimento.

#### Dinâmica _$\longrightarrow$ Heap_
Maior controle na manipulação $\rightarrow$ Mais responsabilidade
>+ Armazenamento de grandes quantidades de dados cujo tamanho máximo é desconhecido na implementação (não fixo);
>+ Tamanho pode variar após o início da execução;
>+ Não estão associadas a um escopo específico.

---