<br>


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
Laravel -> Não tem, quem faz isso é o eloquent através do model

### Factories 
-> Serve como uma fábrica de objetos ficticios

### Seeder 
-> Atua como gerênciador de factiories e faz os inserts no banco de dados (muito usado para testes junto com o factory)


	## Cache

