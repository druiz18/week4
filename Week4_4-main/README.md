# Team - Room 6

DIEGO ALEJANDRO RUIZ ALFONSO - diegoaruiz@ucundinamarca.edu.co
PEDRO PASCUAL MURCIA VARGAS - ppmurcia@ucundinamarca.edu.co
JHON EDUARD TINJACA CRUZ - jetinjaca@ucundinamarca.edu.co
JULIAN DAVID SILVA GUZMAN - jdsilva@ucundinamarca.edu.co

# Week4_4 – Regularización en Deep Learning
Aplicacion de Metodos de Regularizacion en una Red Neuronal

# Objetivo
Aplicar métodos de regularización para reducir el overfitting en una red neuronal.

# Descripción del proyecto
En este proyecto se analiza el uso de técnicas de regularización en redes neuronales con el objetivo de reducir el overfitting y mejorar la capacidad de generalización del modelo.
Para ello, se comparan dos modelos entrenados bajo las mismas condiciones:
- Un modelo base sin regularización
- Un modelo regularizado mediante L2 (weight decay) y Dropout
El experimento permite observar cómo la regularización influye en el comportamiento del loss y en el desempeño del modelo sobre datos no vistos.

# Métodos usados
- Regularización L2
- Dropout

## Comparación
Modelo base vs modelo regularizado manteniendo la misma arquitectura.

## Resultado principal
La regularización mejora la generalización y reduce el sobreajuste.

## Ejecución
Abrir el notebook en Google Colab y ejecutar todas las celdas.

# Dataset
Se utiliza un dataset sintético de clasificación binaria, generado con la función make_moons de sklearn, el cual introduce:

- Distribución no lineal
- Ruido controlado (noise = 0.2)
- Total de muestras: 1000
- División del dataset:
      _70% entrenamiento
      _30% prueba
Este tipo de dataset es adecuado para visualizar problemas de sobreajuste (overfitting) en modelos con alta capacidad.

# Librerías utilizadas
- NumPy
- Matplotlib
- TensorFlow / Keras
- Scikit-learn


# Modelos implementados
## 1. Modelo base (sin regularización)
# Arquitectura:
- Capa densa de 64 neuronas (ReLU)
- Capa densa de 64 neuronas (ReLU)
- Capa de salida de 1 neurona (Sigmoid)

# Configuración:
- Optimizador: Adam
- Función de pérdida: Binary Crossentropy
- Métrica: Accuracy
- Épocas: 50
Este modelo tiene alta capacidad, lo que lo hace propenso al overfitting.

## 2. Modelo con regularización (L2 + Dropout)
# Arquitectura:
- Capa densa (64 neuronas, ReLU) con regularización L2
- Dropout (30%)
- Capa densa (64 neuronas, ReLU) con regularización L2
- Capa de salida (Sigmoid)
  
# Configuración adicional:
- Regularización L2 con factor 0.01
- Dropout para desactivar neuronas aleatoriamente durante el entrenamiento
El resto de hiperparámetros se mantiene igual al modelo base, garantizando una comparación justa.

# Comparación de resultados
Se analiza la evolución del loss de validación para ambos modelos:
- El modelo base muestra un descenso rápido del loss en entrenamiento, pero un comportamiento inestable en validación.
- El modelo regularizado presenta una curva de loss más estable, indicando mejor generalización.
- La regularización evita que el modelo dependa excesivamente de pesos individuales.
La gráfica de validación permite visualizar claramente el overfitting del modelo base frente al comportamiento más controlado del modelo regularizado.

## Conclusiones

-  El modelo sin regularización presenta mayor overfitting, ajustándose en exceso a los datos de entrenamiento.
-  La regularización L2 penaliza pesos grandes y contribuye a modelos más simples y estables.
-  Dropout reduce la co-adaptación de las neuronas y mejora la robustez del modelo.
-  El modelo regularizado muestra mejor generalización, reflejada en un loss de validación más estable.
-  El uso combinado de L2 + Dropout resulta efectivo para controlar el overfitting en redes neuronales densas.
-  La regularización es una herramienta clave cuando se trabaja con modelos de alta capacidad y datasets con ruido.

## Conclusión general:
La aplicación de técnicas de regularización permite construir modelos más robustos, evitando el sobreajuste y mejorando el desempeño sobre datos no vistos, lo cual es fundamental en aplicaciones reales de deep learning.
