# Sesion 13: Estrategias de Implementacion BI y Madurez Organizacional

**Fecha:** Por definir (TBD)
**Unidad:** 5 - Estrategias y Tendencias en BI
**Duracion:** 4 horas (2 teoricas + 2 practicas)

## Objetivo de Aprendizaje

> **EVALUAR** nivel de madurez BI organizacional y proponer estrategias de adopcion, gobierno de datos y change management

## Contenidos

- 5.1 Planificacion e Implementacion de proyectos BI
- 5.2 Factores criticos de exito en adopcion de BI
- 5.3 Gobernanza de Datos: calidad, privacidad, seguridad
- 5.4 Madurez organizacional en BI (niveles de adopcion)
- 5.5 Tendencias emergentes: BI en la nube (AWS, Azure)
- 5.6 BI movil y self-service analytics
- 5.7 Inteligencia Artificial aplicada a BI
- 5.8 Smart Data: de Big Data a datos accionables

## Estructura de la Sesion

### Inicio
- Caso: "Fracaso de implementacion BI"
- Discusion: ¿Por que fallan los proyectos BI?

### Desarrollo
- Exposicion: BI maturity models + Data governance DAMA + Change management
- **[INGLES]** Lecturas paralelas por grupos:
  - Grupo A: Gartner Trends 2024
  - Grupo B: DAMA Framework
  - Grupo C: Forrester Wave
- Presentaciones cruzadas de hallazgos
- Taller: Diagnosticar madurez de la PYME del proyecto
- Exposicion: Tendencias Cloud/Mobile/AI en BI

### Cierre
- Inicio Fase 4: Roadmap de implementacion
- Anuncio: Ensayo de Investigacion individual (10%)

## Actividades del Estudiante

### En Clase
- [ ] Analisis de caso de fracaso BI
- [ ] Lectura asignada segun grupo [INGLES]
- [ ] Presentacion cruzada de hallazgos
- [ ] Diagnostico de madurez BI de la PYME
- [ ] Investigacion de tendencias emergentes

### Trabajo Autonomo
- [ ] Redaccion de Ensayo Investigacion (2500-3000 palabras)
- [ ] Diseno de hoja de ruta de implementacion BI

## Recursos

### Bibliografia
- Davenport, T. H. (2023). *Competing on Analytics* [INGLES]
- DAMA International. (2024). *DAMA-DMBOK* (2nd ed.) [INGLES]
- Gartner. (2024). "Top Strategic Technology Trends for Data and Analytics" [INGLES]
- Forrester Research. (2024). "The Forrester Wave: Enterprise BI Platforms" [INGLES]

### Documentacion Cloud
- Microsoft Azure Documentation [INGLES]
- AWS Analytics Documentation [INGLES]
- Google BigQuery Documentation [INGLES]

### Frameworks
- Data Governance Institute Framework [INGLES]
- Qlik Self-Service Best Practices [INGLES]

## Evaluacion

| Actividad | Tipo | Valor |
|-----------|------|-------|
| Diagnostico madurez | Formativa | - |
| Ensayo Investigacion | Sumativa | 10% |
| Quiz Formativo Unidad 5 | Formativa | 2% |

## Modelo de Madurez BI

### 5 Niveles de Madurez

```
Nivel 5: OPTIMIZADO
    │   • BI integrado en cultura organizacional
    │   • Mejora continua basada en datos
    │   • IA/ML en decisiones automaticas
    │
Nivel 4: GESTIONADO
    │   • Metricas de desempeno BI definidas
    │   • Gobernanza de datos establecida
    │   • Self-service analytics disponible
    │
Nivel 3: DEFINIDO
    │   • Procesos BI documentados
    │   • Data Warehouse centralizado
    │   • Reportes estandarizados
    │
Nivel 2: REPETIBLE
    │   • Algunos procesos BI establecidos
    │   • Reportes ad-hoc frecuentes
    │   • Silos de informacion
    │
Nivel 1: INICIAL
    │   • Reportes manuales en Excel
    │   • Sin estrategia de datos
    │   • Decisiones basadas en intuicion
    ▼
```

