# ViewBinding

_ViewBinding_ é um recurso que permite a vinculação das Classes com os arquivos XML  de forma mais simples, uma instância de uma `binding class` contém referências diretas a todas as `views` que possuem um ID no layout correspondente.

O ViewBinding veio para substituir o `findViewById`.

## **Como configurar o ViewBinding**

Para ativar o view binding, basta definir este parâmetro como "true" no arquivo `biuld.grade(Module)`, segue o exemplo:

~~~ kotlin

// Kotlin
android {
    ...
    buildFeatures {
        viewBinding = true
    }
}
~~~ 

- Configurando dentro de uma _Activity_ usando Kotlin:

~~~ kotlin

class Activity : AppCompatActivity(){

    private lateinit var binding: ActivityBinding

    override fun onCreate(savedInstanceState : Bunlde?){
        super.onCreate(savedInstanceState)

        binding = ActivityBinding.inflate(layoutInflater)
        setContetView(binding.root) // "root" faz com que o XML relacionado a Activity seja identificado automaticamente


        // utilizando o "binding" é possível acessar apenas os ID que estão na Activity em questão
        binding.IdExemplo.text = "Dayv1dx"

    }
}

~~~ 

- Configurando dentro de uma _Activity_ usando Java:

~~~ Java

public class Activity extends AppCompatActivity(){

    private ActivityBinding binding;

    protected void onCreate(Bunlde savedInstanceState){
        super.onCreate(savedInstanceState)

        binding = ActivityBinding.inflate(getLayoutInflater());
        setContetView(binding.getRoot()) // "getRoot()" faz com que o XML relacionado a Activity seja identificado automaticamente


        // utilizando o "binding" é possível acessar apenas os ID que estão na Activity em questão
        binding.IdExemplo.setText("Dayv1dx");

    }
}