# 4. Configuraciones de Prueba

## 4.1. Prueba 1

### 4.1.1. Configuración de Hiperparámetros

```python
# 500 iteraciones de entrenamiento
# 0.5 de tasa de aprendizaje
# Dimensiones posibles-> combinacion altura:[5]x anchura:[4,5,6,7]
# Radio de vecindad: max(dimensiones)/2
pruebas_SOM(500, 0.5)
```

### 4.1.2. Conclusiones de configuración

Dentro del conjunto de pruebas realizadas con la configuración de hiperparámetros mencionada, observamos que las métricas establecidas para la evaluación se mantienen en unos rangos tales que:

- **Métrica EC**: [1.445, 1.532] -> Teniendo el mejor valor dado de este error la red neuronal con la forma de 5x6. El peor valor de las redes neuronales entrenadas con esta configuración se da en la red neuronal con la forma de 7x5.

- **Métrica ET**: [0.005, 0.0359] -> Teniendo el mejor valor dado de este error la red neuronal entrenada con la forma de 7x5. El peor valor de las redes neuronales entrenadas con esta configuración se da en la red neuronal con la forma de 7x5. Por otro lado, la red neuronal con la forma de 5x6 es la que comprende un error Topográfico mayor.

Analizando el trade-off entre las dos métricas, las diferencias dentro del error de cuantización no son tan significativas, sin embargo, el error topográfico muestra una diferencia más sustancial en la proporción, dado que hay uno de estos errores que se mantiene por debajo del 1% (en concreto un 0.5%), mientras que el error topográfico presentado en el segundo caso es de un +-3.5%.

### 4.1.3. Resultados de cada red neuronal

PRUEBA 1/16 | Mapa: 4x5 | Iter: 500 | L.R.: 0.5

Error de cuantización tras 500 iteraciones: 1.5161493003332027
Error topográfico tras 500 iteraciones: 0.005988023952095809
Medida de divergencia tras 500 iteraciones: 6518.604013073583

PRUEBA 2/16 | Mapa: 5x4 | Iter: 500 | L.R.: 0.5

Error de cuantización tras 500 iteraciones: 1.4725070177173702
Error topográfico tras 500 iteraciones: 0.017964071856287425
Medida de divergencia tras 500 iteraciones: 6182.67599936539

PRUEBA 3/16 | Mapa: 5x5 | Iter: 500 | L.R.: 0.5

Error de cuantización tras 500 iteraciones: 1.4618639660861314
Error topográfico tras 500 iteraciones: 0.03592814371257485
Medida de divergencia tras 500 iteraciones: 6679.535513767946

PRUEBA 4/16 | Mapa: 5x6 | Iter: 500 | L.R.: 0.5

Error de cuantización tras 500 iteraciones: 1.4455583184017906
Error topográfico tras 500 iteraciones: 0.03592814371257485
Medida de divergencia tras 500 iteraciones: 8739.277393105376

PRUEBA 5/16 | Mapa: 5x7 | Iter: 500 | L.R.: 0.5

Error de cuantización tras 500 iteraciones: 1.4941947800224964
Error topográfico tras 500 iteraciones: 0.029940119760479042
Medida de divergencia tras 500 iteraciones: 10259.776933843612

PRUEBA 6/16 | Mapa: 6x5 | Iter: 500 | L.R.: 0.5

Error de cuantización tras 500 iteraciones: 1.458883637808908
Error topográfico tras 500 iteraciones: 0.017964071856287425
Medida de divergencia tras 500 iteraciones: 8192.38249279116

PRUEBA 7/16 | Mapa: 7x5 | Iter: 500 | L.R.: 0.5

Error de cuantización tras 500 iteraciones: 1.5326934890309047
Error topográfico tras 500 iteraciones: 0.005988023952095809
Medida de divergencia tras 500 iteraciones: 9934.15308393959

#### 4.1.4. Mejor red neuronal encontrada

PRUEBA 6/16 | Mapa: 6x5 | Iter: 500 | L.R.: 0.5

Error de cuantización tras 500 iteraciones: 1.458883637808908
Error topográfico tras 500 iteraciones: 0.017964071856287425
Medida de divergencia tras 500 iteraciones: 8192.38249279116

La mejor red neuronal encontrada en esta configuración de hiperparámetros es la red neuronal entrenada con la forma de 6x5, dado que es la que presenta el mejor equilibrio en las medidas de error de cuantización, aunque el error topográfico no es el mejor, se mantiene en un rango aceptable.
