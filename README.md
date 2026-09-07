# 📊 Análisis del Comportamiento del Consumidor en E-Commerce

**Segmentación de clientes, predicción de insatisfacción y análisis logístico sobre 100.000 órdenes reales del marketplace brasileño Olist.**

`Python` · `SQL` · `scikit-learn` · `FastAPI` · `Power BI`

---

## 🚧 Estado del proyecto

> **Repositorio público desde el día 1, en construcción abierta.**
> Arrancó el 7 de septiembre de 2026 y se desarrolla en 6 sprints hasta diciembre. Cada sprint deja algo ejecutable en `main`, no una promesa: si un sprint no cierra, se recorta el alcance y se mantiene la fecha.

| Sprint | Entregable | Fecha objetivo | Estado |
|---|---|---|---|
| **S0** | Dataset cargado en DuckDB/SQLite (9 tablas) + `01_carga_sql.ipynb` con 5 consultas | 14-sep-2026 | 🟡 En curso |
| **S1** | Limpieza + `02_eda.ipynb` — 10 gráficos, cada uno con su lectura | 05-oct-2026 | ⚪ Pendiente |
| **S2** | `03_segmentacion.ipynb` — variables RFM + K-Means (elbow y silhouette) | 26-oct-2026 | ⚪ Pendiente |
| **S3** | `04_insatisfaccion.ipynb` — clasificador de reseñas + `api/` FastAPI + `Dockerfile` | 16-nov-2026 | ⚪ Pendiente |
| **S4** | Dashboard en Power BI + documento del informe | 07-dic-2026 | ⚪ Pendiente |
| **S5** | README final con resultados, `requirements.txt` congelado, test mínimo | 19-dic-2026 | ⚪ Pendiente |

**Hoy el repositorio contiene solo el andamiaje** — estructura, dependencias y este plan. El primer notebook llega con S0.

---

## 📌 Resumen

Proyecto de Ciencia de Datos sobre el dataset público de **Olist**, el marketplace de e-commerce más grande de Brasil. Integra obtención, limpieza, análisis, modelado y despliegue de datos para responder una pregunta de negocio concreta.

> **¿Qué patrones de comportamiento permiten segmentar a los clientes de un marketplace de e-commerce, y cómo esos segmentos —junto con factores logísticos y de satisfacción— se relacionan con el valor generado para el negocio?**

---

## 🎯 Objetivos

Aplicar técnicas de ciencia de datos sobre datos transaccionales reales para generar insights accionables sobre comportamiento de clientes, performance logística y satisfacción del consumidor.

1. Integrar y limpiar las 9 tablas relacionales del dataset Olist
2. Análisis exploratorio sobre ventas, geografía, categorías y reseñas
3. Construir variables **RFM** (Recencia, Frecuencia, Monetario) por cliente
4. Segmentar clientes mediante clustering no supervisado (K-Means)
5. Modelar los factores que predicen la insatisfacción del cliente
6. Analizar la relación entre tiempos de entrega y calificaciones
7. Exponer el modelo tras una API y contenerizarlo
8. Sintetizar los hallazgos en un dashboard interactivo

---

## 📂 Dataset

**Brazilian E-Commerce Public Dataset by Olist**

- **Fuente:** [Kaggle — olistbr/brazilian-ecommerce](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)
- **Volumen:** ~100.000 órdenes reales · **Período:** sep-2016 → oct-2018
- **Cobertura:** Brasil, todos los estados
- **Licencia:** CC BY-NC-SA 4.0

Los CSV **no se versionan** (ver `.gitignore`): se descargan de Kaggle a `data/raw/`.

