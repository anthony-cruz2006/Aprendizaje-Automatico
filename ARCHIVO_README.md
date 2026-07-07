# Comparación de LDA y QDA sobre el Wine Dataset

Proyecto de la materia **Aprendizaje Automático** — Universidad de Guayaquil, Facultad de Ciencias Matemáticas y Físicas, Carrera de Ciencia de Datos e Inteligencia Artificial.

Implementación y comparación de **Análisis Discriminante Lineal (LDA)** y **Análisis Discriminante Cuadrático (QDA)** como modelos de clasificación, utilizando el **Wine Dataset** de scikit-learn.

## Autor
Anthony Cruz Huacon

## Contenido del repositorio

├── LDA_QDA_Wine.ipynb   # Notebook con el análisis completo
├── README.md            # Este archivo
└── requirements.txt     # Dependencias necesarias

## Dataset

Se utiliza el **Wine Dataset**, un conjunto de datos clásico del UCI Machine Learning Repository, integrado directamente en `scikit-learn`. Contiene 178 observaciones de vinos italianos pertenecientes a 3 cultivares distintos, descritos por 13 variables químicas (alcohol, flavonoides, prolina, etc.).

No es necesario descargar ningún archivo aparte. El dataset se carga automáticamente al ejecutar la celda correspondiente del notebook mediante:

from sklearn.datasets import load_wine
wine = load_wine()

## Cómo ejecutar el proyecto

Requisitos: Python 3.9 o superior, y Jupyter Notebook o Google Colab.

Pasos:

1. Clona este repositorio:
git clone https://github.com/tu-usuario/tu-repositorio.git
cd tu-repositorio

2. Instala las dependencias:
pip install -r requirements.txt

3. Abre el notebook:
jupyter notebook LDA_QDA_Wine.ipynb
O súbelo directamente a Google Colab (https://colab.research.google.com/) usando "Subir notebook".

4. Ejecuta todas las celdas en orden (Kernel → Restart & Run All en Jupyter, o Entorno de ejecución → Ejecutar todas en Colab).

## Principales hallazgos

- El dataset no presenta valores faltantes y las tres clases están razonablemente balanceadas (59, 71 y 48 observaciones).
- Variables como flavanoids, proline y alcohol muestran buena capacidad discriminante entre cultivares, visible tanto en histogramas como en el diagrama de dispersión.
- LDA obtuvo un accuracy de 98.15%, con precisión de 98.25%, recall de 98.41% y F1-score de 98.29% sobre el conjunto de prueba.
- QDA obtuvo un accuracy de 100%, con precisión, recall y F1-score perfectos (1.00) sobre el conjunto de prueba.
- Las fronteras de decisión confirman la diferencia teórica entre ambos modelos: LDA genera fronteras rectas (covarianza compartida entre clases), mientras que QDA genera fronteras curvas (covarianza distinta por clase).
- El desempeño similar y alto de ambos modelos sugiere que las clases del Wine Dataset, tras ser estandarizadas, tienen una estructura de covarianza razonablemente parecida, favoreciendo el supuesto de LDA, aunque QDA logra capturar mejor la variabilidad interna de cada cultivar.

## Tecnologías utilizadas

- Python
- pandas, numpy
- scikit-learn
- matplotlib, seaborn
