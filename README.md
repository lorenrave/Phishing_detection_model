# Modelo para detectar phishing

### ¿Qué es el phishing? 
El phishing, o fraude electrónico, representa una amenaza seria en el mundo cibernético. Este delito implica que los atacantes se hagan pasar por entidades
de confianza para obtener información confidencial de las personas, como datos bancarios o contraseñas. La detección efectiva de phishing es crucial para proteger la seguridad en línea de los usuarios.


## ¿Cómo podemos evitar el phishing?
A través del aprendizaje automático, podemos identificar si existe una amenaza de phishing y actuar ante ello. Desde el punto de vista de la seguridad es una herramienta clave que puede evitar muchos delitos.

Para abordar este desafío, decidí emplear una red neuronal del tipo MLP (Perceptrón Multicapa). 
Elegí esta arquitectura debido a su capacidad para aprender patrones complejos en los datos, lo cual es esencial para identificar las sutilezas asociadas con el phishing.

### Preprocesamiento de Datos
En el preprocesamiento de datos, eliminé la columna "url" ya que no aportaba información relevante para la detección de phishing. Además, normalicé las características 
utilizando MinMaxScaler para asegurar que todas las variables tengan la misma escala y contribuyan equitativamente al modelo.

### Codificación de Etiquetas
Realicé una codificación de etiquetas (label encoding) para convertir las clases de "status" en valores numéricos. Esto es esencial para que el modelo pueda entender y procesar las etiquetas en el proceso de entrenamiento.

### Arquitectura de la Red Neuronal
La red neuronal consta de tres capas: una capa de entrada con 87 nodos (correspondiente al número de características en el conjunto de datos), 
dos capas ocultas con 300 y 100 nodos respectivamente, y una capa de salida con 1 nodo y función de activación sigmoide para la clasificación binaria.

### Evaluación y Métricas
Después de entrenar el modelo, evalué su rendimiento utilizando métricas como precisión, recall y F1-score en un conjunto de prueba independiente. Estas métricas proporcionan una comprensión completa de cómo el modelo se comporta en situaciones reales.

### Interpretación de Resultados
Analizando ejemplos de falsos positivos y falsos negativos, obtuve información valiosa sobre las limitaciones del modelo. Esto me permite ajustar y mejorar continuamente el rendimiento del modelo.

# Conclusión
En resumen, el enfoque adoptado para construir este modelo se basó en decisiones bien fundamentadas en términos de arquitectura de red, preprocesamiento de datos y evaluación. Este modelo tiene como objetivo proporcionar
una capa adicional de seguridad al identificar posibles amenazas de phishing y, por lo tanto, contribuir a un entorno en línea más seguro.
La precisión del modelo en el conjunto de datos de entrenamiento es de 98.6% y la precisión en el conjunto de datos de validación es de 97.3%. Esto significa que el modelo es capaz de clasificar correctamente con un alto grado de precisión correos electrónicos legítimos y de phishing. El modelo también muestra una buena estabilidad durante el entrenamiento. La precisión del modelo en el conjunto de datos de entrenamiento aumenta gradualmente durante los primeros 50 o 60 epochs, y luego se estabiliza. Esto sugiere que el modelo ha alcanzado un punto de convergencia y no es probable que mejore significativamente con más entrenamiento.
