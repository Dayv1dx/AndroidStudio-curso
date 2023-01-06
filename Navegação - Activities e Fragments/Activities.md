# Activities

**Activity** é um componente de aplicativo que fornece uma tela com a qual os usuários podem interagir para fazer algo, como discar um número no telefone, tirar uma foto, enviar um e-mail ou ver um mapa. Cada atividade recebe uma janela que exibe a interface do usuário. Geralmente, a janela preenche a tela, mas pode ser menor que a tela e flutuar sobre outras janelas.


## Ciclo de vida de uma Activity:

![alt](https://w3cschoool.com/public/file/Android/Android-Activity-Lifecycle.png)

## Passando dados entre as Activities:
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

## Passando objetos entre Activities
