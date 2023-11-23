# Mario

CODIGO ENEMIGO

open class Enemy(val name: String,val strength: Int) {
protected var direction: String="LEFT"
    protected  fun changeDirection(){
        direction= if (direction=="RIGTH") "LEFT" else "RIGHT"
        println("$name va en direccion $direction")
    }
    protected fun die(){
        println("$name ha muerto y tenia familiawe")
            }
 open   fun collision(collider: String){ //decidir qué acción ejecutar dependiendo del objeto con que se ccolisiona
        when(collider) {
            "Weapon" -> die()
            "Enemy" -> changeDirection()
        }
    }
}

open class Enemy(val name: String,val strength: Int) {
protected var direction: String="LEFT"
    protected  fun changeDirection(){
        direction= if (direction=="RIGTH") "LEFT" else "RIGHT"
        println("$name va en direccion $direction")
    }
    protected fun die(){
        println("$name ha muerto y tenia familiawe")
            }
 open   fun collision(collider: String){ //decidir qué acción ejecutar dependiendo del objeto con que se ccolisiona
        when(collider) {
            "Weapon" -> die()
            "Enemy" -> changeDirection()
        }
    }
}


BOMBA

class Goomba:
    Enemy("Goomba",1)
    {
        init {
            println("Iniciando subclase de $name")
            }
}

class Koopa:
      Enemy("Koopa",2){

    override fun collision(collider:String){
    when(collider){
    "Weapon "->{
        var  state="Shell"
        println("El estado es ahora $state")
    }
        "Enemy"->changeDirection()
}
    }
      }

FUNCION MAIN

fun main(){
            var mario= Mario()
       //     mario.collision("pipe")
         for(i in 1..6 ){
             mario.collision("Gomba")
             println("Te quedan ${mario.vidas}")
         }
        }

class Mario(var vidas: Int=3) {
    init {
        println("Its a me Mario moafoka")
    }
    private var state ="small"
        set(value) {
            field = value
        }
        get()=field
    private var lives=3
    private fun die(){
        lives--
        println("Has perdido una vida que noob")
    }
    fun getLives(): Int {
        return vidas
    }

    public fun collision(collisionObj: String){
        when(collisionObj){
            "Goomba"-> die()
            "super mushroom"-> state="Super mario"
            "Fire flower"-> state= "Fire mario"
            else-> println("Objeto desconocido ¡no pasa nada!")

        }

    }

}
