# MIT LIFT Digitization and Performance Index - Argentina

## Descripción

Este repositorio contiene el análisis de datos del proyecto MIT LIFT LAB para Argentina (Fall 2025), enfocado en evaluar el índice de digitalización y desempeño de pequeñas y medianas empresas. El proyecto es parte de la iniciativa MIT LIFT LAB del MIT Sloan School of Management, que trabaja en la transformación digital de empresas en mercados emergentes.

## Estructura del Proyecto

```
mit_analisis/
├── src/
│   ├── data/
│   │   ├── raw/              # Datos originales de encuestas Qualtrics
│   │   └── processed/        # Datos limpios y procesados
│   └── notebooks/
│       ├── 0_initial_cleaning.ipynb    # Limpieza inicial de datos
│       └── 1_EDA.ipynb                 # Análisis exploratorio de datos
├── pyproject.toml
└── README.md
```

## Datos

Los datos provienen de encuestas recopiladas mediante Qualtrics que evalúan:

- Características demográficas de los negocios
- Nivel de adopción digital
- Indicadores de desempeño
- Prácticas operativas y comerciales
- Ubicación geográfica de los establecimientos

El conjunto de datos contiene registros de negocios encuestados en Argentina.

## Metodología

### 1. Limpieza de Datos (0_initial_cleaning.ipynb)

- Eliminación de columnas de metadata técnica de Qualtrics
- Renombrado de columnas para reducir complejidad
- Generación de dos versiones del dataset:
  - `clean_survey_full.csv`: incluye información de identificación para cruce de datos
  - `clean_survey_to_analyze.csv`: versión reducida para análisis

### 2. Análisis Exploratorio (1_EDA.ipynb)

- Análisis descriptivo de variables
- Visualizaciones geoespaciales
- Patrones de digitalización
- Correlaciones entre variables de desempeño
- Clustering y segmentación de negocios

## Requisitos

El proyecto utiliza Python 3.13+ con las siguientes dependencias principales:

- pandas
- numpy
- matplotlib
- seaborn
- plotly
- folium
- geopandas
- scikit-learn
- nltk
- wordcloud

Para instalar todas las dependencias:

```bash
pip install -e .
```

## Uso

1. Clonar el repositorio
2. Instalar dependencias
3. Ejecutar los notebooks en orden secuencial:
   - Primero `0_initial_cleaning.ipynb` para procesar los datos
   - Luego `1_EDA.ipynb` para análisis exploratorio

## Resultados

Los análisis generan insights sobre:

- Patrones de adopción digital en PyMEs argentinas
- Relación entre digitalización y desempeño empresarial
- Distribución geográfica de negocios y características
- Segmentación de negocios según perfiles digitales

## Contacto

Proyecto desarrollado como parte de la iniciativa MIT LIFT LAB del MIT Sloan School of Management.
