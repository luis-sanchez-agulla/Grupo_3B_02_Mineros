
# 4. Configuraciones de Prueba

## 4.1. Prueba 1

### 4.1.1. Configuración de Hiperparámetros

```python
# 500 iteraciones de entrenamiento
# 0.1 de tasa de aprendizaje
# Dimensiones posibles-> combinacion altura:[4]x anchura:[4,5,6,7]
# Radio de vecindad: max(dimensiones)/2
pruebas_SOM(500, 0.1)
```

### 4.1.2. Conclusiones de configuración

Dentro del conjunto de pruebas realizadas con la configuración de hiperparámetros mencionada (500 iteraciones, L.R. 0.1) y enfocadas en dimensiones de orden 4, observamos que las métricas establecidas para la evaluación se mantienen en unos rangos tales que:

- **Métrica EC:** [1.326, 1.340] -> Teniendo el mejor valor dado de este error las redes neuronales con las formas de 4x6 y 6x4. El peor valor de las redes neuronales entrenadas con esta configuración se da en la red neuronal con la forma de 7x4.

- **Métrica ET:** [0.0, 0.0239] -> Teniendo el mejor valor dado de este error la red neuronal entrenada con la forma de 7x4. El peor valor de las redes neuronales entrenadas con esta configuración se da en la red neuronal con la forma de 4x4.

Analizando el trade-off entre las dos métricas, se observa una simetría perfecta entre las configuraciones invertidas (4x5 vs 5x4 y 4x6 vs 6x4). Aunque el mapa 7x4 logra la mayor fidelidad topográfica ($ET = 0$), esto conlleva un ligero incremento en el error de cuantización comparado con los mapas de 24 neuronas (4x6/6x4).

### 4.1.3. Resultados de cada red neuronal

PRUEBA 1/16 | Mapa: 4x4 | Iter: 500 | L.R.: 0.1

Error de cuantización tras 500 iteraciones: 1.3315798856599155
Error topográfico tras 500 iteraciones: 0.023952095808383235
Medida de divergencia tras 500 iteraciones: 4072.4285584999557

PRUEBA 2/16 | Mapa: 4x5 | Iter: 500 | L.R.: 0.1

Error de cuantización tras 500 iteraciones: 1.3323187489737283
Error topográfico tras 500 iteraciones: 0.017964071856287425
Medida de divergencia tras 500 iteraciones: 5465.412553734962

PRUEBA 3/16 | Mapa: 4x6 | Iter: 500 | L.R.: 0.1

Error de cuantización tras 500 iteraciones: 1.326211994711765
Error topográfico tras 500 iteraciones: 0.005988023952095809
Medida de divergencia tras 500 iteraciones: 6887.914913375627

PRUEBA 4/16 | Mapa: 4x7 | Iter: 500 | L.R.: 0.1

Error de cuantización tras 500 iteraciones: 1.3404849531950196
Error topográfico tras 500 iteraciones: 0.0
Medida de divergencia tras 500 iteraciones: 8125.730222582585

PRUEBA 5/16 | Mapa: 5x4 | Iter: 500 | L.R.: 0.1

Error de cuantización tras 500 iteraciones: 1.3323187489737283
Error topográfico tras 500 iteraciones: 0.017964071856287425
Medida de divergencia tras 500 iteraciones: 5465.412553734961

PRUEBA 9/16 | Mapa: 6x4 | Iter: 500 | L.R.: 0.1

Error de cuantización tras 500 iteraciones: 1.326211994711765
Error topográfico tras 500 iteraciones: 0.005988023952095809
Medida de divergencia tras 500 iteraciones: 6887.914913375626

PRUEBA 13/16 | Mapa: 7x4 | Iter: 500 | L.R.: 0.1

Error de cuantización tras 500 iteraciones: 1.3404849531950196
Error topográfico tras 500 iteraciones: 0.0
Medida de divergencia tras 500 iteraciones: 8125.730222582585

#### 4.1.4. Mejor red neuronal encontrada

PRUEBA 3/16 | Mapa: 4x6 | Iter: 500 | L.R.: 0.1

Error de cuantización tras 500 iteraciones: 1.326211994711765
Error topográfico tras 500 iteraciones: 0.005988023952095809
Medida de divergencia tras 500 iteraciones: 6887.914913375627

La mejor red neuronal encontrada en esta configuración de hiperparámetros es la red neuronal entrenada con la forma de 4x6 (o 6x4), dado que es la que presenta el mejor equilibrio en las medidas de error de cuantización, aunque el error topográfico no es el mejor, se mantiene en un rango aceptable y extremadamente bajo (0.005).

