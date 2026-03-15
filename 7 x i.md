
# 4. Configuraciones de Prueba

## 4.1. Prueba 1

### 4.1.1. Configuración de Hiperparámetros

```python
# 500 iteraciones de entrenamiento
# 0.01 de tasa de aprendizaje
# Dimensiones posibles -> combinacion altura:[7] x anchura:[4, 5, 6, 7]
# Radio de vecindad: max(dimensiones)/2
pruebas_SOM(500, 0.01)
```

### 4.1.2. Conclusiones de configuración

Dentro del conjunto de pruebas realizadas con la configuración de hiperparámetros mencionada (500 iteraciones, L.R. 0.01) y enfocadas en dimensiones de orden 7, observamos que las métricas establecidas para la evaluación se mantienen en los siguientes rangos:

- **Métrica EC**: [1.217, 1.351] -> El mejor valor de este error lo presenta la red neuronal con forma de 7x7. El peor valor de las redes entrenadas con esta configuración se da en la red neuronal con forma de 7x4.

- **Métrica ET**: [0.0, 0.023] -> El mejor valor (perfección topográfica) se alcanza en las configuraciones 4x7 y 7x7. El peor valor de las redes entrenadas en este bloque se da en la red con forma de 5x7.

Analizando el trade-off entre las métricas, se observa que al aumentar el número total de neuronas (hasta 49 en el caso de la 7x7), el error de cuantización experimenta una mejora significativa respecto a bloques anteriores, situándose por debajo de 1.22. Es notable que, a pesar de haber reducido el número de iteraciones a 500, la mayor resolución del mapa permite una representación más fina del espacio de entrada, logrando en varios casos un error topográfico nulo.

### 4.1.3. Resultados de cada red neuronal

PRUEBA 4/16 | Mapa: 4x7 | Iter: 500 | L.R.: 0.01

Error de cuantización tras 500 iteraciones: 1.348817823737043
Error topográfico tras 500 iteraciones: 0.0
Medida de divergencia tras 500 iteraciones: 8139.846268369206

PRUEBA 8/16 | Mapa: 5x7 | Iter: 500 | L.R.: 0.01

Error de cuantización tras 500 iteraciones: 1.3382832017032025
Error topográfico tras 500 iteraciones: 0.023952095808383235
Medida de divergencia tras 500 iteraciones: 9707.84450419021

PRUEBA 12/16 | Mapa: 6x7 | Iter: 500 | L.R.: 0.01

Error de cuantización tras 500 iteraciones: 1.2440719134614988
Error topográfico tras 500 iteraciones: 0.005988023952095809
Medida de divergencia tras 500 iteraciones: 10739.28040316173

PRUEBA 13/16 | Mapa: 7x4 | Iter: 500 | L.R.: 0.01

Error de cuantización tras 500 iteraciones: 1.3518224802889631
Error topográfico tras 500 iteraciones: 0.005988023952095809
Medida de divergencia tras 500 iteraciones: 8106.802038680977

PRUEBA 14/16 | Mapa: 7x5 | Iter: 500 | L.R.: 0.01

Error de cuantización tras 500 iteraciones: 1.2950908951104045
Error topográfico tras 500 iteraciones: 0.005988023952095809
Medida de divergencia tras 500 iteraciones: 9565.954620915301

PRUEBA 15/16 | Mapa: 7x6 | Iter: 500 | L.R.: 0.01

Error de cuantización tras 500 iteraciones: 1.2531766371317048
Error topográfico tras 500 iteraciones: 0.005988023952095809
Medida de divergencia tras 500 iteraciones: 10672.30167652269

PRUEBA 16/16 | Mapa: 7x7 | Iter: 500 | L.R.: 0.01

Error de cuantización tras 500 iteraciones: 1.217979656198678
Error topográfico tras 500 iteraciones: 0.0
Medida de divergencia tras 500 iteraciones: 11554.560142262011

### 4.1.4. Mejor red neuronal encontrada

PRUEBA 16/16 | Mapa: 7x7 | Iter: 500 | L.R.: 0.01

Error de cuantización tras 500 iteraciones: 1.217979656198678
Error topográfico tras 500 iteraciones: 0.0
Medida de divergencia tras 500 iteraciones: 11554.560142262011

La mejor red neuronal encontrada en esta configuración de hiperparámetros es la red neuronal entrenada con la forma de 7x7, dado que es la que presenta el rendimiento superior absoluto. No solo logra minimizar la pérdida de información al obtener el error de cuantización más bajo registrado hasta el momento (1.2179), sino que además garantiza una preservación estructural perfecta de los datos con un error topográfico de 0.0.

## 4.1 Prueba 2

