# AlertDialog

![d](https://www.tutorialkart.com/wp-content/uploads/2018/05/android-alert-dialog-example.png)
~~~ java
public void abrirDialog (){
    // instanciando a AlertDialog
        AlertDialog.Builder sairDialog = new AlertDialog.Builder(this);

    // configurando o título e a mensagem
        dialog.setTitle("Confirmação");
        dialog.setMessage("Deseja sair do aplicativo?");

    /* por default já vem definido "true", onde usuário consegue cancelar a AlertDialog clicando fora dela.
     Já o "false" obriga o usuário a apertar uma das duas opções exibidas na tela. */
        dialog.setCancelable(false);

    // configurando ações para o "sim" e o "não"

        dialog.setPositiveButton("Sim", new DialogInterface.OnClickListener() {
            @Override
            public void onClick(DialogInterface dialog, int which) {
                // ação a ser executada
            }
        });

        dialog.setNegativeButton("Não", new DialogInterface.OnClickListener() {
            @Override
            public void onClick(DialogInterface dialog, int which) {
                // ação a ser executada
                dialog.dismiss();
            }
        });

        // criando e exibindo a AlertDialog
        
        AlertDialog dialog = sairDialog.create();
        dialog.show();
    }