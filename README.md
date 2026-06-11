# Global Trade Intelligence Dashboard 🌍📊
> **Análisis dinámico de importaciones, exportaciones y estrategias de Pricing de la competencia a partir de registros masivos de aduanas.**

Este proyecto automatiza y optimiza el proceso de extracción, transformación y carga (ETL) de datos comerciales masivos de comercio exterior para el sector de salud visual y de dispositivos médicos (líneas oftálmica, quirúrgica y de cuidado ocular). El sistema recopila datos históricos desde la plataforma **Veritrade**, centraliza la información en un entorno analítico y despliega dashboards avanzados que permiten monitorizar el *Market Share*, las cadenas de suministro y las estrategias de precios de los competidores clave en el mercado local.

---

## 🚀 Propósito del Proyecto
Anteriormente, los equipos comerciales consumían la data directamente desde la plataforma web de Veritrade, lo que limitaba las consultas a análisis planos, manuales y de corto plazo sin capacidad de consolidar un histórico real. 

Este proyecto reconstruyó desde cero un sistema obsoleto, permitiendo:
*   **Análisis Histórico Consolidado:** Integración de meses y años de registros aduaneros para evaluar tendencias a largo plazo.
*   **Inteligencia Competitiva Avanzada:** Mapeo y comparativa directa del rendimiento de la compañía frente a competidores directos (como Johnson & Johnson, entre otros).
*   **Segmentación por Líneas de Producto:** Clasificación exacta por subfamilias como lentes intraoculares, lentes de contacto, gotas oftalmológicas y equipos quirúrgicos.

---

## 🛠️ Stack Tecnológico
*   **Origen de Datos:** Veritrade API / Web Platform (Data de Aduanas).
*   **Base de Datos / Almacenamiento:** SQL Server (Modelamiento, estructuración e histórico).
*   **Procesamiento y ETL:** SQL (Limpieza de textos, filtrado por palabras clave y subpartidas aduaneras).
*   **Visualización de Datos:** Tableau (Dashboards interactivos y analítica visual masiva).

---

## ⚙️ Arquitectura del Datos y Flujo ETL

### 1. Extracción (Data Sourcing)
Se extrae la data cruda pagada mediante la licencia corporativa desde la plataforma Veritrade. Esta incluye la totalidad de campos críticos de las declaraciones aduaneras:
*   **Actores:** Importador local, Exportador/Proveedor internacional.
*   **Logística:** Vía de transporte (Marítimo, Aéreo), flotas, rutas logísticas y fechas de transacciones.
*   **Métricas Financieras:** Valor FOB, flete, seguros, impuestos pagados, aranceles y precios unitarios calculados.
*   **Métricas Físicas:** Peso bruto, peso neto, unidades físicas y unidades comerciales.

### 2. Transformación y Limpieza (Data Cleansing)
Dado que las consultas por texto libre de Veritrade introducen "ruido" y registros ajenos al core business del ojo (ej. importaciones de insumos cardiológicos, pulmonares u otros productos médicos con palabras clave similares), se implementó una lógica rigurosa de limpieza en SQL Server:
*   **Filtros de Negocio:** Exclusión de registros irrelevantes mediante validación cruzada de palabras clave específicas del sector oftalmológico y códigos de referencia o partidas aduaneras.
*   **Normalización de Unidades:** Homogeneización de unidades físicas, empaques y valores económicos para permitir comparativas reales.
*   **Limpieza de Entidades (Data Steward):** Estandarización de nombres de competidores y fabricantes extranjeros (ej. unificar diferentes variaciones de nombres comerciales de una misma matriz).

### 3. Carga y Modelamiento (Data Loading)
Consolidación de la data depurada en tablas optimizadas dentro de SQL Server, estructuradas de manera eficiente para su rápida lectura desde el motor de BI (Tableau).

---

## 📊 Componentes del Dashboard y Análisis Analítico
El entregable final en Tableau proporciona una interfaz dinámica interactiva para la toma de decisiones comerciales y de compras:

*   **Módulo de Market Share:** Visualización de la cuota de mercado en tiempo real segmentada por subfamilias de producto (Gotas, Lentes de Contacto, Lentes Intraoculares).
*   **Monitoreo de Competencia & Stock:** Alertas visuales basadas en volumen y frecuencia de importación para predecir si un competidor se está quedando sin stock o está sobreabasteciendo el mercado.
*   **Análisis de Pricing Strategy:** Evolución del precio de importación por producto a lo largo del tiempo para identificar descuentos de proveedores o estrategias agresivas de precios en el mercado.
*   **Análisis de Tendencias (MAT):** Implementación de análisis dinámicos basados en *Moving Annual Total* (MAT), comparativas interanuales (YoY), mensuales (MoM), variaciones porcentuales y evolución por zonas geográficas.

---

## 📂 Estructura Sugerida del Repositorio
```text
├── src/
│   ├── sql/
│   │   ├── extraction_queries.sql     # Consultas iniciales y filtros por palabras clave
│   │   └── data_cleansing_etl.sql     # Lógica de limpieza, normalización y exclusión de ruido
│   └── tableau/
│       └── global_trade_dashboard.twbx # Archivo empaquetado del Dashboard o documentación de diseño
├── docs/
│   └── data_dictionary.md             # Diccionario de campos extraídos de Veritrade
└── README.md                          # Descripción general del proyecto
```
---
## 📈 Impacto en el Negocio
*   **Automatización:** Eliminación del proceso manual de descarga y cruce de datos en hojas de cálculo por parte de los analistas.

*   **Precisión Comercial:** Reducción del margen de error en un 100% respecto a registros fuera del sector oftálmico.

*   **Visión Estratégica:** Capacidad de anticipación ante los movimientos de distribución, precios y proveedores globales de los principales competidores del sector salud.
---
### 👤 Autoría y Liderazgo Analítico
**Juan Chocce** - Lead Business Intelligence & Systems Engineer

[LinkedIn](https://www.linkedin.com/in/juanchocce/) 🔗
[GitHub Profile](https://github.com/juanchocce) 🐙
