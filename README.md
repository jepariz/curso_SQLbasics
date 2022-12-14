# curso_SQLbasics
Notas de estudo do curso SQL basics do LearnSQL.com
***
## Parte 1: um pouco sobre bancos de dados <h2>

Bancos de dados SQL (Structured Query Language) são **relacionais**.

As informações ficam salvas em **tabelas**. Dentro de um banco pode haver várias tabelas que ficam salvas por nome. Em um curso, por exemplo, pode haver a tabela "alunos" e a tabela "matérias".

Cada **coluna** de uma tabela recebe um nome que indica qual informação está armazenada ali. 

Cada **linha** armazena informações sobre um **objeto**. Por exemplo, na tabela "alunos", cada linha equivaleria a um aluno. 

id   | alunos | semestre
--------- | ------ | -------
1 | Jéssica | 1
2 | Ana | 2

OBS: notação usada no curso para se referir a uma tabela -> alunos(id, nome, semestre)

SQL é uma **linguagem** usada por vários tipos de bancos de dados.

Para buscar informações no banco nós usamos **queries** escritas em SQL. 
********
## Parte 2: selcionando informações de uma tabela <h2>

### Selecionar TODAS as infos de uma tabela: <h3>

``` SELECT * FROM nome_da_tabela; ```

> Por exemplo, para selecionar as informações contidas na tabela "user", usamos a query:

> SELECT * FROM user; 

Onde **SELECT** indica que queremos selecionar dados, **FROM user** indica de qual tabela estamos buscando as infos e o * (asterisco) indica que queremos buscar informações de **todas** as colunas. Para indicar o fim da query usamos ; (ponto e vírgula). 

*********

### Selecionar apenas as infos de UMA COLUNA da tabela: <h3>

``` SELECT nome_da_coluna FROM nome_da_tabela; ```

> Por exemplo, para selecionar as informações contidas na coluna "name" da tabela "user", usamos a query:

> SELECT name FROM user;

**********

### Selecionar VÁRIAS COLUNAS da tabela: <h3>

``` SELECT nome_da_coluna, nome_da_coluna FROM nome_da_tabela; ```

> Por exemplo, para selecionar as informações contidas nas colunas "name" e "age" da tabela "user", usamos a query:
> SELECT name, age FROM user;

Para separar os nomes das colunas que queremos buscar, usamos , (vírgula).

********

### Selecionar uma LINHA específica da tabela: <h3>

``` SELECT * FROM nome_da_tabela WHERE id= numero_da_id; ```

> Por exemplo, para selecionar as informações do user cuja id é 100 da tabela "user", usamos a query:
> SELECT * FROM user WHERE id=100;

Para selecionar um usuário específico usamos uma **condição**. Para isso usamos a palavra WHERE (onde) e id=100, ou seja, o banco deve retornar o usuário que atenda à condição de ter a id de número 100. A condição pode ser relacionada a outros dados, por exemplo, buscar usuários que tenham idade de 20 anos, aí teríamos WHERE age=20. 

OBS: todas as linhas de uma tabela recebem uma id que, geralmente, é gerada pelo próprio banco. 

*********

### Selecionar uma LINHA específica da tabela com OPERADORES CONDICIONAIS: <h3>

``` SELECT * FROM nome_da_tabela WHERE condição < número_da_condição; ```

Podemos usar *operadores condicionais* para realizar seleções mais específicas. Alguns dos operadores possíveis são:

```
< (menor que),
> (maior que),
<= (menor ou igual a),
>= (maior ou igual a).
```

> Por exemplo, para selecionar as informações do user cuja idade é maior que 18 anos da tabela "user", usamos a query:
> SELECT * FROM user WHERE age > 18;

********












