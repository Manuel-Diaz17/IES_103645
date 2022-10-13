# IES_103645 - Lab2

REVIEW QUESTIONS:

A) What are the responsibilities/services of a “servlet container”?

Um servlet container gerencia e é responsável pelo ciclo de vida dos servlets e mapeia a URL para um servlet específico para garantir que quem o solicita tenha os direitos de acesso corretos.

B) Explain, in brief, the “dynamics” of Model-View-Controller approach used in Spring Boot to serve web content. (You may exemplify with the context of the previous exercises.)

O Spring Boot utiliza o padrão MVC, no qual a aplicação é dividida em 3 componentes:

Model: middleware entre o Controller e a View, que é controlado e atualizado pelo Controller.
Controller: quando é feito um HTTP request, ele recebe-o e processa-o.
View: componente que permite ao utilizador ver o request processado.

C) Inspect the POM.xml for the previous SpringBoot projects. What is the role of the “starters” dependencies?

Ele fornece todas as dependências padrão para que possamos executar o aplicativo Spring Boot sem adicionar outras dependências.

D) Which annotations are transitively included in the @SpringBootApplication?

@EnableAutoConfiguration, @ComponentScan and @Configuration

E) Search online for the topic “Best practices for REST APIdesign”. From what you could learn, select your “top 5”practices,and briefly explain them in you own words.

Usar Logical Nesting em endpoints:

    Ao projetar endpoints, faz sentido agrupar aqueles que contêm informações associadas. Ou seja, se um objeto pode conter outro objeto, devemos projetar o ponto de extremidade para refletir isso.

Lidar com erros de maneira elegante e retornar códigos de erro padrão:

    Para evitar criar confusão nos utilizadores da API quando um erro ocorre, devemos lidar com os erros de maneira adequada e retornar códigos de resposta HTTP que indicam que tipo de erro ocorreu. Isso fornece aos mantenedores da API informações suficientes para entender o problema que ocorreu.

Manter boas práticas de segurança:

    A maior parte da comunicação entre cliente e servidor deve ser privada, pois muitas vezes enviamos e recebemos informações privadas. Portanto, usar SSL/TLS para uma maior segurança é obrigatório.

Utilizar versões diferentes nas nossas APIs:

    Devemos ter versões diferentes da API, se estivermos a fazer alterações que possam quebrar a comunicação com os clientes.

Cache de dados para melhorar o desempenho:

    Podemos adicionar uma cache para retornar dados da cache de memória local em vez de consultar o banco de dados todas as vezes que quisermos recuperar alguns dados solicitados pelos utilizadores.