## 🧠 MiniSom

SOM es un tipo de red neuronal no supervisada, es decir, aprende a proyectar datos sobre
una cuadrícula de baja dimensión, por lo general en 2D, preservando las relaciones
topológicas entre los datos originales. Esta red neuronal es especialmente utilizada en
tareas de clustering, reducción de dimensionalidad y visualización exploratoria de los datos.

Tras investigar una manera de implementar SOM en nuestro estudio con diferentes librerías
de Python, la que más destacaba era MiniSom. Otras librerías que hemos podido utilizar han
sido, por ejemplo, TensorFlow o PyTorch, pero MiniSom destaca por su simplicidad y ligereza:
está implementada en un único fichero sin dependencias externas más allá de NumPy.

Nuestro objetivo es clasificar países en función de indicadores socioeconómicos sin etiquetas
previas. SOM es el método más adecuado para realizar el estudio porque una de sus
características más importantes es que no necesita que se le indique de antemano ni el número
ni la definición de los grupos, para poder realizar un buen análisis. La red aprende sola.

Usamos RobustScaler para normalizar los datos y, como obtenemos un array NumPy (df_scaled),
MiniSom consigue trabajar perfectamente con el conjunto de datos.

som = MiniSom(x=altura, y=anchura, input_len=columnas_dataset, ...)
som.pca_weights_init(df_scaled)

El uso de estos métodos de la librería MiniSom acelera la convergencia del entrenamiento y
proporciona resultados más reproducibles.

MiniSom nos permite definir los hiperparámetros más importantes para el estudio, como son
sigma, learning_rate y neighborhood_function. Nosotros hemos calculado el sigma mediante una
operación matemática (sigma = max(altura, anchura) / 2), lo que nos da un control real sobre
la configuración sin recurrir a valores arbitrarios.