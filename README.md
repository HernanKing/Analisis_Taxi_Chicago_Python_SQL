# Análisis de Datos de Viajes Compartidos en Chicago (Zuber)

## Descripción del Proyecto
Este proyecto se centra en el análisis de datos de viajes en taxi en Chicago para una nueva empresa de viajes compartidos, Zuber. El objetivo principal es identificar patrones en las preferencias de los pasajeros y evaluar el impacto de factores externos, específicamente las condiciones climáticas, en la frecuencia de los viajes.

## Problema de Negocio / Objetivo
La empresa Zuber necesita comprender mejor su mercado potencial en Chicago. Para ello, es crucial:
1.  Identificar las preferencias de los pasajeros (ej. barrios de recogida/destino populares, duración de viajes).
2.  Determinar cómo las condiciones climáticas (lluvia, nieve, etc.) afectan la demanda y el comportamiento de los viajes.
3.  Validar hipótesis sobre la relación entre el clima y la frecuencia de los viajes.

## Conjunto de Datos
Se trabajó con una base de datos relacional que contiene información detallada sobre viajes en taxi en Chicago, estructurada en las siguientes tablas:
* `neighborhoods`: Detalles de los barrios (`name`, `neighborhood_id`).
* `cabs`: Información sobre los vehículos (`cab_id`, `vehicle_id`, `company_name`).
* `trips`: Registros de cada viaje (`trip_id`, `start_ts`, `end_ts`, `duration_seconds`, `distance_miles`, `pickup_location_id`, `dropoff_location_id`).
* `weather_records`: Datos meteorológicos (`record_id`, `ts`, `temperature`, `description`).

## Herramientas y Tecnologías Utilizadas
* **Python:** Para la manipulación, limpieza y análisis de datos.
    * `pandas`: Para la gestión y transformación de DataFrames.
    * `numpy`: Para operaciones numéricas.
    * `matplotlib` / `seaborn`: Para la visualización de datos (si aplicaste).
    * `scipy.stats` (o similar): Para pruebas de hipótesis (si realizaste un test estadístico).
* **SQL:** Para la extracción y combinación de datos de la base de datos relacional.

## Metodología
1.  **Extracción de Datos:** Se utilizaron consultas SQL para extraer y combinar la información relevante de las tablas `trips`, `neighborhoods`, `cabs` y `weather_records`.
2.  **Preprocesamiento y Limpieza de Datos:**
    * Manejo de valores ausentes y tipos de datos.
    * Normalización de datos temporales para facilitar el análisis.
3.  **Análisis Exploratorio de Datos (EDA):**
    * Identificación de los barrios con mayor actividad de recogida/destino.
    * Análisis de la duración y distancia promedio de los viajes.
    * Exploración de la distribución de los viajes a lo largo del tiempo (horas del día, días de la semana).
4.  **Análisis de Impacto del Clima:**
    * Combinación de datos de viajes con registros meteorológicos.
    * Análisis comparativo de la frecuencia de viajes en diferentes condiciones climáticas (ej. días lluviosos vs. días despejados).
    * **Prueba de Hipótesis:** Se realizó una prueba estadística (ej. t-test) para determinar si existe una diferencia significativa en la duración/frecuencia de los viajes en días con condiciones climáticas adversas (ej. 'lluvia ligera', 'lluvia', 'nubes dispersas') comparado con días de clima normal.
