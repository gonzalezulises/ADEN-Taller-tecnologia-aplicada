# Sesion 02: Arquitectura de BI y Componentes del Ecosistema

**Fecha:** 23 de enero, 2026
**Unidad:** 1 - Introduccion al Business Intelligence
**Duracion:** 4 horas (2 teoricas + 2 practicas)

## Objetivo de Aprendizaje

> **ANALIZAR** arquitectura de sistema BI identificando fuentes de datos, ETL, DW, reporting y usuarios finales

## Contenidos

- Arquitectura de BI por capas
- Fuentes de datos empresariales
- Procesos ETL (Extraccion, Transformacion, Carga)
- Data Warehouse y Data Marts
- Capa de reporting y usuarios finales

## Estructura de la Sesion

### Inicio
- Revision de resultados del diagnostico
- Conexion con sesion anterior

### Desarrollo
- Exposicion: Arquitectura BI (capas)
- **[INGLES]** Lectura: Watson (2023) "BI: Past, Present, Future"
- Caso Copa Airlines: Identificar componentes de su arquitectura BI
- Demo: Power BI y Google Data Studio

### Cierre
- Quiz Formativo Unidad 1 (2%)
- Tarea: Investigar Gartner Magic Quadrant

## Actividades del Estudiante

### En Clase
- [ ] Lectura previa: Davenport & Harris "Competing on Analytics" Cap.1 [INGLES]
- [ ] Analisis colaborativo caso Copa Airlines
- [ ] Identificacion de componentes BI en casos reales
- [ ] Participacion en debate estructurado
- [ ] Toma de notas de conceptos clave

### Trabajo Autonomo
- [ ] Investigar Gartner Magic Quadrant BI [INGLES]
- [ ] Completar Quiz formativo Canvas

## Recursos

### Bibliografia
- Turban et al. (2021) Cap.1 [INGLES]
- Davenport & Harris (2022) [INGLES]
- Watson (2023) "BI: Past, Present, Future" [INGLES]
- Video TED: Hans Rosling

### Software
- Power BI Desktop (demo)
- Google Data Studio (demo)

### Casos de Estudio
- Copa Airlines BI Roadmap

## Evaluacion

| Actividad | Tipo | Valor |
|-----------|------|-------|
| Quiz Unidad 1 (Canvas) | Formativa | 2% |
| Observacion participacion | Formativa | - |
| Rubrica colaboracion | Formativa | - |

## Arquitectura BI - Capas

```
┌─────────────────────────────────────────────────┐
│           CAPA DE PRESENTACION                  │
│    (Dashboards, Reportes, Analisis Ad-hoc)      │
├─────────────────────────────────────────────────┤
│              CAPA OLAP                          │
│    (Cubos multidimensionales, MDX)              │
├─────────────────────────────────────────────────┤
│           DATA WAREHOUSE                        │
│    (Modelo dimensional, Data Marts)             │
├─────────────────────────────────────────────────┤
│              CAPA ETL                           │
│    (Extraccion, Transformacion, Carga)          │
├─────────────────────────────────────────────────┤
│         FUENTES DE DATOS                        │
│    (ERP, CRM, Archivos, APIs, IoT)              │
└─────────────────────────────────────────────────┘
```

## Notas del Docente

Enfatizar la importancia de cada capa y como se relacionan entre si. Usar el caso de Copa Airlines como ejemplo concreto de implementacion en Latinoamerica.

---
*Taller de Tecnologia Aplicada - ADEN University - Cuatrimestre I 2026*