| Tabla | Descripción |
|---|---|
| `olist_customers_dataset` | Clientes y ubicación geográfica |
| `olist_orders_dataset` | Órdenes con timestamps del ciclo de vida |
| `olist_order_items_dataset` | Items por orden, precios y flete |
| `olist_order_payments_dataset` | Métodos y cuotas de pago |
| `olist_order_reviews_dataset` | Calificaciones (1-5) y comentarios |
| `olist_products_dataset` | Categoría, peso y dimensiones |
| `olist_sellers_dataset` | Vendedores y ubicación |
| `olist_geolocation_dataset` | Coordenadas por código postal |
| `product_category_name_translation` | Traducción de categorías al inglés |

---

## 🔬 Metodología

**CRISP-DM** (Cross-Industry Standard Process for Data Mining):

1. **Comprensión del negocio** — problema y pregunta de investigación
2. **Comprensión de los datos** — EDA inicial, perfilado, diagrama relacional
3. **Preparación** — limpieza, integración y feature engineering
4. **Modelado** — segmentación (K-Means) y clasificación supervisada
5. **Evaluación** — silhouette, accuracy, F1, AUC e interpretación
6. **Despliegue** — API, dashboard y conclusiones de negocio

### Ejes analíticos

| Eje | Pregunta de negocio | Técnica |
|---|---|---|
| **Segmentación** | ¿Qué tipos de clientes existen en la plataforma? | RFM + K-Means + PCA |
| **Satisfacción y logística** | ¿Qué factores predicen una mala reseña? | Clasificación supervisada |
| **Análisis de mercado** | ¿Qué categorías y regiones generan más valor? | EDA geográfico + series de tiempo |

---

## 🛠️ Stack

| Categoría | Herramientas |
|---|---|
| Lenguaje | Python 3.10+ |
| Datos | pandas · numpy |
| Base de datos | DuckDB / SQLite + SQL |
| Visualización | matplotlib · seaborn · plotly |
| Machine Learning | scikit-learn · mlxtend |
| API y despliegue | FastAPI · Docker |
| Dashboard | Power BI Desktop |
| Entorno | Jupyter Notebook |

---

## 📁 Estructura

```
TIF-Olist/
│
├── data/
│   ├── raw/                      # CSVs de Kaggle (no versionados)
│   ├── processed/                # Datasets intermedios limpios
│   └── final/                    # Tablón consolidado para modelado
│
├── notebooks/
│   ├── 01_carga_sql.ipynb        # S0 · Carga en DuckDB + consultas SQL
│   ├── 02_eda.ipynb              # S1 · Limpieza y análisis exploratorio
│   ├── 03_segmentacion.ipynb     # S2 · RFM + K-Means
│   └── 04_insatisfaccion.ipynb   # S3 · Clasificador de reseñas
│
├── api/                          # S3 · FastAPI que expone el modelo
│   └── Dockerfile
│
├── dashboard/                    # S4 · Power BI
├── informe/                      # S4 · Documento y figuras
│
├── .gitignore
├── README.md
└── requirements.txt
```

---

## 🚀 Instalación

```bash
# 1. Clonar
git clone https://github.com/marcosfpaz/TIF-Olist.git
cd TIF-Olist

# 2. Entorno virtual
python -m venv venv
source venv/bin/activate          # Linux / macOS
venv\Scripts\activate             # Windows

# 3. Dependencias
pip install -r requirements.txt

# 4. Dataset
# Descargar de Kaggle y descomprimir los CSV en data/raw/

# 5. Notebooks
jupyter notebook
```

Ejecutar los notebooks en orden numérico.

---

## 📈 Hallazgos

*Se completa a medida que cierran los sprints. Vacío es vacío: acá no va nada hasta que haya un número detrás.*

---

## 👤 Autor

**Ing. Marcos F. Paz**
Ingeniero Electrónico · Ciencia de Datos y Machine Learning
Tucumán, Argentina

Desarrollado en el marco de la Diplomatura Universitaria en Ciencia de Datos (UCSE).

---

## 📄 Licencia

Proyecto académico y de portafolio. El dataset utilizado está bajo licencia **CC BY-NC-SA 4.0** (Creative Commons Atribución-NoComercial-CompartirIgual).
