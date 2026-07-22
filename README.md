# RetailCol: Dashboard de Business Intelligence para Retail

Dashboard de análisis de ventas retail construido de extremo a extremo en Power BI: adquisición y modelado de datos, medidas DAX, visualización ejecutiva y storytelling analítico orientado a decisiones de negocio.

## Sobre los datos

Este proyecto utiliza un **dataset generado con lógica de negocio realista** (patrones de estacionalidad, distribución geográfica, comportamiento de descuentos y desempeño de vendedores), dado que datos comerciales reales de retail no son de acceso público. El objetivo del proyecto es demostrar dominio técnico completo del pipeline de BI (modelado, DAX, visualización y narrativa), no realizar un análisis de mercado real.

## Datos crudos y proceso de limpieza

El archivo original (`data/raw/RetailCol_Ventas_2025.xlsx`) contiene 2,808 registros de transacciones con las siguientes inconsistencias reales, generadas intencionalmente para practicar el proceso de limpieza:

 Problemas detectados:
 52 transacciones con `ID_Transaccion` repetido 
 96 registros sin `Precio_Unitario` 
 **Inconsistencia de texto en `Ciudad`** : 14 variantes distintas para 5 ciudades reales (ej. "Bogotá", "Bogota", "BOGOTA", "bogota" todas representan la misma ciudad) 
 **Sin estandarizar mayúsculas/tildes**   Mezcla de mayúsculas, minúsculas y con/sin tilde en nombres de ciudad 

El proceso de limpieza en Power Query incluyó: Creacion de un perfil de datos para detectar anomalías en el dataset, que concluyó en la eliminación de duplicados por `ID_Transaccion`, exclusión de nulos en `Precio_Unitario`, y estandarización de la columna `Ciudad` a un formato único por ciudad (capitalización y tildes consistentes) para permitir agrupaciones correctas en el modelo de datos.

## Contenido del dashboard

1. **Resumen Ejecutivo y Balance General** — KPIs principales (Ingreso Total, Total Transacciones, Ticket Promedio, Total Unidades) e ingreso por ciudad.
2. **Registro Cronológico** — evolución mensual de ingresos y transacciones.
3. **Análisis Geográfico** — desempeño por ciudad con mapa interactivo, ticket promedio e ingreso total.
4. **Productos y Categoría** — unidades e ingresos por categoría de producto y canal de venta.
5. **Rendimiento por Canal y Descuentos** — impacto de los descuentos aplicados sobre el ticket promedio y las unidades vendidas.
6. **Rendimiento de Vendedores** — ingreso por vendedor y evolución trimestral de ventas.
7. **Insights Analíticos** — hallazgos clave: estabilidad del ticket promedio entre ciudades y la relación entre categorías con mayor volumen vs. mayor rentabilidad.
8. **Estrategia de Descuentos** — evidencia de que los descuentos aplicados (hasta 25%) no generan un incremento real de volumen, con un 69.63% de las unidades vendidas sin ningún descuento.
9. **Recomendación y Simulador What-If** — proyección interactiva de ingreso neto según distintos escenarios de descuento (0-20%), con recomendación de eliminar o rediseñar la estrategia actual.

## Hallazgo principal

El análisis muestra que la estrategia de descuentos vigente **no genera un aumento proporcional en volumen de ventas** — el comportamiento de compra es en gran medida inmune a las promociones, y los descuentos solo reducen el ingreso neto sin un retorno claro. El simulador What-If permite cuantificar el impacto de mantener, reducir o eliminar esta estrategia.

## Herramientas utilizadas

Power BI · Power Query · DAX (medidas de agregación, parámetros What-If) · Modelado de datos relacional

## Medidas DAX destacadas

- `Ingreso Total`
- `Total Transacciones`
- `Ticket Promedio` (con `DIVIDE` para control de división por cero)
- `Total Unidades`
- `Medidas Utilizadas para el Simulador`


*Proyecto de portafolio — Juan Camilo Morales Cervantes, estudiante de Ingeniería de Sistemas, Universidad del Magdalena.*
