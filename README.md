# An-lisis-Aseguradora-nps
📌 Descripción del proyecto
Este proyecto corresponde al análisis de datos de siniestros y encuestas NPS de una aseguradora, integrando ambas fuentes con el fin de:

Limpiar y preparar los datos para modelado.
Explorar la distribución del indicador NPS (nps100).
Seleccionar variables relevantes que expliquen la satisfacción del cliente.
Entrenar modelos de clasificación (Random Forest, Regresión Logística, etc.).
Realizar visualizaciones descriptivas y análisis estadístico.

El trabajo se ha realizado en Python dentro de un Jupyter Notebook, cuya exportación generó el archivo HTML proporcionado.

📂 Estructura del proyecto
.
├── Analisis Mapfre Brasil.html    # Exportación del notebook con todo el análisis
├── BBDD Siniestro - consolidado - definitivo.xlsx
├── Encuestas corregidas 2021-2022.xlsx
└── README.md                      # Este archivo


📊 Dataset utilizado
1. Base de siniestros
Archivo: BBDD Siniestro - consolidado - definitivo.xlsx
Contiene información operacional de siniestros, incluyendo:

Fechas (ocurrencia, término).
Importes.
Duraciones.
Datos de pólizas.
Clasificaciones internas.

2. Base de encuestas
Archivo: Encuestas corregidas 2021-2022.xlsx
Incluye:

Información de encuestas posterior al siniestro.
Indicador NPS (nps100) con valores:

100 → Promotor
0 → Pasivo
-100 → Detractor



Distribución encontrada:

100 → 68.89%
-100 → 18.36%
0 → 12.75%


🧹 Limpieza y preparación de datos
En el análisis se ejecutaron tareas clave como:

Eliminación de columnas irrelevantes o duplicadas:

"nps100", "ID da pesquisa", "ID da transação" de encuestas.
Columnas equivalentes en siniestros.


Reemplazo de valores no válidos (e.g., reemplazo de "." en fechas).
Eliminación de "ID Transacción", "IDPoliza".
Unión de ambas bases por identificadores comunes.
Eliminación de filas sin valor en el target nps100.


🔍 Análisis exploratorio (EDA)
Incluye:

Estadísticos descriptivos.
Histogramas y distribuciones.
Análisis de correlación.
Detección de variables redundantes o con baja variabilidad.
Conversión de variables datetime.
Codificación del target (Label Encoding):
0 → 100.0
1 → -100.0
2 → 0.0




🧠 Feature Selection
Se empleó la librería featurewiz con:
Pythonfeaturewiz(df, target="nps100", corr_limit=0.7)Mostrar más líneas
Resultados destacados:

Eliminación de 13 variables ID o sin relevancia.
Eliminación de 15 variables altamente correlacionadas.
Dataset final con 99 variables explicativas.


🤖 Modelos entrenados
✔ RandomForestClassifier

Entrenamiento con train_test_split.
Evaluación: accuracy general del modelo.
Análisis de importancias.

✔ LogisticRegression

Comparación con baseline.
Más interpretable que Random Forest.


📈 Visualización
El proyecto utiliza:

Matplotlib
Seaborn (theme ggplot)
Configuraciones globales:
Pythonplt.rcParams['image.cmap'] = "bwr"plt.rcParams['savefig.bbox'] = "tight"Mostrar más líneas



📦 Librerías utilizadas
Instalación recomendada
Shellpip install numpy pandas seaborn matplotlib scikit-learn featurewiz fitterMostrar más líneas
Librerías detectadas en el análisis

numpy
pandas
matplotlib
seaborn
scikit-learn

neighbors
model_selection
ensemble
metrics
linear_model


featurewiz
fitter
random
itertools
multiprocessing


▶ Cómo ejecutar el análisis

Abrir Jupyter Notebook:
Shelljupyter notebookMostrar más líneas

Cargar el archivo fuente del análisis (versión .ipynb del HTML).
Asegurar que los archivos Excel estén en la misma carpeta.
Ejecutar las celdas en orden.


📝 Licencia
El archivo HTML contiene estilos y estructuras de JupyterLab bajo licencia Modified BSD License (Jupyter Development Team, 2014–2017).
