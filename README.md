# 📞 ConnectaTel: Análisis de Consumo y Segmentación de Clientes (Latam)

Este repositorio contiene el análisis exploratorio de datos (EDA), la auditoría de calidad y la segmentación estratégica de la base de usuarios de **ConnectaTel**, una empresa de telecomunicaciones con operaciones en México y Colombia.

El proyecto aborda un escenario real de ingeniería y análisis de datos donde la información de origen presenta problemas estructurales, inconsistencias temporales y comportamientos de consumo atípicos que impactan directamente en el diseño de la oferta comercial y en la retención de usuarios (*churn*).

## 🧠 Objetivo del Proyecto

* **Auditar y Validar:** Identificar y mitigar problemas críticos de calidad de datos (valores centinela, formatos inválidos, fechas incongruentes y registros corruptos).
* **Perfilamiento Estadístico:** Construir un perfil estadístico robusto (media, mediana, percentiles) del uso de llamadas y mensajes por cliente y segmentos demográficos.
* **Detección de Outliers:** Diagnosticar analíticamente los valores atípicos mediante métodos estadísticos y visuales para identificar consumos inusuales o errores de registro.
* **Segmentación Multidimensional:** Crear segmentaciones basadas en reglas de negocio (edad, plan y comportamiento de uso) para emitir recomendaciones.

## 📂 Datasets Utilizados

El análisis integra y consolida información proveniente de tres fuentes de datos principales:
1. **`plans.csv`:** Catálogo de planes comerciales con sus estructuras de costos (precio, minutos incluidos, GB incluidos, costo por extra).
2. **`users_latam.csv`:** Información demográfica y contractual de los clientes (`age`, `city`, `reg_date`, `plan`, `churn_date`).
3. **`usage.csv`:** Detalle del uso real y consumo histórico generado por los usuarios, dividiéndose en llamadas (`duration`) y mensajes (`length`).

## 🛠️ Etapas del Análisis Realizadas

1. **Auditoría de Calidad de Datos:** Identificación de nulos masivos, conteo de faltantes y detección de comportamientos anómalos en las tres fuentes independientes.
2. **Data Wrangling (Limpieza):** Imputación de valores centinela en edad (`-999`), remoción de fechas futuras incoherentes (`2026`), estandarización de strings corruptos (`?` en ciudades) e imputación lógica de ausencias en llamadas y mensajes por tipo de servicio (Mecanismo MAR).
3. **Análisis de Distribuciones:** Modelado visual con histogramas y curvas de densidad para las variables de uso real (minutos consumidos y longitud de mensajes).
4. **Identificación de Outliers:** Diagnóstico analítico con BoxPlots complementados con líneas de tendencia central (media y mediana) y cálculo del límite superior teórico por método IQR para separar el consumo típico de posibles anomalías o fraudes.
5. **Segmentación Multidimensional:** Construcción de perfiles demográficos personalizados (`Joven`, `Adulto`, `Adulto mayor`) y de consumo (`Bajo uso`, `Uso medio`, `Alto uso`) mediante funciones lógicas en Pandas.
6. **Visualización Avanzada:** Creación de gráficos cruzados de barras agrupadas (`countplot` usando `hue`) para el análisis simultáneo de variables de edad y nivel de interactividad.
7. **Insight Ejecutivo:** Redacción de conclusiones y recomendaciones comerciales basadas en los patrones de consumo para el equipo de Estrategia de ConnectaTel.

## ▶️ Cómo abrir el notebook en Google Colab

Haz clic en el siguiente botón para ejecutar el entorno interactivo:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Andreaa27/Telecom-analysis/blob/main/S7_Version_Estudiante_Project_ConnectaTel_(2).ipynb)


O de forma alternativa:
1. Abre el archivo `.ipynb` directamente desde este repositorio de GitHub.
2. Haz clic en el botón superior **Open in Colab** que la interfaz de GitHub renderiza automáticamente.

