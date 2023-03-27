# Firebase

1. Registrar app
2. Fazer download do JSON
3. Adicionar o SDK do Firebase (aqui estão as mudanças)
    1. copiar o `classpath 'com.google.gms:google-services:4.3.15'`

    2. ir no `build.gradle(app)` e colar em 'plugins' da seguinte forma:

    ~~~ gradle
     id 'com.google.gms.google-services'
    ~~~

    3. ir no `build.gradle(project)`, colar também a linha acima em 'plugins' e adicionar a versão da seguinte forma:

    ~~~ gradle
     id 'com.google.gms.google-services' version '4.3.15' apply false
    ~~~
