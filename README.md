# Predicción de Años Críticos de Derretimiento del Hielo Antártico

Este proyecto aplica técnicas de **Aprendizaje Automático** para predecir si un año será **crítico en la disminución de la extensión del hielo antártico**, utilizando datos de **temperaturas anuales de Ushuaia, Tierra del Fuego**. El objetivo es anticipar comportamientos extremos relacionados con el cambio climático a partir de registros locales.

---

## 📁 Estructura del Proyecto

Organizado según una plantilla tipo *CookieCutter* para ciencia de datos:

proyecto_hielo_antartico_ml/
│
├── data/
│ ├── raw/ # Datos originales
│ └── processed/ # Dataset final limpio
│                # Entrega3_informe_final_Marcelo_Renzone.txt
│
├── notebooks/
│ ├── analisis_exploratorio.ipynb
│ └── modelo_clasificacion.ipynb
│
├── video_presentacion.mp4 
├── README.md
├── requirements.txt
└── .gitignore

---

## 📊 Dataset

### Origen de los Datos

- **Temperaturas de Ushuaia (2009–2021)**  
  Fuente: Servicio Meteorológico Nacional – [datos.gob.ar](https://datos.gob.ar)
  
- **Extensión mensual de hielo marino en la Antártida**  
  Fuente: NSIDC (Sea Ice Index v3) – [nsidc.org](https://nsidc.org/data/seaice_index)

El dataset final (`dataset_final.csv`) contiene:
- `anio`
- `temp_media_anual`
- `temp_max_anual`
- `temp_min_anual`
- `anio_critico` (1 = año con baja extrema de hielo / 0 = normal)

---

## 📈 Análisis Exploratorio

Realizado en: `notebooks/analisis_exploratorio.ipynb`

- Se observaron correlaciones fuertes entre años críticos y temperaturas mínimas más elevadas.
- Se usaron boxplots y gráficos de línea para observar tendencias.
- Años críticos se definieron por extensión mínima de hielo menor a la media histórica.

---

## 🤖 Modelo de Machine Learning

Realizado en: `notebooks/modelo_clasificacion.ipynb`

- **Algoritmo utilizado:** Random Forest Classifier
- **Hiperparámetros:**  
  - `n_estimators = 100`  
  - `max_depth = 3`  
  - `test_size = 0.3`

### 🔍 Métricas de Evaluación (sobre conjunto de test):

| Clase | Precision | Recall | F1-score |
|-------|-----------|--------|----------|
| 0 (No crítico) | 0.75 | 1.00 | 0.86 |
| 1 (Crítico)     | 0.00 | 0.00 | 0.00 |

- **Accuracy total:** 75%  
- **Macro avg F1-score:** 0.43  
- **Weighted avg F1-score:** 0.64

> ⚠️ **Conclusión**: El modelo predice bien los años normales, pero **no logra detectar los años críticos**. Esto se debe a la baja cantidad de datos y el desbalance entre clases.

---

## 📌 Conclusiones

- El modelo aprende patrones relacionados a los años normales, pero necesita ajustes y más datos para predecir años críticos.
- La temperatura mínima anual mostró ser la variable más relevante.
- Se recomienda en futuras versiones:
  - Aumentar la cantidad de instancias
  - Balancear las clases (SMOTE)
  - Probar otros modelos (como SVM o XGBoost)


## Enlace a video

- https://drive.google.com/file/d/1I4BMlpDgw_qUTPxEzIjlUGik-qljCYei/view?usp=sharing