```python
    # 1000 iteraciones de entrenamiento
    # 0.1 de tasa de aprendizaje
    # Dimensiones posibles -> combinacion altura:[7] x anchura:[4, 5, 6, 7]
    # Radio de vecindad: sigma fijo = 1
    pruebas_SOM(1000, 0.1)
```

### 4.2.2. Conclusiones de configuración

Dentro del conjunto de pruebas realizadas con la configuración de hiperparámetros mencionada (1000 iteraciones, L.R. 0.1) y dimensiones vinculadas al orden 7, observamos que las métricas de evaluación se sitúan en los siguientes rangos:

- **Métrica EC**: [1.179, 1.346] -> El mejor valor de este error lo alcanza la red neuronal con forma de 7x7. El peor valor se da en las configuraciones simétricas de 4x7 y 7x4.

- **Métrica ET**: [0.0, 0.011] -> La perfección topográfica se logra en las redes 5x7, 6x7, 7x5 y 7x6. El peor valor (mayor distorsión) se presenta curiosamente en la red de mayor tamaño, la 7x7.

Analizando el trade-off entre las dos métricas, se observa que el aumento de la tasa de aprendizaje a 0.1 junto con las 1000 iteraciones ha permitido que los errores de cuantización sean los más bajos de todo el estudio (rompiendo la barrera del 1.18). Sin embargo, en la red de 7x7, esta mayor agresividad en el aprendizaje ha provocado un ligero error topográfico (0.011), lo que sugiere que para mapas de mayor densidad, un L.R. tan alto podría dificultar el despliegue perfectamente ordenado de las neuronas.

### 4.2.3. Resultados de cada red neuronal

PRUEBA 4/16 | Mapa: 4x7 | Iter: 1000 | L.R.: 0.1

Error de cuantización tras 1000 iteraciones: 1.3461153462367312
Error topográfico tras 1000 iteraciones: 0.005988023952095809
Medida de divergencia tras 1000 iteraciones: 8201.471710478516

PRUEBA 8/16 | Mapa: 5x7 | Iter: 1000 | L.R.: 0.1

Error de cuantización tras 1000 iteraciones: 1.2828238560573535
Error topográfico tras 1000 iteraciones: 0.0
Medida de divergencia tras 1000 iteraciones: 9642.745098603658

PRUEBA 12/16 | Mapa: 6x7 | Iter: 1000 | L.R.: 0.1

Error de cuantización tras 1000 iteraciones: 1.2411903571311258
Error topográfico tras 1000 iteraciones: 0.0
Medida de divergencia tras 1000 iteraciones: 10868.374002202541

PRUEBA 13/16 | Mapa: 7x4 | Iter: 1000 | L.R.: 0.1

Error de cuantización tras 1000 iteraciones: 1.3461153462367312
Error topográfico tras 1000 iteraciones: 0.005988023952095809
Medida de divergencia tras 1000 iteraciones: 8201.471710478516

PRUEBA 14/16 | Mapa: 7x5 | Iter: 1000 | L.R.: 0.1

Error de cuantización tras 1000 iteraciones: 1.2828238560573535
Error topográfico tras 1000 iteraciones: 0.0
Medida de divergencia tras 1000 iteraciones: 9642.74509860366

PRUEBA 15/16 | Mapa: 7x6 | Iter: 1000 | L.R.: 0.1

Error de cuantización tras 1000 iteraciones: 1.2233058475768779
Error topográfico tras 1000 iteraciones: 0.0
Medida de divergencia tras 1000 iteraciones: 10954.950231922921

PRUEBA 16/16 | Mapa: 7x7 | Iter: 1000 | L.R.: 0.1

Error de cuantización tras 1000 iteraciones: 1.1797949455201076
Error topográfico tras 1000 iteraciones: 0.011976047904191617
Medida de divergencia tras 1000 iteraciones: 11726.467038116582

### 4.2.4. Mejor red neuronal encontrada

PRUEBA 15/16 | Mapa: 7x6 | Iter: 1000 | L.R.: 0.1

Error de cuantización tras 1000 iteraciones: 1.2233058475768779
Error topográfico tras 1000 iteraciones: 0.0
Medida de divergencia tras 1000 iteraciones: 10954.950231922921

La mejor red neuronal encontrada en esta configuración es la red con forma de 7x6, ya que presenta el equilibrio óptimo entre precisión y estructura. Logra un error de cuantización sumamente bajo (1.2233) manteniendo un error topográfico nulo. Aunque la red 7x7 ofrece un error de cuantización ligeramente inferior, la 7x6 garantiza una fidelidad topográfica total, siendo la opción más fiable para representar la variedad de los datos sin generar discontinuidades en el mapa.

## 4.3. Prueba 3

### 4.3.1. Configuración de Hiperparámetros

