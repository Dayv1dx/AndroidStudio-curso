# Ações com Fragments

Para acessar os componentes dentro dos fragments utilizando o `findViewById`, é necessário criar um objeto do tipo _View_

~~~ kotlin

private lateinit var btnExecutar: Button
private lateinit var textNome: TextView

class ExemploFragment : Fragment() {

    // método que vai construir a visualização
    override fun onCreateView( 
        inflater: LayoutInflater,
        container: ViewGroup?,
        savedInstanceState: Bundle?
    ): View? {

        val view = inflater.inflate(R.layout.fragment_exemplo, container, false)

        btnExecutar = view.findViewById( R.id.btn_executar )

        return view // :View
    }
}
~~~

## Passando parâmetros para Fragments

É possível passar parâmetros da Activity para um Fragment dá seguinte forma:

1. Construir o fragment
2. Passar os dados por meio de `arguments`
3. Recuperar esses dados no fragment desejado

~~~ kotlin
//Activity

btnCategoria = view.findViewById( R.id.btn_executar )
        btnExecutar.setOnClickListener {

            val exemploFragment = ExemploFragment() //1

            val bundle = bundleOf(
                "categoria" to "mercado" // chave, valor
            )

            exemploFragment.arguments = bundle //2
        }

~~~

~~~ kotlin
//Fragment
private lateinit var btnExecutar: Button
private var textCategoria: TextView? = null

class ExemploFragment : Fragment() {

    override fun onCreateView( 
        inflater: LayoutInflater,
        container: ViewGroup?,
        savedInstanceState: Bundle?
    ): View? {

        val view = inflater.inflate(R.layout.fragment_exemplo, container, false)

        btnExecutar = view.findViewById( R.id.btn_executar )
        btnExecutar.setOnClickListener {
        
        textCategoria = arguments?.getString("categoria") // 3


        
    }

    return view // :View
}
}
~~~