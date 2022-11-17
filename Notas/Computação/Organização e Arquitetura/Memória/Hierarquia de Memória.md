# Hierarquia de memória
A [[CPU]] só é capaz de buscar instruções e dados da [[Memória Cache|memória cache]] (SRAM), localizada diretamente no chip do processador. A memória cache deve ser preenchida com dados da memória principal do sistema (DRAM). Entretanto, a memória RAM só retém seu conteúdo enquanto a energia está ligada (memória **volátil**), então precisa ser armazenada de forma mais permanente em outro componente.

| Velocidade  | Tipo  | Descrição                                                                                                                                                                                                                                                                                                                                        |
| ----------- | ----- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Mais rápida | Cache | Memória cache é a memória que é realmente embarcada na CPU, sendo muito rápida, demorando, normalmente, um único ciclo para ser acessada. Contudo, ela é muito pequena pois deve caber dentro da CPU, além de ser muito mais cara por utilizar a tecnologia SRAM.                                                                                |
|             | RAM   | Todas as instruções e endereços de armazenamento que vão para o processador devem vir da memória RAM. Mesmo que a DRAM seja muito veloz, ainda demora um tempo considerável para a CPU acessá-la (esse tempo é chamado **latência**). A RAM é armazenada separadamente, em chips dedicados acoplados à placa-mãe, sendo muito maior que a cache. |
| Mais lenta  | Disco | Estamos familiarizados com os CDROMs e com salvar arquivos em discos rigidos. Sabemos que esses dispositivos têm o acesso muito mais demorado, mas também um preço muito menor, além de uma capacidade maior. Vale ressaltar que mesmo após desligar a energia, os dados se preservam (memória **não-volátil**).                                                                                                                                                                                                                                                                                                                                               |

---
 ### Princípio da localidade
> ###### Temporal
> + Dados ascessados recentemente têm mais chance de serem usados novamente do que dados usados há mais tempo.
> + Manter os dados e instruções usados recentemente no topo da Hirarquia, onde o ascesso é mais veloz.

>  ###### Espacial
> + Probabilidade de ascesso maior para dados e instruções em ***endereços próximos***  àqueles acessados recentemente.
> + Variáveis são armazenadas próximas umas às outras
> + Vetores e matrizes armazenados em sequência

---
### Memória Virtual
A maior demanda por memória principal levou ao uso de parte da memória secundária para armazenar dados quando a memória principal está cheia.
Tal processo é realizado automaticamente pela Unidade de Gerência de Memória (UGM) presente nos processadores. Assim, todo dado que é acessado é antes buscado pela UGM na memória principal. Se esse dado não estiver lá, a UGM vai buscar na memória secundária. Ao encontrar, faz-se uma cópia do dado na memória principal e libera-se o acesso ao dado.
Tal processo tem impacto no custo de acesso, tornando o acesso ao dado mais lento.

---
