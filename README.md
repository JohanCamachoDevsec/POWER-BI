# 🩺 Integración y Análisis de Indicadores de Salud Global

## 📘 Descripción del Proyecto

Este proyecto tiene como objetivo **integrar, transformar y analizar indicadores globales de salud** provenientes de múltiples fuentes. A través de un proceso **ETL desarrollado en Pentaho Data Integration (PDI)** y un **modelo analítico en Power BI**, se construyó un dashboard interactivo que permite analizar tendencias en mortalidad infantil, esperanza de vida, gasto en salud, vacunación y población, por país, continente y periodo temporal.

---

## 🎯 Objetivos de Aprendizaje

* Implementar un proceso **ETL completo** (Extract, Transform, Load) usando **Pentaho Data Integration**.
* Aplicar principios de **Data Governance** para garantizar calidad, trazabilidad y consistencia en los datos.
* Diseñar un **modelo de datos en Power BI** con relaciones entre tablas de hechos y dimensiones.
* Crear **medidas DAX** para el análisis temporal y comparativo de indicadores.
* Desarrollar visualizaciones que faciliten la **toma de decisiones basada en datos (Data-Driven Decisions)**.

---

## 🧩 Arquitectura del Proyecto

### **1. Extracción y Transformación (ETL)**

* Herramienta: **Pentaho Data Integration (PDI)**
* **Fuentes de datos (CSV):**

  * `Infant_Death_Rate.csv` → Mortalidad infantil y tasa de vacunación
  * `Life_Expectancy.csv` → Esperanza de vida y gasto en salud
  * `Population.csv` → Población total por país y fecha
* **Proceso:**

  * Carga de los tres datasets.
  * Unión (join) por `country` y `fecha`.
  * Validación de campos clave:
    `country, fecha, tasa_vacunacion, mortalidad_infantil, gasto_salud, esperanza_vida, poblacion`
  * Exportación final: `IndicadoresSalud.csv`.

> 🧠 En esta etapa apliqué buenas prácticas de **data quality**, verificación de duplicados y consistencia temporal.

---

### **2. Modelado de Datos en Power BI**

* Integración del dataset consolidado `IndicadoresSalud.csv`.
* Creación de **tablas de dimensiones**:

  * **DimTiempo** (Año, Mes, Trimestre, Fecha, NombreMes)
  * **DimPaises** (País, Continente)
* Configuración de relaciones:

  * `IndicadoresSalud[fecha]` → `DimTiempo[Fecha]`
  * `IndicadoresSalud[country]` → `DimPaises[country]`
* Validación del modelo mediante el **diagrama de relaciones en estrella (Star Schema)**, alineado con principios de **Data Modeling for Analytics**.

---

### **3. Cálculos DAX**

Se desarrollaron medidas personalizadas para el análisis exploratorio y descriptivo:

* **Mortalidad Infantil Promedio**
* **Tasa de Vacunación Promedio**
* **Gasto en Salud Promedio**
* **Total de Población**
* **Esperanza de Vida Promedio**
* **Tasa de Mortalidad por 1,000 habitantes**
* **Cambio Anual en Mortalidad Infantil**
* **Porcentaje de Vacunación por Año**
* **Mortalidad Promedio por Continente**

> 🧮 En esta fase reforcé habilidades de **DAX avanzado** y **time intelligence functions** aplicadas a análisis longitudinales.

---

### **4. Visualizaciones en Power BI**

El dashboard final incluye:

* 📊 **Evolución de la mortalidad infantil** por año y continente.
* 💰 **Relación entre gasto en salud y esperanza de vida**.
* 🗺️ **Mapa mundial de población** por país y año.
* 💉 **Comparación entre tasa de vacunación y mortalidad infantil**.
* ⚠️ **Indicadores KPI** para resaltar países con mayor vulnerabilidad sanitaria.

> El diseño se enfocó en **data storytelling**, aplicando **colores condicionales y filtros interactivos** para análisis dinámico.

---

## 🧠 Lo que Aprendí

* Implementar flujos **ETL robustos y documentados**, considerando **metadatos, control de versiones y calidad de datos**.
* Modelar información siguiendo principios de **Data Governance**: integridad, consistencia y linaje.
* Desarrollar **medidas DAX complejas** que permitan comparar tendencias en el tiempo y entre regiones.
* Diseñar reportes ejecutivos de **BI con enfoque analítico** y visualmente claros.
* Integrar conocimientos de **Data Science descriptiva** en herramientas de BI, para obtener insights basados en evidencia.

---

## 🧱 Tecnologías Utilizadas

| Herramienta                         | Propósito                                        |
| ----------------------------------- | ------------------------------------------------ |
| **Pentaho Data Integration (PDI)**  | Proceso ETL (extracción, transformación y carga) |
| **Microsoft Power BI**              | Modelado y visualización de datos                |
| **DAX (Data Analysis Expressions)** | Creación de medidas analíticas                   |
| **CSV / Excel**                     | Fuentes y exportaciones de datos                 |
| **Data Governance Frameworks**      | Estandarización y control de calidad de datos    |

---

## 📈 Resultados y Conclusiones
<img width="1275" height="786" alt="image" src="https://github.com/user-attachments/assets/cfb528b7-2250-4499-acb0-3e4420252fe7" />
<img width="1237" height="753" alt="image" src="https://github.com/user-attachments/assets/67616718-a300-415e-8612-527519cc7842" />

El proyecto permitió consolidar múltiples fuentes de datos heterogéneas en un modelo único, confiable y analíticamente útil.
El reporte final facilita identificar **relaciones entre gasto en salud, vacunación y esperanza de vida**, así como **disparidades sanitarias entre continentes**.

Además, el proceso fortaleció mi dominio en **BI end-to-end**, desde la extracción de datos hasta la presentación visual y narrativa de resultados.
