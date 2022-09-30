# IES_103645

Lab 1:

1.2 - c) 
Nota: “-D” é utilizado para definir uma propriedade para o Maven no CLI.

Maven Archetype: funciona, basicamente, como um template de um projeto que possibilita desenvolver novos projetos de forma mais rápida baseando-se numa base de arquivos, xmls e classes já existentes.

groupId: este elemento indica o identificador exclusivo da organização ou grupo que criou o projeto.

artifactId: nome do ficheiro .jar sem versão.

REVIEW QUESTIONS:

A) Maven has three lifecycles: clean, site and default. Explain the main phases in the default lifecycle.

R:  Validar-> validar se o projeto está correto e todas as informações necessárias estão disponíveis.

    Compilar-> compilar o código fonte do projeto.

    Teste-> testar o código-fonte compilado usando uma estrutura de teste de unidade adequada. Esses testes não devem exigir que o código seja empacotado ou implantado.

    Package-> empacotar o código compilado em seu formato distribuível, como um JAR.

    Verificar-> executar verificações nos resultados dos testes de integração para garantir que os critérios de qualidade sejam atendidos.

    Instalar-> instalar o pacote no repositório local, para usar como dependência em outros projetos localmente

    Deploy-> feito no ambiente de compilação, copia o pacote final para o repositório remoto para compartilhar com outros desenvolvedores e projetos.

B) Maven is a build tool; is it appropriate to run your project to?

R: Sim. O objetivo principal do Maven é configurar projetos e lidar com as atividades de construção e artefatos resultantes, mas também pode ativar diferentes plugins que podem ser usados ​​para executar classes específicas.

C) What wouldbe a likely sequence of Git commands required to contribute with a new feature to a given project? (i.e., get a fresh copy, develop some increment, post back the added functionality)

R:  git pull - Para obter as alterações mais recentes do código

    git add . - Para adicionar os arquivos que queremos atualizar. Parâmetro "." significa que estamos a selecionar tudo do repositório.

    git commit -m "Lab01 completed" - Para confirmar as alterações feitas. Requer o parâmetro -m seguido por uma mensagem de confirmação.

    git push - Para atualizar o repositório com as alterações confirmadas anteriormente.

D) There are strong opinions on how to write Git commitmessages... Find some best practices online and give your own informed recommendationson how to write good commit messages(in a teamproject).

R:  As mensagens de commit são importantes porque nos dão uma ideia generalizada do que está a acontecer no código atual e o que foi atualizado ou removido, para que outros colaboradores do projeto possam estar bem informados acerca das alterações. Uma mensagem "git commit" bem elaborada é a melhor maneira de comunicar o contexto sobre uma mudança para outros desenvolvedores.

    Algumas regras:
    1. Separar o assunto do corpo com uma "blank line"
    2. Limitar o assunto a 50 caracteres
    3. Capitalizar a linha de assunto
    4. Não terminar a linha de assunto com um ponto
    5. Usar o modo imperativo na linha de assunto
    6. Usar o corpo para explicar o que é e porquê vs como

E) Docker automatically prepares the required volume space as you start a container. Why is it important that you take an extra step configuring the volumes for a (production) database?

R: Os volumes ajudam a dissociar a configuração do Docker host do tempo de execução do container. Quando desejamos armazenar os dados do container em um host remoto ou numa cloud, em vez de localmente ou quando precisamos de fazer backup, restaurar ou migrar dados de um Docker host para outro, os volumes são a melhor opção.
Recursos dedicados tornam os dados mais seguros contra problemas, como exclusão de container, e também é mais fácil fazer backup de bancos de dados de produção.