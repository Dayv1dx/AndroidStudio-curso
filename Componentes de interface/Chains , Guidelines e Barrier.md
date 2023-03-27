# Chains

Permite que você configure espaçoes entre componentes de interface, criando uma cadeia de itens, sendo possível controlar os espaços entre eles.

![i](https://i.stack.imgur.com/ZU3Ch.png)

- Como usar:

    1. Selecionar todos os itens desejados;
    2. Clicar com o direito do mouse e ir em `Chains >`
    3. Selecionar o tipo de Chain, horizontal ou vertical.

Dessa forma, os itens vão ficar espaçados em uma distância proporcional e essa distância pode ser controlada. Com a _Chain_ criada, basta clicar no direito do mouse e ir em: `Chains > Horizontal/Vertical Chain Style >` e selecionar um dos três tipos.

1. **spread** - significa "espalhar" e é o valor padrão.
2. **spread inside** - espalhar a partir de dentro, colocando espaços maiores e cola nas extremidades.
3. **packed** - significa "empacotar", junta todos os itens centralizando eles.

![i](https://images.ctfassets.net/emmiduwd41v7/3VmsOS8KYUQeoME8o0owYM/46fad6654b17db62e1f96dd6627b7712/Cool_ConstraintLayout_09.jpg)

<br>

# Guidelines

É uma linda utilizada para alinhar elementos baseados nela e que não será visualizada ao executar o App, essa linha pode ser horizontal ou vertical. Elas podem ser ajustadas de forma proporcional (em porcetagem) ao tamanho da tela.

Para adicionar:

    direito do mouse > Add helpers > `seleciona o tipo`

<br>

# Barrier

São "barreiras" que se ajustam ao conteúdo de forma dinâmica. Ele pode expandir ou diminuir de acordo com o conteúdo. 

Para adicionar:

    direito do mouse > Add helpers > `seleciona o tipo`

Em `Attributes` é possível definir onde o _barrier_ vai ficar na caixa de texto (top, bottom...). Também é importante definir um _id_ para o _barrier_, pois é necessário na hora de fazer as ligações do constraint layout, caso contrário não haverá a adptação do tamanho do texto.
