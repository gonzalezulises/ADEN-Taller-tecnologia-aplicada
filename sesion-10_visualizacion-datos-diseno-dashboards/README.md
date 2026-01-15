# Sesion 10: Principios de Visualizacion de Datos y Diseno de Dashboards

**Fecha:** 27 de marzo, 2026
**Unidad:** 4 - Aplicaciones Avanzadas de Business Intelligence
**Duracion:** 4 horas (2 teoricas + 2 practicas)

## Objetivo de Aprendizaje

> **DISENAR** visualizaciones efectivas aplicando principios de Few y Tufte para comunicar insights claramente

## Contenidos

- 4.3 Principios de visualizacion de datos efectiva
- 4.4 Diseno de dashboards interactivos con Power BI
- Data-Ink Ratio (Tufte)
- Seleccion de graficos apropiados

## Estructura de la Sesion

### Inicio
- Muestra de dashboards buenos vs malos
- Pregunta: "¿Que hace efectiva una visualizacion?"

### Desarrollo
- **[INGLES]** Lectura: Few "Dashboard Design" + Tufte "Data-Ink Ratio"
- Exposicion: Tipos de graficos y cuando usarlos
- Taller critico: Analizar dashboards reales
- Ejercicio: Re-disenar dashboard en wireframe
- Introduccion a Power BI interface

### Cierre
- Galeria de wireframes
- Tarea: Instalar Power BI Desktop

## Actividades del Estudiante

### En Clase
- [ ] Analisis critico de dashboards reales
- [ ] Aplicacion de principios de Few y Tufte
- [ ] Diseno de wireframe de dashboard
- [ ] Familiarizacion con Power BI interface

### Trabajo Autonomo
- [ ] Instalar Power BI Desktop
- [ ] Tutoriales Microsoft Learn Power BI [INGLES]
- [ ] Lectura: Nussbaumer Knaflic "Storytelling with Data" [INGLES]

## Recursos

### Bibliografia
- Few, S. (2021). *Information Dashboard Design* (2nd ed.) Cap.1-3 [INGLES]
- Tufte, E. R. (2020). *The Visual Display of Quantitative Information* [INGLES]
- Cairo, A. (2023). *The Truthful Art* [INGLES]
- Nussbaumer Knaflic, C. (2022). *Storytelling with Data* [INGLES]

### Software
- Power BI Desktop
- Tableau Public
- Google Data Studio

### Recursos Online
- Tableau Public Gallery
- Microsoft Learn Power BI [INGLES]
- Tableau Dashboard Starter Kit [INGLES]

## Evaluacion

| Actividad | Tipo | Valor |
|-----------|------|-------|
| Wireframe dashboard | Formativa | - |
| Analisis critico | Formativa | - |

## Principios de Tufte: Data-Ink Ratio

> "Above all else, show the data" - Edward Tufte

```
                    Tinta dedicada a los datos
Data-Ink Ratio = ─────────────────────────────────
                    Tinta total del grafico

Objetivo: Maximizar este ratio (cercano a 1)
```

### Eliminar "Chartjunk"

| Evitar | Por que |
|--------|---------|
| Fondos decorativos | Distraen del mensaje |
| Efectos 3D | Distorsionan percepcion |
| Gridlines excesivas | Ruido visual |
| Colores innecesarios | Confunden |
| Leyendas redundantes | Ocupan espacio |

## Principios de Stephen Few

### Los 13 Errores Comunes en Dashboards

1. Exceder limites de una pantalla
2. Proporcionar contexto inadecuado
3. Mostrar precision excesiva
4. Elegir medidas inapropiadas
5. Elegir graficos inapropiados
6. Usar variaciones de color inefectivas
7. Disenar visualizacion desordenada
8. Codificar datos cuantitativos incorrectamente
9. Organizar datos pobremente
10. Resaltar datos incorrectamente
11. Usar medios de visualizacion inapropiados
12. Producir desalineacion visual
13. Agregar distracciones visuales

## Seleccion de Graficos

```
¿Que quieres mostrar?
        │
        ├── Comparacion ──────► Barras, Columnas
        │
        ├── Composicion ──────► Pie (pocos), Stacked Bars, Treemap
        │
        ├── Distribucion ─────► Histograma, Box Plot, Scatter
        │
        ├── Relacion ─────────► Scatter Plot, Bubble Chart
        │
        └── Tendencia ────────► Lineas, Area
```

### Guia Rapida

| Tipo de Dato | Grafico Recomendado | Evitar |
|--------------|---------------------|--------|
| Categorias (pocas) | Barras horizontales | Pie con muchas categorias |
| Series temporales | Lineas | Barras (dificulta ver tendencia) |
| Parte del todo | Stacked bars, Treemap | Pie 3D |
| Correlacion | Scatter plot | Tablas |
| Distribucion | Histograma, Box plot | Barras simples |
| KPIs individuales | Cards, Gauges | Graficos complejos |

## Anatomia de un Dashboard Efectivo

```
┌─────────────────────────────────────────────────────────────────┐
│  TITULO DEL DASHBOARD                              [Filtros]    │
├─────────────────┬─────────────────┬─────────────────────────────┤
│                 │                 │                             │
│   KPI Card 1    │   KPI Card 2    │         KPI Card 3          │
│   $1.2M         │   +15%          │         847                 │
│   Ventas        │   Crecimiento   │         Clientes            │
│                 │                 │                             │
├─────────────────┴─────────────────┼─────────────────────────────┤
│                                   │                             │
│    GRAFICO PRINCIPAL              │    GRAFICO SECUNDARIO       │
│    (Tendencia temporal)           │    (Top 10, Comparacion)    │
│                                   │                             │
│                                   │                             │
│                                   │                             │
├───────────────────────────────────┴─────────────────────────────┤
│                                                                 │
│              TABLA DE DETALLE O GRAFICO ADICIONAL               │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

## Ejercicio: Redisenar Dashboard

### Dashboard Original (Problematico)
- [ ] Identificar 5 problemas de diseno
- [ ] Aplicar principios de Tufte y Few
- [ ] Crear wireframe mejorado
- [ ] Justificar cada decision de diseno

### Criterios de Evaluacion
1. Reduccion de chartjunk
2. Seleccion apropiada de graficos
3. Jerarquia visual clara
4. Uso efectivo de color
5. Facilidad de comprension

## Preparacion para Siguiente Sesion

### Instalacion Requerida
1. Descargar Power BI Desktop: https://powerbi.microsoft.com/desktop/
2. Crear cuenta Microsoft (si no tienen)
3. Revisar tutorial basico de interface

### Lectura Recomendada
- Microsoft Power BI Best Practices [INGLES]
- DAX Function Reference (introduccion) [INGLES]

---
*Taller de Tecnologia Aplicada - ADEN University - Cuatrimestre I 2026*
