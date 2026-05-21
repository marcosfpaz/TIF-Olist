# 📊 Análisis del Comportamiento del Consumidor en E-Commerce

### Trabajo Integrador Final — Diplomatura Universitaria en Ciencia de Datos
**Universidad Católica de Santiago del Estero (UCSE)** · Facultad de Ciencia, Innovación y Diseño

---

## 📌 Resumen

Proyecto de Ciencia de Datos sobre el dataset público de **Olist**, el marketplace de e-commerce más grande de Brasil. El trabajo integra técnicas de obtención, limpieza, análisis, modelado y visualización de datos para responder a una pregunta de negocio real: **¿qué patrones de comportamiento permiten segmentar a los clientes de un marketplace y cómo se relacionan con la satisfacción y el valor generado para el negocio?**

El proyecto se materializa en un dashboard interactivo de **Power BI** que sintetiza los hallazgos y permite la toma de decisiones basada en datos.

---

## 🎯 Pregunta de investigación

> ¿Qué patrones de comportamiento permiten segmentar a los clientes de un marketplace de e-commerce, y cómo esos segmentos —junto con factores logísticos y de satisfacción— se relacionan con el valor generado para el negocio?

---

## 🎓 Objetivos

### Objetivo general
Aplicar técnicas de ciencia de datos sobre datos transaccionales reales de e-commerce para generar insights accionables sobre comportamiento de clientes, performance logística y satisfacción del consumidor.

### Objetivos específicos
1. Integrar y limpiar las 9 tablas relacionales del dataset Olist
2. Realizar un análisis exploratorio profundo (EDA) sobre ventas, geografía, categorías y reseñas
3. Construir variables RFM (Recencia, Frecuencia, Monetario) por cliente
4. Segmentar clientes mediante clustering no supervisado (K-Means)
5. Modelar los factores que predicen la insatisfacción del cliente
6. Analizar la relación entre tiempos de entrega y calificaciones
7. Diseñar un dashboard interactivo con los hallazgos clave
8. Proponer decisiones de negocio fundamentadas en los datos

---

## 📂 Dataset

**Brazilian E-Commerce Public Dataset by Olist**
- **Fuente:** [Kaggle — olistbr/brazilian-ecommerce](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)
- **Volumen:** ~100.000 órdenes reales
- **Período:** Septiembre 2016 — Octubre 2018
- **Cobertura geográfica:** Brasil (todos los estados)
- **Licencia:** CC BY-NC-SA 4.0

### Tablas que componen el dataset

| Tabla | Descripción |
|---|---|
| `olist_customers_dataset` | Clientes y ubicación geográfica |
| `olist_orders_dataset` | Órdenes con timestamps del ciclo de vida |
| `olist_order_items_dataset` | Items por orden, precios y flete |
| `olist_order_payments_dataset` | Métodos y cuotas de pago |
| `olist_order_reviews_dataset` | Calificaciones (1-5) y comentarios |
| `olist_products_dataset` | Categoría, peso y dimensiones de productos |
| `olist_sellers_dataset` | Vendedores y ubicación |
| `olist_geolocation_dataset` | Coordenadas geográficas por código postal |
| `product_category_name_translation` | Traducción de categorías al inglés |

---

## 🔬 Metodología

El proyecto sigue la metodología **CRISP-DM** (Cross-Industry Standard Process for Data Mining):

1. **Comprensión del negocio** — definición del problema y la pregunta de investigación
2. **Comprensión de los datos** — EDA inicial, perfilado y diagrama relacional
3. **Preparación de los datos** — limpieza, integración y feature engineering
4. **Modelado** — segmentación (K-Means) y clasificación (Random Forest / Regresión Logística)
5. **Evaluación** — métricas (silhouette, accuracy, F1, AUC) e interpretación
6. **Despliegue** — dashboard final en Power BI y conclusiones de negocio

---

## 🧠 Ejes analíticos

| Eje | Pregunta de negocio | Técnica aplicada |
|---|---|---|
| **1. Segmentación de clientes** | ¿Qué tipos de clientes existen en la plataforma? | RFM + K-Means + PCA |
| **2. Satisfacción y logística** | ¿Qué factores predicen una mala reseña? | Clasificación supervisada |
| **3. Análisis de mercado** | ¿Qué categorías y regiones generan más valor? | EDA geográfico + series de tiempo |

---

## 🛠️ Stack tecnológico

