## Parte 2: selecionando informações de uma tabela <h2>

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

## 2.1 - Operações com NÚMEROS

### Selecionar uma LINHA específica da tabela com OPERADORES CONDICIONAIS: <h3>

``` SELECT * FROM nome_da_tabela WHERE condição < valor_da_condição; ```

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

``` SELECT * FROM nome_da_tabela WHERE condição != valor_da_condição; ```

Para fazer seleções de linhas que são DIFERENTES de determinada condição, usamos o operador de diferença !=.

> Por exemplo, para selecionar as informações do user cuja idade é diferente de 18 anos da tabela "user", usamos a query:
> SELECT * FROM user WHERE age != 18;

*********

### Selecionar COLUNAS ESPECÍFICAS usando OPERADORES CONDICIONAIS

``` SELECT nome_da_coluna, nome_da_coluna FROM nome_da_tabela WHERE condição <= valor_da_condição; ```

Nesse caso, estamos apenas combinando duas operações anteriores: selecionar informações de colunas específicas, mas colocando condições para isso. 

> Por exemplo, para selecionar as colunas id e age dos usuários com menos de 21 anos da tabela "user", usamos a query:
> SELECT id, age FROM user WHERE age < 21;

*********

### Selecionar com mais de UMA CONDIÇÃO usando operador OR

``` SELECT nome_da_coluna, nome_da_coluna FROM nome_da_tabela WHERE condição <= valor_da_condição OR condição > valor_da_condição; ```

Nesse caso, estamos buscando linhas que atendam a uma OU a outra condição, então usamos o operador lógico OR.

> Por exemplo, para selecionar as colunas id e age dos usuários com menos de 21 anos ou mais de 1.85 de altura, usamos a query:
> SELECT id, age FROM user WHERE age < 21 OR heigth > 185;

*********

### Selecionar linhas que atendam MAIS DE UMA condição

``` SELECT nome_da_coluna, nome_da_coluna FROM nome_da_tabela WHERE condição <= valor_da_condição AND condição > valor_da_condição; ```

Nesse caso, estamos buscando linhas que atendam a MAIS DE UMA condição, então usamos o operador lógico AND.

> Por exemplo, para selecionar as colunas id e age dos usuários com menos de 21 anos E mais de 1.85 de altura, usamos a query:
> SELECT id, age FROM user WHERE age < 21 AND heigth > 185;

*********
### Selecionar com o operador BETWEEN 

``` SELECT nome_da_coluna, nome_da_coluna FROM nome_da_tabela WHERE condição BETWEEN valor_da_condição AND valor_da_condição; ```

Nesse caso, estamos buscando linhas que atendam a MAIS DE UMA condição dentro da mesma coluna. É uma forma própria do SQL de fazer essa busca que também poderia ser feita apenas com AND. 

> Por exemplo, para selecionar as colunas id e age dos usuários com idade entre 21 e 30 anos, usamos a query:
> SELECT id, age FROM user WHERE age BETWEEN 21 AND 30;

OBS: alguns bancos não incluem na busca os valores 21 e 30, pegando apenas o que está entre esses valores (de 22 a 29). É preciso verificar como cada banco atua nesse caso. 

*********
### Selecionar com o operador NOT + BETWEEN 

``` SELECT * FROM nome_da_tabela WHERE condição NOT BETWEEN valor_da_condição AND valor_da_condição; ```

Nesse caso, estamos buscando linhas que NÃO atendam a MAIS DE UMA condição dentro da mesma coluna. 

> Por exemplo, para selecionar todas as colunas da tabela "user" que contenham usuários com idade que não estejam entre 21 e 30 anos, usamos a query:
> SELECT * FROM user WHERE age NOT BETWEEN 21 AND 30;

*********
### Selecionar agrupando mais condições 

``` SELECT nome_da_coluna FROM nome_da_tabela WHERE (condição < valor_da_condição AND condição > valor_da_condição) AND (condição = valor_da_condição); ```

Para agrupar várias condições, devemos colocá-las entre parênteses. 

