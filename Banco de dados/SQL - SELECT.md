# Consultando registros

- **SELECT**
~~~ sql
SELECT * FROM vendas WHERE usuario = 'ana.silva';

-- selecione todas as colunas de 'vendas' que tem o valor do 'where'
~~~

## Operadores de comparação

valor | operador
:-----: | :----:
igual | =  
diferente | <> 
menor ou igual | <= 
maior ou igual | >=

<br>

## Operadores lógicos

valor | operador
:-----: | :----:
e | AND 
ou | OR

<br>

## Palavra-chave: LIKE

É usada para encontrar valores baseados em caracteres curinga %, muito útil em pesquisas com apenas parte do valor.

~~~ sql
WHERE produto LIKE 'note%'

-- retorna: NoteBOOK HP

WHERE produto LIKE '%book%'

-- retorna: NOTEbook HP
~~~

## Exemplos:

~~~ sql
CREATE TABLE vendas 
(
	usuario VARCHAR(40),
    produto VARCHAR(60),
    preco DECIMAL(15,2),
    quantidade int,
    categoria VARCHAR(60)
);

ALTER TABLE vendas ADD COLUMN total DECIMAL(15,2);

INSERT INTO vendas VALUES(
	'jamilton.damasceno', 'Zenphone Celular', 3500.90,
    1, 'eletronicos'
);


/* SELECT */
SELECT * FROM vendas WHERE preco > 1200;

/* Mais sobre consultas com SELECT */
-- BETWEEN
SELECT * FROM vendas WHERE preco BETWEEN 1200.90 AND 2000;

-- IN e NOT IN
SELECT * FROM vendas WHERE categoria IN('livros', 'eletrodomesticos');

-- NOT
SELECT * FROM vendas WHERE NOT preco > 1200;
SELECT * FROM vendas WHERE NOT preco BETWEEN 1200.90 AND 2000;-- ...1200.90 2000...
SELECT * FROM vendas WHERE NOT produto LIKE '%note%';

-- Ordenação com ORDER BY e LIMIT
/*
ASC -> ASCENDENTE A..Z 0..100
DESC -> DESCENDENTE Z...A 100..0
*/
SELECT * FROM vendas 
WHERE 1=1
ORDER BY produto ASC
LIMIT 5;

-- Consultas com agregação, FUNCÕES SUM, MAX, MIN utilizando alias
SELECT produto AS pro, preco, quantidade FROM vendas;
SELECT produto, preco, quantidade, (preco * quantidade) AS total FROM vendas;
SELECT usuario, MAX(total) AS total_vendas FROM vendas GROUP BY usuario;



-- Alterando a tabela para total
UPDATE vendas SET total = preco * quantidade;


/* Limpar e remover tabelas */
DROP TABLE postagens;
TRUNCATE TABLE usuarios;
~~~