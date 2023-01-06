# Tarefas Assíncronas
 
Class AsyncTask

Ordem de execução dos métodos na AsyncTask

1. `onPreExecute()`
2. `doInBackground()`
3. `onProgressUpdate()`
4. `onPostExecute()`

~~~ java
public class TarefasAssicronas extends AppCompatActivity {

    private ProgressBar progressBar;
    private Button bt_progress;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_tarefas_assicronas);

        progressBar = findViewById(R.id.progressBar);
        bt_progress = findViewById(R.id.bt_progress);

        bt_progress.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                MyAsyncTask task = new MyAsyncTask();
                task.execute(10);
            }
        });
    }

    class MyAsyncTask extends AsyncTask<Integer, Integer, String >{
        /*
         * 1 -> Parâmetro a ser passado para a classe / Void
         * 2 -> Tipo de valor que será utilizado para o progresso da tarefa
         * 3 -> Retorno após tarefa finalizada
         * */
        @Override
        protected void onPreExecute() { // não é recomendado fazer execuções pesadas nesse método
                                        // pois será executado no contexto da thread principal
            super.onPreExecute();
            progressBar.setVisibility(View.VISIBLE);
        }

        @Override
        protected String doInBackground(Integer... integers) { // Vararg em Java (Tipo...nome)
           // é executado em um contexto paralelo e por isso deve executar as tarefas mais pesadas

            int numero = integers[0];
            for (int i = 0 ; i < numero; i++){
                publishProgress(i);
                try {
                    Thread.sleep(1000);
                } catch (InterruptedException e) {
                    e.printStackTrace();
                }
            }
            return "finalizado";
        }

        @Override
        protected void onProgressUpdate(Integer... values) {
            super.onProgressUpdate(values);
            progressBar.setProgress(values[0]);
        }

        @Override
        protected void onPostExecute(String s) {
            super.onPostExecute(s);
            Toast.makeText(TarefasAssicronas.this, s, Toast.LENGTH_SHORT).show();
            progressBar.setProgress(0);
            progressBar.setVisibility(View.INVISIBLE);
        }





    }
}
~~~