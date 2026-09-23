# Ejercicio1-David.Mateo.Merida

Actividad: En el README, explica como desarollarias una pequeña aplicacion o juego.

Actividad: cómo desarrollaría esta pequeña aplicación o juego

El jugador controlará un personaje que tendrá que evitar diferentes obstáculos. Cuanto más tiempo consiga sobrevivir, más metros recorrerá y mayor será la velocidad del juego. El objetivo será conseguir la mayor distancia posible sin chocar.

01. Problema, plataforma y lenguaje elegido

Problema: quiero hacer un juego sencillo donde el personaje tenga que esquivar obstáculos que van apareciendo, y donde la dificultad suba sola con el paso del tiempo, sin niveles ni menús complicados. Gana quien más distancia recorra sin chocar.

Plataforma: PC
Lenguaje: Java

Elijo Java porque es un lenguaje que ya conozco un poco, funciona igual en cualquier ordenador (Windows, Mac o Linux) y no necesito instalar nada raro: con tener Java en el ordenador, el juego se puede compilar y ejecutar.

02. Algoritmo o paradigma

Para organizar el código, divido el juego en tres partes, cada una con su propia responsabilidad:

Jugador: controla el movimiento del personaje.
Obstáculo: controla la posición y la velocidad de los obstáculos.
Juego: controla la partida en general: la distancia recorrida, la velocidad actual y si ha habido alguna colisión.

Esto es lo que se llama programación orientada a objetos: en vez de tener todo el código mezclado, cada "cosa" del juego (el jugador, un obstáculo, la partida) es como una pieza independiente con su propio comportamiento, y luego todas esas piezas trabajan juntas.

Cómo funciona el juego paso a paso:

Empieza la partida con una velocidad normal.
Van apareciendo obstáculos que hay que esquivar moviéndose a los lados.
Si el personaje choca con un obstáculo, la partida termina y se pierde.
Si se sigue esquivando sin chocar, la partida continúa y va cada vez más rápido, sumando más metros de distancia.

Este ciclo de "mover, comprobar, dibujar y repetir" se hace muchas veces por segundo (por ejemplo 60 veces por segundo) mientras dura la partida. A esto se le llama el bucle del juego, y es la base de prácticamente cualquier videojuego, por sencillo que sea.


Ejemplo sencillo: los controles

Así es como se maneja el movimiento del personaje. El juego está todo el rato "escuchando" el teclado, y según la tecla que se pulsa, se mueve el jugador a un lado o a otro:

// Cuando se pulsa una tecla
if (tecla == "izquierda" || tecla == "A") {
    jugador.posicionX -= 5;   // se mueve a la izquierda
}

if (tecla == "derecha" || tecla == "D") {
    jugador.posicionX += 5;   // se mueve a la derecha
}
Es así de simple: cada vez que se pulsa una tecla, el personaje suma o resta a su posición, y eso hace que se vea moviéndose por la pantalla.


03. Cómo llega el código a ejecutarse
Escribir el código no es suficiente para poder jugar, hay que seguir unos pasos:

1. Escribo el código en un archivo de texto, por ejemplo Juego.java.
2. Lo traduzco (compilo) con el comando javac Juego.java. El ordenador no entiende directamente lo que escribo, así que este paso lo convierte a un formato que sí puede ejecutar.
3. Lo ejecuto con el comando java Juego. Aquí es donde entra en juego el método main.


Qué hace el main en este juego, paso a paso:
1. Se crea la ventana del juego.
2. Se indica que, si se cierra la ventana, el programa se cierra también
3. Se crea el propio juego (donde está todo lo del punto 02: el jugador, los obstáculos, el bucle...).
4. Ese juego se coloca dentro de la ventana.
5. La ventana se ajusta de tamaño y se muestra en pantalla.
6. Por último, se activa el teclado, para que el jugador ya pueda moverse.

// Color actual (azul)
g2.setColor(new Color(52, 152, 219));

// Para cambiarlo, por ejemplo a verde:
g2.setColor(new Color(46, 204, 113));
Con eso, el cuadrado que controla el jugador cambiaría de color sin tocar nada más del juego.


