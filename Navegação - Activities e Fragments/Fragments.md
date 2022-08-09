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