## 4.2. Prueba 2

### 4.2.1. Configuración de Hiperparámetros

```python
# 1000 iteraciones de entrenamiento
# 0.5 de tasa de aprendizaje
# Dimensiones posibles-> combinacion altura:[4]x anchura:[4,5,6,7]
# Radio de vecindad: max(dimensiones)/2
pruebas_SOM(1000, 0.5)
```

### 4.2.2. Conclusiones de configuración

Dentro del conjunto de pruebas realizadas con la configuración de hiperparámetros mencionada (1000 iteraciones, L.R. 0.5) y enfocadas en dimensiones de orden 4, observamos que las métricas establecidas para la evaluación se mantienen en unos rangos tales que:

- **Métrica EC:** [1.334, 1.370] -> Teniendo el mejor valor dado de este error la red neuronal con la forma de 4x4. El peor valor de las redes neuronales entrenadas con esta configuración se da en las redes con forma de 4x7 y 7x4.

- **Métrica ET:** [0.011, 0.023] -> Teniendo el mejor valor dado de este error las redes neuronales entrenadas con las formas de 4x5/5x4 y 4x6/6x4. El peor valor se registra en la configuración 4x4.

Analizando el trade-off entre las dos métricas, se observa nuevamente una simetría total entre los mapas invertidos. El mapa 4x4 ofrece la mayor precisión en la representación de los datos (menor EC), pero a costa de duplicar el error topográfico respecto a los mapas de 20 y 24 neuronas.

### 4.2.3. Resultados de cada red neuronal

PRUEBA 1/16 | Mapa: 4x4 | Iter: 1000 | L.R.: 0.5

Error de cuantización tras 1000 iteraciones: 1.334523964841622
Error topográfico tras 1000 iteraciones: 0.023952095808383235
Medida de divergencia tras 1000 iteraciones: 4263.133798858161

PRUEBA 2/16 | Mapa: 4x5 | Iter: 1000 | L.R.: 0.5

Error de cuantización tras 1000 iteraciones: 1.3452532552975476
Error topográfico tras 1000 iteraciones: 0.011976047904191617
Medida de divergencia tras 1000 iteraciones: 5738.530317403285

PRUEBA 3/16 | Mapa: 4x6 | Iter: 1000 | L.R.: 0.5

Error de cuantización tras 1000 iteraciones: 1.3563474894878156
Error topográfico tras 1000 iteraciones: 0.011976047904191617
Medida de divergencia tras 1000 iteraciones: 7065.486017676412

PRUEBA 4/16 | Mapa: 4x7 | Iter: 1000 | L.R.: 0.5

Error de cuantización tras 1000 iteraciones: 1.370257222252679
Error topográfico tras 1000 iteraciones: 0.017964071856287425
Medida de divergencia tras 1000 iteraciones: 8510.60025992372

PRUEBA 5/16 | Mapa: 5x4 | Iter: 1000 | L.R.: 0.5

Error de cuantización tras 1000 iteraciones: 1.3452532552975476
Error topográfico tras 1000 iteraciones: 0.011976047904191617
Medida de divergencia tras 1000 iteraciones: 5738.530317403285

PRUEBA 9/16 | Mapa: 6x4 | Iter: 1000 | L.R.: 0.5

Error de cuantización tras 1000 iteraciones: 1.3563474894878156
Error topográfico tras 1000 iteraciones: 0.011976047904191617
Medida de divergencia tras 1000 iteraciones: 7065.486017676412

PRUEBA 13/16 | Mapa: 7x4 | Iter: 1000 | L.R.: 0.5

Error de cuantización tras 1000 iteraciones: 1.370257222252679
Error topográfico tras 1000 iteraciones: 0.017964071856287425
Medida de divergencia tras 1000 iteraciones: 8510.60025992372

#### 4.2.4. Mejor red neuronal encontrada

PRUEBA 2/16 | Mapa: 4x5 | Iter: 1000 | L.R.: 0.5

Error de cuantización tras 1000 iteraciones: 1.3452532552975476
Error topográfico tras 1000 iteraciones: 0.011976047904191617
Medida de divergencia tras 1000 iteraciones: 5738.530317403285

La mejor red neuronal encontrada en esta configuración de hiperparámetros es la red neuronal entrenada con la forma de 4x5 (o 5x4), dado que es la que presenta el mejor equilibrio en las medidas de error de cuantización, aunque el error topográfico no es el mejor (igualando al de 4x6), permite una mayor precisión con una estructura ligeramente más compacta.

## 4.3. Prueba 3

