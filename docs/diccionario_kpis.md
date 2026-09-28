# Diccionario de KPIs — Sample Superstore

Definición de cada indicador usado en el dashboard: qué mide, cómo se calcula, de dónde salen los datos y quién lo usaría. Se completa a medida que se construyen las medidas DAX.

## Formato de cada entrada

| Campo | Descripción |
|---|---|
| **Nombre** | Nombre del KPI tal como aparece en el dashboard |
| **Definición** | Qué mide, en una frase clara para un usuario no técnico |
| **Fórmula (DAX)** | La medida tal como está escrita en Power BI |
| **Fuente** | Tabla(s) y columna(s) de origen |
| **Frecuencia** | Con qué periodicidad se actualiza o se revisa |
| **Dueño / Área** | Quién lo usa o es responsable de validarlo |

---

## KPIs definidos

*(Pendiente — se completa en la fase de medidas DAX)*

### Ejemplo de referencia (borrar al completar el primero real)

| Campo | Detalle |
|---|---|
| **Nombre** | Ventas Totales |
| **Definición** | Suma del monto vendido, sin descuentos aplicados por separado (ya incluidos en `Sales`) |
| **Fórmula (DAX)** | `Ventas Total = SUM(Ventas[Sales])` |
| **Fuente** | Tabla `Ventas`, columna `Sales` |
| **Frecuencia** | Diaria (según actualización del dataset) |
| **Dueño / Área** | Gerencia Comercial |