
# 4. Configuraciones de Prueba

## 4.1. Prueba 1

### 4.1.1. Configuración de Hiperparámetros

```python
# 500 iteraciones de entrenamiento
# 0.01 de tasa de aprendizaje
# Dimensiones posibles-> combinacion altura:[5]x anchura:[4,5,6,7]
# Radio de vecindad: max(dimensiones)/2
pruebas_SOM(500, 0.01)
```

### 4.1.2. Conclusiones de configuración

Dentro del conjunto de pruebas realizadas con la configuración de hiperparámetros mencionada (L.R. 0.01), observamos que las métricas establecidas para la evaluación se mantienen en unos rangos tales que:

- **Métrica EC:** [1.866, 1.901] -> El mejor valor de este error lo da la red con forma 5x4, mientras que el peor se da en la configuración 4x5.

- **Métrica ET:** [0.0, 0.011] -> El mejor valor absoluto (perfección topográfica) se alcanza en la red 5x4, mientras que la red 4x5 presenta un error ligeramente superior.

Analizando el trade-off entre ambas métricas, vemos que en esta configuración de baja tasa de aprendizaje, la red 5x4 domina en ambos aspectos, no presentando conflicto entre precisión y topología.

### 4.1.3. Resultados de cada red neuronal

PRUEBA 1/16 | Mapa: 4x5 | Iter: 500 | L.R.: 0.01

Error de cuantización tras 500 iteraciones: 1.901948624757941
Error topográfico tras 500 iteraciones: 0.011976047904191617
Medida de divergencia tras 500 iteraciones: 5271.9777047027665

PRUEBA 2/16 | Mapa: 5x4 | Iter: 500 | L.R.: 0.01

Error de cuantización tras 500 iteraciones: 1.8660993449003709
Error topográfico tras 500 iteraciones: 0.0
Medida de divergencia tras 500 iteraciones: 5243.3503604668795

#### 4.1.4. Mejor red neuronal encontrada

PRUEBA 2/16 | Mapa: 5x4 | Iter: 500 | L.R.: 0.01

Error de cuantización tras 500 iteraciones: 1.8660993449003709
Error topográfico tras 500 iteraciones: 0.0
Medida de divergencia tras 500 iteraciones: 5243.3503604668795

La mejor red neuronal encontrada en esta configuración de hiperparámetros es la red neuronal entrenada con la forma de 5x4, dado que es la que presenta el mejor equilibrio en las medidas de error de cuantización y, además, logra un error topográfico nulo ($0.0$), lo cual es el escenario ideal para la preservación de la estructura de los datos.

## 4.2. Prueba 2

### 4.2.1. Configuración de Hiperparámetros

```python
# 2000 iteraciones de entrenamiento
# 0.5 de tasa de aprendizaje
# Dimensiones posibles-> combinacion altura:[5]x anchura:[4,5,6,7]
# Radio de vecindad: max(dimensiones)/2
pruebas_SOM(2000, 0.5)
```

### 4.2.2. Conclusiones de configuración

Dentro del conjunto de pruebas realizadas con la configuración de hiperparámetros mencionada (2000 iteraciones, L.R. 0.5), observamos que las métricas establecidas para la evaluación se mantienen en unos rangos tales que:

- **Métrica EC:** [1.469, 1.533] -> Teniendo el mejor valor dado de este error la red neuronal con la forma de 4x5. El peor valor de las redes neuronales entrenadas con esta configuración se da en la red neuronal con la forma de 5x4.

- **Métrica ET:** [0.017, 0.053] -> Teniendo el mejor valor dado de este error la red neuronal entrenada con la forma de 4x5. El peor valor de las redes neuronales entrenadas con esta configuración se da en la red neuronal con la forma de 5x4.

Analizando el trade-off entre las dos métricas, se observa que al aumentar el número de iteraciones a 2000, la disposición 4x5 se vuelve significativamente más eficiente que la 5x4, logrando reducir tanto el error de representación como el error de vecindad simultáneamente.

### 4.2.3. Resultados de cada red neuronal

PRUEBA 1/16 | Mapa: 4x5 | Iter: 2000 | L.R.: 0.5

Error de cuantización tras 2000 iteraciones: 1.469700317777774
Error topográfico tras 2000 iteraciones: 0.017964071856287425
Medida de divergencia tras 2000 iteraciones: 5888.379666798518

PRUEBA 2/16 | Mapa: 5x4 | Iter: 2000 | L.R.: 0.5

Error de cuantización tras 2000 iteraciones: 1.5338558667412352
Error topográfico tras 2000 iteraciones: 0.05389221556886228
Medida de divergencia tras 2000 iteraciones: 5566.080772279158

#### 4.2.4. Mejor red neuronal encontrada

PRUEBA 1/16 | Mapa: 4x5 | Iter: 2000 | L.R.: 0.5

Error de cuantización tras 2000 iteraciones: 1.469700317777774
Error topográfico tras 2000 iteraciones: 0.017964071856287425
Medida de divergencia tras 2000 iteraciones: 5888.379666798518

La mejor red neuronal encontrada en esta configuración de hiperparámetros es la red neuronal entrenada con la forma de 4x5, dado que es la que presenta el mejor equilibrio en las medidas de error de cuantización, aunque el error topográfico no es el mejor de toda la serie histórica, se mantiene en un rango aceptable y es el más bajo de este grupo específico.
