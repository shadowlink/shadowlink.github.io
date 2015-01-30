---
published: false
---

## Commit [e4c859f7d8](https://github.com/shadowlink/GoProject/commit/e4c859f7d8d1e2896f3e5734a9cc9354044df96a)]

Ha pasado algún tiempo desde la última actualización del blog. Por entonces estaba empezando a implementar cierta lógica de juego pero sin nada concreto. 
A día de hoy la lógica de juego está implementada al 95% mas o menos. El juego ya es totalmente jugable pero queda implementar algunos detalles para que sea 100% jugable.
Lo que falta por implementar es:

- Relojes de partida, como los relojes del ajedrez
- Poder seleccionar grupos de piedras muertos una vez finalizada la partida, esto lo explicaré posteriormente cuando comente el funcionamiento del sistema de recuento de terrirorios.

# Estado del roadmpap

![](http://gyazo.com/03c9368134c57c092f75b96316064108.png)

Como se puede observar, hay varias tareas que han pasado a estar completadas desde la última actualización. Vamos a comentarlas.

## El juego!

Como ya he comentado al inicio, la lógica de juego está practicamente implementada a falta de algunas características. Aún así es posible jugar una partida sin problemas.
Lo mas destacable desde la última vez, que no es poco, es lo siguiente:

- Las cadenas de fichas mueren al ser rodeadas por cadenas del color rival
- Al final de la partida se produce un recuento de terriotorios que asigna puntuaciones a los dos jugadores.

El recuento de territorios se produce cuando el juego termina, es decir, los dos jugadores pasan turno. Tiene este aspecto.

![](http://gyazo.com/dff41120a414a3ca81a1a24a5583d2ae.png)

Se puede ver que el juego reconoce los territorios que estan bajo el dominio de cada color y asigna la puntuación correspondiente en función del número de territorios controlados.
Aunque es un sistema automatizado, existen algunos detalles por pulir. Y es que un ahora mismo si una ficha de otro color esta dentro de un territorio rival, este territorio no se contaría para ninguno de los dos.

Ejemplo: 
![](http://gyazo.com/15c6484fba20b5d901d9c65ed129841b)

Como se puede ver, el territorio es claramente de las fichas negras ya que la ficha blanca no tiene nada que hacer ahí. Sin embargo dado que el sistema, actualmente, busca que los territorios estén libres de fichas rivales, el  recuento no se produce.

Existe una cierta limitación en cuanto a la automatización de estas reglas, ya que este caso es muy claro pero muchas veces no es así y es complicado saber sin ayuda humana cuando unas cadena dentro de otra cadena se considera eliminada o no.

Es por ello que se suele recurrir a poder marcar de forma manual las cadenas muertas y si ambos jugdores estan de acuerdo, se valida.

Por lo general un humano puede saber, en función de su experiencia si una cadena esta muerta o no, un algoritmo quizás debiera realizar muchas combinaciones para poder dilucidar si alguna jugada concreta podría salvar esa cadena. Algo que sería bastante costoso a nivel de procesamiento.

Ejemplo:

![](http://gyazo.com/e41ce27789caf1697c3a68cbd1858cc6.png)

Si la partida acabase aquí ¿diríamos que la cadena de fichas blancas esta muerta? es decir ¿negras tiene alguna posibilidad mediante alguna jugada de matar a la cadena de blancas? Es dificil para un algoritmo decir eso, y lo es para un humano en función de la experiencía que tenga con el juego.
Si siguiesemos jugando se daría esta situación

![](http://gyazo.com/664b46d59a6490cc1777114f58d9755f)

Las blancas se salvan haciendo esos movimientos concretos. Pero ¿Es un algoritmo capaz de predecir eso? Tendría que buscar cualquier posible escenario en el que negras consiguiese ganar ese territorio, lo que como ya he comentado puede ser tremendamente costoso. No por nada el Go es un autentico hueso de roer para la inteligencia artificial.

# Chat

![](http://gyazo.com/07876b7b4a1de222a6696a1a5d733d1a.png)

Y este es el aspecto que presenta ahora mismo la interfaz de una partida. Aún quedan muchos retoques que hacer en cuanto a lo "artístico", pero la base ya está.
Como podemos ver, encontramos elementos nuevos como es el chat!
Ya se puede hablar con tu rival de tablero como en cualquier otro chat.

#Avatares
Como podemos ver en la imagen anterior, ya existen los avatares y son completamente automáticos. Esto es gracias a la ayuda del paquete de meteor llamado "meteor-avatar".
Gracias a este paquete se busca y se inserta automáticamente el avatar que tengamos en nuestras redes sociales o en Gravatar.

## Top List

La lista de partidas ha sido renombrada a Top List. Esta mostrara solo las cuatro partidas mas destacadas del momento. Por ahora muestra las cuatro últimas partidas pero en un futuro y junto a una posible implementación de rangos, se espera que muestre las partidas entre los mas destacados jugadores.

Además podemos ver que ha sufrido un ligero rediseño. Nunca definitivo.
![](http://gyazo.com/4a1178f5f46775ab5bd7d2d1d1350233.png)

##Barra de navegación

Poco a descatar dalvo al incorporación de la nueva lista de partidas y el nombre de usuario deonde antes ponía "Perfil".

![](http://gyazo.com/7f9d7485b360220707cc594f348851db.png)

## Listado de partidas

Tras haber cambiado la funcíon que cumplia nuestro anterior listado de partidas, necesitabamos de otro donde se mostraran las partidas ya de una forma mas ligera y sin previsualizaciones. Esta lista es en la que estoy trabajando en estos momentos, actualmente se encuentra en este estado.

![](http://gyazo.com/4922d9b0df60cfc904e17923d185312b.png)

Falta añadirle opciones de busqueda y filtrado, y quizas alguna cosa mas que estoy barajando, nada definitivo aún.

