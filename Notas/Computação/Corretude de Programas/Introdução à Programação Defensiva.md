[[Depuração de software|]]
# Programação Defensiva
Queremos evitar errors de execução apesar de ações incorretas dos usuários e das condições adversas de execução.

## Filosofias de Programação Defensiva
- Garbage in, nothing out
- Garbage in, error message out
- No garbage allowed

---
## Princípio da Robustez
Consiste em sempre tentar fazer algo que permita que o software continue operando mesmo que isso algumas vezes leve a resultados imprecisos.

## Princípio da Corretude
Consiste em nunca retornar um resultado impreciso. Não retornar nenhum resultado é melhor do que retornar um resultado incorreto.

---
## Estratégias de Programação Defensiva
- [[#Validação de Entradas]]
- [[#Barricadas]]
- [[#Asserções]]
- [[#Tratamento de Exceções]]

### Validação de Entradas
Interceptar as entradas e avaliá-las antes de executar a funcionalidade.

### Barricadas
- Minimizam o dano causado por dados incorretos
- Verificam os dados que cruzam os limites de áreas seguras
- Centralizam a verificação de dados

### Asserções
São instruções inseridas no código para certificar que determinada condição é verdadeira.

Uma expressão booleana que deve set verdadeira. O programa é interrompido e apresenta uma mensagem de error caso a expressão seja falsa.

### Tratamento de Exceções
Uma exceção é uma situação excepcional que requer uma ação específica e imediata.

---