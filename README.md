
# Aquela calculadora REST!
Implementar (de sua autoria o algorítmo de cálculo. Sem uso de componentes nessa parte) uma calculadora de expressões que receberá as
expressões via REST API e efetuará os cálculos. Salvar as expressões enviadas e os
resultados obtidos no banco de dados H2. Quando uma mesma consulta for enviada,
usar o resultado já calculado previamente.

Payload de envio deve ser : { "expressao": "<expr>"}
 
 Ex: { "expressao": "2+2-1" }

 Deve receber o retorno no formato usando a precisão de 2 dígitos após a
vírgula: 

Ex: { "resultado": 3.00}

Deve suportar as operações "+" (adição), "-"(subtração), "*" (multiplicação) e "/"
divisão.
Use boas práticas de programação e lembre-se de se divertir! 

## Ambiente

- Java 11+;
- Spring Boot 2+
- Gradle ou Maven
- Commit do projeto no github

## Segurança

Usar Token Header com Spring Security para segurança da API que deve
validar o token em todas as chamadas da API. Dessa forma, somente quem possuir tal
token poderá usar a API.

## Armazenamento

Usar banco H2 em memória
Usar Spring Data

## Testes automatizados

Usar spring test para validar os cenários abaixo. (Usar JUnit e Spring Test)

- Cenário 1 - Dados que: foi enviada a expressão "2+2". Ao executar a chamada na API
Deve: Retornar o valor "4"

- Cenário 2 - Dados que foi enviada a expressão: "2.2+2.2". Ao executar a chamada na API com esse mesmo parâmetro 2 vezes.
Deve retornar "4.4" em ambas as chamadas e ter usado o resultado previamente gravado no banco na segunda chamada.

- Cenário 3 - Dados que: foi enviada a expressão "2.3*2.3+5". Ao executar a chamada na API
Deve retornar o valor "10.29"

- Cenário 4 - Dados que: foi enviada a expressão "2.33/3". Ao executar a chamada na API
Deve retornar o valor "0.78" (round up)

- Cenário 5 - Dados que: foi enviada a expressão "1/0". Ao executar a chamada na API
Deve retornar um erro HTTP 40X notificando sobre o erro de cálculo


---

1. Esta etapa é importante para podermos entender qual o seu nível técnico, validar a aderência aos requisitos e também para definir qual a sua faixa de senioridade.
2. O resultado do desafio será utilizado somente para o processo seletivo, não utilizaremos seu código para o Nex. 
3. As únicas pessoas que terão acesso ao seu desafio são a recrutadora, gestão e equipe de Backoffice. 
4. O prazo de entrega é definido por você após avaliar o escopo do desafio.
