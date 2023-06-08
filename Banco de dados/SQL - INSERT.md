

~~~  sql
CREATE DATABASE facebook;
-- comentário

/*
comentário
de multiplas linhas
*/

USE facebook;
create table usuariosemail
(
	email VARCHAR(30),
    senha VARCHAR(8)
);
~~~

## **INSERT**

~~~ sql
CREATE DATABASE facebook;

create table usuariosemail
(
	email VARCHAR(30),
    senha VARCHAR(8)
);

INSERT INTO usuarios ( email, senha) -- inserindo dados na coluna
			VALUES	('dayvid@gmail', '12345');
            
TRUNCATE TABLE usuarios; -- limpa os dados da tabela
DROP TABLE usuarios; -- exclua a tabela