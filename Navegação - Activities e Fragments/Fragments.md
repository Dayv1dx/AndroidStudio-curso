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

New > Fragment > Fragment (Blank)

O atributo **gravity** permite fazer alinhamentos no TextView

É necessário adicionar um `FrameLayout`, pois ele é um conteiner onde os Fragments serão carregados.

MainActivity

~~~ java
public class FragmentExemplo extends Fragment {

    private FragmentExemplo fragmentExemplo; // definindo o objeto

onCreate(){

   fragmentExemplo = new FragmentExemplo(); // instanciando

   // Configurar objeto para o fragmento
   FragmentTransaction transaction = getSupportFragementManager().beginTransaction;
   transaction.add.(R.id.frameLayout, fragment exemplo);

   // o método "add" adiciona e o método "replace" muda/substitui
   transaction.commit(); // o "commit" finaliza as transações.
}
} 
 ~~~~ 

Fragment

~~~ java

public class FragmentExemplo extends Fragment {

    private TextView texto;

onCreate(){

    View view = inflater.inflater(R.layout.fragment_exemplo, conteiner,)


    // No Fragment tem que usar o "view"
    texto = view.findViewId.(R.id.texto);

    return view;
}
} 
~~~

