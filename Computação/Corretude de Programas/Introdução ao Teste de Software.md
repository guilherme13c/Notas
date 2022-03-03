[[Depuração de software|]]
# Teste de Unidade
Verificam a corretude de unidades individuais do sistema.
É um trecho de código que executa outro trecho de código para verificar o seu comportamento.

O objetivo é isolar cada parte do programa e mostrar que as partes individuais estão funcionando corretamente.

Um caso de teste avalia uma propriedade específica do módulo testado.

Testes de unidade devem:
- Testar uma única unidade
- Ser curtos e executar rapidamente
- Funcionar de forma independente de outros testes
- Testar a maioria das funções públicas
- Lidar com casos triviais e extremos
- Cobrir os principais caminhos das funções

Permitem que alterações sucessivas no código sejam validadas imediatamente.

É um contrato rigoroso que dita o que o pedaço de código testado deve fazer.

Facilitam a implementação dos testes de integração.

## Frameworks de Teste de Unidade
Permitem que iniciantes escrevam testes facilmente e rapidamente e que programadores seniores escrevam testes não triviais.

Frameworks (C++):
- Doctest
- Catch2
- GoogleTest

## Fases de um Teste de Unidade Não Trivial
- Inicialização (_setup_)
- Execução (_exercise_)
- Verificação (_verify_)
- Finalização (_teardown_)

## Cobertura de Código
- Medida da porcentagem do código que foi executada durante os testes
$$\mbox{linhas executadas durante os testes}\over\mbox{total de linhas do programa}$$
- Quanto maior a cobertura, menor a chance de erros não detectados.
- Bons testes cobrem grande parte dos fluxos possíveis de execução.

## Test Driven Development (_TDD_)
![[Pasted image 20220205131053.png]]


---
# Teste de Integração
É a fase do teste de software em que módulos são combinados e testados em grupo.

---
# Testes de Sistema
Avaliam propriedades do sistema como um todo.

Englobam vários tipos de testes:
- Teste de segurança
- Teste de desempenho
- Teste de escalabilidade
- Entre outros

---
# Testes de Aceitação
Verificam se o sistema atende a sua especificação e às necessidades do usuário.

---
