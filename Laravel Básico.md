

## Métodos de criação de rotas:

- get -> Rotas de leitura
- post -> Rotas de envio de dados voltado para criação de objetos
- put -> Rotas de envio de dados para atualização total de um objeto
- patch -> Rotas para atualização parcial de um objeto
- delete -> Rotas para deletar um objeto
- match -> Acessa apenas os tipos declarados no parâmetro
- any -> Permite todo tipo de acesso http
- apiResource -> Gera automaticamente rotas para os 5 métodos HTTP padrões

Quando chamamos uma classe controller e seus métodos:
exemplo de Uso do apiResource para poder chamar todos os métodos juntos
-> Route::apiResource('rooms', RoomController::class);

Exemplo de uso de quando queremos chamar os métodos do controller separadamente
-> Route::post('reserves', [ReserveController::class, 'store']);

Parametrização de rotas:
Exemplo: Route::get("/produto/{id}", function($id){});

Para deixar os parâmetros opcionais -> Uso do valor default = null dentro do parâmetro e uso da ? após o parâmetro da URL
Exemplo: Route::get("/produto/{id}/{cat?}"), fuction($id, $cat=null){});


## Comparando Arquivos e suas funções entre Java/SpringBoot e PHP/Laravel

### Controller:
Java -> Chama o service e expõe o endpoint para a web e chama o DTO de request com @Valid para poder validar os campos da entrada de dados
Laravel -> Ponte entre route e service. O FormRequests faz a validação de dados antes de chegar ao controller

### Service: 
-> Funcionalidades parecidas

### Validação da entrada de dados
Java -> Entrada e validação de dados que vem na requisição por meio de um DTO de Request
Laravel -> Entrada e validação de dados antes mesmo de chegar ao controller 

Formatação da resposta de dados:
Java -> Uso de um DTO Response
Laravel -> Uso do Resource

### Model:
Java -> Servem para um mapeamento do objeto dentro do código
Laravel -> Serve como um mapeamento indireto (Já que a estruturação do objeto é feita diretamente nas migrations). Usa o eloquent para poder entregar o acesso/persistência de dados ao banco de dados e alguns outros métodos (Faz o papel do repository também). Serve para indicar quais objetos podem ser usados para factories (Criação de objetos ficticios geralmente usados para testes) e os tipos de relacionamentos com outras tabelas do banco

### Migrations:
Java -> Arquivos em SQL gerados para estruturação de colunas e regras estruturais dos objetos no banco de dados
Laravel -> Fazem como no java, mas são arquivos escritos em PHP e são conectados com os models da mesma tabela por trás dos panos (Por isso que o arquivo de models geralmente é "vazio" no quesito estrutura do objeto)

### Repository:
Java -> Arquivo de persistência de dados com o banco
Laravel -> Não é tão comum quanto na arquitetura SpringBoot. É mais utilizado para salvar querys mais específicas e que podem ser reutilizadas 

### Factories 
-> Serve como uma fábrica de objetos ficticios, com dados fake vindos diretamente de um dicionário que o próprio laravel fornece

### Seeder 
-> Atua como gerenciador de factories e faz os inserts no banco de dados (muito usado para testes junto com o factory). 


## Autenticação

-> No laravel as formas de autenticação mais comum são autenticação via cookies (via CSRF), voltado mais para aplicações fullstack, com laravel backend + laravel blade e também utilizando autenticação via Sanctum (tokens via header)

- JWT vs Sanctum: 
	- JWT é stateless enquanto o Sanctum é statefull
	- JWT carrega as informações do usuário dentro dele. Sanctum carrega apenas o ID da tabela de tokens, e o próprio banco armazena os dados do usuário ao invés do token

## Middlewares: O que são?

-> Em resumo, middlewares são como uma cadeia filtros criados para monitorar e validar as requisições HTTP recebidas pela aplicação

-> Podem ser criadas com o comando php artisan make:middleware

## Providers

-> Permitem a criação de gates que são funções anônimas que servem para controle de autorização de usuários autenticados, determinando se eles tem ou não permissões para certos tipos de ações

-> Permitem o registro de policies também

-> São definidos nos providers de auth e chamados no controller/service


## Policies

-> Assim como os gates, servem para lidar com autorização de usuários e definição de permissões

-> Podem ser criadas com o comando php artisan make:policy

-> São registrados nos middlewares