### Caracteristicas por Nivel

| Nivel | Tecnologia | Procesos | Personas |
|-------|------------|----------|----------|
| 1 | Excel, reportes manuales | Ad-hoc | Sin roles BI |
| 2 | BI basico, algunos dashboards | Parcialmente definidos | Analistas aislados |
| 3 | DW, ETL automatizado | Documentados | Equipo BI dedicado |
| 4 | Self-service, gobernanza | KPIs de BI medidos | Cultura data-driven |
| 5 | IA/ML, tiempo real | Mejora continua | Todos son data citizens |

## Data Governance Framework (DAMA)

### 11 Areas de Conocimiento

```
┌─────────────────────────────────────────────────────────────────┐
│                    DATA GOVERNANCE                              │
│               (Funcion Central de Control)                      │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│   ┌───────────┐  ┌───────────┐  ┌───────────┐  ┌───────────┐   │
│   │Arquitect. │  │ Modelado  │  │Almacenam. │  │ Seguridad │   │
│   │  Datos    │  │  y Diseno │  │ y Operac. │  │  Datos    │   │
│   └───────────┘  └───────────┘  └───────────┘  └───────────┘   │
│                                                                 │
│   ┌───────────┐  ┌───────────┐  ┌───────────┐  ┌───────────┐   │
│   │Integracion│  │ Doc. y    │  │  Datos    │  │ Data      │   │
│   │ e Interop.│  │ Contenido │  │ Referenc. │  │ Quality   │   │
│   └───────────┘  └───────────┘  └───────────┘  └───────────┘   │
│                                                                 │
│   ┌───────────┐  ┌───────────┐                                 │
│   │  DW y BI  │  │ Metadata  │                                 │
│   │           │  │           │                                 │
│   └───────────┘  └───────────┘                                 │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

## Por que Fallan los Proyectos BI

### Factores Criticos de Fracaso

| Factor | % Proyectos Afectados | Mitigacion |
|--------|----------------------|------------|
| Falta de sponsorship ejecutivo | 65% | Involucrar C-level desde inicio |
| Calidad de datos pobre | 55% | Data governance previo |
| Requisitos mal definidos | 50% | CRISP-DM, iteraciones cortas |
| Resistencia al cambio | 45% | Change management, capacitacion |
| Tecnologia inadecuada | 30% | POC antes de seleccion |
| Falta de skills | 25% | Capacitacion, contratacion |

## Tendencias BI 2024-2026

### BI en la Nube

| Plataforma | Fortaleza | Uso |
|------------|-----------|-----|
| **Azure Synapse** | Integracion Microsoft | Empresas con ecosistema MS |
| **AWS Redshift** | Escalabilidad | Startups, alta demanda |
| **Google BigQuery** | ML integrado | Data science intensivo |
| **Snowflake** | Multi-cloud | Flexibilidad |

### IA Aplicada a BI

- **AutoML**: Generacion automatica de modelos
- **NLP**: Consultas en lenguaje natural
- **Augmented Analytics**: Insights automaticos
- **Predictive Analytics**: Forecasting integrado

## Ensayo de Investigacion (10%)

### Tema
**Comparativa de Herramientas BI**

### Requisitos
- Extension: 2500-3000 palabras
- Comparar minimo 3 herramientas (ej: Power BI, Tableau, Looker)
- Criterios: Funcionalidad, precio, facilidad de uso, integraciones
- Fuentes academicas y oficiales
- Formato APA 7ma edicion

### Rubrica

| Criterio | Peso |
|----------|------|
| Profundidad de analisis | 30% |
| Argumentacion y evidencia | 25% |
| Fuentes academicas | 20% |
| Estructura y redaccion | 15% |
| Formato APA | 10% |

---
*Taller de Tecnologia Aplicada - ADEN University - Cuatrimestre I 2026*
