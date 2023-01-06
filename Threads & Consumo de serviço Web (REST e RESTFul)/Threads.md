# Threads no Android

Toda vez que um app é executado, isso é feito dentro de um `processo`.

**Thread** é um pequeno programa que trabalha como um subsistema, sendo uma forma de um `processo` se auto dividir em duas ou mais tarefas.

Ao criar novas `Threads` é possível executar tarefas em paralelo enquanto o usuário utiliza a `UI thread` sem erros no aplicativo.

``` java
public class MainActivity extends AppCompatActivity {

    private Button bt_iniciar;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        bt_iniciar = findViewById(R.id.bt_iniciar);

        // instanciado e inicializando a nova thread
        MyThread myThread = new MyThread();

        bt_iniciar.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                myThread.start();
            }
        });
    }

    class MyThread extends Thread{
        // Ao criar a nossa thread, ela não será executada na principal (UI thread) evitando erros no app.
        @Override
        public void run() {
            for(int i = 0 ; i<=10; i++){
                Log.d("thread","contador:" + i);
                try {
                    Thread.sleep(2000);
                } catch (InterruptedException e) {
                    e.printStackTrace();
                }
            }
        }
    }
}
```

## Executando alterações na UI Thread

Não é possível criar alterações na interface (UI) dentro de uma `thread` criada. É necessário mexer diretamente na `UI thread`.

Com o método `runOnUiThread` é possível adicionar uma fila de execução na Thread principal.

~~~ java
public class MainActivity extends AppCompatActivity {

    private Button bt_iniciar, bt_parar;
    private int numero;
    private Boolean pararExecução = false;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        bt_iniciar = findViewById(R.id.bt_iniciar);
        bt_parar = findViewById(R.id.bt_parar);

        // instanciado a nova thread (2nd FORMA)
        Runnable myRunnable = new Runnable();


        bt_iniciar.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // inicializando a nova thread (2nd FORMA)
                new Thread(myRunnable).start();
                pararExecução = false;

            }
        });

        bt_parar.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                pararExecução = true;
            }
        });
    }

   class Runnable implements java.lang.Runnable{
       @Override
       public void run() {
           for(int i = 0 ; i<=10; i++){

               if(pararExecução.equals(true))
                   return;

               numero = i;
               Log.d("thread","contador:" + i);

               runOnUiThread(new Runnable() {
                   @Override
                   public void run() {
                       bt_iniciar.setText("contador:" + numero);
                   }
               });

               try {
                   Thread.sleep(2000);
               } catch (InterruptedException e) {
                   e.printStackTrace();
               }
           }
       }
   }
}
~~~ 