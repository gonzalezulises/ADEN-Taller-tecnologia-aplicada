# Sesion 05: OLAP vs OLTP - Procesos ETL Conceptuales

**Fecha:** 13 de febrero, 2026
**Unidad:** 2 - Data Warehouse
**Duracion:** 4 horas (2 teoricas + 2 practicas)

## Objetivo de Aprendizaje

> **DIFERENCIAR** operaciones OLTP de OLAP analizando consultas SQL y comprendiendo rol de ETL

## Contenidos

- 2.5 Diferencias OLAP vs OLTP
- 2.6 Procesos de Extraccion, Transformacion y Carga (ETL)
- Mapeo de transformaciones necesarias
- Introduccion a herramientas ETL

## Estructura de la Sesion

### Inicio
- Quiz rapido Kahoot: OLTP vs OLAP

### Desarrollo
- Exposicion comparativa OLTP/OLAP
- **[INGLES]** Video: Microsoft Learn "Design Data Warehouse"
- Lab SQL: Queries OLTP (Northwind) vs OLAP (AdventureWorksDW)
- Introduccion ETL conceptual
- Mapeo de transformaciones necesarias

### Cierre
- **ENTREGA Proyecto Fase 1:** Analisis necesidades + Diseno DW (15%)

## Actividades del Estudiante

### En Clase
- [ ] Participacion en Quiz Kahoot
- [ ] Ejecucion de queries SQL comparativos
- [ ] Analisis de diferencias OLTP vs OLAP
- [ ] Mapeo de transformaciones ETL

### Entregables
- [ ] **Proyecto Fase 1** (15%): Documento tecnico + Diagrama ER dimensional

## Recursos

### Bibliografia
- Kimball & Ross (2013) Cap.1-5 [INGLES]
- Microsoft SQL Server Documentation [INGLES]
- Pentaho Kettle Guide [INGLES]

### Datasets
- Northwind (OLTP)
- AdventureWorksDW (OLAP)

### Tutoriales
- Microsoft Learn "Design DW" [INGLES]
- Kimball Group Techniques [INGLES]

## Evaluacion

| Actividad | Tipo | Valor |
|-----------|------|-------|
| **Proyecto Fase 1** | Sumativa | **15%** |
| Quiz Kahoot | Formativa | - |

## OLTP vs OLAP - Comparativa

| Caracteristica | OLTP | OLAP |
|----------------|------|------|
| **Proposito** | Operaciones diarias | Analisis y reportes |
| **Usuarios** | Empleados operativos | Analistas, gerentes |
| **Queries** | Simples, predefinidas | Complejas, ad-hoc |
| **Datos** | Actuales, detallados | Historicos, agregados |
| **Modelo** | Normalizado (3NF) | Dimensional (estrella) |
| **Volumen query** | Miles/segundo | Pocas/minuto |
| **Tiempo respuesta** | Milisegundos | Segundos a minutos |

## Ejemplos de Queries

### Query OLTP (Northwind)
```sql
-- Obtener detalle de una orden especifica
SELECT o.OrderID, c.CompanyName, p.ProductName,
       od.Quantity, od.UnitPrice
FROM Orders o
JOIN Customers c ON o.CustomerID = c.CustomerID
JOIN [Order Details] od ON o.OrderID = od.OrderID
JOIN Products p ON od.ProductID = p.ProductID
WHERE o.OrderID = 10248;
```

### Query OLAP (AdventureWorksDW)
```sql
-- Ventas totales por categoria y anio
SELECT
    d.EnglishProductCategoryName AS Categoria,
    t.CalendarYear AS Anio,
    SUM(f.SalesAmount) AS VentasTotales,
    COUNT(DISTINCT f.CustomerKey) AS ClientesUnicos
FROM FactInternetSales f
JOIN DimProduct p ON f.ProductKey = p.ProductKey
JOIN DimProductSubcategory s ON p.ProductSubcategoryKey = s.ProductSubcategoryKey
JOIN DimProductCategory d ON s.ProductCategoryKey = d.ProductCategoryKey
JOIN DimDate t ON f.OrderDateKey = t.DateKey
GROUP BY d.EnglishProductCategoryName, t.CalendarYear
ORDER BY Anio, VentasTotales DESC;
```

## Proceso ETL - Flujo Conceptual

```
┌─────────────────────────────────────────────────────────────────┐
│                         PROCESO ETL                              │
├─────────────────┬─────────────────────┬─────────────────────────┤
│   EXTRACCION    │   TRANSFORMACION    │        CARGA            │
│   (Extract)     │   (Transform)       │       (Load)            │
├─────────────────┼─────────────────────┼─────────────────────────┤
│ • Bases de datos│ • Limpieza datos    │ • Carga inicial (Full)  │
│ • Archivos CSV  │ • Estandarizacion   │ • Carga incremental     │
│ • APIs          │ • Derivacion campos │ • Validacion integridad │
│ • Web scraping  │ • Agregaciones      │ • Actualizacion indices │
│ • IoT/Sensores  │ • Joins/Lookups     │ • Log de errores        │
└─────────────────┴─────────────────────┴─────────────────────────┘
```

## Transformaciones Comunes

| Tipo | Descripcion | Ejemplo |
|------|-------------|---------|
| Limpieza | Eliminar duplicados, nulos | DISTINCT, COALESCE |
| Estandarizacion | Formato uniforme | UPPER(), DATE_FORMAT |
| Derivacion | Calcular nuevos campos | edad = YEAR(NOW()) - YEAR(fecha_nac) |
| Agregacion | Resumir datos | SUM(), AVG(), COUNT() |
| Lookup | Enriquecer con datos externos | JOIN con tabla de referencia |

## Rubrica Proyecto Fase 1 (15%)

| Criterio | Excelente (4) | Bueno (3) | Regular (2) | Deficiente (1) |
|----------|---------------|-----------|-------------|----------------|
| Analisis de necesidades | Completo y justificado | Adecuado | Parcial | Incompleto |
| Modelo dimensional | Correcto y optimizado | Funcional | Con errores menores | Incorrecto |
| Documentacion | Clara y profesional | Adecuada | Basica | Insuficiente |
| Trabajo en equipo | Excelente colaboracion | Buena | Regular | Deficiente |

---
*Taller de Tecnologia Aplicada - ADEN University - Cuatrimestre I 2026*
