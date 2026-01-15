# Taller de Tecnologia Aplicada - Contexto del Proyecto

> **Sistema de Continuidad:** Este archivo y `COURSE_STATE.yaml` garantizan coherencia
> entre sesiones de Claude Code, manteniendo el contexto pedagogico y tecnico del curso.

## Descripcion

Curso presencial de **Business Intelligence (BI)** y **analisis de datos** para ADEN University Panama.
14 sesiones que cubren el ciclo completo de BI: fundamentos, Data Warehouse, ETL, Data Mining,
dashboards y estrategias de implementacion.

## Informacion del Curso

| Campo | Valor |
|-------|-------|
| **Universidad** | ADEN University |
| **Facultad** | Ciencias Empresariales |
| **Codigo** | CT ING 027 |
| **Creditos** | 3 |
| **Periodo** | Cuatrimestre I - 2026 |
| **Modalidad** | Presencial - Panama |
| **Docente** | Ulises Javier Gonzalez Diaz |
| **Contacto** | ulises@rizo.ma |

## Stack Tecnologico del Curso

| Herramienta | Uso en el Curso |
|-------------|-----------------|
| **Power BI Desktop** | Dashboards interactivos (Sesiones 10-12) |
| **SQL Server / PostgreSQL** | Bases de datos, modelado dimensional |
| **Pentaho Data Integration** | Procesos ETL (Sesion 6) |
| **Python** | Data Mining con pandas, scikit-learn, matplotlib |
| **Jupyter Notebooks** | Analisis exploratorio y algoritmos ML |
| **Google Colab** | Alternativa para notebooks (Big Data) |

---

## CRITICO: Sistema de Contratos para Continuidad

Claude Code no tiene memoria entre sesiones. La coherencia pedagogica del curso
depende de **artefactos explicitos** que capturen el estado del diseno instruccional.

### Archivo de Estado del Curso

```
ADEN-Taller-tecnologia-aplicada/
├── CLAUDE.md              ← Este archivo (contexto)
├── COURSE_STATE.yaml      ← CONTRATO OBLIGATORIO (estado)
├── README.md              ← Documentacion publica
├── planificacion-academica.pdf
└── sesion-XX/
    └── README.md          ← Contenido de cada sesion
```

### Protocolo Obligatorio para Claude Code

**ANTES de crear o modificar contenido:**

1. **LEER** `COURSE_STATE.yaml`
2. **VERIFICAR** que conceptos ya se introdujeron en sesiones anteriores
3. **RESPETAR** las convenciones de codigo establecidas
4. **NO INTRODUCIR** conceptos planificados para sesiones posteriores
5. **MANTENER** coherencia con el proyecto integrador

**AL COMPLETAR trabajo en una sesion:**

1. **ACTUALIZAR** `concepts_introduced` con nuevos conceptos
2. **ACTUALIZAR** `last_session_worked` y `last_updated`
3. **REGISTRAR** actividades y materiales creados
4. **ACTUALIZAR** `next_session_spec` si corresponde

---

## Estructura del Curso

### 5 Unidades Tematicas

| Unidad | Sesiones | Tema Principal |
|--------|----------|----------------|
| 1 | 1-3 | Fundamentos de BI |
| 2 | 4-6 | Data Warehouse y ETL |
| 3 | 7-9 | Data Mining y Big Data |
| 4 | 10-12 | Aplicaciones Avanzadas de BI |
| 5 | 13-14 | Estrategias y Tendencias |

### Proyecto Integrador (65% de la nota)

El curso incluye un proyecto grupal con 4 fases acumulativas:

| Fase | Sesion Entrega | Peso | Entregable |
|------|----------------|------|------------|
| 1 | Sesion 4 | 15% | Analisis de necesidades + Diseno DW |
| 2 | Sesion 8 | 15% | Implementacion ETL + Data Mining |
| 3 | Sesion 12 | 20% | Dashboard interactivo Power BI |
| 4 | Sesion 14 | 15% | Roadmap de implementacion BI |

### Evaluacion Completa

| Actividad | Porcentaje |
|-----------|------------|
| Quiz formativos (5 unidades) | 10% |
| Proyecto Fase 1 | 15% |
| Laboratorio ETL Pentaho | 10% |
| Proyecto Fase 2 | 15% |
| Proyecto Fase 3 | 20% |
| Ensayo Investigacion | 10% |
| Proyecto Fase 4 | 15% |
| Participacion | 5% |

---

## Convenciones de Codigo

### SQL (Data Warehouse)

```sql
-- Convenciones para modelado dimensional
-- Tablas de hechos: fact_[nombre]
-- Tablas de dimensiones: dim_[nombre]
-- Claves sustitutas: [tabla]_key
-- Claves de negocio: [tabla]_id

-- Ejemplo de esquema estrella
CREATE TABLE fact_ventas (
    venta_key INT PRIMARY KEY,
    fecha_key INT REFERENCES dim_fecha(fecha_key),
    producto_key INT REFERENCES dim_producto(producto_key),
    cliente_key INT REFERENCES dim_cliente(cliente_key),
    monto DECIMAL(10,2),
    cantidad INT
);

CREATE TABLE dim_fecha (
    fecha_key INT PRIMARY KEY,
    fecha DATE,
    anio INT,
    mes INT,
    dia INT,
    trimestre INT
);
```