```python
# 1500 iteraciones de entrenamiento
# 0.5 de tasa de aprendizaje
# Dimensiones posibles -> combinacion altura:[7] x anchura:[4, 5, 6, 7]
# Radio de vecindad: sigma fijo = 1
pruebas_SOM(1500, 0.5)
```

### 4.3.2. Conclusiones de configuración

Dentro del conjunto de pruebas realizadas con la configuración de hiperparámetros mencionada (1500 iteraciones, L.R. 0.5) y dimensiones de orden 7, observamos que las métricas de evaluación se sitúan en los siguientes rangos:

- **Métrica EC**: [1.191, 1.365] -> El mejor valor de este error vuelve a darlo la red 7x7. El peor valor se encuentra en las redes 4x7 y 7x4.

- **Métrica ET**: [0.005, 0.017] -> En esta configuración ninguna red ha logrado la perfección topográfica (0.0). El mejor valor (menor error) se da en las redes de 5x7, 7x5, 6x7 y 7x6. El peor valor aparece en la red 7x7.

Analizando el trade-off entre las dos métricas, se evidencia que una tasa de aprendizaje tan elevada (0.5) junto con un número alto de iteraciones es contraproducente para la estructura del mapa. Aunque el error de cuantización en la red 7x7 sigue siendo muy bajo (1.191), el error topográfico ha subido a su punto máximo (0.017). Esto indica que la red está intentando ajustarse tanto a los datos individuales (overfitting local) que termina "rompiendo" la continuidad de la malla.

### 4.3.3. Resultados de cada red neuronal

PRUEBA 4/16 | Mapa: 4x7 | Iter: 1500 | L.R.: 0.5

Error de cuantización tras 1500 iteraciones: 1.3652841639304267
Error topográfico tras 1500 iteraciones: 0.011976047904191617
Medida de divergencia tras 1500 iteraciones: 8192.077596979001

PRUEBA 8/16 | Mapa: 5x7 | Iter: 1500 | L.R.: 0.5

Error de cuantización tras 1500 iteraciones: 1.3387929849893536
Error topográfico tras 1500 iteraciones: 0.005988023952095809
Medida de divergencia tras 1500 iteraciones: 9564.050641474189

PRUEBA 12/16 | Mapa: 6x7 | Iter: 1500 | L.R.: 0.5

Error de cuantización tras 1500 iteraciones: 1.250140814954152
Error topográfico tras 1500 iteraciones: 0.005988023952095809
Medida de divergencia tras 1500 iteraciones: 11074.589901905114

PRUEBA 13/16 | Mapa: 7x4 | Iter: 1500 | L.R.: 0.5

Error de cuantización tras 1500 iteraciones: 1.3652841639304267
Error topográfico tras 1500 iteraciones: 0.011976047904191617
Medida de divergencia tras 1500 iteraciones: 8192.077596979

PRUEBA 14/16 | Mapa: 7x5 | Iter: 1500 | L.R.: 0.5

Error de cuantización tras 1500 iteraciones: 1.3387929849893536
Error topográfico tras 1500 iteraciones: 0.005988023952095809
Medida de divergencia tras 1500 iteraciones: 9564.050641474189

PRUEBA 15/16 | Mapa: 7x6 | Iter: 1500 | L.R.: 0.5

Error de cuantización tras 1500 iteraciones: 1.250140814954152
Error topográfico tras 1500 iteraciones: 0.005988023952095809
Medida de divergencia tras 1500 iteraciones: 11074.589901905114

PRUEBA 16/16 | Mapa: 7x7 | Iter: 1500 | L.R.: 0.5

Error de cuantización tras 1500 iteraciones: 1.191348823585386
Error topográfico tras 1500 iteraciones: 0.017964071856287425
Medida de divergencia tras 1500 iteraciones: 12032.670943247931

### 4.3.4. Mejor red neuronal encontrada

PRUEBA 12/16 | Mapa: 6x7 | Iter: 1500 | L.R.: 0.5

Error de cuantización tras 1500 iteraciones: 1.250140814954152
Error topográfico tras 1500 iteraciones: 0.005988023952095809
Medida de divergencia tras 1500 iteraciones: 11074.589901905114

La mejor red neuronal encontrada en esta configuración es la red con forma de 6x7 (o su simétrica 7x6). A pesar de que no alcanzan el error topográfico nulo, presentan el mejor equilibrio con un error de cuantización de 1.2501 y el error topográfico más bajo del grupo (0.0059). Se descarta la 7x7 en este escenario debido a que el incremento en la precisión de cuantización no compensa la notable pérdida de coherencia topográfica producida por el alto L.R.

## 4.4. Prueba 4

### 4.4.1. Configuración de Hiperparámetros

