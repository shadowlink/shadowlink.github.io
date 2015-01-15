---
published: false
---

## Build [[d170f9f]](https://github.com/shadowlink/GoProject/commit/d170f9f2a5ec70b3f422c4aa3c70aadae13d2a61)

Tras unos meses en blanco retomo he retomado el desarrollo del proyecto a un ritmo normal. La build actual viene cargada de varias mejoras en la gestión de las partidas como ahora veremos.

Hasta ahora podiamos crear partidas y poner fichas como prueba de concepto del tablero.
Estos últimos dias he estado trabajando en implementar una lógica de juego, empezado por la gestión de turnos una vez en la partida y tambíen la forma en la que los jugadores entran en ellas.

Por lo tanto los avances son los siguientes:

- Los jugadores no pueden crear mas partidas si ya se encuentran en una
- Los jugadors pueden observar otras partidas mientras juegan la suya propia
- Los jugadores pueden entrar a jugar en partidas donde aun no haya un segundo jugador
- Si una partida está llena, cualquiera puede entrar a observar, este logueado en la web o no. Naturalmente, no puede participar en el juego, solo mirar.
- Por defecto el jugador 1 es el creador de la partida
- Cuando se crea una partida, se redirecciona automaticamente a la misma
- Por defecto el jugador 1 juega negras y el jugador 2 juega blancas (Esto cambiará en el futuro)
- Una vez en partida se sigue un orden de turnos
- Ya aparecen los nombres de los jugadores en las partidas y en el listado de partidas

Se han añadido ciertos indicadores visuales que muestran el estado de una partida

![](http://gyazo.com/83fd0a9293a840c4b1a375dfad945a3a.png)

En este caso la partida ya tiene un jugador pero está abierta a que otro jugador entre en ella.
![](http://gyazo.com/c289bbe9abbffd06fd5c215dc65c7390.png)

Aquí vemos como la partida esta completa y nos indica que es nuestra partida.

![](http://gyazo.com/004cbdb19cea613a960fede23e0c0bb9.png)

Además vemos como en el menu superior aparece un acceso directo a nuestra partida actual.

![](http://gyazo.com/6d95b99566757089c7ecaeb1c9ce39d4.png)

Como vemos, ya podemos jugar tanto con piezas blancas como con piezas negras.

### Estado del roadmap

![](http://gyazo.com/b2ede4b634bca86674b1f264140336bf.png)

Lo siguiente ya es seguir desarrollando la lógica de juego, la cual tengo ya un poco adelantada en cuanto a generación y detección de cadenas de fichas muertas, por lo que en breves habrá novedades en este sentido.








