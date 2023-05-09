# Funções como parâmetro

~~~ kotlin 
class Matematica{
    // quando associado a classe é chamado de método
    fun somar (n1: Int, n2: Int): Int {
        return n1 + n2
    }
}
// fora de uma classe é uma função
fun somar (n1: Int, n2: Int): Int {
    return n1 + n2
}
// estrutura para receber uma função como parâmetro
// nome: (Tipo parâmetro 1, Tipo parâmetro 2) -> Tipo retorno
fun calcular ( funcao: (Int, Int) -> Int ){

    val retorno = funcao(10,15)
    println( retorno )

}

fun main (){

    calcular(:: somar)

}
~~~