# Trabajo Final - Prompt Engineering en IA

Proyecto del módulo de Prompt Engineering.

## Contenido

Este proyecto incluye dos ejercicios:

1. Ejercicio 1: extracción de información de alojamientos de Airbnb mediante LLMs.
2. Ejercicio 2: análisis de reseñas de videojuegos mediante un pipeline en dos pasos con LLMs.

## Estructura

- data/raw/: datasets originales proporcionados.
- data/processed/: datasets procesados generados por el notebook.
- notebooks/: notebooks del trabajo.
- results/: resultados finales exportados.
- src/: código auxiliar si fuera necesario.

## Dataset principal del entregable final

- videogames_reviews.csv

## Objetivo

El objetivo principal es diseñar prompts claros y controlados para transformar texto libre en información estructurada.

En el ejercicio principal se construye un pipeline en dos fases:

1. Filtrado de reseñas relevantes.
2. Extracción estructurada de información útil desde las reseñas seleccionadas.

## Estructura del proyecto

data/raw/          Datasets originales
data/processed/    Datos procesados generados por el notebook
notebooks/         Notebook principal del proyecto
results/           Resultados finales exportados en CSV
src/               Carpeta auxiliar

## Datasets utilizados

Los archivos CSV utilizados son:

listings1_cleaned.csv
Airbnb_reviews_5000.csv
videogames_reviews.csv
analisis_videojuegos_resultados.csv

## Notebook principal

El desarrollo completo se encuentra en:

notebooks/trabajo_final_prompt_engineering.ipynb

El notebook incluye:

- carga y exploración de datasets
- selección de textos largos
- diseño de prompts
- llamadas a la API de OpenAI
- filtrado de reseñas relevantes
- extracción estructurada en JSON
- conversión a DataFrame
- exportación de resultados finales
- justificación técnica de las decisiones tomadas

## Modelo utilizado

Se utiliza la API de OpenAI con el modelo:

gpt-4o-mini

La elección se justifica por ser un modelo rápido, económico y adecuado para tareas de clasificación, extracción de información y generación de JSON estructurado.

## Configuración de API key

1. El proyecto usa un archivo .env para guardar la clave de OpenAI.
2. Crear un archivo .env en la raíz del proyecto con el siguiente contenido:
``OPENAI_API_KEY=your_openai_api_key_here``
3. El archivo .env real no se incluye en el repositorio por seguridad.
3. Se proporciona .env.example como referencia.

## Resultados generados

Los resultados finales se encuentran en la carpeta results/:

results/ejercicio1_airbnb_entidades_descripciones.csv
results/ejercicio1_airbnb_analisis_comentarios.csv
results/ejercicio2_analisis_videojuegos_resultado_final.csv

## Decisiones técnicas principales

- Se usa salida en formato JSON para facilitar la conversión a DataFrame.
- Se aplica temperatura baja para obtener respuestas estables y consistentes.
- Se separan las tareas en dos prompts principales: filtrado y extracción.
- Se usa time.sleep() entre llamadas para reducir problemas con límites de uso de la API.
- Se procesa una reseña por llamada para evitar problemas de longitud de contexto y controlar mejor las respuestas.

## Ejecución

1. Crear y activar un entorno virtual.
2. Instalar dependencias:
- pip install -r requirements.txt
- Configurar el archivo .env.
3. Abrir y ejecutar el notebook principal:
- notebooks/trabajo_final_prompt_engineering.ipynb