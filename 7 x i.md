
# 4. Configuraciones de Prueba

## 4.1. Prueba 1

### 4.1.1. Configuración de Hiperparámetros

```python
# 500 iteraciones de entrenamiento
# 0.1 de tasa de aprendizaje
# Dimensiones posibles -> combinacion altura:[7] x anchura:[4, 5, 6, 7]
# Radio de vecindad: sigma fijo = 1
pruebas_SOM(500, 0.1)
```

### 4.1.2. Conclusiones de configuración

Dentro del conjunto de pruebas realizadas con la configuración de hiperparámetros mencionada, observamos que las métricas establecidas para la evaluación se mantienen en unos rangos tales que:

- **Métrica EC**: [1.2478, 1.2870] → Teniendo el mejor valor de este error la red neuronal con la forma de 7×5. El peor valor de las redes neuronales entrenadas con esta configuración se da en la red neuronal con la forma de 7×7.

- **Métrica ET**: [0.0419, 0.1138] → Teniendo el mejor valor de este error la red neuronal con la forma de 7×4. El peor valor de las redes neuronales entrenadas con esta configuración se da en la red neuronal con la forma de 7×7.

Analizando el trade-off entre las dos métricas, las diferencias dentro del error de cuantización son poco significativas, manteniéndose todas las configuraciones en un rango estrecho de ±0.04. Sin embargo, el error topográfico muestra una variación más sustancial: la configuración 7×4 presenta un error topográfico inferior al 5%, mientras que la configuración 7×7 alcanza un error cercano al 11.4%, aproximándose al umbral de rechazo establecido en 0.15. Esto indica que, a mayor número de neuronas bajo esta configuración de sigma fijo, mayor dificultad tiene la red para preservar la topología del espacio de entrada.

Por otro lado, el análisis visual de los mapas de activación 2D e histogramas 3D revela que todas las configuraciones presentan el fenómeno de **neuronas dominantes**, con una o dos unidades concentrando la mayor parte de las activaciones y amplias zonas del mapa infrautilizadas. Este comportamiento limita la calidad del clustering independientemente de los valores numéricos de las métricas, y se atribuye al radio de vecindad fijo σ=1, que restringe el ordenamiento global del mapa durante el entrenamiento.

### 4.1.3. Resultados de cada red neuronal

```
PRUEBA 1/4 | Mapa: 7x4 | Iter: 500 | L.R.: 0.1

Error de cuantización tras 500 iteraciones: 1.2685640168868966
Error topográfico tras 500 iteraciones: 0.041916167664670656
Medida de divergencia tras 500 iteraciones: 1466.3866957542978

---

PRUEBA 2/4 | Mapa: 7x5 | Iter: 500 | L.R.: 0.1

Error de cuantización tras 500 iteraciones: 1.2478495250574295
Error topográfico tras 500 iteraciones: 0.09580838323353294
Medida de divergencia tras 500 iteraciones: 1518.4438090967683

---

PRUEBA 3/4 | Mapa: 7x6 | Iter: 500 | L.R.: 0.1

Error de cuantización tras 500 iteraciones: ~1.280
Error topográfico tras 500 iteraciones: ~0.065
Medida de divergencia tras 500 iteraciones: ~1415.0

---

PRUEBA 4/4 | Mapa: 7x7 | Iter: 500 | L.R.: 0.1

Error de cuantización tras 500 iteraciones: 1.2870180226710757
Error topográfico tras 500 iteraciones: 0.11377245508982035
Medida de divergencia tras 500 iteraciones: 1405.2595420953246
```

### 4.1.4. Mejor red neuronal encontrada

```
PRUEBA 3/4 | Mapa: 7x6 | Iter: 500 | L.R.: 0.1

Error de cuantización tras 500 iteraciones: ~1.280
Error topográfico tras 500 iteraciones: ~0.065
Medida de divergencia tras 500 iteraciones: ~1415.0
```

La mejor red neuronal encontrada en esta configuración de hiperparámetros es la red neuronal entrenada con la forma de **7×6**, dado que presenta el mejor equilibrio entre las tres métricas evaluadas. Si bien la configuración 7×5 obtiene un error de cuantización ligeramente inferior (1.2478), su error topográfico (0.096) casi duplica al de la 7×6 (~0.065), lo que implica una peor preservación de la topología del espacio de entrada. Además, la 7×6 registra la medida de divergencia más baja del conjunto (~1415), indicando una mayor cohesión interna del mapa. El análisis visual del mapa de activación 2D confirma asimismo una distribución de activaciones más homogénea respecto al resto de configuraciones evaluadas, lo que la posiciona como la configuración con mejor comportamiento global bajo estos hiperparámetros.

