## O que é o Firebase?

É uma plataforma poderosa para armazenamento e sincronismo de dados em tempo real, um sistema de Back-End.

## Como funciona o armazenamento?

- Banco de dados NoSQL
> NoSQL é um termo genérico que representa os bancos de dados não relacionais. Uma classe definida de banco de dados que fornecem um mecanismo para armazenamento e recuperação de dados que são modelados de formas diferentes das relações tabulares usadas nos bancos de dados relacionais.

Estrutura dos dados:

![i](https://kodular-community.s3.dualstack.eu-west-1.amazonaws.com/optimized/3X/0/1/011597289fe38ed93658c24ce2d531dc71fde38b_2_401x500.jpeg)

## Salvando e atualizando dados

## Storage

- Link para a Documentação com os [primeiros passos.](https://firebase.google.com/docs/storage/android/start?hl=pt&authuser=0)
- Link para a Documentação sobre [fazer upload de arquivos.](https://firebase.google.com/docs/storage/android/upload-files?hl=pt&authuser=0)


Para o upload de arquivos é necessário:

1. adicionar o SDK do Cloud Storage no seu app:

~~~ java

dependencies {
    // Import the BoM for the Firebase platform
    implementation platform('com.google.firebase:firebase-bom:30.3.1')

    // Declare the dependency for the Cloud Storage library
    // When using the BoM, you don't specify versions in Firebase library dependencies
    implementation 'com.google.firebase:firebase-storage'
} 
~~~

2. Configurar o Cloud Storage

~~~ java
 FirebaseStorage storage = FirebaseStorage.getInstance();
~~~

Exemplo de upload de uma imagem:

~~~ java

// Configura para a imagem ser salva em memória
imagemFoto.setDrawingCacheEnabled(true);
imagemFoto.biuldDrawingCache();

// Recupera bitmap da imagem (imagem a ser carregada)
Bitmap bitmap = imagem foto.getDrawingCache()

// Comprimir bitmap para um formato png/jpeg
ByteArrayOutpuStream baos = new ByteArrayOutpuStream ();
bitmap.compress(Bitmap.CompressFormat.JPEG, 75, baos ) // (formato, qualidade de 0 a 100)

// converte o baos para pixel brutos em uma matriz de bytes
// dados da imagem

byte[] dadosImagem = baos.toByteArray();

// Define nós para o Storage
StorageReference storeReference = FirebaseStorage.getInstance()
StorageReference imagens = storeReference.child("imagens") // criando a pasta
StorageReference imagemRef = imagens.child("exemplo.jpeg")

// Retorna objeto que irá controlar o upload
UploadTask uploadTask = imagemRef.putBytes (dadosImagem);
imagemRef.getDownloadUrl().addOnCompleteListener( new OnCompleteListener(){
    Uri url = task.getResult();
    Toast.makeText(getApplicationContext(), "Sucesso ao fazer upload", Toast.LENGTH_SHORT).show();
});
~~~