| Categoría | Herramientas |
|---|---|
| Lenguaje | Python 3.10+ |
| Manipulación de datos | pandas, numpy |
| Visualización | matplotlib, seaborn, plotly |
| Base de datos | SQLite + SQL |
| Machine Learning | scikit-learn, mlxtend |
| Dashboard | Power BI Desktop |
| Entorno | Jupyter Notebook |
| Control de versiones | Git + GitHub |

---

## 📁 Estructura del repositorio

```
TIF-Olist/
│
├── data/
│   ├── raw/                    # CSVs originales del dataset (no versionados)
│   ├── processed/              # Datasets intermedios limpios
│   └── final/                  # Tablón consolidado para modelado
│
├── notebooks/
│   ├── 01_EDA_inicial.ipynb           # Exploración por tabla y calidad de datos
│   ├── 02_limpieza_integracion.ipynb  # Limpieza y construcción del tablón único
│   ├── 03_EDA_avanzado.ipynb          # Storytelling y hallazgos
│   ├── 04_segmentacion_RFM.ipynb      # Clustering de clientes
│   ├── 05_modelo_satisfaccion.ipynb   # Clasificación de reseñas
│   └── 06_analisis_geografico.ipynb   # Mapas y series temporales
│
├── sql/
│   └── consultas_exploratorias.sql    # Queries SQL sobre el modelo relacional
│
├── dashboard/
│   └── Olist_Dashboard.pbix           # Dashboard final en Power BI
│
├── informe/
│   ├── informe_final.docx             # Documento académico final
│   ├── presentacion_defensa.pptx      # Slides para la defensa
│   └── img/                           # Gráficos y figuras
│
├── .gitignore
├── README.md
└── requirements.txt
```

---

## 🚀 Instalación y ejecución

### 1. Clonar el repositorio
```bash
git clone https://github.com/marcosfpaz/TIF-Olist.git
cd TIF-Olist
```

### 2. Crear entorno virtual (recomendado)
```bash
python -m venv venv
source venv/bin/activate          # Linux / Mac
venv\Scripts\activate             # Windows
```

### 3. Instalar dependencias
```bash
pip install -r requirements.txt
```

### 4. Descargar el dataset
- Descargar desde [Kaggle](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)
- Descomprimir los CSV en la carpeta `data/raw/`

### 5. Ejecutar los notebooks
```bash
jupyter notebook
```
Ejecutar los notebooks en orden numérico, del `01` al `06`.

### 6. Abrir el dashboard
Abrir `dashboard/Olist_Dashboard.pbix` con **Power BI Desktop**.

---

## 📅 Cronograma de desarrollo

| Semana | Etapa | Estado |
|---|---|---|
| 1 | Setup, descarga y EDA inicial | 🟢 En curso |
| 2 | Limpieza e integración de tablas | ⚪ Pendiente |
| 3 | EDA avanzado y storytelling | ⚪ Pendiente |
| 4 | Feature engineering RFM | ⚪ Pendiente |
| 5 | Modelado de segmentación (K-Means) | ⚪ Pendiente |
| 6 | Modelado de satisfacción | ⚪ Pendiente |
| 7 | Dashboard en Power BI | ⚪ Pendiente |
| 8 | Informe final y preparación de defensa | ⚪ Pendiente |

---

## 📈 Principales hallazgos

*Esta sección se completará a medida que avance el proyecto.*

---

## 📚 Bibliografía consultada

- Dangeti, P., & Eswara, N. J. (2019). *Introducción a la estadística para la ciencia de datos*. Editorial Montesco.
- Montenegro, Á. (2019). *Aprendizaje automático*. Editorial HWK.
- Domínguez, E. M. (2015). *Data Science: Introducción*. Editorial Océano.
- Caballero, S. G. (2020). *Big Data y Business Intelligence*. Editorial Prints.
- Fernández de Larrea, C., & Martínez Rubio, E. (2021). *Data Science para la toma de decisiones empresariales*. McGraw-Hill.
- Provost, F., & Fawcett, T. (2013). *Data Science for Business*. O'Reilly Media.

---

## 👤 Autor

**Ing. Marcos F. Paz**
Cursante de la Diplomatura Universitaria en Ciencia de Datos — UCSE
Tucumán, Argentina · 2026

**Docente a cargo:** Prof. Lilia Palomo

---

## 📄 Licencia

Este proyecto se desarrolla con fines exclusivamente académicos en el marco del Trabajo Integrador Final de la Diplomatura Universitaria en Ciencia de Datos de la UCSE. El dataset utilizado se encuentra bajo licencia Creative Commons (CC BY-NC-SA 4.0).
