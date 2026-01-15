# Sesion 04: Data Warehouse - Modelado Dimensional

**Fecha:** 6 de febrero, 2026
**Unidad:** 2 - Data Warehouse
**Duracion:** 4 horas (2 teoricas + 2 practicas)

## Objetivo de Aprendizaje

> **APLICAR** tecnicas de modelado dimensional (star schema, snowflake) disenando modelo conceptual para DW del proyecto

## Contenidos

- 2.1 Conceptos y Modelado del Data Warehouse
- 2.2 Diseno dimensional: esquema estrella y copo de nieve
- 2.3 Tablas de hechos (facts) y dimensiones
- 2.4 Dimensiones lentamente cambiantes (SCD Type 1, 2, 3)

## Estructura de la Sesion

### Inicio
- Activacion: "Dibuja como organizarias ventas para analisis"
- Revision de conceptos previos OLTP/OLAP

### Desarrollo
- **[INGLES]** Lectura: Kimball & Ross "Dimensional Modeling"
- Exposicion: Hechos vs Dimensiones
- Demo: AdventureWorksDW en SQL Server
- Lab grupal: Disenar modelo dimensional en Draw.io

### Cierre
- Presentacion de borradores
- Tarea: Completar diagrama ER dimensional

## Actividades del Estudiante

### En Clase
- [ ] Ejercicio diagnostico individual
- [ ] Lectura: Kimball & Ross Cap.1-5 [INGLES]
- [ ] Diseno de modelo dimensional en Draw.io (equipos)
- [ ] Documentacion de decisiones de diseno

### Trabajo Autonomo
- [ ] Completar diagrama ER dimensional
- [ ] Tutorial Microsoft Learn "Design DW" [INGLES]
- [ ] Quiz formativo preparacion

## Recursos

### Bibliografia
- Kimball, R., & Ross, M. (2013). *The Data Warehouse Toolkit* (3rd ed.). Cap.1-5 [INGLES]
- Inmon, W. H. (2021). *Building the Data Warehouse* (5th ed.) [INGLES]
- Rainardi, V. (2022). *Building a Data Warehouse* [INGLES]

### Documentacion Tecnica
- Microsoft SQL Server Documentation [INGLES]
- Kimball Group Techniques [INGLES]

### Herramientas
- SQL Server 2022 / PostgreSQL
- Draw.io / Lucidchart
- Dataset AdventureWorksDW

### Tutoriales
- Microsoft Learn "Design DW" [INGLES]
- Kimball Group Techniques [INGLES]

## Evaluacion

| Actividad | Tipo | Valor |
|-----------|------|-------|
| Modelo dimensional (borrador) | Formativa | - |
| Participacion en lab | Formativa | - |

## Esquema Estrella vs Copo de Nieve

### Esquema Estrella (Star Schema)
```
                    ┌─────────────┐
                    │ DIM_TIEMPO  │
                    │─────────────│
                    │ fecha_id    │
                    │ dia         │
                    │ mes         │
                    │ anio        │
                    └──────┬──────┘
                           │
┌─────────────┐     ┌──────┴──────┐     ┌─────────────┐
│ DIM_PRODUCTO│     │ FACT_VENTAS │     │ DIM_CLIENTE │
│─────────────│     │─────────────│     │─────────────│
│ producto_id │◄────│ producto_id │────►│ cliente_id  │
│ nombre      │     │ cliente_id  │     │ nombre      │
│ categoria   │     │ fecha_id    │     │ segmento    │
│ precio      │     │ tienda_id   │     │ region      │
└─────────────┘     │ cantidad    │     └─────────────┘
                    │ monto       │
                    │ descuento   │
┌─────────────┐     └──────┬──────┘
│ DIM_TIENDA  │            │
│─────────────│◄───────────┘
│ tienda_id   │
│ nombre      │
│ ciudad      │
│ region      │
└─────────────┘
```

### Esquema Copo de Nieve (Snowflake)
```
┌──────────────┐     ┌─────────────┐
│ DIM_CATEGORIA│◄────│ DIM_PRODUCTO│
│──────────────│     │─────────────│
│ categoria_id │     │ producto_id │
│ nombre       │     │ nombre      │
│ descripcion  │     │ categoria_id│
└──────────────┘     └──────┬──────┘
                            │
                     ┌──────┴──────┐
                     │ FACT_VENTAS │
                     └─────────────┘
```

## Tablas de Hechos vs Dimensiones

| Caracteristica | Tabla de Hechos | Tabla de Dimension |
|----------------|-----------------|-------------------|
| Contenido | Metricas numericas | Atributos descriptivos |
| Granularidad | Una fila por evento | Una fila por entidad |
| Tamano | Millones de filas | Miles de filas |
| Crecimiento | Rapido (transaccional) | Lento |
| Ejemplo | Ventas, Inventario | Producto, Cliente, Tiempo |

## Dimensiones Lentamente Cambiantes (SCD)

| Tipo | Estrategia | Uso |
|------|------------|-----|
| **SCD Type 1** | Sobrescribir | No se requiere historial |
| **SCD Type 2** | Nueva fila con fechas | Historial completo |
| **SCD Type 3** | Columna adicional | Solo valor anterior |

## Ejercicio Practico: AdventureWorksDW

Explorar la base de datos de ejemplo de Microsoft:
- Identificar tablas de hechos
- Identificar tablas de dimensiones
- Analizar relaciones y cardinalidad
- Documentar granularidad de cada fact table

---
*Taller de Tecnologia Aplicada - ADEN University - Cuatrimestre I 2026*
