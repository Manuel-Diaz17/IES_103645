# IES_103645 - Lab3

3.1 - Alínea b)

- The “UserController” class gets an instance of “userRepository” through its constructor; how is this new repository instantiated?
    O "UserRepository" é inicializado porque o "UserController" tem a anotação @Autowired, que injeta uma instância de "UserRepository" no objeto "UserController".

- List the methods invoked in the “userRepository” object by the “UserController”. Where are these methods defined?
    Os métodos invocados são os segyintes: findAll(), save(), findById() e delete(). Estes são definidos na classe "CrudRepository", que o nosso repositório extende.

- Where is the data being saved?
    Os dados são guardados através do h2database, que adicionamos ao projeto como uma dependência. Por padrão, é um banco de dados na memória.

- Where is the rule for the “not empty” email address defined?
    A regra "not empty" é definida na classe Utilizador, com a anotação @NotBlank quando declaramos o atributo.

3.2 - Alínea f)

Listar:

Filtrar um:

Inserir:

Atualizar:

REVIEW QUESTIONS:

A) Explain the differences between the RestControllerand Controller components used in different parts of this lab.
    A principal diferença entre a componente Controller e RestController está na forma como o "HTTP  responde body" é criado. Ao utilizar a anotação @Controller precisávamos de definir a view, mas utilizando @RestController, o serviço simplesmente devolve os dados do objecto em JSON/XML sem ter de adicionar @RequestBody a cada manipulador.

B) Create a visualization of the Spring Boot layers (UML diagramor similar), displaying the key abstractions in the solutionof 3.3, in particular: entities, repositories, servicesand REST controllers.
    


C) Explain the annotations @Table, @Colum, @Id found in the Employee entity.
@Table
    Especifica a tabela primária para a entidade anotada.
    Se não for especificada a anotação da tabela para uma classe de entidade, aplicam-se os valores por defeito.
    Permite especificar os detalhes da tabela que será utilizada para persistir a entidade na base de dados.
    Assim, quando utilizamos @Table(name = "employees"), estamos basicamente a dizer que a entidade será guardada na tabela "employees" dentro da nossa base de dados MySQL, permitindo que os dados persistam.

@Colum
    É utilizada para especificar a coluna mapeada para uma propriedade ou campo persistente.
    Se não for especificada a anotação da coluna, aplicam-se os valores por defeito.
    Permite-lhe aceder a uma coluna específica a partir de uma tabela, permitindo-lhe aceder a um determinado ficheiro em vez de ter de aceder a todos eles.
    Assim, quando utilizamos @Column(name = "first_name", nullable = false), estamos a aceder apenas à coluna "first_name" da nossa tabela "employees".

@Id
    Cada objecto de entidade armazenado na base de dados tem uma chave primária.
    Uma vez atribuída, a chave primária não pode ser modificada. Ela representa o objecto da entidade desde que exista na base de dados.
    Permite marcar um determinado campo como sendo a chave primária do objecto (ou seja, o que o identifica). Assim, quando usamos @Id @GeneratedValue(strategy = GenerationType.AUTO), estamos a criar uma chave primária automaticamente gerada para o nosso "Employee".

D) Explain the use of the annotation @AutoWired (in the Rest Controller class).
    A anotação @Autowired pode ser utilizada directamente nas propriedades, eliminando assim a necessidade de getters e setters. Esta, por sua vez, pode ser utilizada em métodos de setter ou construtores.
    Permite que "Spring" resolva e injete "beans" colaboradores no seu "bean".