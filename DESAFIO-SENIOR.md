
# Aquela calculadora REST!
Implementar (de sua autoria) uma calculadora de expressões que receberá as
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
- Colocar Swagger para documentação da API

## Segurança

Usar Token Header com Spring Security para segurança da API que deve
validar o token em todas as chamadas da API. Dessa forma, somente quem possuir tal
token poderá usar a API.

## Armazenamento

Usar banco H2 em memória para testes e produção
Usar Spring Data para manipular os dados


## Testes automatizados

Usar spring test para validar os cenários abaixo. (Usar JUnit e Spring Test)

- Cenário 1 - Dados que: foi enviada a expressão "(2+2)*3". Ao executar a chamada na API
Deve: Retornar o valor "12"

- Cenário 2 - Dados que foi enviada a expressão: "2.2+2.2". Ao executar a chamada na API com esse mesmo parâmetro 2 vezes.
Deve retornar "4.4" em ambas as chamadas e ter usado o resultado previamente gravado no banco na segunda chamada.

- Cenário 3 - Dados que: foi enviada a expressão "2.3*2.3+5". Ao executar a chamada na API
Deve retornar o valor "10.29"

- Cenário 4 - Dados que: foi enviada a expressão "2.33/3". Ao executar a chamada na API
Deve retornar o valor "0.78" (round up)

- Cenário 5 - Dados que: foi enviada a expressão "1/0". Ao executar a chamada na API
Deve retornar um erro HTTP 40X notificando sobre o erro de cálculo
 
- Cenário 6 - Dados que: foi enviada a expressão "((2*2)+(6*3))/2". Ao executar a chamada na API
Deve: Retornar o valor "11"

 
 ## DEPLOY e CI
 
 A calculadora deve ser implantanda em um ambiente AWS ou GCP. Deev ser implementado build e deploy automáticos a cada commit usando GITHUB ACTIONS. Esse deploy deve ser feito automaticamente.
 
**Caso julgue necessário, sinta-se à vontade para implementar outros
cenários.
O prazo para conclusão ideal é de 7 dias corridos a partir da data de envio do
desafio. Os resultados deverão estar em um repositório privado do Git Hub, dar permissão de acesso para os usuários "uetanabaro" e "AndreiBubolz". Envie o link enviado por mensagem. Enviar também o link da calculadora publicada na AWS||GCP juntamente com o link do Swagger da API**
