# Sesion 11: Implementacion de Dashboards Interactivos en Power BI

**Fecha:** 3 de abril, 2026
**Unidad:** 4 - Aplicaciones Avanzadas de Business Intelligence
**Duracion:** 4 horas (2 teoricas + 2 practicas)

## Objetivo de Aprendizaje

> **CREAR** dashboard interactivo en Power BI con filtros, drill-down y narrativa visual para proyecto integrador

## Contenidos

- 4.4 Diseno de dashboards interactivos con Power BI
- Medidas DAX
- Slicers y filtros
- Drill-down y drill-through
- Publicacion en Power BI Service

## Estructura de la Sesion

### Inicio
- Revision de instalaciones de Power BI
- Resolucion de dudas tecnicas

### Desarrollo
- **[INGLES]** Microsoft Power BI Best Practices + DAX Reference
- Demo docente: Dashboard completo (medidas DAX, slicers, drill-down, publicar Service)
- Lab grupal: Construir dashboard Proyecto Fase 3

### Cierre
- Check-in de progreso
- Troubleshooting
- Anuncio: Entrega Fase 3 proxima semana (20%)

## Actividades del Estudiante

### En Clase
- [ ] Construccion de dashboard interactivo en Power BI (equipos)
- [ ] Creacion de medidas DAX
- [ ] Configuracion de slicers y drill-down
- [ ] Aplicacion de principios de diseno visual
- [ ] Desarrollo de narrativa de datos

### Preparacion Presentacion
- [ ] Preparar demo del dashboard
- [ ] Estructurar narrativa: problema → insights → recomendaciones

## Recursos

### Bibliografia
- Microsoft Power BI. (2024). "Dashboard Design Best Practices" [INGLES]
- Microsoft Power BI. (2024). "DAX Function Reference" [INGLES]
- Kaplan, R. S., & Norton, D. P. (2021). *The Balanced Scorecard* [INGLES]

### Software
- Power BI Desktop
- Power BI Service (para publicacion)

### Tutoriales
- Microsoft Learn Power BI [INGLES]
- DAX Patterns [INGLES]

## Evaluacion

| Actividad | Tipo | Valor |
|-----------|------|-------|
| Dashboard en progreso | Formativa | - |
| **Proyecto Fase 3** (siguiente sesion) | Sumativa | **20%** |

## Power BI - Componentes Principales

```
┌─────────────────────────────────────────────────────────────────┐
│                    POWER BI DESKTOP                             │
├─────────────────┬─────────────────┬─────────────────────────────┤
│    REPORT       │     DATA        │         MODEL               │
│    VIEW         │     VIEW        │         VIEW                │
├─────────────────┴─────────────────┴─────────────────────────────┤
│  • Visualizaciones  │  • Transformar datos  │  • Relaciones    │
│  • Slicers          │  • Power Query        │  • Medidas DAX   │
│  • Filtros          │  • Columnas calc.     │  • Cardinalidad  │
└─────────────────────┴─────────────────────┴─────────────────────┘
```

## DAX - Formulas Esenciales

### Medidas Basicas

```dax
// Suma total de ventas
Total Ventas = SUM(Ventas[Monto])

// Conteo de transacciones
Num Transacciones = COUNTROWS(Ventas)

// Promedio de venta
Promedio Venta = AVERAGE(Ventas[Monto])

// Conteo de clientes unicos
Clientes Unicos = DISTINCTCOUNT(Ventas[ClienteID])
```

### Medidas con Contexto

```dax
// Ventas del año anterior
Ventas Año Anterior =
CALCULATE(
    [Total Ventas],
    SAMEPERIODLASTYEAR(Calendario[Fecha])
)

// Crecimiento YoY
Crecimiento YoY =
DIVIDE(
    [Total Ventas] - [Ventas Año Anterior],
    [Ventas Año Anterior],
    0
)

// Ventas acumuladas YTD
Ventas YTD =
TOTALYTD([Total Ventas], Calendario[Fecha])
```

### Medidas Condicionales

```dax
// Clasificacion de clientes
Segmento Cliente =
SWITCH(
    TRUE(),
    [Total Compras Cliente] >= 10000, "Premium",
    [Total Compras Cliente] >= 5000, "Gold",
    [Total Compras Cliente] >= 1000, "Silver",
    "Bronze"
)
```

## Interactividad en Power BI

### Slicers (Filtros Visuales)

| Tipo | Uso | Ejemplo |
|------|-----|---------|
| Lista | Seleccion multiple | Categorias de producto |
| Dropdown | Espacio limitado | Regiones |
| Entre (Range) | Valores numericos | Rango de fechas |
| Relativo | Fechas dinamicas | Ultimos 30 dias |

### Drill-down vs Drill-through

| Caracteristica | Drill-down | Drill-through |
|----------------|------------|---------------|
| Navegacion | Dentro del mismo visual | A otra pagina |
| Jerarquia | Si (Año → Mes → Dia) | No necesariamente |
| Contexto | Se mantiene en visual | Se pasa a nueva pagina |
| Uso | Explorar niveles | Ver detalle completo |

## Estructura del Dashboard del Proyecto

### Pagina 1: Resumen Ejecutivo
- KPIs principales (cards)
- Tendencia temporal
- Top 5 categorias/productos

### Pagina 2: Analisis Detallado
- Visualizaciones interactivas
- Comparativas
- Drill-down habilitado

### Pagina 3: Insights Data Mining
- Resultados de clustering/clasificacion
- Segmentos identificados
- Recomendaciones basadas en datos

## Checklist Pre-Presentacion

- [ ] Datos cargados y actualizados
- [ ] Relaciones configuradas correctamente
- [ ] Medidas DAX funcionando
- [ ] Slicers sincronizados
- [ ] Drill-down probado
- [ ] Colores consistentes con identidad
- [ ] Titulos claros en cada visual
- [ ] Sin errores de carga
- [ ] Narrativa preparada

## Preparacion para Entrega Fase 3

### Entregables (Sesion 12)
1. **Dashboard publicado** en Power BI Service
2. **Presentacion oral** (10-15 min por equipo)
3. **Documento** con descripcion de visualizaciones

### Criterios de Evaluacion (20%)
- Calidad tecnica del dashboard
- Aplicacion de principios de diseno
- Efectividad de la narrativa
- Desempeno en presentacion oral

---
*Taller de Tecnologia Aplicada - ADEN University - Cuatrimestre I 2026*