> Por exemplo, para selecionar todas as colunas da tabela "user" que contenham usuários com idade que não estejam entre 21 e 30 anos e que tenham altura de 1.85, usamos a query:
> SELECT * FROM user WHERE age (NOT BETWEEN 21 AND 30) AND (height = 185);

**********
## 2.2 - Operações com TEXTO

### Selecionar usando strings no WHERE

``` SELECT nome_da_coluna FROM nome_da_tabela WHERE condição = 'valor_da_condição'; ```

OBS: o valor da condição é case sensitive, ou seja, há diferença entre minúsculas e maiúsculas.

> Por exemplo, para selecionar as informações do user cujo nome é 'Smith', usamos a query:
> SELECT * FROM user WHERE name = 'Smith';
> Se os nomes forem cadastrados no banco com letra maiúscula, usamos a query:
> SELECT * FROM user WHERE name = 'SMITH';

**********
### Selecionar por palavras que iniciam COM DETERMINADA LETRA usando o operador LIKE

``` SELECT * FROM nome_da_tabela WHERE condição LIKE 'letra%'; ```

Nesse caso, usamos o operador LIKE depois da condição e colocamos entre aspas simples a letra seguida de % (porcentagem).

> Por exemplo, para selecionar todos os usuários com nomes iniciados com a letra 'A', usamos a query:
> SELECT * FROM user WHERE name LIKE "A%';

***********

### Selecionar por palavras que possuem DETERMINADA LETRA 

``` SELECT * FROM nome_da_tabela WHERE condição LIKE '%letra%'; ```

Nesse caso, usamos o operador LIKE depois da condição e colocamos entre aspas simples % (porcentagem), então a letra e mais uma % (porcentagem).

> Por exemplo, para selecionar todos os usuários com nomes que possuem a letra 'A', usamos a query:
> SELECT * FROM user WHERE name LIKE "%A%';

Para buscar por nomes que terminam com determinada letra usamos '%letra'

***********

### Selecionar sem saber qual letra buscar

``` SELECT * FROM nome_da_tabela WHERE condição LIKE '_restante_da_palavra'; ```

Nesse caso, usamos o _ (underscore) para substituir uma letra que não temos certeza. Isso é muito útil quando não sabemos com que letra determinada palavra é escrita.

> Por exemplo, se não sabemos se o nome do usuário começa com K ou com C, usamos a query:
> SELECT * FROM user WHERE name LIKE "_atherine';

Assim, o banco vai retornar todos os usuários que tenham nomes Katherine ou Catherine. 

**********

## 2.3 Operações com valores NULL

### Selecionar APENAS valores que NÃO SÃO NULL

``` SELECT * FROM nome_da_tabela WHERE condição IS NOT NULL; ```

As tabelas podem ter linhas com campos vazios, então, para ignorar essas linhas em uma pesquisa, nós usamos o operador IS NOT NULL.

> Por exemplo, para buscarmos todos os usuários que possuem nome do meio, usamos a query:
> SELECT * FROM user WHERE middle_name IS NOT NULL;

**********

### Selecionar APENAS valores que SÃO NULL

``` SELECT * FROM nome_da_tabela WHERE condição IS NULL; ```

Nesse caso, estamos buscando por valores que não foram preenchidos ainda. 

> Por exemplo, para buscarmos todos os usuários que NÃO possuem nome do meio, usamos a query:
> SELECT * FROM user WHERE middle_name IS NULL;

OBS: em comparações os valores NULL sempre são excluídos. Por exemplo, se eu busco usuários com age > 21 e um dos usuário tem o campo age com valor NULL, ele não será retornado naquela busca. 

OBS²: em comparações como age >= 0, o usuário com age NULL também não será retornado.

***********

## 2.4 Operações matemáticas em SQL

Assim como funciona com operadores condicionais, nós também podemos realizar **operações matemáticas** nas buscas. Alguns dos operadores possíveis são:

```
+ (soma),
- (subtração),
* (multiplicação),
/ (divisão).
```

> Por exemplo, para buscarmos por usuários que ganham anualmente um salário acima de 50 mil, usamos a query:
> SELECT * FROM user WHERE (monthly_salary * 12) > 50000;

OBS: perceba que a operação matemática está entre parênteses.

