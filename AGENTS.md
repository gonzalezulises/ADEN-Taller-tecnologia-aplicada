# Taller de Tecnologia Aplicada — Contexto para Agentes

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
| **Tableau** | Dashboards interactivos y visualizacion (Sesiones 10-12) |
| **Supabase / PostgreSQL** | Bases de datos relacionales, modelado dimensional |
| **Pentaho Data Integration** | Procesos ETL (Sesion 6) |
| **Python** | Data Mining con pandas, scikit-learn, matplotlib |
| **Jupyter Notebooks** | Analisis exploratorio y algoritmos ML |
| **Google Colab** | Alternativa para notebooks (Big Data) |
| **Google NotebookLM** | Material de apoyo con IA |

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
| 3 | Sesion 12 | 20% | Dashboard interactivo Tableau |
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

### Tableau (Campos Calculados)

```
// Medidas estandar
Total Ventas: SUM([Monto])
Num Transacciones: COUNT([ID Transaccion])
Promedio Venta: AVG([Monto])
Clientes Unicos: COUNTD([Cliente ID])

// Calculo con condicion
Ventas Altas: IF SUM([Monto]) > 10000 THEN "Alto" ELSE "Normal" END

// Calculo de fecha
Año Venta: YEAR([Fecha])
Mes Venta: MONTH([Fecha])

// Crecimiento porcentual (Table Calculation)
Crecimiento YoY: (SUM([Monto]) - LOOKUP(SUM([Monto]), -1)) / LOOKUP(SUM([Monto]), -1)
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

---

# Contrato de trabajo del harness

This project is the course repository for a business-intelligence workshop: one directory per session, each holding the teaching material and exercises for that class.

This file is the operating contract for any coding agent working in this repo
(Codex, Claude Code, Cursor, Windsurf, or a human). It is a router, not a manual:
it states the startup path, the rules, and what "done" means. Details live in `docs/`.

## Startup (clock-in)

Before touching code, in this order:

1. Confirm the working directory with `pwd`.
2. Read `PROGRESS.md` — it holds the last verified state and the next step.
3. Read `COURSE_STATE.yaml`, then `feature_list.json`, and pick the highest-priority unfinished feature.
4. Review recent history: `git log --oneline -5`.
5. Run `./init.sh` to install and verify the baseline.

If baseline verification is already failing, repair it first. MUST NOT stack new
feature work on a broken baseline — a red baseline makes every later result unreadable.

## Verification

The single command that proves this repo is consistent:

```bash
bash scripts/check-course.sh
```

The repo is in a consistent state when that command exits 0. Run it before every
commit and at every clock-out.

## Working rules

- **WIP=1** — only one feature may be `active` at a time. Finish it, verify it, then
  activate the next. why: parallel half-finished features leave no verifiable state.
- **Evidence before done** — never mark a feature `passing` because code was written.
  Mark it passing only after the verification command actually ran and produced output.
- **Feature granularity** — each feature must be completable in one session. If it
  spans sessions, split it.
- **State machine** — `not_started` → `active` → `passing`. No skipping states.
- **Stay in scope** — do not modify files unrelated to the active feature. A blocking
  fix is allowed, but record it in `PROGRESS.md`.
- **Repo over chat** — durable repo artifacts beat chat summaries. The next session
  will not have your context window.
- **No stale docs** — update docs in the same commit as the code change.
- **Atomic commits** — one logical change per commit; the repo stays consistent after
  each one. Commit messages explain WHY the change was made, not just what changed.

## Definition of Done

A feature is done only when all of these are true:

1. **Layer 1 — static.** Types/lint/build pass.
2. **Layer 2 — runtime.** The code actually runs and produces the target behavior:
   the app reaches its ready state, side effects are correct, no debug artifacts remain.
3. **Layer 3 — end-to-end.** The user-visible behavior described in
   `user_visible_behavior` was exercised the way a real user would.
4. Evidence is recorded in `feature_list.json`.
5. `bash scripts/check-course.sh` exits 0.

Do not proceed to Layer N+1 while Layer N fails. Layer 3 is required whenever a change
crosses component or domain boundaries.

Writing code is not done. Being confident is not done. Runtime evidence is done.

## State files

| File | Holds |
|---|---|
| `COURSE_STATE.yaml` | The course contract: sessions, status, content inventory. Read it before creating or editing any session material. |
| `PROGRESS.md` | Current verified state, session log, next step |
| `feature_list.json` | Every feature, its state, verification steps, evidence |
| `docs/decisions/` | Architectural decisions and why they were made |
| `clean-state-checklist.md` | The checklist to clear before ending a session |

## Tools and permissions

Tool access is scoped by the agent's own config (`.claude/settings.json`, `.mcp.json`,
`.cursor/`, or equivalent). Agents MUST NOT widen their own permissions to complete a
task — if a task needs a capability that is not granted, stop and say so.

Never commit secrets. Credentials belong in `.env` (gitignored) or the OS keychain.

## Session end (clock-out)

Before closing a session:

1. Run `bash scripts/check-course.sh` and record the result.
2. Update `PROGRESS.md`: current state, what changed, next best action.
3. Update `feature_list.json` states and evidence.
4. Walk `clean-state-checklist.md`.
5. Commit. Leave the repo restartable from `./init.sh`.

**If you are running low on context, do NOT rush to finish.** Stop, write the state
down, commit a clean checkpoint. A rushed finish that skips verification costs the next
session more than an unfinished feature does.

Beyond the per-session cleanup above, do a periodic (weekly or monthly) sweep for
structural drift: dead files, stale docs, features stuck in `active`.
