# Semana 4 - Optimizacion de Redes Neuronales: Comparacion de Optimizadores

## Objetivo

Aplicar y comparar tecnicas de optimizacion en el entrenamiento de una red neuronal, evidenciando como la eleccion del optimizador y la tasa de aprendizaje afectan la velocidad de convergencia, la estabilidad del entrenamiento y el desempeno final del modelo.

---

## Tecnicas comparadas

Se implementan y comparan cuatro optimizadores desde cero (solo NumPy):

| Optimizador | Descripcion |
|-------------|-------------|
| SGD | Descenso de gradiente estandar sin adaptacion |
| SGD + Momentum | SGD con acumulacion de velocidad en la direccion del gradiente |
| RMSprop | Ajuste adaptativo de LR por componente usando media movil de gradientes cuadraticos |
| Adam | Combinacion de Momentum y RMSprop con correccion de sesgo |

Adicionalmente, se compara el **efecto de la tasa de aprendizaje** sobre Adam (LR de 0.0001 a 0.1).

---

## Configuracion base

Red: Entrada(2) -> Oculta1(16,ReLU) -> Oculta2(8,ReLU) -> Salida(1,Sigmoid), dataset espiral binario (200 muestras), 1000 epocas, semilla fija=42. El unico elemento que cambia entre experimentos es el optimizador o la tasa de aprendizaje.

---

## Resultados principales

Adam y RMSprop convergen significativamente mas rapido y con mayor precision que SGD puro en el problema de espiral no linealmente separable. SGD con Momentum ofrece una mejora intermedia sobre SGD puro, suavizando las oscilaciones y acelerando la convergencia en las primeras epocas. La tasa de aprendizaje optima para Adam en este problema se encuentra en el rango 0.001 -- 0.01.

---

## Como ejecutar el notebook

### Google Colab (recomendado)

1. Descarga `optimizacion_red_neuronal.ipynb`.
2. Ve a [https://colab.research.google.com](https://colab.research.google.com).
3. Selecciona **Archivo -> Subir notebook** y carga el archivo.
4. Ejecuta todas las celdas con **Runtime -> Run all**.

### Local con Jupyter

```bash
pip install numpy pandas matplotlib jupyter
jupyter notebook notebook_optimizacion.ipynb
```

### Dependencias

```
numpy
pandas
matplotlib
```

No se requieren frameworks de deep learning. Todo el proceso (red, backpropagation, optimizadores) se implementa con NumPy puro.

---

## Estructura de la carpeta

```
week4/week4_3_main
├── optimizacion_red_neuronal.ipynb   # Notebook principal ejecutable
└── README.md                     # Este archivo
```

---

*Actividad desarrollada como parte del modulo de Aprendizaje Profundo - Semana 4*
