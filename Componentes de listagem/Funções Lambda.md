# Funções Lambda

É uma função "mais curta", feita para ser utilizada como parâmetro e que tem apenas o bloco de execução.

~~~ kotlin
class Botao{
    // Unit é tipo de retorno padrão
    fun configurarClique( funcao: () -> Unit){
        funcao()
    }
}

fun main() {

    //função lambda
    val funcaoLambda = 
    { nome: String, idade: Int -> // passando parâmetro para a função lambda
        println("Executar nome: $nome, idade: $idade")
    }

    funcaoLambda()

val botao = Botao()
botao.configurarClique { println("Executar nome: $nome, idade: $idade")
 }

}
~~~