### 4.3.1. Configuración de Hiperparámetros

```python
# 1500 iteraciones de entrenamiento
# 1 de tasa de aprendizaje
# Dimensiones posibles-> combinacion altura:[4]x anchura:[4,5,6,7]
# Radio de vecindad: max(dimensiones)/2
pruebas_SOM(1500, 1)
```

### 4.3.2. Conclusiones de configuración

Dentro del conjunto de pruebas realizadas con la configuración de hiperparámetros mencionada (1500 iteraciones, L.R. 1) y enfocadas en dimensiones de orden 4, observamos que las métricas establecidas para la evaluación se mantienen en unos rangos tales que:

- **Métrica EC:** [1.398, 1.433] -> Teniendo el mejor valor dado de este error las redes neuronales con las formas de 4x5 y 5x4. El peor valor de las redes neuronales entrenadas con esta configuración se da en las redes con forma de 4x6 y 6x4.

- **Métrica ET:** [0.011, 0.017] -> Teniendo el mejor valor dado de este error la gran mayoría de las configuraciones analizadas (4x5, 4x6, 4x7 y sus inversas). El peor valor de las redes neuronales entrenadas con esta configuración se registra en la red con la forma de 4x4.

Analizando el trade-off entre las dos métricas, se observa que con una tasa de aprendizaje tan alta, los mapas con 20 neuronas (4x5/5x4) logran un rendimiento superior incluso a configuraciones con más unidades, como la 4x6, la cual presenta un error de cuantización inesperadamente más elevado en esta tanda.

### 4.3.3. Resultados de cada red neuronal

PRUEBA 1/16 | Mapa: 4x4 | Iter: 1500 | L.R.: 1

Error de cuantización tras 1500 iteraciones: 1.4118037613916932
Error topográfico tras 1500 iteraciones: 0.017964071856287425
Medida de divergencia tras 1500 iteraciones: 4188.6117191776075

PRUEBA 2/16 | Mapa: 4x5 | Iter: 1500 | L.R.: 1

Error de cuantización tras 1500 iteraciones: 1.3985324998433253
Error topográfico tras 1500 iteraciones: 0.011976047904191617
Medida de divergencia tras 1500 iteraciones: 5730.067472838158

PRUEBA 3/16 | Mapa: 4x6 | Iter: 1500 | L.R.: 1

Error de cuantización tras 1500 iteraciones: 1.4331689611004605
Error topográfico tras 1500 iteraciones: 0.011976047904191617
Medida de divergencia tras 1500 iteraciones: 7048.102235068567

PRUEBA 4/16 | Mapa: 4x7 | Iter: 1500 | L.R.: 1

Error de cuantización tras 1500 iteraciones: 1.400498989218186
Error topográfico tras 1500 iteraciones: 0.011976047904191617
Medida de divergencia tras 1500 iteraciones: 8335.917869703868

PRUEBA 5/16 | Mapa: 5x4 | Iter: 1500 | L.R.: 1

Error de cuantización tras 1500 iteraciones: 1.3985324998433253
Error topográfico tras 1500 iteraciones: 0.011976047904191617
Medida de divergencia tras 1500 iteraciones: 5730.06747283816

PRUEBA 9/16 | Mapa: 6x4 | Iter: 1500 | L.R.: 1

Error de cuantización tras 1500 iteraciones: 1.4331689611004605
Error topográfico tras 1500 iteraciones: 0.011976047904191617
Medida de divergencia tras 1500 iteraciones: 7048.102235068567

PRUEBA 13/16 | Mapa: 7x4 | Iter: 1500 | L.R.: 1

Error de cuantización tras 1500 iteraciones: 1.400498989218186
Error topográfico tras 1500 iteraciones: 0.011976047904191617
Medida de divergencia tras 1500 iteraciones: 8335.917869703866

#### 4.3.4. Mejor red neuronal encontrada

PRUEBA 2/16 | Mapa: 4x5 | Iter: 1500 | L.R.: 1

Error de cuantización tras 1500 iteraciones: 1.3985324998433253
Error topográfico tras 1500 iteraciones: 0.011976047904191617
Medida de divergencia tras 1500 iteraciones: 5730.067472838158

La mejor red neuronal encontrada en esta configuración de hiperparámetros es la red neuronal entrenada con la forma de 4x5 (o 5x4), dado que es la que presenta el mejor equilibrio en las medidas de error de cuantización al obtener el mínimo global de este grupo, manteniendo a su vez un error topográfico en el rango más bajo registrado para esta serie.

## 4.4. Prueba 4

