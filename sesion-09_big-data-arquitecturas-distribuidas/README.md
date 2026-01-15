# Sesion 09: Big Data Fundamentals y Arquitecturas Distribuidas

**Fecha:** 20 de marzo, 2026
**Unidad:** 3 - Data Mining y Big Data
**Duracion:** 4 horas (2 teoricas + 2 practicas)

## Objetivo de Aprendizaje

> **ANALIZAR** caracteristicas Big Data (5 V's) y comprender arquitecturas Hadoop/Spark mediante casos empresariales

## Contenidos

- 3.5 Introduccion al Big Data: las 5 V's (Volumen, Velocidad, Variedad, Veracidad, Valor)
- 3.6 Desafios y oportunidades del Big Data empresarial
- Arquitecturas distribuidas: Hadoop, Spark
- Bases de datos NoSQL

## Estructura de la Sesion

### Inicio
- Video: "What is Big Data?"
- Brainstorming: Empresas que usan Big Data

### Desarrollo
- Exposicion: 5 V's + Limitaciones de RDBMS
- **[INGLES]** Lectura: Han et al. Ch.1 "Data Mining in Big Data Era"
- Casos empresariales: Netflix, Walmart, Target
- Demo conceptual: Hadoop/Spark/MongoDB
- Debate etico: Privacidad y sesgos en algoritmos

### Cierre
- **ENTREGA Fase 2:** Analisis Data Mining (15%)
- Reflexion sobre etica en Big Data

## Actividades del Estudiante

### En Clase
- [ ] Analisis de casos empresariales Big Data
- [ ] Identificacion de las 5 V's en casos reales
- [ ] Participacion en debate etico
- [ ] Comprension de arquitecturas distribuidas

### Entregables
- [ ] **Proyecto Fase 2** (15%): Informe tecnico + Notebook Python

## Recursos

### Bibliografia
- Han, J., Kamber, M., & Pei, J. (2022). *Data Mining* Ch.1 "Big Data Era" [INGLES]
- Apache Hadoop Documentation [INGLES]
- Apache Spark MLlib Guide [INGLES]
- MongoDB Documentation [INGLES]

### Tutoriales
- Kaggle Learn ML [INGLES]
- Google ML Crash Course [INGLES]

## Evaluacion

| Actividad | Tipo | Valor |
|-----------|------|-------|
| **Proyecto Fase 2** | Sumativa | **15%** |
| Participacion debate | Formativa | - |
| Quiz Formativo Unidad 3 | Formativa | 2% |

## Las 5 V's del Big Data

```
                         ┌─────────────────┐
                         │     VOLUMEN     │
                         │   Terabytes a   │
                         │   Petabytes     │
                         └────────┬────────┘
                                  │
        ┌─────────────────────────┼─────────────────────────┐
        │                         │                         │
        ▼                         ▼                         ▼
┌───────────────┐         ┌───────────────┐         ┌───────────────┐
│   VELOCIDAD   │         │   VARIEDAD    │         │   VERACIDAD   │
│  Streaming,   │         │ Estructurado, │         │   Calidad,    │
│  Real-time    │         │ Semi, No-est. │         │   Confianza   │
└───────────────┘         └───────────────┘         └───────────────┘
                                  │
                                  ▼
                         ┌───────────────┐
                         │     VALOR     │
                         │   Insights    │
                         │   accionables │
                         └───────────────┘
```

### Descripcion de las 5 V's

| V | Descripcion | Ejemplo |
|---|-------------|---------|
| **Volumen** | Cantidad masiva de datos | Facebook: 500+ TB/dia |
| **Velocidad** | Rapidez de generacion y procesamiento | Transacciones en tiempo real |
| **Variedad** | Diferentes tipos y formatos | Texto, imagenes, video, sensores |
| **Veracidad** | Calidad y confiabilidad | Datos incompletos, inconsistentes |
| **Valor** | Utilidad para el negocio | Insights accionables |

## Arquitecturas Big Data

### Hadoop Ecosystem

```
┌─────────────────────────────────────────────────────────────────┐
│                      APLICACIONES                               │
│    Hive (SQL)    │    Pig    │    Spark    │    HBase           │
├─────────────────────────────────────────────────────────────────┤
│                         YARN                                    │
│              (Resource Management)                              │
├─────────────────────────────────────────────────────────────────┤
│                         HDFS                                    │
│            (Hadoop Distributed File System)                     │
└─────────────────────────────────────────────────────────────────┘
```

### Apache Spark

```
┌─────────────────────────────────────────────────────────────────┐
│                      SPARK CORE                                 │
├──────────────┬──────────────┬──────────────┬───────────────────┤
│  Spark SQL   │  Spark       │  MLlib       │  GraphX           │
│  (consultas) │  Streaming   │  (ML)        │  (grafos)         │
└──────────────┴──────────────┴──────────────┴───────────────────┘
```

## Bases de Datos NoSQL

| Tipo | Ejemplo | Uso |
|------|---------|-----|
| **Documento** | MongoDB | Datos semi-estructurados |
| **Clave-Valor** | Redis | Cache, sesiones |
| **Columnar** | Cassandra | Series temporales |
| **Grafo** | Neo4j | Redes sociales, recomendaciones |

## Casos Empresariales Big Data

### Netflix
- **Volumen:** 500M+ usuarios, petabytes de streaming
- **Velocidad:** Recomendaciones en tiempo real
- **Variedad:** Video, metadata, comportamiento usuario
- **Valor:** Sistema de recomendaciones (80% contenido visto)

### Walmart
- **Volumen:** 2.5 PB datos transaccionales
- **Velocidad:** 1M transacciones/hora
- **Variedad:** POS, inventario, clima, redes sociales
- **Valor:** Prediccion de demanda, optimizacion inventario

### Target
- **Caso:** Prediccion de embarazo basada en patrones de compra
- **Etica:** Limites de la prediccion y privacidad

## Debate Etico: Big Data

### Temas de Discusion

1. **Privacidad**
   - ¿Hasta donde es etico usar datos personales?
   - GDPR y regulaciones de proteccion de datos

2. **Sesgos Algoritmicos**
   - Discriminacion en algoritmos de credito
   - Sesgos en reconocimiento facial

3. **Consentimiento**
   - ¿Los usuarios entienden como se usan sus datos?
   - Terms of Service vs consentimiento informado

4. **Transparencia**
   - Explicabilidad de modelos (XAI)
   - Derecho a saber por que se tomo una decision

## Rubrica Proyecto Fase 2 (15%)

| Criterio | Excelente (4) | Bueno (3) | Regular (2) | Deficiente (1) |
|----------|---------------|-----------|-------------|----------------|
| Aplicacion algoritmos | Correcta y justificada | Adecuada | Con errores | Incorrecta |
| Interpretacion resultados | Profunda y accionable | Clara | Superficial | Ausente |
| Calidad codigo | Limpio, documentado, reproducible | Funcional | Parcial | Desordenado |
| Informe tecnico | Completo y profesional | Adecuado | Basico | Incompleto |

---
*Taller de Tecnologia Aplicada - ADEN University - Cuatrimestre I 2026*
