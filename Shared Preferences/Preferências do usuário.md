# Preferências do usuário

É possível salvar dados dentro do celular do usuário. Para isso, é necessário utilizar a classe: **`SharedPreferences.`**

Essa classe cria um arquivo XML, onde são salvas as informações. Ou seja, se trata de um arquivo e não de um banco de dados.

~~~ java

private final String ARQUIVO_PREFERENCIA = "ArquivoPreferencia" // é recomendável definir constantes sempre com maiúsculas.

SharedPreferences preferences = getSharedPreferences(ARQUIVO_PREFERENCIA, 0) // (nome, modo) modo = 0, modo privado. apenas o app vai acessar esses dados.
SharedPreferences.Editor editor = preferences.edit()

String nome = "Esther";

// Salvando os dados

editor.putString("nome", nome); // (chave, valor)
editor.commit(); // comando para salvar

// Recuperando dados
SharedPreferences preferences = getSharedPreferences(ARQUIVO_PREFERENCIA, 0)
String nome = preferences.getString("nome", "usuário não definido"); // (chave, valor padrão)

