# Firebase Helper

~~~ java
public class ConfiguracaoFirebase {

    private DatabaseReference referenciaFirebase;
    private FirebaseAuth referenciaAutenticacao;
    private StorageReference referenciaStorage;

    public DatabaseReference getFirebase(){
        if(referenciaFirebase == null){
            referenciaFirebase = FirebaseDatabase.getInstance().getReference();
        } return referenciaFirebase;
    }

    public FirebaseAuth getFirebaseAutenticacao(){
        if(referenciaAutenticacao== null){
            referenciaAutenticacao = FirebaseAuth.getInstance();
        } return referenciaAutenticacao;
    }

    public StorageReference getFirebaseStorage(){
        if(referenciaStorage == null){
            referenciaStorage = FirebaseStorage.getInstance().getReference();
        } return referenciaStorage;
    }

}
~~~