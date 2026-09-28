# Log de limpieza de datos — Sample Superstore

Registro de los problemas de calidad de datos encontrados durante la preparación en Power Query, cómo se detectaron, cómo se resolvieron y cómo se validó cada solución.

## Contexto del dataset

- **Fuente:** Sample Superstore Dataset (Kaggle)
- **Filas:** *(completar tras activar "Generación de perfiles de columna basada en todo el conjunto de datos")*
- **Columnas:** 19
- **Nota:** el dataset no incluye `Customer Name` ni `Postal Code`. Se usa `Customer ID` como identificador de cliente en los visuales, y la dimensión geográfica se construye con `Country`, `Region`, `State` y `City`.

---

## Registro de problemas y soluciones

| # | Columna(s) | Problema detectado | Cómo se detectó | Solución aplicada | Validación |
|---|---|---|---|---|---|
| 1 | `Order Date`, `Ship Date` | Fechas cargadas como texto, con separadores mixtos (`-` y `/`) y formato mes/día/año (estilo EE. UU.) | Vista previa de Power Query: ícono ABC en vez de calendario; comparación de filas mostró formatos distintos para la misma columna | Cambio de tipo a Fecha usando **configuración regional en-US** (clic derecho en encabezado > Cambiar tipo > Usar configuración regional) | 0% de errores en ambas columnas tras la conversión; columna de control `Duración de envío` sin valores negativos |
| 2 | `Order ID`, `Ship Date`, `Order Date` (control) | Verificar consistencia: `Ship Date` no debería ser anterior a `Order Date` | Columna personalizada `Duration.Days([Ship Date] - [Order Date])`, ordenada ascendente | N/A — columna de verificación, no de corrección | Rango observado: *(completar con mínimo y máximo obtenidos)* |
| 3 | `Row ID` | Confirmar que no haya filas duplicadas | Comparación de "Distinto" vs. "Único" en el perfil de columna (Vista > Calidad de columna) | *(pendiente)* | *(pendiente)* |
| 4 | Todas las columnas | Identificar valores nulos/vacíos | Perfil de columna con generación de perfiles sobre el 100% de los datos | *(pendiente)* | *(pendiente)* |
| 5 | `Region`, `Category`, `Sub-Category`, `Segment` | Espacios sobrantes o inconsistencias de mayúsculas/minúsculas en texto | *(pendiente de revisión)* | *(pendiente — Transformar > Formato > Recortar / Limpiar)* | *(pendiente)* |

---

## Decisiones y notas adicionales

- *(Ejemplo a completar más adelante: "No se eliminaron filas con Discount = 0.8 porque corresponden a ventas reales con pérdida, relevantes para el análisis de rentabilidad.")*

## Columnas renombradas / pasos clave en Power Query

- Paso "Tipo cambiado" (automático) → revisado manualmente fila por fila para `Order Date` y `Ship Date`.
- Paso "Fechas convertidas (en-US)" → conversión con configuración regional.
- Paso "Duración de envío" → columna de control, evaluar si se conserva como KPI (`Días de Envío`) o se elimina antes de publicar.