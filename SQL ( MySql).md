

## Tipos de relacionamentos

- One to One (Um para um)
	-> Pode ser um para um com obrigatoriedade  dos dois lados (A ||────|| B) , com obrigatoriedade de apenas um lado (A ||────○| B) ou opcional dos dois lados (A ○|────○| B)

- One to many (Um para muitos)
	-> Um obrigatório e para muitos opcionais ( A`||────○<` B), um obrigatório para um ou mais obrigatórios (A ||────|< B) , um opcional para vários opcionais (A ○|────○< B) ou um opcional para um ou vários obrigatórios (A `○|────|<` B)

- Many to Many (Muitos para muitos)
	-> Um A tem zero ou muitos  B, e o B tem 0 ou muitos A (A `>○────○<` B; um A tem um ou muitos B e um B tem zero ou muitos A (A `>○────|<` B); um A tem um ou muitos B, um B tem um ou muitos A (A `>|────|<` B)


## Tipos de comandos SQL (Os principais para o BÁSICO)

### DDL (Data Definition Language)
- CREATE -> Usado para criar estruturas do banco(tabelas, colunas, índices)
- ALTER -> Usado para atualizar estruturas do banco
- DROP -> Usado para deletar estruturas do banco

### DML (Data Manipulation Language)
- Usada para inserir, alterar ou apagar dados do dentro das tabelas
- Exemplos: 
	- INSERT
	- UPDATE
	- DELETE

### DQL (Data Query Language)
- Usada para fazer queries (buscas) no banco de dados
- Usa principalmente o SELECT para dizer quais colunas vão ser usadas para extrair dados


## Consultas e Filtros
- FROM -> indica qual de qual tabela os dados serão extraídos
- WHERE -> Filtra registros baseados em uma condição específica
- ORDER BY -> Ordena os dados em forma crescente (ASC) e decrescente (DESC) - *A prioridade fica sempre pro primeiro item após o ORDER BY 
- GROUP BY -> Agrupa linhas que tem valores iguais nas mesmas colunas - ***Muito usada para SUM e COUNT*
- HAVING -> Funciona como um WHERE, mas filtra resultados depois do agrupamento com GROUP BY
- LIMIT / TOP -> Restringem a quantidade máxima de linhas retornadas
- OFFSET -> Aumenta o ponteiro inicial de cada busca (Exemplo: OFFSET 2,conta apartir do segundo registro ) - *Bastante usado em paginação*

## Operadores lógicos e de Comparação
- AND / OR / NOT -> Combinam ou negam multiplas condições
- IN -> Verifica se um valor corresponde a qualquer item dentro de uma lista específica
- BETWEEN -> Filtra valores dentro de um intervalo 
- IS NULL / IS NOT NULL -> Verifica se um campo está vazio ou preenchido


