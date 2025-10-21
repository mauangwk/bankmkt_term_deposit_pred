# Marketing Bancario

## Objectivo

Este proyecto se enfoca en un problema de clasificacion binaria para predecir si un cliente bancario se suscribirá o no a un deposito a plazo

<!-- This project focuses on a binary classification for predicting whether a bank client will subscribe to a term deposit. 
if not (params.preprocess_required and params.training_required):
    print("\nfavor de explorar el directorio insights en busqueda de una version inicial")

-->


## Estructura del Proyecto

El repositorio está organizado de la siguiente manera:

- **/datasets**: Contiene los datos brutos (`raw`) y los datos listos para ser procesados para la creacion del modelo(`pre-processed`).
- **/files/documentation**: Almacena la estructura/modelo de datos y notebooks de Jupyter para análisis exploratorio o referencias del proyecto en un bootcamp en tripleten.
- **<a href="insights/bankmkt.ipynb">/insights/</a>**: Archivos de exploracion y donde se puede encontrar una primer vesion del proyecto o en version Jupyter Notebook
- **/files/outputs**: Guarda los resultados del proyecto, como el modelo entrenado (`models`), imagenes (`images`)
- **/src**: Contiene el código fuente modularizado en scripts de Python.
- **`requirements.txt`**: Lista de dependencias del proyecto.
- En la raiz del proyecto se encuentran los archivos principales para la ejecución y prueba del mismo.

## Preparando el ambiente virtual
Por favor considerar el ejecutar las siguientes instrucciones para manejar el workspace dentro de un ambiente virtual:

```
python3 -m venv .venv
source .venv/bin/activate
user$ pip install --upgrade pip
user$ python -m pip install -r requirements.txt
```

## Como ejecutar el proyecto

Se puede controlar las secciones del proceso a ejecutar por medio de variables dentro del modulo **params** en la raiz del proyecto segun se requiera. 

- preprocess_required = True/False
- training_required = True/False

Para la ejecucion del pipeline, es suficiente con la siguiente linea en raiz del proyecto:

```
python project_pipeline.py 

```
## Modelo Final y Resultados del entrenamiento

El modelo final es un `CatBoost` optimizado. Las siguientes fueron las metricas obtenidas:

{'RandomForestClassifier': np.float64(0.6008638719758517),
 'XGBClassifier': np.float64(0.5659917041064582),
 'LGBMClassifier': np.float64(0.5742320597687598),
 'CatBoostClassifier': np.float64(0.6186668751078144)}

### Conclusión
De los experimentos realizados hasta ahora, CatBoostClassifier mostró buenos resultados con una precisión métrica de 0,62.

### ¿Qué se puede mejorar?

- Conviene equilibrar las clases.
- Revisitar y refinar la ingeniería de clases así como la normalización. 
