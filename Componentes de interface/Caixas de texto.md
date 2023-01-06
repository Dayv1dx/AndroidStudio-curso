# Caixas de textos

São componentes que podem capturar o que foi digitado pelo usuário, dentre várias outras coisas.

- Recuperando valores de uma caixa de texto
~~~ java
// recuperando o que foi digitado na caixa de texto 
EditText campoExemplo = findViewByID(R.id.campoExemplo)

String nome = campoExemplo.getText().toString()