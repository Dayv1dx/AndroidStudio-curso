# ListView

O `ListView` é um item depreciado, o recomendado é o RecyclerView. Em Java:

~~~ java 
    private ListView lista;
    private String[] itens = {"OS Exemplo 1","OS Exemplo 2","OS Exemplo 3","OS Exemplo 4","OS Exemplo 5"}

       lista = view.findViewById(R.id.listView);

       //Criar adaptador para a lista
       //(contexto, layout, id, array)
        ArrayAdapter<String> adapter = new ArrayAdapter<String>(getContext(),
                android.R.layout.simple_list_item_1, android.R.id.text1, itens);

        //Adiciona adaptador para a lista
        lista.setAdapter(adapter);

        
        //Adicionando clique na lista
        lista.setOnItemClickListener(new AdapterView.OnItemClickListener() {
            @Override
            public void onItemClick(AdapterView<?> parent, View view, int position, long id) {

                String valorSelecionado = lista.getItemAtPosition(position).toString();

~~~ 

## ListView customizado

Para criar um ListView customizado temos que seguir os seguintes passos:

1. Criar um `Layout resource file` para definir o layout;

2. Criar uma classe para definir os atributos;

3. Estender a classe `ArrayAdapter` para associar os dados com o layout definido;

4. Associar o ListView com o adapter que foi criado.


