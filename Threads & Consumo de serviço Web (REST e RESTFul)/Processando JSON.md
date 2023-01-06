# JSON

**JSON** ( _JavaScript Object Notation - Notação de Objetos JavaScript_ ) é uma formatação leve de troca de dados. Para seres humanos, é fácil de ler e escrever. Para máquinas, é fácil de interpretar e gerar. Está baseado em um subconjunto da linguagem de programação JavaScript, Standard ECMA-262 3a Edição -Dezembro - 1999. JSON é em formato texto e completamente independente de linguagem, pois usa convenções que são familiares às linguagens C e familiares, incluindo C++, C#, Java, JavaScript, Perl, Python e muitas outras. Estas propriedades fazem com que JSON seja um formato ideal de troca de dados.

~~~ json
{
    "nome" : "Dayv1dx",
    "idade" : 25,
    "enderecos" : {
        "endereco1" : {"rua" : "um", "numero" : 920},
        "endereco2" : {"rua" : "dois", "numero" : 2}
    }
}
~~~

- [Introdução ao JSON](https://www.json.org/json-pt.html)
- [Validar JSON](https://jsonformatter.org/)
- [Formatar JSON](https://jsonformatter.curiousconcept.com/)

## Processando JSON

~~~ java
@Override
        protected void onPostExecute(String resultado) {
            super.onPostExecute(resultado);

            String logradouro = null;


            try {
                // é passada a chave para o objeto e ele retorna o valor
                JSONObject jsonObject = new JSONObject();
                logradouro = jsonObject.getString("bairro");


            } catch (JSONException e) {
                e.printStackTrace();
            }

            textResultado.setText(logradouro);
        }
~~~