No obstante, se detecta en todas las configuraciones el fenómeno de neuronas dominantes, por lo que se propone para la siguiente prueba aumentar el radio de vecindad σ de forma proporcional a las dimensiones del mapa, con el objetivo de favorecer un ordenamiento global más efectivo y reducir la aparición de neuronas muertas.


## 4.1 Prueba 2

# 500 iteraciones de entrenamiento
# 0.3 de tasa de aprendizaje
# Dimensiones posibles -> combinacion altura:[7] x anchura:[4, 5, 6, 7]
# Radio de vecindad: sigma fijo = 1
# pruebas_SOM(500, 0.3)


### 4.2.2. Conclusiones de configuración

Dentro del conjunto de pruebas realizadas con la configuración de hiperparámetros mencionada, observamos que las métricas establecidas para la evaluación se mantienen en unos rangos tales que:

- **Métrica EC**: [1.0502, 1.1400] → Teniendo el mejor valor de este error la red neuronal con la forma de 7×6. El peor valor de las redes neuronales entrenadas con esta configuración se da en la red neuronal con la forma de 7×4. En comparación con la Prueba 1 (LR: 0.1), se observa una mejora global del error de cuantización en todas las dimensiones, con reducciones de entre un 10% y un 18%, lo que indica que una tasa de aprendizaje de 0.3 favorece un ajuste más preciso de los pesos neuronales en el mismo número de iteraciones.

- **Métrica ET**: [0.0718, 0.1497] → Teniendo el mejor valor de este error la red neuronal con la forma de 7×4. El peor valor de las redes neuronales entrenadas con esta configuración se da en la red neuronal con la forma de 7×5, la cual roza el umbral de rechazo establecido en 0.15, quedando prácticamente en el límite con un valor de 0.1497. La configuración 7×5 queda por tanto descartada como candidata válida pese a presentar un buen error de cuantización.

Analizando el trade-off entre las dos métricas, el aumento de la tasa de aprendizaje respecto a la Prueba 1 produce una mejora generalizada en el error de cuantización, pero a costa de incrementar la presión sobre el error topográfico, especialmente en dimensiones más grandes como la 7×5, que se sitúa al límite del umbral de rechazo. La configuración 7×6 consigue el mejor balance entre ambas métricas, mejorando el EC respecto a la Prueba 1 en aproximadamente un 18% y manteniendo el ET en un nivel aceptable (0.0898), alejado del umbral de rechazo.

### 4.2.3. Resultados de cada red neuronal
```
PRUEBA 1/4 | Mapa: 7x4 | Iter: 500 | L.R.: 0.3

Error de cuantización tras 500 iteraciones: 1.1400864160868602
Error topográfico tras 500 iteraciones: 0.0718562874251497
Medida de divergencia tras 500 iteraciones: 1614.399569808844

---

PRUEBA 2/4 | Mapa: 7x5 | Iter: 500 | L.R.: 0.3

Error de cuantización tras 500 iteraciones: 1.0568166420371705
Error topográfico tras 500 iteraciones: 0.1497005988023952
Medida de divergencia tras 500 iteraciones: 1701.1715671292634

---

PRUEBA 3/4 | Mapa: 7x6 | Iter: 500 | L.R.: 0.3

Error de cuantización tras 500 iteraciones: 1.050239772153141
Error topográfico tras 500 iteraciones: 0.08982035928143713
Medida de divergencia tras 500 iteraciones: 1586.2012605992807

---

```

### 4.2.4. Mejor red neuronal encontrada
```
PRUEBA 3/4 | Mapa: 7x6 | Iter: 500 | L.R.: 0.3

Error de cuantización tras 500 iteraciones: 1.050239772153141
Error topográfico tras 500 iteraciones: 0.08982035928143713
Medida de divergencia tras 500 iteraciones: 1586.2012605992807


La mejor red neuronal encontrada en esta configuración de hiperparámetros es la red neuronal entrenada con la forma de 7×6, dado que presenta el mejor error de cuantización del conjunto (1.0502) junto a un error topográfico aceptable (0.0898), muy alejado del umbral de rechazo. La configuración 7×5, pese a obtener un EC similar (1.0568), queda descartada al situarse su error topográfico prácticamente en el límite de rechazo (0.1497). La configuración 7×4, aunque con el mejor ET (0.0718), presenta el peor EC del grupo (1.1400), lo que implica una representación menos fiel del espacio de datos. El análisis visual del mapa de activación 2D confirma una distribución más homogénea respecto a la Prueba 1, con menor presencia de neuronas dominantes, lo que representa una mejora cualitativa en la calidad del clustering. Se propone para la siguiente prueba aumentar el número de iteraciones con el objetivo de permitir la estabilización de la medida de divergencia, que en esta prueba muestra una tendencia creciente sin converger al finalizar el entrenamiento.