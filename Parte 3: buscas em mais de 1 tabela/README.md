## Parte : selecionando informações de múltiplas tabelas <h2>

### Selecionar TODAS as infos de duas tabelas: <h3>


> Por exemplo, para selecionar todas as informações contidas na tabela "person" e todas da tabela "car", usamos a query:

> SELECT * FROM person, car; 

A tabela person possui 5 linhas e a tabela car possui 8 linhas. Se juntarmos as duas, quantas linhas teremos nessa nova tabela? <br>

A RESPOSTA É **40 linhas**  <br>

Isso acontece porque o SQL pega todas as pessoas da tabela "person" e combina com todos os carros da tabela "car", já que ele não sabe exatamente o que você quer combinar da tabela "person" com a tabela "car". <br>

Digamos que você quer buscar quem é o dono de cada carro. Para isso, você precisa ligar a coluna "id" da tabela "person" (ou seja, a id de cada usuário) com a coluna "owner_id" da tabela "car" (ou seja, o id do dono de cada carro, que é igual ao id do usuário). Assim, o SQL sabe exatamente o que você que ligar em cada tabela. A query ficaria assim:

> SELECT * FROM person, car WHERE person.id = car.owner_id;

Ou seja, o CORRETO é fazer a query dessa forma: <br>

``` SELECT * FROM nome_da_tabela1, nome_da_tabela2 WHERE nome_da_tabela1.nome_da_coluna = nome_da_tabela2.nome_da_coluna; ```

Perceba que para mostrar qual coluna de cada tabela nós vamos combinar a gente usa nome_da_tabela seguindo de . (ponto) e o nome da coluna.

***********

### Selecionar informações de múltiplas tabelas usando JOIN: <h3>

Como operações de união de tabelas são tão comuns, o SQL possui uma palavra reservada para isso: JOIN. <br>

Para fazer a mesma operação do item anterior usando JOIN, a query seria:

``` SELECT * FROM nome_da_tabela1 JOIN nome_da_tabela2 ON nome_da_tabela1.nome_da_coluna = nome_da_tabela2.nome_da_coluna; ```

A diferença é que aqui nós estamos usando JOIN e colocando quais colunas serão ligadas de pois da palavra ON. Mas, basicamente estamos falando para o SQL retornar apenas as linhas em que a id de "person" seja igual à owner_id de "car". 

### Selecionar APENAS ALGUMAS COLUNAS de múltiplas tabelas usando JOIN: <h3>

Para que o banco retorne apenas algumas colunas, colocamos os nomes dessas colunas antes de FROM.


``` SELECT nome_da_tabela1.nome_da_coluna, nome_da_tabela2.nome_da_coluna FROM nome_da_tabela1 JOIN nome_da_tabela2 ON nome_da_tabela1.nome_da_coluna = nome_da_tabela2.nome_da_coluna; ```


> Por exemplo, para saber apenas o nome do modelo do carro e o nome do dono desse carro, nós precisamos que a busca retorne apenas as colunas "model" de "car" e "name" de "person". Então, a query fica assim::

> SELECT car.model, person.name FROM car JOIN person ON car.owner_id = person.id; 

OBS: caso não haja nas tabelas colunas com nomes iguais, o nome da tabela pode ser omitido na hora de selecionar as colunas. Por exemplo:

> SELECT model, name FROM car JOIN person ON owner_id = person.id; 

A coluna "model" só existe na tabela "car", então não é preciso especificar escrevendo "car.model". O mesmo vale para a coluna "name", que só existe em "person" e "owner_id" que só existe em "car". 

********

### Renomeando uma coluna usando AS: <h3>

Nós podemos renomear as colunas que buscamos usando a keyword AS + o nome desejado:


``` SELECT nome_da_tabela1.nome_da_coluna AS nome_que_você_deseja, nome_da_tabela2.nome_da_coluna AS nome_que_você_deseja FROM nome_da_tabela1 JOIN nome_da_tabela2 ON nome_da_tabela1.nome_da_coluna = nome_da_tabela2.nome_da_coluna; ```

> Por exemplo, para que a coluna "car.model" seja chamada de "modelo" e a coluna "person.name" seja chamada de "dono", a query fica assim::

> SELECT car.model AS modelo, person.name AS dono FROM car JOIN person ON car.owner_id = person.id; 

OBS: esse novo nome é um apelido e não modifica a tabela original. 

***********

### Filtrando informações depois do JOIN: <h3>

Se for necessário, é possível filtrar dados da união das tabelas usando o WHERE. 

> Por exemplo, para retornar o modelo do carro, o nome do dono e filtrar por aqueles donos que tenham idade superior a 25 anos, a query fica assim::

> SELECT car.model, person.name FROM car JOIN person ON car.owner_id = person.id WHERE person.age > 25; 

