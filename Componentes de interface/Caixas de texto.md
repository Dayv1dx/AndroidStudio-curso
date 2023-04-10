# Caixas de textos

São componentes que podem capturar o que foi digitado pelo usuário, dentre várias outras coisas. É possível configurar o `inputType` dessas caixas, fazendo com que o teclado, por exemplo, mostre apenas números quando for pedido para o usuário digitar um número de celular.

- Recuperando valores de uma caixa de texto
~~~ java
// recuperando o que foi digitado na caixa de texto 
EditText campoExemplo = findViewByID(R.id.campoExemplo)

String nome = campoExemplo.getText().toString()
~~~