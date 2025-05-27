# proyecto-ml-hielo-antartico# 🧊 Predicción de Años Críticos de Derretimiento del Hielo Antártico usando Temperaturas Históricas de Tierra del Fuego

**Autor:** Marcelo Renzone  
**Materia:** Aprendizaje Automático  
**Carrera:** Tecnicatura en Análisis de Datos e Inteligencia Artificial  
**Entrega:** Segunda instancia – Descripción y documentación del dataset  
**Fecha:** [Completar]

---

## 📘 Descripción del Proyecto

Este proyecto utiliza Aprendizaje Automático para **predecir si un año determinado será crítico en términos de derretimiento del hielo antártico**, utilizando datos históricos de temperatura registrados en Ushuaia (Tierra del Fuego).  
Se considera “año crítico” aquel cuya extensión mínima de hielo está por debajo del umbral (percentil 25) del promedio anual.

---

## 📂 Estructura del Repositorio

proyecto-ml-hielo-antartico/
├── data/ # Datos originales crudos
│ ├── 22_2_02_clima_Ushuaia_2009_2021.xlsx
│ ├── Sea_Ice_Index_Monthly_Data.csv
│
├── processed/ # Dataset limpio y unificado
│ └── dataset_final.csv
│
├── notebooks/ # Análisis exploratorio y modelado
│ └── analisis_exploratorio.ipynb
│
└── README.md


---

## 🔍 Descripción de los Datasets

### 📄 1. Dataset de Temperatura - Ushuaia

- **Fuente:** [datos.gob.ar](https://datos.gob.ar)
- **Archivo:** `data/22_2_02_clima_Ushuaia_2009_2021.xlsx`
- **Período:** 2009 a 2021
- **Columnas:** Año, Enero a Diciembre
- **Preprocesamiento:**
  - Conversión de ancho a formato largo.
  - Cálculo de temperatura media, máxima y mínima por año.

---

### 🧊 2. Dataset de Extensión de Hielo Antártico

- **Fuente:** National Snow and Ice Data Center (NSIDC)  
- **Enlace:** https://nsidc.org/data/G02135  
- **Archivo:** `data/Sea_Ice_Index_Monthly_Data.csv`
- **Columnas:** Year, Month, Hemisphere, Extent
- **Preprocesamiento:**
  - Filtrado por Hemisferio Sur.
  - Agregado de extensión mínima anual.
  - Generación de variable objetivo binaria: `anio_critico`.

---

## 🧾 Dataset Final para el Modelo

**Archivo:** `processed/dataset_final.csv`

| anio | temp_media_anual | temp_max_anual | temp_min_anual | ext_minima_anual | anio_critico |
|------|------------------|----------------|----------------|------------------|---------------|
| 2009 | 5.7              | 6.9            | 4.3            | 3.52             | 0             |
| ...  | ...              | ...            | ...            | ...              | ...           |

---

## 🤖 Tipo de Modelo

Se implementará un modelo de **clasificación binaria** usando algoritmos supervisados como:

- `LogisticRegression`
- `RandomForestClassifier`
- `KNeighborsClassifier`
- `Support Vector Machine (SVM)`

---

## 🛠️ Requisitos

- Python 3.10+
- Pandas, NumPy, Scikit-learn
- Matplotlib, Seaborn
- Jupyter Notebook / Google Colab

---

## 🧠 Objetivo

Entrenar un modelo capaz de **predecir si un año será crítico o no**, en función de las temperaturas históricas registradas en Tierra del Fuego.

---

