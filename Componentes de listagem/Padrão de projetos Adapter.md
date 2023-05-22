# Adpater

~~~ kotlin
package com.dayv1dx.teste2023

class TomadaAntiga(val conector: Conector){
    fun passarEnergia(){
        val qtdPinos = conector.quantidadePinos()
        if( qtdPinos == 2){
            conector.ligaAparelho()
            println("passando energia")
        } else{
            println("Essa tomada só funciona com 2 pinos, você passou: $qtdPinos pinos")
        }

    }
}

class ConectorNovoPadrao : Conector{
    override fun quantidadePinos() : Int {
        return 3
    }

    override fun ligaAparelho(){
        println("aparelho ligado")
    }

}

class ConectorAdaptador( val conectorNovoPadrao: ConectorNovoPadrao) : Conector{
    override fun quantidadePinos(): Int {
        return 2
    }

    override fun ligaAparelho() {
        conectorNovoPadrao.ligaAparelho()
    }
}

interface Conector {
    fun quantidadePinos() : Int
    fun ligaAparelho()
}


fun main(){

    val conector = ConectorNovoPadrao()
    val novoConector = ConectorAdaptador( conector)

    val tomadaAntiga = TomadaAntiga(novoConector)
    tomadaAntiga.passarEnergia()

}
~~~