```python
# 2000 iteraciones de entrenamiento
# 1 de tasa de aprendizaje
# Dimensiones posibles -> combinacion altura:[7] x anchura:[4, 5, 6, 7]
# Radio de vecindad: sigma fijo = 1
pruebas_SOM(2000, 1)
```

### 4.4.2. Conclusiones de configuración

Dentro del conjunto de pruebas realizadas con la configuración de hiperparámetros mencionada (2000 iteraciones, L.R. 1) y dimensiones de orden 7, observamos que las métricas de evaluación se sitúan en los siguientes rangos:

- **Métrica EC**: [1.289, 1.450] -> El mejor valor lo da la red 7x7. Sin embargo, es notable que estos errores son mucho más altos que en configuraciones con menor L.R., lo que indica que la red no logra "asentarse" debido a una tasa de aprendizaje demasiado agresiva.

- **Métrica ET**: [0.0, 0.035] -> Solo las redes más pequeñas (4x7 y 7x4) mantienen la perfección topográfica. En la red 7x7, el error topográfico se dispara a 0.035, el valor más alto registrado en todo el estudio.

Analizando el trade-off entre las dos métricas, se evidencia un fenómeno de inestabilidad por hiperparámetros. Al fijar el L.R. en 1, las neuronas realizan desplazamientos demasiado bruscos. Esto impide que la red minimice el error de cuantización de forma efectiva y "rompe" la malla topográfica en cuanto el mapa gana complejidad (a partir de 5x7). La simetría vuelve a ser total en los resultados, confirmando la consistencia del algoritmo incluso en condiciones de baja eficiencia.

### 4.4.3. Resultados de cada red neuronal

PRUEBA 4/16 | Mapa: 4x7 | Iter: 2000 | L.R.: 1

Error de cuantización tras 2000 iteraciones: 1.450602809459048
Error topográfico tras 2000 iteraciones: 0.0
Medida de divergencia tras 2000 iteraciones: 8171.29492701887

PRUEBA 8/16 | Mapa: 5x7 | Iter: 2000 | L.R.: 1

Error de cuantización tras 2000 iteraciones: 1.40881217921135
Error topográfico tras 2000 iteraciones: 0.023952095808383235
Medida de divergencia tras 2000 iteraciones: 9471.89591677154

PRUEBA 12/16 | Mapa: 6x7 | Iter: 2000 | L.R.: 1

Error de cuantización tras 2000 iteraciones: 1.3423515798000127
Error topográfico tras 2000 iteraciones: 0.029940119760479042
Medida de divergencia tras 2000 iteraciones: 10728.451974495832

PRUEBA 13/16 | Mapa: 7x4 | Iter: 2000 | L.R.: 1

Error de cuantización tras 2000 iteraciones: 1.450602809459048
Error topográfico tras 2000 iteraciones: 0.0
Medida de divergencia tras 2000 iteraciones: 8171.29492701887

PRUEBA 14/16 | Mapa: 7x5 | Iter: 2000 | L.R.: 1

Error de cuantización tras 2000 iteraciones: 1.40881217921135
Error topográfico tras 2000 iteraciones: 0.023952095808383235
Medida de divergencia tras 2000 iteraciones: 9471.89591677154

PRUEBA 15/16 | Mapa: 7x6 | Iter: 2000 | L.R.: 1

Error de cuantización tras 2000 iteraciones: 1.3423515798000127
Error topográfico tras 2000 iteraciones: 0.029940119760479042
Medida de divergencia tras 2000 iteraciones: 10728.45197449583

PRUEBA 16/16 | Mapa: 7x7 | Iter: 2000 | L.R.: 1

Error de cuantización tras 2000 iteraciones: 1.2896541108531563
Error topográfico tras 2000 iteraciones: 0.03592814371257485
Medida de divergencia tras 2000 iteraciones: 11558.956166054006

### 4.4.4. Mejor red neuronal encontrada

PRUEBA 4/16 | Mapa: 4x7 | Iter: 2000 | L.R.: 1

Error de cuantización tras 2000 iteraciones: 1.450602809459048
Error topográfico tras 2000 iteraciones: 0.0
Medida de divergencia tras 2000 iteraciones: 8171.29492701887

La mejor red neuronal encontrada en esta configuración es la red con forma de 4x7 (o su simétrica 7x4). Aunque presenta un error de cuantización elevado (1.4506), es la única capaz de absorber el impacto de un L.R. de 1 sin perder la estructura del mapa (ET: 0.0). En este caso, la simplicidad del mapa actúa como un mecanismo de defensa contra el ruido introducido por la tasa de aprendizaje, siendo preferible un mapa estable aunque sea menos preciso que un mapa denso (7x7) con una topología gravemente distorsionada.
