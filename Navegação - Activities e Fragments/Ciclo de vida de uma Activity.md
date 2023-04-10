# Ciclo de vida de uma Activity

![alt](https://w3cschoool.com/public/file/Android/Android-Activity-Lifecycle.png)

Diferente dos paradigmas da programação em que o programa é iniciado com um método main(), como no C ou no Kotlin, o Android inicia o código em uma instância Activity, invocando métodos do ciclo de vida dessa activity.

Ao longo da vida útil de uma atividade, ela passa por vários estados. Uma série de callbacks são usados para lidar com transições entre estados. Vamos ver TODOS eles agora, por isso preste atenção:

1) **`onCreate()`**

 Esse callback é executado pelo sistema quando sua activity é criada.

É aqui que você PRECISA chamar o método setContentView() para definir o layout da interface do usuário na activity. É um método obrigatório.

2) **`onStart()`**

Esse callback é executado quando o onCreate() termina. Após o onCreate(), a activity entra em um estado de "iniciada" e se torna visível para o usuário.

É aqui que você deve fazer os preparativos finais da activity para ir para o primeiro plano e se tornar interativa com o usuário.

3) **`onResume()`**

O sistema invoca esse callback imediatamente antes de a atividade começar a interagir com o usuário.

A maior parte da funcionalidade principal de um app é implementada no método onResume().

4) **`onPause()`**

O sistema invoca esse callback quando a activity sai de foco. Quando a activity perde o foco, ela entra em um estado "Pausado"

Uma activity no estado "Pausado" pode continuar atualizando a IU se o usuário estiver esperando por isso.

Exemplos de uma dessas atividades incluem a exibição da tela de um mapa de navegação ou de um player de mídia sendo reproduzido. Mesmo que essas atividades percam o foco, o usuário espera que a IU continue sendo atualizada.

Não use _onPause( )_ para salvar dados do app ou do usuário, fazer chamadas de rede ou executar transações de banco de dados.

5) **`onStop()`**
 
O sistema chama onStop() quando a activity não está mais visível para o usuário. Isso pode acontecer porque a atividade está sendo destruída, uma nova atividade está sendo iniciada ou uma atividade existente está entrando em um estado "Retomado" e está cobrindo a atividade interrompida. Em todos esses casos, a atividade interrompida não fica mais visível.

6) **`onDestroy()`**

O sistema invoca esse callback antes de uma atividade ser destruída. Esse é o último callback que a atividade recebe. onDestroy() normalmente é implementado para garantir que todos os recursos de uma atividade sejam liberados quando ela (ou o processo que a contém) for destruída.