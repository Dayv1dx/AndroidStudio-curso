# Encadeamento de métodos

Para utilizar o encadeamento de métodos é necessário que o método anterior retorne um objeto.

~~~ kotlin

class Mensagem(){

    companion object {

        const val DURACAO_CURTA = 0
        const val DURACAO_LONGA = 1

        fun contruirTexto (mensagem: String, duracao: Int): Mensagem {
            return Mensagem
        }
    }

    fun exibir(){
        println("Exibindo mensagem")
    }

fun main(){

    Mensagem.contruirTexto("olá", Mensagem.DURACAO_LONGA).exibir()

}

}