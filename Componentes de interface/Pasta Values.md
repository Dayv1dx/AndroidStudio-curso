# Values

Essa pasta possui dois arquivos:

- `strings.xml`
- `colors.xml`

No primeiro arquivo é onde os textos do aplicativo devem ser guardados, isso é uma prática recomendada, pois facilita eventuais alterações.

~~~ xml
 <!-- strings -->
<resources>

    <string name="app_name">InterfacesAppsClone</string>
    <string name="texto_exemplo">Texto exemplo</string>

</resources>
~~~

No segundo arquivo é onde as cores do aplicativos devem ser definidas.

~~~ xml
 <!-- colors -->
<resources>

    <color name="purple_200">#FFBB86FC</color>
    <color name="purple_500">#FF6200EE</color>
    <color name="purple_700">#FF3700B3</color>
    <color name="teal_200">#FF03DAC5</color>
    <color name="teal_700">#FF018786</color>
    <color name="black">#FF000000</color>
    <color name="white">#FFFFFFFF</color>

    <!-- cores personalizadas -->
    <color name="cor_exemplo">#FFF455FF</color>

</resources>
~~~

Também possui uma pasta com os temas do app, a pasta `themes`

~~~ xml
        <!-- Tema base da aplicação -->
<style name="Theme.InterfacesAppsClone" parent="Theme.MaterialComponents.DayNight.DarkActionBar">
        <!-- Cores primárias -->
        <item name="colorPrimary">@color/purple_500</item>
        <item name="colorPrimaryVariant">@color/purple_700</item>
        <item name="colorOnPrimary">@color/white</item>
        <!-- Cores secundárias -->
        <item name="colorSecondary">@color/teal_200</item>
        <item name="colorSecondaryVariant">@color/teal_700</item>
        <item name="colorOnSecondary">@color/black</item>
        <!-- Cor da barra de status -->
        <item name="android:statusBarColor">?attr/colorPrimaryVariant</item>


        <!-- Customizações do tema -->
    </style>
~~~ 