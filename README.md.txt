# 🚀 Olist E-Commerce: Executive Logistics & Sales Dashboard

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-3776AB?style=for-the-badge&logo=python&logoColor=white)
![SQL / Data Modeling](https://img.shields.io/badge/Star%20Schema-00E5FF?style=for-the-badge&logo=databricks&logoColor=black)
![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)

Tablero ejecutivo de Business Intelligence (*One-Page Dashboard*) desarrollado en Power BI Desktop utilizando el dataset público de **Olist E-Commerce** (Brasil). El proyecto está diseñado bajo una estética visual **Dark Modern Tech / SaaS**, combinando un modelo de datos robusto en estrella con un diseño de interfaz de usuario de alto impacto visual y optimizado para la toma de decisiones gerenciales.

---

## 📊 Vista Previa del Dashboard
*(Acá podés insertar la captura de pantalla que tomaste de tu tablero)*
> `[ ![Preview del Tablero](./assets/dashboard_preview.png) ]`

---

## 🏗️ Arquitectura y Modelado de Datos
Para garantizar un rendimiento óptimo y evitar problemas de redundancia, se consolidó un **Modelo en Estrella (*Star Schema*)** relacionando 5 tablas principales del negocio de E-Commerce:
* **`olist_orders_dataset`** (Tabla de Hechos central)
* **`olist_order_items_dataset`** (Detalle de ítems por orden)
* **`olist_order_payments_dataset`** (Información de transacciones y pagos)
* **`olist_customers_dataset`** (Dimensión geográfica de clientes)
* **`olist_products_dataset`** (Dimensión de productos y categorías)

---

## 📐 Medidas DAX Principales
El núcleo analítico del reporte se construyó mediante medidas DAX optimizadas:

```dax
-- Cálculo de la facturación global del e-commerce
Ingresos Totales = SUM(olist_order_payments_dataset[payment_value])

-- Conteo único de transacciones completadas
Total Pedidos = DISTINCTCOUNT(olist_orders_dataset[order_id])

-- Indicador clave de rendimiento comercial por transacción
Ticket Promedio = DIVIDE([Ingresos Totales], [Total Pedidos])
[📥 Descargar archivo .pbix completo desde Google Drive](https://drive.google.com/file/d/1Vdl1xCrnJsJrelJFWe06QfZT3P824dEO/view?usp=sharing)