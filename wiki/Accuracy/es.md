# Precisión

La precisión es una forma de medir la consistencia de un jugador. Hay tres tipos de precision que un jugador puede tener. Una de ellas es la precision del beatmap que depende de los puntajes obtenidos. Otra, es la precision general del jugador, que se mide a partir de sus mejores puntajes, por ultimo la precision [pp](/wiki/pp) del jugador que depende de la precision del puntaje obtenido.

### osu!standard

![Precision = (50 \* numero de 50s + 100 \* numero de 100s + 300 \* numero de 300s) / 300(numero de 0s + numero de 50s + numero de 100s + numero de 300s)](osu-wiki/wiki/Accuracy/img/accuracy_standard.png "Formula de precision para osu!standard")

En osu!standar, la precisión se calcula ponderando el criterio con el que se le da a cada nota por su valor y dividido por la maxima cantidad posible.

Referencias para un "Hit Circle"

```
300 -> 300 / 300 = 1   = 100.00%
100 -> 100 / 300 = 1/3 =  33.00%
50  ->  50 / 300 = 1/6 =  16.67%
0   ->   0 / 300 = 0   =   0.00%
```

### osu!taiko

![Precision = 0.5(numero de GOOD + numero de GREAT) / (numero de BAD + numero de GOOD + numero de GREAT)](img/accuracy_taiko.png "Formula de precision para osu!taiko")

En osu!taiko, la precisión se calcula sumando la precisión de la nota, dividida por el número de notas. La precisión de la nota son las siguientes: Un GREAT (良) cuenta como 100%, GOOD (可) como 50% (mitad), y MISS / BAD (不可) como 0% (El cual también rompe el combo). Los Drum rolls y los spinners no influyen en la precisión.

### osu!catch

![Precision = (numero de gotitas + numero de gotas + numero de frutas) / (numero de gotitas falladas + numero de gotas falladas + numero de frutas falladas + numero de gotitas + numero de gotas + numero de frutas)](img/accuracy_catch.png "Formula de precision para osu!catch")

En osu!catch, la precisión se calcula tomando el total de objetos golpeados no-spiners recogidos, dividido por el número total de objetos no-spiners. Todos los objetos golpeados tienen el mismo valor, a excepción de los plátanos, ya que son parte del spinner

*Nota para los usuarios de API: Para calcular la precisión en osu!catch, el número de gotas está bajo `count50` y el número de gotas perdidas está bajo `countkatu`.*

### osu!mania

![Precision = (50 \* numero de 50s + 100 \* numero de 100s + 200 \* numero de 200s + 300 \* numero de 300s + 300 \* numero de MAXs) / 300(numero de 0s + numero de 50s + numero de 100s + numero de 200s + numero de 300s + numero de MAXs)](img/accuracy_mania.png "Formula de precision para osu!mania")

En osu!mania, la precision es calculada de forma similar a [osu!standard](#osu!standard).

## Gráfico de rendimiento

![Gráfico de rendimiento](img/performance_graph.jpg "Gráfico de rendimiento")

El gráfico de rendimiento es un gráfico que muestra el rendimiento del jugador (basado en su barra de vida) en el transcurso de una jugada (tiempo). Se puede mostrar información adicional al pasar el cursor sobre él.

*Nota: La información adicional solo se puede ver después de reproducir un beatmap o ver una repetición exportada. Después de salir de la [pantalla de resultados](/wiki/results_screen), esta información no se guardará.*

### Precisión

Al pasar el cursor sobre el gráfico de rendimiento, se muestra un mensaje de informacion con *Error* y *Unstable rate*.

Debido a la forma en que se implementan los mods [DT](/ wiki / DT)(Tiempo doble) y [HT](/wiki/HT)(Medio tiempo), los valores de error e inestabilidad se multiplicarán por el mismo factor que la canción. Para obtener los valores verdaderos al jugar DT, divida los resultados por 1.5. Del mismo modo, multiplice los resultados por 1,33 al jugar HT.

#### Error

Error siempre mostrará dos valores que representan cuán lejos estaban los primeros hits en promedio y cuán lejos estaban los hits finales en promedio. Cuanto mayor sea el valor de [Dificultad general](/wiki/Overall_Difficulty) del beatmap, menores tendran que ser los valores de error para tener un buen rendimiento al jugar el beatmap.

#### Unstable rate

Unstable rate representa la consistencia del tiempo de los golpes, donde los números más bajos son mejores (los mejores jugadores a menudo puntúan por debajo de 100). Tenga en cuenta que el valor mide la consistencia, no la precisión, por lo que consistentemente en golpear 15ms temprano es lo mismo que golpear constantemente "a tiempo". La fórmula es esencialmente la desviación estándar de los errores de acierto (en milisegundos) multiplicados por 10.

### Spin

*Nota: Spin solo se usa para [osu!standard](/wiki/osu!standard).*

Además de la precisión, también se ve algo de información sobre los spinners en el mismo mensaje de informacion.

#### Velocidad

La velocidad representa las RPM(revoluciones por minuto) promedio en todos los spinners en el beatmap. Max es el RPM más alto logrado en cualquiera de los spinners del beatmap.

#### Unstable rate

Unstable rate representa el promedio contra la desviación máxima, donde los números más bajos son mejores. La fórmula es desconocida.
