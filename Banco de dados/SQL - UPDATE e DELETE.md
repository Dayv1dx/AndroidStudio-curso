# Atualizando e removendo registros

- Com **DELETE**

~~~ sql
DELETE FROM usuarios
            WHERE usuario = 'dayvid.cunha';

-- Deleta na tabela 'usuarios' a coluna 'usuario'
~~~

- Com **UPDATE**

~~~ sql
UPDATE usuarios
            SET senha = '123456'
            WHERE usuario = 'dayvid.cunha';

-- atualiza a tabela 'usuarios' na coluna 'senha' onde o campo 'usuario' é igual ao valor do 'where'
~~~