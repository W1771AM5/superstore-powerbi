# Análisis de Ventas y Rentabilidad — Sample Superstore

Proyecto de práctica para portafolio de Analista de Datos / BI. Simula el trabajo de un analista que recibe un requerimiento de negocio y lo convierte en un modelo de datos, medidas DAX y un dashboard funcional en Power BI.

## Estado del proyecto
🚧 En progreso — Fase actual: limpieza y modelado de datos.

## Requerimiento de negocio (ficticio)

> "Soy la gerente comercial. Necesito ver cómo van las ventas y la rentabilidad, por región y categoría, comparadas con el año pasado, y saber qué productos o clientes nos están haciendo perder margen."

## Dataset

- **Fuente:** [Sample Superstore Dataset](https://www.kaggle.com/datasets/bravehart101/sample-supermarket-dataset) (Kaggle)
- **Contenido:** transacciones de venta de una tienda ficticia (pedidos, productos, clientes, envíos).
- **Tamaño:** ver `docs/log_limpieza.md` para el conteo final de filas.
- **Columnas:** 19 (Row ID, Order ID, Order Date, Ship Date, Ship Mode, Customer ID, Segment, Country, City, State, Region, Product ID, Category, Sub-Category, Product Name, Sales, Quantity, Discount, Profit).
- **Limitaciones conocidas:** esta versión no incluye `Customer Name` ni `Postal Code`. La dimensión de clientes se trabaja con `Customer ID`; la dimensión geográfica se arma con `Country`, `Region`, `State` y `City`.

## Herramientas utilizadas

- **Power BI Desktop:** Power Query (limpieza y transformación), modelado de datos, medidas DAX, visualización.
- **Excel:** análisis exploratorio previo con tablas dinámicas.
- **SQL:** consultas de validación sobre el mismo conjunto de datos.

## Estructura del repositorio

```
superstore-powerbi/
├── README.md
├── data/               # dataset original, sin modificar
├── docs/
│   ├── log_limpieza.md       # registro de problemas de calidad de datos y sus soluciones
│   └── diccionario_kpis.md   # definición de cada KPI del dashboard
├── powerbi/            # archivo .pbix
└── img/                # capturas del dashboard final
```

## Proceso

1. **Limpieza y calidad de datos** (Power Query) — ver `docs/log_limpieza.md`.
2. **Modelado** — separación en tabla de hechos (Ventas) y dimensiones (Clientes, Productos, Geografía, Calendario), esquema estrella.
3. **Medidas DAX** — KPIs de ventas, margen y comparativos interanuales.
4. **Dashboard** — resumen ejecutivo, análisis de rentabilidad y detalle por cliente/producto.

## Próximos pasos

- Completar limpieza (duplicados, nulos, normalización de texto).
- Construir el modelo estrella.
- Definir y documentar KPIs.
- Publicar capturas del dashboard en `img/`.