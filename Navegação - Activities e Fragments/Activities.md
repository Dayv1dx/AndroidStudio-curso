# Activities

**Activity** é um componente de aplicativo que fornece uma tela com a qual os usuários podem interagir para fazer algo, como discar um número no telefone, tirar uma foto, enviar um e-mail ou ver um mapa. Cada atividade recebe uma janela que exibe a interface do usuário. Geralmente, a janela preenche a tela, mas pode ser menor que a tela e flutuar sobre outras janelas. Ela é composta por uma Classe (Java ou Kotlin) e um arquivo XML.

<br>

## Passando dados entre as Activities

- **Java**

MainActivity

~~~ java
    Intent intent = new Intent(getApplicaitionContext(), SegundaActivity.class); // Parâmetros: Intent(contexto, destino).

    // Passando dados
    // Deve-se utilizar o método: .putExtra(chave, valor)

    intent.putExtra(name:"nome", value:"Dayvid");
    intent.putExtra(name:"idade", value: 25);

    startActivity (intent); // "intent" significa "intenção"
~~~

SegundaActivity

~~~ java
    private TextView textNome, textIdade;

    textNome = findViewById(R.id.textNome);    
    textIdade = findViewById(R.id.textIdade);

    // Recuperar os dados enviados    
    Bundle dados = getIntent().getExtras() // esse objeto (Bundle) permite recuperar dados

    String nome = dados.getString(key:"nome");
    int idade = dados.getInt(key:"idade");

    // Configurar valores recuperados
    textNome.settext ( nome );
    textIdade.setText( String.valueOf( idade )); // O método String.valueOf(), permite a conversão de um tipo de dado para String.
~~~

<br>
<br>

- **Kotlin**

MainActivity

~~~ kotlin
    val intent = Intent(this, SegundaActivity::class.java); // Parâmetros: Intent(contexto, destino).

    // Passando dados
    // Deve-se utilizar o método: .putExtra(chave, valor)

    intent.putExtra(name:"nome", value:"Dayvid");
    intent.putExtra(name:"idade", value: 25);

    startActivity (intent); // "intent" significa "intenção"
~~~

SegundaActivity

~~~ kotlin
    lateinit var textNome:TextView
    lateinit var textIdade: TextView

    textNome = findViewById(R.id.textNome)   
    textIdade = findViewById(R.id.textIdade)

    // Recuperar os dados enviados    
    val dados: Bundle = intent.extras // esse objeto (Bundle) permite recuperar dados
    if ( dados != null){
        
        val nome = dados.getString(key:"nome")
        val idade = dados.getInt(key:"idade")  

        // Configurar valores recuperados
        textNome.text ( "nome: $nome" )
        textIdade.text( "idade: $idade")  
             
    }    
~~~

<br>

## Passando objetos entre Activities

Para fazer isso é utilizado um processo chamado `serialização`, o qual consiste em salvar o estado atual do objeto em formato binário, podendo ser recuperado esse estado posteriormente.

Pode se feito de duas maneiras: 

1. **`Interface Serializable`**
2. **`Kotlin-parcelize (plugin)`**

A segunda forma é a recomendada atualmente, basta adicionar essa extensão no `build.gralde(app)`
~~~ js
 plugins {
    id 'com.android.application'
    id 'org.jetbrains.kotlin.android'
    id 'kotlin-parcelize' // extensão
}
~~~

### Utilizando o Plugin:

<br>

MainActivity

~~~ kotlin
    
    @Parcelize
    data class Filme(
    val nome: String,
    val descricao: String,
    val avaliacoes: Double,
    val diretor: String
) : Parcelable

    val filme = Filme("Minha Vida", "loading...", "9.2", "Dayv1dx")

    intent.putExtra(name:"filme", filme)

    startActivity (intent); // "intent" significa "intenção"
~~~

SegundaActivity

~~~ kotlin
    lateinit var textFilme:TextView

    textFilme = findViewById(R.id.textFilme)   

    // Recuperar os dados enviados    
    val dados: Bundle = intent.extras // esse objeto (Bundle) permite recuperar dados
    if ( dados != null){
        
        val filme = dados.getParcelable<Filme>(key:"filme")

        // Configurar valores recuperados
        textFilme.text = "${filme?.nome} , {filme?.diretor}" 
    }    
~~~
