# Fragments

Fragments (Fragmentos) representam um comportamento ou uma porção de interface com o usuário na activity. Permite o reuso de código e deixa as Interfaces mais dinâmicas.

![imagem](https://www.cdn.geeksforgeeks.org/wp-content/uploads/Fragments_android_1.jpg)


Para se utilizar um fragment, é necessário criar uma estrutura chamada: **FrameLayout**

~~~ java 
// Remover sombra da ActionBar
getSupportActionbar().setElevation(0);
~~~
O comando acima deve ser feito dentro do método **OnCreate**

## Criando um fragment

- **1ª Forma:**

~~~
New > Fragment > Fragment (Blank)
~~~

É necessário adicionar um `FragmentContainer`, pois ele é um conteiner onde os Fragments serão carregados.

- **2ª Forma:**

1. Criar uma Classe

~~~
New > Kotlin/Class File > `ExemploFragment.kt`
~~~

2. Estabelecer relação de herança com `Fragment()`
3. Criar um arquivo XML para associar ao fragment

~~~ kotlin
class ExemploFragment : Fragment() { // 2

    // método que vai construir a visualização
    override fun onCreateView( 
        inflater: LayoutInflater,
        container: ViewGroup?,
        savedInstanceState: Bundle?
    ): View? {
        return inflater.inflate(R.layout.fragment_exemplo, container, false) // 3
    }
}
~~~

<br>

## Navegando pelos Fragments

~~~ kotlin
class MainActivity : AppCompatActivity() {

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        // objeto que permite manipular os fragments
        val fragmentManager = supportFragmentManager.beginTransaction()
        
        // adiciona o fragment
        fragmentManager.add( R.id.fragment_container, ExemploFragment() ).commit()

        // o método "replace" é o recomendado na navegação
        fragmentManager.replace( R.id.fragment_container, ExemploFragment() ).commit()
    }
}