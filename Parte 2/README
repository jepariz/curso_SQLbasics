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

### Selecionar algo com o operador lógico de DIFERENÇA

``` SELECT * FROM nome_da_tabela WHERE condição != número_da_condição; ```

Para fazer seleções de linhas que são DIFERENTES de determinada condição, usamos o operador de diferença !=.

> Por exemplo, para selecionar as informações do user cuja idade é diferente de 18 anos da tabela "user", usamos a query:
> SELECT * FROM user WHERE age != 18;

*********

### Selecionar COLUNAS ESPECÍFICAS usando OPERADORES CONDICIONAIS

``` SELECT nome_da_coluna, nome_da_coluna FROM nome_da_tabela WHERE condição <= número_da_condição; ```

Nesse caso, estamos apenas combinando duas operações anteriores: selecionar informações de colunas específicas, mas colocando condições para isso. 

> Por exemplo, para selecionar as  colunas id e age dos usuários com menos de 21 anos da tabela "user", usamos a query:
> SELECT id, age FROM user WHERE age < 21;

*********