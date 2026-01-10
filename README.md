# MIT LIFT Digitization and Performance Index - Argentina

## Descripción

Este repositorio contiene el análisis de datos del proyecto MIT LIFT LAB para Argentina (Fall 2025), enfocado en evaluar el índice de digitalización y desempeño de pequeñas y medianas empresas. El proyecto es parte de la iniciativa MIT LIFT LAB del MIT Sloan School of Management, que trabaja en la transformación digital de empresas en mercados emergentes.

## Estructura del Proyecto

```
mit_analisis/
├── src/
│   ├── borrador_trabajo.md   # Borrador del informe en Markdown
│   ├── data/
│   │   ├── raw/              # Datos originales de encuestas Qualtrics
│   │   └── processed/        # Datos limpios y procesados
│   ├── notebooks/
│       ├── 0_initial_cleaning.ipynb    # Limpieza inicial de datos
│       ├── 1_EDA.ipynb                 # Análisis exploratorio de datos
│       └── 2_analisis_estacionalidad.ipynb  # Figuras para informe (texto + expectativas)
│   ├── viz/                 # Figuras exportadas (PNG)
│   └── latex/               # Informe en LaTeX (fuente + PDF)
│       ├── main.tex
│       ├── main.pdf
│       ├── references.bib
│       └── sections/
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

### 3. Figuras e indicadores para informe (2_analisis_estacionalidad.ipynb)

- Generación de figuras reproducibles para el informe:
  - Nube de palabras (razones de cambio en ventas)
  - Distribución de expectativas de ventas a 3 meses
  - Indicador de consistencia (alineación) entre expectativa y desempeño reciente, segmentado por tipo de negocio y antigüedad
- Exportación automática de PNGs a `src/viz/`

### 4. Informe en PDF (LaTeX)

- Versión del informe en LaTeX en `src/latex/` (texto + bibliografía)
- Compilación a PDF: `src/latex/main.pdf`

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

Para compilar el informe en PDF se requiere una distribución LaTeX (por ejemplo, MiKTeX en Windows) y `latexmk`.

## Uso

1. Clonar el repositorio
2. Instalar dependencias
3. Ejecutar los notebooks en orden secuencial:
  - Primero `0_initial_cleaning.ipynb` para procesar los datos
  - Luego `1_EDA.ipynb` para análisis exploratorio
  - Luego `2_analisis_estacionalidad.ipynb` para regenerar las figuras del informe (exporta PNGs a `src/viz/`)
4. (Opcional) Compilar el informe en PDF (desde `src/latex/`):

```bash
latexmk -pdf -interaction=nonstopmode main.tex
```

## Resultados

Los análisis generan insights sobre:

- Patrones de adopción digital en PyMEs argentinas
- Relación entre digitalización y desempeño empresarial
- Distribución geográfica de negocios y características
- Segmentación de negocios según perfiles digitales

Además, el repositorio incluye artefactos de salida para el informe:

- Figuras exportadas a `src/viz/`:
  - `figura_1_nube_palabras_ventas.png`
  - `figura_2_expectativa_ventas_3m.png`
  - `figura_3_consistencia_expectativa_vs_ventas.png`
- Informe en LaTeX y PDF en `src/latex/`:
  - `main.tex` (fuente)
  - `main.pdf` (salida)
- Borrador del informe en Markdown: `src/borrador_trabajo.md`

## Contacto

Proyecto desarrollado como parte de la iniciativa MIT LIFT LAB del MIT Sloan School of Management.
