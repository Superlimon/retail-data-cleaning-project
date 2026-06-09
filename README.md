# Proyecto de Limpieza de Datos - Retail

## 📊 Descripción del proyecto

Este proyecto se centra en la limpieza, transformación y validación de un dataset de transacciones de un negocio retail que contiene aproximadamente 10.400 registros.

El dataset incluye información sobre clientes, productos, fechas de compra, cantidades, precios unitarios y gasto total por transacción.

El objetivo principal es preparar un conjunto de datos limpio, consistente y fiable para su posterior análisis exploratorio o modelado.

---

## 🧹 Proceso de limpieza de datos

Durante el análisis inicial se identificaron varios problemas de calidad de datos:

- Eliminación de 367 registros duplicados exactos
- Tratamiento de valores faltantes en variables de clientes y transacciones
- Eliminación de filas donde faltaban simultáneamente `purchase_quantity` y `total_spent` (datos irrecuperables)
- Conversión de `purchase_date` de tipo `object` a `datetime64[ns]`
- Estandarización de tipos de datos:
  - Variables numéricas: `age`, `purchase_quantity`
  - Variables categóricas e identificadores: `customer_name`, `city`, `product_name`, `category`, etc.
- Normalización de texto (minúsculas y eliminación de espacios en blanco)

---

## ✔️ Validación de calidad de datos

Tras la limpieza, se realizaron distintas comprobaciones:

- Verificación de valores nulos mediante `isna().sum()`
- Confirmación de eliminación de duplicados con `duplicated()`
- Validación de tipos de datos en todas las columnas
- Creación de una columna de verificación (`check`) para comprobar la coherencia: purchase_quantity * price_per_unit = total_spent

- Detección y marcado de valores atípicos (*outliers*) en:
- Edad
- Cantidad de compra
- Precio por unidad
- Gasto total

El dataset final queda reducido a **9.340 registros** (desde los 10.400 iniciales).

---

## 📦 Resultado final

El dataset limpio ha sido exportado como:

cleaned_dataset.csv

Este dataset está listo para su uso en análisis posteriores, visualización de datos o modelos predictivos.

---

## 🧠 Supuestos realizados

- La ausencia de información de cliente no invalida necesariamente una transacción.
- Las filas sin cantidad y gasto total simultáneamente se consideran datos no recuperables.
- Los valores atípicos se mantienen como variables de control (flags) para análisis posterior.

---

## 🚀 Tecnologías utilizadas

- Python
- Pandas
- NumPy
- Google Colab

---

## 📌 Autor

Proyecto de limpieza y preparación de datos desarrollado como práctica de análisis de datos.

  
