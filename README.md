# 🧊 Predicción de Años Críticos de Derretimiento del Hielo Antártico

Este proyecto aplica técnicas de **Aprendizaje Automático** para predecir si un año será **crítico en la disminución de la extensión del hielo antártico**, utilizando datos de **temperaturas anuales de Ushuaia, Tierra del Fuego**. El objetivo es anticipar comportamientos extremos relacionados con el cambio climático a partir de registros locales.

---

## 📁 Estructura del Proyecto

Organizado según una plantilla tipo *CookieCutter* para ciencia de datos:

proyecto_hielo_antartico_ml/
│
├── data/
│ ├── raw/ # Datos originales
│ └── processed/ # Dataset final limpio
│
├── notebooks/
│ ├── analisis_exploratorio.ipynb
│ └── modelo_clasificacion.ipynb
│
├── models/ # Modelos entrenados
├── reports/
│ └── figures/ # Gráficos generados
├── src/ # Código fuente (opcional)
├── tests/ # Tests (opcional)
│
├── README.md
├── requirements.txt
└── .gitignore


---

## 🌎 Dataset

### 📌 Fuente de Datos

- **Temperaturas en Ushuaia (2009–2021)**  
  Fuente: Servicio Meteorológico Nacional – [datos.gob.ar](https://datos.gob.ar)
  
- **Extensión mensual de hielo marino en la Antártida**  
  Fuente: NSIDC (Sea Ice Index v3) – [nsidc.org](https://nsidc.org/data/seaice_index)

El dataset final `dataset_final.csv` contiene:
- `anio`
- `temp_media_anual`
- `temp_max_anual`
- `temp_min_anual`
- `anio_critico` (1 = año con baja extrema de hielo / 0 = normal)

---

## 🔍 Análisis Exploratorio

Realizado en: `notebooks/analisis_exploratorio.ipynb`

- 📊 **Correlación** entre temperatura mínima y años críticos
- 📈 Gráficos de líneas y boxplots para observar tendencias
- 📉 Años críticos: identificados por extensión mínima de hielo inferior a la media

---

## 🤖 Modelo de Machine Learning

Realizado en: `notebooks/modelo_clasificacion.ipynb`

- **Algoritmo:** Random Forest Classifier
- **Hiperparámetros:**
  - `n_estimators = 100`
  - `max_depth = 3`
  - `test_size = 0.3`

### ✅ Métricas de Evaluación

- Accuracy: 0.75  
- Precision: 0.80  
- Recall: 0.67  
- F1-score: 0.73

---

## 🧠 Conclusiones

- El modelo logra detectar patrones útiles a pesar del tamaño reducido del dataset.
- La temperatura mínima anual es una de las variables más predictivas.
- Este enfoque puede servir como base para futuras investigaciones combinando variables climáticas, oceánicas o atmosféricas.