### Python (Data Mining)

```python
# Imports estandar del curso
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from sklearn.model_selection import train_test_split
from sklearn.preprocessing import StandardScaler

# Convenciones de variables
df = pd.read_csv('datos.csv')  # dataframe principal
X = df.drop('target', axis=1)  # features
y = df['target']               # variable objetivo
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2)
model = None                   # modelo entrenado

# Patron de EDA
def explorar_datos(df):
    print(f"Shape: {df.shape}")
    print(f"\nTipos:\n{df.dtypes}")
    print(f"\nNulos:\n{df.isnull().sum()}")
    print(f"\nEstadisticas:\n{df.describe()}")
```

### DAX (Power BI)

```dax
// Medidas estandar
Total Ventas = SUM(Ventas[Monto])
Num Transacciones = COUNTROWS(Ventas)
Promedio Venta = AVERAGE(Ventas[Monto])
Clientes Unicos = DISTINCTCOUNT(Ventas[ClienteID])

// Medidas con contexto temporal
Ventas Año Anterior =
CALCULATE(
    [Total Ventas],
    SAMEPERIODLASTYEAR(Calendario[Fecha])
)

Crecimiento YoY =
DIVIDE(
    [Total Ventas] - [Ventas Año Anterior],
    [Ventas Año Anterior],
    0
)
```

---

## Estilo Pedagogico

### Estructura de Sesiones (4 horas)

```
1. INICIO (30 min)
   - Caso introductorio o pregunta detonadora
   - Conexion con sesion anterior
   - Objetivo de aprendizaje (verbo Bloom)

2. DESARROLLO (2.5 horas)
   - Exposicion teorica con ejemplos
   - Lecturas en ingles (paralelas por grupos)
   - Actividad practica / laboratorio
   - Retroalimentacion entre pares

3. CIERRE (1 hora)
   - Sintesis de conceptos clave
   - Entrega de actividad (si aplica)
   - Quiz formativo
   - Preview siguiente sesion
```

### Verbos de Bloom por Unidad

| Unidad | Nivel Cognitivo | Verbos |
|--------|-----------------|--------|
| 1 | Comprender | IDENTIFICAR, EXPLICAR, COMPARAR |
| 2 | Aplicar | DISEÑAR, CONSTRUIR, EJECUTAR |
| 3 | Analizar | IMPLEMENTAR, CLASIFICAR, SEGMENTAR |
| 4 | Evaluar | EVALUAR, CREAR, PRESENTAR |
| 5 | Crear | PROPONER, DEFENDER, INTEGRAR |

### Politica de Retroalimentacion

- Directa, sin condescendencia
- Enfocada en mejora, no en error
- Conectar con aplicacion profesional real
- Celebrar brevemente el exito, no exceso de elogios

---

## Recursos Clave

### Bibliografia Obligatoria

| Autor | Titulo | Uso |
|-------|--------|-----|
| Kimball & Ross | The Data Warehouse Toolkit | DW y modelado dimensional |
| Inmon | Building the Data Warehouse | Arquitectura DW |
| Han, Kamber & Pei | Data Mining: Concepts and Techniques | Algoritmos ML |
| Nussbaumer Knaflic | Storytelling with Data | Visualizacion |
| DAMA International | DAMA-DMBOK | Gobernanza de datos |

### Datasets del Curso

| Dataset | Sesiones | Descripcion |
|---------|----------|-------------|
| ventas_retail.csv | 3-8 | Ventas de retail para KPIs y DW |
| clientes_segmentacion.csv | 7-8 | Datos para clustering |
| productos_clasificacion.csv | 8 | Datos para decision tree |

---

## Documentacion

| Archivo | Proposito |
|---------|-----------|
| `README.md` | Documentacion publica del curso |
| `CLAUDE.md` | Este archivo (contexto para Claude) |
| `COURSE_STATE.yaml` | Estado del curso (contrato de continuidad) |
| `planificacion-academica.pdf` | Syllabus oficial |
| `sesion-XX/README.md` | Contenido detallado de cada sesion |

---

## Errores Comunes a Evitar

| Error | Consecuencia | Prevencion |
|-------|--------------|------------|
| No leer COURSE_STATE | Conceptos duplicados o desordenados | Siempre leer primero |
| Cambiar convenciones de codigo | Codigo inconsistente, confunde estudiante | Respetar code_conventions |
| Saltar next_session_spec | Contenido sin progresion logica | Seguir la especificacion |
| Introducir concepto futuro | Rompe curva de aprendizaje | Verificar concepts_introduced |
| No actualizar al terminar | Proxima sesion pierde contexto | Actualizar antes de commit |

---

*Taller de Tecnologia Aplicada - ADEN University - Cuatrimestre I 2026*
*Docente: Ulises Javier Gonzalez Diaz - ulises@rizo.ma*
