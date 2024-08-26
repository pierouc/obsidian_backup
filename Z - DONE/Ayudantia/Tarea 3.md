
## AULA
# Introducción a los Juegos de Pokémon

Los juegos de Pokémon son una serie de videojuegos desarrollados por Game Freak y publicados por Nintendo y The Pokémon Company. En estos juegos, los jugadores asumen el rol de entrenadores cuyo objetivo es capturar y entrenar criaturas llamadas "pokémon" para competir en batallas contra otros entrenadores y líderes de gimnasio. Los juegos se centran en la exploración, el combate estratégico y la recolección.

Estos son los atributos básicos que se utilizan para calcular cuánto daño hará un ataque en los juegos. Este dataset trata sobre los juegos de Pokémon (NO sobre las cartas de Pokémon ni Pokémon Go).

## Variables del Dataset de Pokémon

Las variables incluidas en el dataset reflejan las características esenciales de los pokémon que son relevantes para el juego:

1. **# (Número)**: Identificación única en la Pokédex.
2. **Name (Nombre)**: Nombre del pokémon.
3. **Type 1 (Tipo 1)**: Tipo principal, determina fortalezas y debilidades.
4. **Type 2 (Tipo 2)**: Tipo secundario, si lo tiene.
5. **Total**: Suma de todas las estadísticas base.
6. **HP**: Puntos de salud, vitalidad en batalla.
7. **Attack (Ataque)**: Fuerza en ataques físicos.
8. **Defense (Defensa)**: Resistencia a ataques físicos.
9. **Sp. Atk (Ataque Especial)**: Fuerza en ataques especiales.
10. **Sp. Def (Defensa Especial)**: Resistencia a ataques especiales.
11. **Speed (Velocidad)**: Determina el orden de ataque en batalla.
12. **Generation (Generación)**: Juego en el que debutó.
13. **Legendary (Legendario)**: Indica si es legendario, afectando su rareza y habilidades únicas.

## Tarea
## KMEANS - KMEDIANS - KMEDOIDS
1. Cargar y verificar integridad de los datos. Realizar curación si corresponde.
2. Graficar matriz de correlación y realizar un scatter_matrix con plotly.
3. Seleccionar los valores del dataset que son de utilidad para entrenar cada modelo.
4. Entrenar un modelo de KMEANS - KMEDIANS - KMEDOIDS y para cada uno de ellos: 
	4.1. Mediante el método del codo, determinar el número de clústeres óptimo, explicar por que lo eligieron, con el gráfico correspondiente.
	4.2. Luego de determinar el número, entrenar  con dicho número y realizar un grafico de radar para cada clúster que muestre todas las variables que utilizó para entrenar utilizando los centroides de cada algoritmo como valor representativo de cada clúster. 
	4.3. Realizar un grafico scatter_matrix con plotly usando como parámetro color la variable clústeres. 
	4.4 Tomar dos variables que prefieran (pero las mismas para comparar los 3 modelos) y graficar con una X el punto del centroide, medoide y median, según corresponda.
5. Sacar conclusiones al respecto:
	5.1 ¿Qué diferencias existen entre los diferentes clústeres que crearon los modelos?. 
	5.2 ¿Tienen sentido las agrupaciones que hizo cada algoritmo? HINT: Recuerde que siempre en los videojuegos siempre hay personajes que aguantan harto y atacan poco, otros que atacan mucho pero resisten poco, etc. 
	5.4 Basándose en la métrica Silhouette y en los resultados visuales obtenidos, ¿Qué modelo realizó mejor el agrupamiento en clústeres?


## AULA
# Resumen del Dataset de Pingüinos

El dataset de pingüinos, conocido como "Penguin Dataset: The New Iris", proporciona datos sobre tres especies de pingüinos (Adelie, Chinstrap, y Gentoo) recolectados en las islas Palmer de la Antártida. Este dataset es utilizado como alternativa al famoso dataset Iris para la enseñanza de técnicas de clasificación, aunque en este caso se utilizará en el ámbito de aprendizaje no supervisado.

#### Variables del Dataset

1. **Species (Especie)**: Especie del pingüino (Adelie, Chinstrap, Gentoo).
2. **Island (Isla)**: Isla donde se recolectaron los datos (Biscoe, Dream, Torgersen).
3. **Culmen Length (Longitud del Pico)**: Longitud del pico en milímetros.
4. **Culmen Depth (Profundidad del Pico)**: Profundidad del pico en milímetros.
5. **Flipper Length (Longitud de Aletas)**: Longitud de las aletas en milímetros.
6. **Body Mass (Masa Corporal)**: Masa corporal en gramos.
7. **Sex (Sexo)**: Sexo del pingüino.
8. **Year (Año)**: Año en el que se recolectaron los datos.

## TAREA
## KNN DBSCAN GAUSSIAN MIXTURE

1. Cargar los datos y verificar integridad de los datos. Realizar curación si corresponde.
2. Crear un scatter_matrix de las variables numéricas reales y con parámetro color igual a la columna species. TIP: Este va a ser la mejor forma de comparar visualmente los modelos entrenados.
3. Estandarizar datos
4. Probar modelo Gaussian Mixture con el numero de clústeres igual a la cantidad de especies de pingüinos. Comparar el accuracy de los resultados, interpretando visualmente a que especie corresponde cada clúster. Para lo anterior, se debe realizar un scatter matrix con el parámetro color igual a los clúster. Imprimir la métrica Sillohuete y matriz de confusión correspondiente. Comente acerca de los resultados. 
5. Entrenar un modelo KNN,
	5.1. Separe train y test con el numero de especies estratificado (prefiera usar el parámetro stratify de train_test_split en vez de hacerlo a mano) . 
	5.2. Realice una búsqueda del mejor n_neighbors en base a la métrica Sillohuete, en un rango de 1 a 30 y grafique los resultados. Si los valores convergen utilice el primer resultado mas alto. 
	5.3 Entrene el modelo con el mejor n_neighbors obtenido. Imprima el mejor valor n_neighbors, métrica Sillohuette de los resultados y accuracy del conjunto de test. 
	5.4 Finalmente encuentre la distancia promedio de los n_neighbors y guardela en una variable llamada 'epsilon'. Esta se usará para ajustar el DBSCAN

2. Entrene un modelo de DBSCAN con el hiperparámetro eps igual a la variable 'epsilon' anteriormente obtenida, ahora basándose en la métrica Sillohuette, pruebe valores de min_samples de 1 a 15 y grafique. Entrene el modelo con el mejor valor y realice un scatter matrix con el parámetro color igual a los clúster. Comente sus Resultados