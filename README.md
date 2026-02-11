# 🚗 Predicción de Precios de Autos Usados

## 📌 Resumen

Este proyecto consiste en el desarrollo de una aplicación web interactiva construida con **Streamlit**, cuyo objetivo es permitir a vendedores, compradores y lotes de autos cargar datos de vehículos en formato CSV para estimar precios de mercado, utilizando un modelo **XGBoost** previamente entrenado y optimizado.

La aplicación se enfoca en la **rapidez de valuación** y la **precisión del mercado**, evitando el reentrenamiento del modelo y ofreciendo estimaciones inmediatas basadas en patrones históricos de más de 180,000 registros filtrados.

| Problema en el Mercado Automotriz                  | Solución de la Aplicación                                   |
| -------------------------------------------------- | ----------------------------------------------------------- |
| **Fijación de precios subjetiva o inconsistente**  | Estimación objetiva basada en ML con variables clave        |
| **Tiempo excesivo en valuación manual**            | Resultados inmediatos tras carga de archivo CSV             |
| **Sobreprecio o subprecio en inventarios**         | Optimización de márgenes mediante predicciones precisas     |
| **Variabilidad entre evaluadores**                 | Estandarización mediante modelo XGBoost validado            |
| **Pérdida de oportunidades de venta**              | Precios competitivos alineados con el mercado real          |

---

## 🧠 Descripción del Proyecto

Sistema de valuación automotriz basado en **XGBoost** que procesa múltiples características del vehículo (marca, modelo, año, kilometraje, estado, etc.) vía CSV para estimar precios en segundos, sin reentrenamiento. Solución práctica de ML para el mercado de autos usados.

### Pipeline de Datos Implementado

1. **Limpieza inicial**: Eliminación de variables irrelevantes (URLs, IDs duplicados)
2. **Manejo de valores nulos**: Imputación estratégica por categoría
3. **Reducción de cardinalidad**: Agrupación de categorías poco frecuentes
4. **Filtrado de calidad**: 
   - Años: 2000 a la actualidad
   - Rango de precios: $1,000 - $40,000 USD
   - Dataset final: **180,000 registros**

---

## 📊 Modelo de Machine Learning

| Elemento             | Descripción                                                                             |
| -------------------- | --------------------------------------------------------------------------------------- |
| **Usuario**          | Vendedores particulares, lotes de autos, compradores                                    |
| **Inputs**           | Marca, modelo, año, kilometraje, estado, transmisión, combustible, etc.                |
| **Modelo**           | **XGBoost Regressor** (optimizado)                                                      |
| **Output**           | Precio estimado en USD                                                                  |
| **Propósito**        | Valuación automática de autos usados para compra/venta                                  |
| **Entorno**          | Lotes de autos, plataformas de venta, evaluación personal                               |
| **Impacto**          | Precios competitivos, reducción de tiempo de inventario, decisiones informadas          |
| **Métrica clave**    | MAE minimizados; R² óptimo                                                       |
| **Formato datos**    | Archivo CSV con carga masiva                                                            |
| **Latencia**         | Resultados inmediatos (&lt; 1 segundo por lote)                                            |
| **Preprocesamiento** | **One-Hot Encoding** (variables categóricas) + **RoboustScaler** (variables numéricas) |
| **Optimización**     | GridSearchCV                         |

### Comparativa de Modelos Desarrollados

| Modelo                | Tiempo Entrenamiento | Interpretabilidad | Precisión | Decisión Final |
| --------------------- | -------------------- | ----------------- | --------- | -------------- |
| **Regresión Lineal Múltiple** | Rápido               | Alta              | Media     | Descartado     |
| **Red Neuronal (PyTorch)**    | Lento                | Baja              | Alta      | Descartado     |
| **XGBoost**                   | Rápido               | Alta              | Alta      | **Seleccionado** |

**Razón de selección**: Balance óptimo entre velocidad de inferencia, capacidad de interpretación de características importantes (feature importance) y precisión predictiva.

---

## 🖥️ Aplicación Web con Streamlit

La aplicación web fue desarrollada con **Streamlit** y cuenta con:

* **Carga de archivo CSV** para ingreso masivo de datos de vehículos (variables requeridas predefinidas).
* **Validación de datos**: Verificación automática de formato y rangos de variables.
* **Botón para generar predicciones**: Estimación de precios individuales y por lote.
* **Descarga de resultados**: Dataset enriquecido con columna de precios predichos.
* **Carga del modelo XGBoost** sin necesidad de reentrenamiento.
* **Interfaz intuitiva** optimizada para usuarios sin conocimientos técnicos.

### Casos de Uso Principales

| Segmento | Beneficio |
|----------|-----------|
| **Vendedores particulares** | Fijar precios competitivos basados en datos reales del mercado |
| **Lotes de autos** | Valuación rápida de inventario completo para optimización de márgenes |
| **Compradores** | Verificar si un vehículo está sobrevalorado o subvalorado antes de comprar |

---
## 🚀 Cómo Usar la Aplicación

### Datos de Ejemplo Incluidos

El repositorio incluye el archivo **`data/new_data.csv`** con datos de ejemplo listos para usar. Este archivo contiene registros de vehículos representativos que puedes cargar directamente en la aplicación para probar el modelo sin necesidad de preparar tu propio dataset.

| Archivo | Descripción | Uso |
|---------|-------------|-----|
| `data/new_data.csv` | Dataset de ejemplo con variables requeridas | Prueba inicial de la aplicación y validación de formato |



## 🛠️ Tecnologías Utilizadas

* **Python**
* **Pandas & NumPy**: Manipulación y limpieza de datos
* **Scikit-learn**: Preprocesamiento y métricas de evaluación
* **XGBoost**: Modelo principal de regresión
* **PyTorch**: Desarrollo de red neuronal comparativa
* **Streamlit**: Despliegue de [**aplicación**](https://sistemaprediccionpreciosautosusadosapp-8d5px7b6iucdskkztehxjc.streamlit.app/)  interactiva
* **Joblib/Pickle**: Serialización del modelo

---