### 4.4.1. Configuración de Hiperparámetros

```python
# 2000 iteraciones de entrenamiento
# 0.01 de tasa de aprendizaje
# Dimensiones posibles-> combinacion altura:[4]x anchura:[4,5,6,7]
# Radio de vecindad: max(dimensiones)/2
pruebas_SOM(2000, 0.01)
```

### 4.4.2. Conclusiones de configuración

Dentro del conjunto de pruebas realizadas con la configuración de hiperparámetros mencionada (2000 iteraciones, L.R. 0.01) y enfocadas en dimensiones de orden 4, observamos que las métricas establecidas para la evaluación se mantienen en unos rangos tales que:

- **Métrica EC:** [1.340, 1.360] -> Teniendo el mejor valor dado de este error la red neuronal con la forma de 6x4. El peor valor de las redes neuronales entrenadas con esta configuración se da en la red neuronal con la forma de 4x6.

- **Métrica ET:** [0.0, 0.023] -> Teniendo el mejor valor dado de este error (perfección topográfica) la mayoría de las configuraciones, incluyendo 4x6, 4x7, 5x4, 6x4 y 7x4. El peor valor de las redes neuronales entrenadas con esta configuración se da en la red neuronal con la forma de 4x4.

Analizando el trade-off entre las dos métricas, se observa que el incremento en el número de iteraciones junto a una tasa de aprendizaje baja ha favorecido enormemente la convergencia topográfica, permitiendo que casi todas las redes alcancen un error topográfico nulo. En este escenario, la red 6x4 destaca al lograr este nivel de fidelidad junto con el error de cuantización más bajo del grupo.

### 4.4.3. Resultados de cada red neuronal

PRUEBA 1/16 | Mapa: 4x4 | Iter: 2000 | L.R.: 0.01

Error de cuantización tras 2000 iteraciones: 1.3416821230440057
Error topográfico tras 2000 iteraciones: 0.023952095808383235
Medida de divergencia tras 2000 iteraciones: 4076.706558544734

PRUEBA 2/16 | Mapa: 4x5 | Iter: 2000 | L.R.: 0.01

Error de cuantización tras 2000 iteraciones: 1.3410944289998428
Error topográfico tras 2000 iteraciones: 0.017964071856287425
Medida de divergencia tras 2000 iteraciones: 5458.061333564971

PRUEBA 3/16 | Mapa: 4x6 | Iter: 2000 | L.R.: 0.01

Error de cuantización tras 2000 iteraciones: 1.3601458259108283
Error topográfico tras 2000 iteraciones: 0.0
Medida de divergencia tras 2000 iteraciones: 6956.165851159923

PRUEBA 4/16 | Mapa: 4x7 | Iter: 2000 | L.R.: 0.01

Error de cuantización tras 2000 iteraciones: 1.3469513137932485
Error topográfico tras 2000 iteraciones: 0.0
Medida de divergencia tras 2000 iteraciones: 8134.448714457917

PRUEBA 5/16 | Mapa: 5x4 | Iter: 2000 | L.R.: 0.01

Error de cuantización tras 2000 iteraciones: 1.3419583821245997
Error topográfico tras 2000 iteraciones: 0.0
Medida de divergencia tras 2000 iteraciones: 5510.6229135774265

PRUEBA 9/16 | Mapa: 6x4 | Iter: 2000 | L.R.: 0.01

Error de cuantización tras 2000 iteraciones: 1.3404306766782823
Error topográfico tras 2000 iteraciones: 0.0
Medida de divergencia tras 2000 iteraciones: 6829.079613417973

PRUEBA 13/16 | Mapa: 7x4 | Iter: 2000 | L.R.: 0.01

Error de cuantización tras 2000 iteraciones: 1.3469513137932485
Error topográfico tras 2000 iteraciones: 0.0
Medida de divergencia tras 2000 iteraciones: 8134.448714457917

#### 4.4.4. Mejor red neuronal encontrada

PRUEBA 9/16 | Mapa: 6x4 | Iter: 2000 | L.R.: 0.01

Error de cuantización tras 2000 iteraciones: 1.3404306766782823
Error topográfico tras 2000 iteraciones: 0.0
Medida de divergencia tras 2000 iteraciones: 6829.079613417973

La mejor red neuronal encontrada en esta configuración de hiperparámetros es la red neuronal entrenada con la forma de 6x4, dado que es la que presenta el mejor equilibrio en las medidas de error de cuantización, aunque el error topográfico no es el único en ser cero, es la que mejor minimiza la pérdida de información sin sacrificar la estructura del mapa.
