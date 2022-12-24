# SQL, a caixa preta da nossa nave

> *Site: [https://app.rocketseat.com.br/node/sql](https://app.rocketseat.com.br/node/sql)*
> 

Para guardar os dados da nossa aplicação usamos banco de dados, e aqui vamos conhecer o SQL, a linguagem responsável por gerenciar as informações guardadas no banco de dados.

# Introdução

- **O que é banco de dados?**
    
    É um repositório sistêmico de informações, ou seja, de forma simples, é um local digital que têm como função, guardar e organizar informações.
    
- **Quais são os serviços de banco de dados existentes?**
    
    Os mais famosos atualmente são:
    
    - [SQLite](https://www.sqlite.org/index.html);
    - [MariaDB](https://mariadb.org/);
    - [MySQL](https://www.mysql.com/);
    - [PostgreSQL](https://www.postgresql.org/);
    - [Oracle](https://www.oracle.com/br/index.html);
    - [Firebase](https://firebase.google.com/?hl=pt);
    - [MongoDB](https://www.mongodb.com/), e;
    - [Redis](https://redis.io/);

# Conceitos

- **O que são tabelas?**
    
    As informações são organizadas no banco de dados em tabelas. Cada tabela contém linhas e colunas, e são estas linhas e colunas que armazenam as informações necessárias para armazenar nossos dados.
    
    ![SQL,%20a%20caixa%20preta%20da%20nossa%20nave%209b2942aa567940dda68347e83b19279e/untitled_(2).png](SQL,%20a%20caixa%20preta%20da%20nossa%20nave%209b2942aa567940dda68347e83b19279e/untitled_(2).png)
    
    <aside>
    💡 É importante ressaltar que dentro de uma banco de dados é possível ter mais de uma tabela.
    
    </aside>
    
    <aside>
    ⚠️ Em alguns casos, a tabela pode ser nomeada como entidade.
    
    </aside>
    
- **O que são os campos?**
    
    De forma simples, o campo é o título de cada colunas, ou melhor, é o nome da informação aramazenada na coluna.
    
    ![SQL,%20a%20caixa%20preta%20da%20nossa%20nave%209b2942aa567940dda68347e83b19279e/untitled_(1).png](SQL,%20a%20caixa%20preta%20da%20nossa%20nave%209b2942aa567940dda68347e83b19279e/untitled_(1).png)
    
    <aside>
    ⚠️ Em alguns casos, o campo pode ser identificado como atributo.
    
    </aside>
    
- **O que são informações?**
    
    Informação é cada dado armazenado no encontro de linha e coluna na tabela, ou seja, o registro de um campo.
    
    ![SQL,%20a%20caixa%20preta%20da%20nossa%20nave%209b2942aa567940dda68347e83b19279e/untitled.png](SQL,%20a%20caixa%20preta%20da%20nossa%20nave%209b2942aa567940dda68347e83b19279e/untitled.png)
    
- **O que são relações entre tabelas?**
    
    No banco de dados pode-se relacionar as informações de uma tabela com outra tabela. Dessa forma, é possível utilizar o campo de uma tabela para encontrar mais informações referentes ao dado da primeira tabela. Assim, não é necessário duplicar informações e permite a escalabilidade do armazenamento das informações.
    
    ![SQL,%20a%20caixa%20preta%20da%20nossa%20nave%209b2942aa567940dda68347e83b19279e/untitled_(1)%201.png](SQL,%20a%20caixa%20preta%20da%20nossa%20nave%209b2942aa567940dda68347e83b19279e/untitled_(1)%201.png)
    

# Tipos de campos

- **O que são tipos de campos?**
    
    Todo campo dentro de uma tabela recebe uma configuração, inclusive o tipo de informação que aquele campo pode receber.
    
    ![SQL,%20a%20caixa%20preta%20da%20nossa%20nave%209b2942aa567940dda68347e83b19279e/db-example_(2).png](SQL,%20a%20caixa%20preta%20da%20nossa%20nave%209b2942aa567940dda68347e83b19279e/db-example_(2).png)
    
    <aside>
    ⚠️ É importante definir com cuidado o tipo de informação que cada campo vai receber, pois essa escolha pode impactar diretamente no futuro do seu projeto.
    
    </aside>
    
- **O que é o tipo TEXT?**
    
    O tipo Text define que determinado campo recebe somente informações do tipo texto, ou seja, letras, números e caracteres especiais. E mesmo recebendo números, esses valores são reconhecidos como textos e não valores numéricos.
    
- **O que é o tipo NUMBER?**
    
    É para campos que armazene apenas informações numéricas. A vantagem de armazenar em Number ao invés que Text (mesmo que ambos possam armazenar números) é que o Number pode ser utilizado para realizar cálculos e comparações de valores numéricos.
    
- **O que é o tipo DATETIME?**
    
    É utilizado em casos que os campos devem aceitar informações de data e hora, que geralmente são a mistura de Number e hífens (caracteres especiais). 
    
- **O que é o tipo PRIMARY KEY?**
    
    É o tipo que define um campo como identificador, ou seja, é um campo de valor único (não deve existir outro igual) na tabela.
    
    Dessa forma, cada registro ou linha da tabela é única.
    
- **O que é o tipo FOREIGN KEY?**
    
    É o tipo que define a relação de uma tabela com outra, ou seja, a partir deste tipo é possível definir qual campo de uma tabela se relaciona com outra tabela.
    
    Diferente da PRIMARY KEY, a FOREIGN KEY pode ser repetir na tabela, pois esse tipo não é utilizado para identificação de uma informação, apenas relacionamento.
    
- **O que é o tipo UNIQUE?**
    
    Este tipo serve para informar ao banco de dados que está informação mesmo não sendo um identificador para os registros, é também um valor único, ou seja, não pode ser repetir no campo.
    
- **Como escrever o nome de tabela e de campos?**
    
    Para definir nome de tabelas e campos devem ser seguidas três regras básicas:
    
    - **deve-se começar com uma letra**
    - **não** deve conter alguns **caracteres especiais**
        
        Ex: ( ) + - / * ' " ; , = & | < > ^ { } %
        
    - **não** deve conter **acentuação**
    - **não** deve conter **espaços**

# Comando SELECT

- **Para que serve o comando SELECT?**
    
    Este comando têm como função buscar alguma informação.
    
    ```sql
    SELECT * FROM Users;
    ```
    
    Além de utilizar o operador * para selecionar todos os campos é possível também especificar campos no comando, o que permite define para o retorno apenas os campos de interesse.
    
    ```sql
    SELECT nick_name, birth_date FROM Users;
    ```
    
- **Para que serve o comando WHERE?**
    
    Em conjunto com o comando SELECT, o comando WHERE serve para espeficificar alguma condição na hora de selecionar informações na tabela desejada.
    
    ```sql
    SELECT * FROM Posts WHERE _id_user = 1;
    ```
    

# Operadores Relacionais

- **Para que serve o operador IGUAL?**
    
    Este operado serve para definir alguma informação que deve ser buscada de forma precisa.
    
    ```sql
    SELECT email FROM Users WHERE _id = 3;
    ```
    
- **Para que serve o operador LIKE?**
    
    Este operador têm como função buscar por textos ou trechos dentro de um texto. E também é possivel utilizar de alguns caracteres de filtro dentro do parâmetro de busca passado para o operador LIKE, como demonstrado abaixo.
    
    ```sql
    SELECT * FROM Posts WHERE message LIKE "Era uma vez %";
    ```
    
    O caracter de filtro `%` é utilizado para informar que não importar qual ou quantos caracteres venham a partir dele.
    
- **Para que serve o operador MAIOR?**
    
    Este operador é comumente utilizado para campos de valores Number. Com ele é possível aplicar uma condição de comparação para retornar valores maiores que algum determinado valor.
    
    ```sql
    SELECT * FROM Users WHERE _id > 1;
    ```
    
- **Para que serve o operador MENOR?**
    
    Este operador é comumente utilizado para campos de valores Number. Com ele é possível aplicar uma condição de comparação para retornar valores menores que algum determinado valor.
    
    ```sql
    SELECT * FROM Users WHERE _id < 10;
    
    ```
    
- **Para que serve o operador MAIOR OU IGUAL?**
    
    Este operador é comumente utilizado para campos de valores Number. Com ele é possível aplicar uma condição de comparação para retornar valores maiores ou igual a um determinado valor.
    
    ```sql
    SELECT * FROM Users WHERE _id >= 3;
    
    ```
    
- **Para que serve o operador MENOR OU IGUAL?**
    
    Este operador é comumente utilizado para campos de valores Number. Com ele é possível aplicar uma condição de comparação para retornar valores menores ou igual a um  determinado valor.
    
    ```sql
    SELECT * FROM Users WHERE _id <= 20;
    
    ```
    
- **Para que serve o operador NÃO IGUAL e DIFERENTE?**
    
    Ambos são operadores que servem para retornar valores diferentes que determinado valor, a diferença entree eles é que o ≠ (DIFERENTE) não é padrão ISO.
    
    ```sql
    SELECT * FROM Users WHERE _id <> 1;
    // ou
    SELECT * FROM Users WHERE _id != 1;
    ```
    

# Operadores Matemáticos

- **Para que serve o operador de ADIÇÃO?**
    
    Este operador serve para realizar operações matemáticas de adição.
    
    ```sql
    SELECT * FROM Users WHERE _id = 1 + 1;
    ```
    
- **Para que serve o operador de SUBTRAÇÃO?**
    
    Assim como o operador de ADIÇÃO pode-se utilizar operações matemáticas de subtração nas condições.
    
    ```sql
    SELECT * FROM Users WHERE _id = 2 - 1;
    
    ```
    
- **Para que serve o operador de MULTIPLICAÇÃO?**
    
    Como outros operadores matemáticos a multplicação serve para operações de multiplicação.
    
    ```sql
    SELECT * FROM Users WHERE _id = 2 * 1;
    
    ```
    
- **Para que serve o operador de DIVISÃO?**
    
    Como citado anteriormente, os operadores matemáticos têm a função de forma uma expressão de operação matemática. E com o operador de divisão é a mesma coisa.
    
    ```sql
    SELECT * FROM Users WHERE _id = 2 / 1;
    ```
    
- **Para que serve o operador de MÓDULO?**
    
    Serve para capturar o resto do resultado de uma divisão. Sua aplicação é a mesma que a de outros operadores matemáticos.
    
    ```sql
    SELECT * FROM Users WHERE _id = 5 % 2;
    ```
    

# Operadores Lógicos

- **Para que serve o operador AND?**
    
    Este operador serve para juntar condições, ou seja, só ocorre resultado se as duas condições forem verdadeiras.
    
    ```sql
    SELECT * FROM Users WHERE age > 18 AND name LIKE "A%";
    ```
    
- **Para que serve o operador OR?**
    
    Este operador especifica o retorno onde a primeira ou a segunda condição seja verdadeira.
    
    ```sql
    SELECT * FROM Users WHERE age > 18 OR name LIKE "A%";
    ```
    
- **Para que serve o operador BETWEEN?**
    
    Este operador têm como função definir um intervalo entre valores, ou seja, é utilizado para definir um intervalo para seleção entre um valor e outro, muito semelhante a condição > X e menor que Y, como demonstrado abaixo.
    
    ```sql
    SELECT * FROM Users WHERE _id > 5 AND _id < 10;
    ```
    
    Dessa forma o comando acima utilizando o BETWEEN fica da seguinte forma
    
    ```sql
    SELECT * FROM Users WHERE _id BETWEEN 5 AND 10;
    ```
    
    Em casos que se deseja "excluir" determinado intervalo de uma seleção, é possível utilizar o operador NOT, ou seja, negar um intervalo para seleção.
    
    ```sql
    SELECT * FROM Users WHERE _id NOT BETWEEN 5 AND 10;
    ```
    
- **Para que serve o operador IN e NOT IN?**
    
    O operado IN serve para definir uma lista de valores que deseja-se especificar para uma seleção, ou seja, com os valores passado pelo operador IN é possível definir uma lista que será utilizada com parâmetro de seleção.
    
    ```sql
    SELECT * FROM Users WHERE _id IN (1, 3, 5, 7);
    ```
    
    E assim como outros operadores, também é possível utilizar o operador NOT para "excluir" uma seleção.
    
    ```sql
    SELECT * FROM Users WHERE _id NOT IN (1, 3, 5, 7);
    ```
    
- **Para que serve o operador IS NULL e IS NOT NULL?**
    
    O operador IS NULL (ou seja, vázio) especifica que o valor do campo deve ser NULL ou se necessário IS NOT NULL (ou seja, não vázio).
    
    <aside>
    ⚠️ É importante citar que por padrão o banco de dados armazena o valor NULL para todos os campos que não têm valor atríbuido.
    
    </aside>
    
    ```sql
    SELECT * FROM Users WHERE birth_date IS NULL;
    ```
    

# Mais Comandos

- **Para que serve o INSERT?**
    
    Este é um comando que têm como função inserir valores em uma determinada tabela.
    
    ```sql
    INSERT INTO Users (name, nick_name, phone_number, birth_date)
    VALUES ("Junior", "@junirio.10", 19992674893, 10-03-2000-13-10-00);
    ```
    
- **Para que serve o UPDATE?**
    
    Este comando têm como função atualizar um registro na tabela.
    
    ```sql
    UPDATE Users SET name="Angelo" WHERE _id = 2;
    ```
    
- **Para que serve o DELETE?**
    
    Este comando permite que sea removido um determinado registro da tabela.
    
    ```sql
    DELETE FROM Users WHERE _id = 3;
    ```
    

# Unindo tabelas

- **Para que serve o JOIN?**
    
    Este comando têm como função "juntar" campos de tabelas no retorno do comando.
    
    <aside>
    ⚠️ Vale ressaltar aqui que para utilizar o comando JOIN é necessário possuir uma FOREIGN KEY que relacione uma tabela com a outra.
    
    </aside>
    
    ```sql
    SELECT * FROM Users
    JOIN Posts
    ON Posts._id_user = Users._id;
    ```
    
- **Como utilizar o comando WHERE junto com o comando JOIN?**
    
    Algumas vezes também é necessário retornar seleções com alguma condição especifica, para isso também é possível utilizar o comando WHERE.
    
    ```sql
    SELECT * FROM Users
    JOIN Posts
    ON Posts._id_user = Users._id
    WHERE Users._id BETWEEN 1 AND 10;
    ```
    
- **Como utilizar o comando ALIAS junto com o comando JOIN?**
    
    O comando ALIAS, é um comando que auxilia no momento de montar os comando SQL.
    
    A função deste comando é dar "apelidos" as tabelas. Dessa forma, os comandos podem ficar mais limpos e simples de entender.
    
    O comando ALIAS é apresentado como AS no código, como demonstrado abaixo.
    
    ```sql
    SELECT * FROM Users AS U
    JOIN Posts As P
    ON P._id_user = U._id;
    ```
    
    <aside>
    ⚠️ É importante citar aqui que, o comando ALIAS é somente válido para cada SELECT, ou seja, ele deve ser declarado em cada SELECT para ser válido. Dessa forma, não é possível utilizar um ALIAS declarado em um outro SELECT anterior.
    
    </aside>
    
    Se necessário, pode-se também "apelidar" campos das tabelas, o que pode torná-las melhor apresentadas.
    
    ```sql
    SELECT nick_name AS NICK, message AS MSG
    FROM Users AS U
    JOIN Posts As P
    ON P._id_user = U._id
    WHERE P.send_date BETWEEN 01-01-2021 AND 30-01-2021;
    ```
    
- **Quais os tipos de JOIN no SQL?**
    
    O comando JOIN possui algumas varições, o que permite retornar mais valores além dos retornado pelo comando simples, dando assim, mais poder ao operador na hora de criar o comando.
    
    Para entender melhor estas variações observe a imagem abaixo.
    
    ![SQL,%20a%20caixa%20preta%20da%20nossa%20nave%209b2942aa567940dda68347e83b19279e/Untitled.png](SQL,%20a%20caixa%20preta%20da%20nossa%20nave%209b2942aa567940dda68347e83b19279e/Untitled.png)
    

# Comandos Avançados

- **Para que serve o ORDER BY?**
    
    Este comando têm como função ordernar as seleções de acordo com alguma ordem especificada.
    
    <aside>
    ⚠️ Vale citar que a ordenação serve tanto para valores numérios quanto para valores de texto.
    
    </aside>
    
    E caso não seja específicado o tipo de ordenação, é automaticamente aplicada a ordem crescente dos valores do campo especificado.
    
    ```sql
    SELECT * FROM Users ORDER BY name DESC;
    ```
    
    <aside>
    💡 Caso seja necessário aplicar a ordenação de forma crescente pode apenas aplicar o ORDER BY sem especificação ou utilizar o comando ASC após o campo que deseja utilizar para ordenar os registros.
    
    </aside>
    
- **Para que serve o LIMIT?**
    
    Este comando serve para limitar a quantidade de registros retornados pelo comando SELECT.
    
    ```sql
    SELECT * FROM Users LIMIT 5;
    ```
    
- **Para que serve o OFFSET?**
    
    Este comando geralmente é utilizado em cojunto com o comando LIMIT. Sua função é ignorar o número de registros especificados a partir do primeiro, ou seja, se for solicitado para retornar os 10 primeiros registros e for definido como OFFSET 10, será ignorado os 10 primeiros registros e será retornado apenas os 10 registros seguintes.
    
    ```sql
    SELECT * FROM Users LIMIT 10 OFFSET 10;
    ```
    
- **Para que serve o COUNT?**
    
    Este comando têm como objetivo contar a quantidade de registros (diferentes) e que se encaixam na especificação do comando SELECT, ou seja, é retornado a quantidade de valores (diferentes) detectados pelo comando SELECT.
    
    ```sql
    SELECT COUNT(name) FROM Users;
    ```
    
    <aside>
    ⚠️ É importante ressaltar que o count não conta valores NULL.
    
    </aside>
    
    <aside>
    ⚠️ Para entender mais sobre COUNT acesse este [artigo da Alura](https://www.alura.com.br/artigos/select-count-count1-e-countnome-a-batalha-dos-counts-de-sql) totalmente dedicado a COUNTs.
    
    </aside>
    
- **Para que serve o GROUP BY?**
    
    Este comando têm como função agrupar dados semelhantes a partir de um campo pré-definido.
    
    Vale citar que este comando é muito utilizado com o comando COUNT, o que permite ter uma precisão maior de contagem.
    
    ```sql
    SELECT Users.name AS "USER NAME", COUNT(Posts._id_user) "POSTS"
    FROM Posts
    JOIN Users
    ON Posts._id_user = User._id
    GROUP BY Posts._id_user;
    ```
    
- **Para que serve o HAVING?**
    
    Este é um comando que facilita a tarefa de agrupamento. Em alguns casos não é viável ou possível utilizar o comando WHERE. Para estes casos é recomendável utilizar o comando HAVING no lugar do WHERE.
    
    Ou seja, por alguns o comando HAVING pode ser visto como um substituto do WHERE, mas na verdade o HAVING se aplica a grupos enquanto o WHERE se aplica a linhas individuais das tabelas.
    
    ```sql
    SELECT Users.name, COUNT(Posts._id_user)
    FROM Posts
    JOIN Users
    ON Posts._id_user = Users._id
    GROUP BY Posts._id_user
    HAVING COUNT(Posts._id_user) >= 2;
    ```
    

# Comandos nas tabelas

- **Para que serve o CREATE TABLE?**
    
    Este comando têm como objetivo criar uma tabela. Para utilizá-lo basta passar o nome da tabela, seus campos com seus respectivos tipos.
    
    ```sql
    CREATE TABLE Users (
    	_id INTEGER PRIMARY KEY AUTOINCREMENT,
    	name TEXT,
    	phone_number INTEGER(12) UNIQUE,
    	birth_date DATE
    );
    ```
    
    ```sql
    CREATE TABLE Posts (
    	_id INTEGER PRIMARY KEY AUTOINCREMENT,
    	_id_user INTEGER,
    	message TEXT,
    	send_date DATE,
    	FOREIGN KEY(_id_user) REFERENCES Users(_id)
    );
    ```
    
- **Para que serve o ALTER TABLE?**
    
    Este comando permite alterar as regras, campos e o nome de alguma tabela.
    
    Para alterar o nome de uma coluna pode-se utilizar o seguinte comando.
    
    ```sql
    ALTER TABLE Users RENAME COLUMN name TO name_user;
    ```
    
    Se for necessário alterar o nome de uma tabela é preciso utilizar o comando RENAME TO.
    
    ```sql
    ALTER TABLE Users RENAME TO employees;
    ```
    
    Se o caso for adicionar uma tabela, o ALTER TABLE também possibilita essa alteração.
    
    ```sql
    ALTER TABLE Users ADD email VARCHAR(50);
    ```
    
    <aside>
    ⚠️ Outras funções podem ser encontradas e estudadas no [site do SQL](https://sql.sh/cours/alter-table).
    
    </aside>
    
- **Para que serve o DROP TABLE?**
    
    Com este comando é possível deletar uma tabela passando somente o nome dela.
    
    ```sql
    DROP TABLE Users;
    ```
    

<aside>
⚠️ Para mais informações ou instruções relacionadas a SQL acesse o [site do SQL](https://www.sql.org/) ou o site de [cursos e tutoriais do SQL](https://sql.sh/).

</aside>