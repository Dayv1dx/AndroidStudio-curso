# RecyclerView

Um componente mais otimizado que o `ListView` e que também é utilizado para listagem de itens, sendo a forma recomendada pelo Google.
São necessários três itens para adicionar um `RecyclerView` :

1. Adapter
2. ViewHolder
3. LayoutManager

~~~ kotlin

class MainActivity : AppCompatActivity() {

    private lateinit var binding: ActivityMainBinding
    private lateinit var rvlista: RecyclerView

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)

        binding = ActivityMainBinding.inflate(layoutInflater)
        setContentView(binding.root)

        val lista = listOf("Dayv1dx", "Edi Cloto", "Vlayck", "Pehols")

        rvlista = binding.rvLista
        rvlista.adapter = MensagemAdapter(lista)
        rvlista.layoutManager = LinearLayoutManager(this)
    }
}
~~~

- Adapter

~~~ kotlin
class MensagemAdapter( private val lista: List<String>) : Adapter<MensagemAdapter.MensagemViewHolder>() {

    inner class MensagemViewHolder(val itemView: View) : ViewHolder( itemView ) {

        val textNome : TextView = itemView.findViewById(R.id.textNome)
        val textUltima : TextView = itemView.findViewById(R.id.textUltima)
        val textHorario : TextView =itemView.findViewById(R.id.textHorario)

    }

    // Ao criar o ViewHolder -> cria a visualização
    override fun onCreateViewHolder(parent: ViewGroup, viewType: Int): MensagemViewHolder {

        val layoutInflater = LayoutInflater.from(parent.context)

        val itemView = layoutInflater.inflate(R.layout.item_lista, parent, false)

        return MensagemViewHolder(itemView)
    }

    // Ao vincular os dados para visualização
    override fun onBindViewHolder(holder: MensagemViewHolder, position: Int) {

        val nome = lista[position]
        holder.textNome.text = nome

    }

    // recupera a quantidade de itens
    override fun getItemCount(): Int {
        return lista.size
    }
}
~~~

## Gerenciador de Layouts

Existem três maneiras de se construir um `RecyclerView` e o Gerenciador permite que sejam utilizado diferentes layouts com a mesma estrutura criada.

1. **LinearLayoutManager:** Organiza os itens na horizontal ou vertical (_orientation_). Para configurar no código:

~~~ kotlin
    rvlista = binding.rvLista
    rvlista.adapter = MensagemAdapter(lista)

    // basta passar a orientação no construtor
    rvlista.layoutManager = LinearLayoutManager(this, RecyclerView.HORIZONTAL, false)
~~~

2. **GridLayoutManager:** Organiza os itens em uma grade, a linha sempre ficará com o tamanho do maior item. 

~~~ kotlin
    rvlista = binding.rvLista
    rvlista.adapter = MensagemAdapter(lista)
    
    rvlista.layoutManager = rvlista.layoutManager = GridLayoutManager(this, 2) // (contexto, número de colunas)
~~~

3. **GridLayoutManager:** Organiza os itens em uma grade, porém não matendo o tamanho da linha de acordo com o tamanho do maior item, tipo um mosaico. Para configurar no código:

~~~ kotlin
    rvlista = binding.rvLista
    rvlista.adapter = MensagemAdapter(lista)

    rvlista.layoutManager = StaggeredGridLayoutManager( 3, RecyclerView.HORIZONTAL ) // (número de colunas, orientação)
~~~

## Divisor e Eventos de Clique

- Divisor

~~~ kotlin
rvlista.addItemDecoration(DividerItemDecoration(this, RecyclerView.VERTICAL))
~~~

- Evento de clique:

~~~ kotlin
override fun onBindViewHolder(holder: MensagemViewHolder, position: Int) {

        val nome = lista[position]
        holder.textNome.text = nome

        //aplicar eventos de clique
        val contexto = holder.imagemPerfil.context
        
        holder.imagemPerfil.setOnClickListener {
            Toast.makeText(contexto, "Olá, $nome", Toast.LENGTH_SHORT).show()
        }
    }
~~~ 

## Notificação de mudança de dados

SEMPRE que houverem mudanças nos dados é necessário notificar o Adapter.

- Métodos de notificação:

1. `notifyDataSetChanged()` - Notifica o Adapter que todo conjunto de dados precisa ser atualizado