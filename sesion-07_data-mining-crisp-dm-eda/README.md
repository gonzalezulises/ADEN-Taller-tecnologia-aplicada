# Sesion 07: Fundamentos Data Mining - CRISP-DM y EDA

**Fecha:** 6 de marzo, 2026
**Unidad:** 3 - Data Mining y Big Data
**Duracion:** 4 horas (2 teoricas + 2 practicas)

## Objetivo de Aprendizaje

> **APLICAR** metodologia CRISP-DM realizando Analisis Exploratorio de Datos (EDA) con Python/pandas

## Contenidos

- 3.1 Fundamentos de Data Mining: proceso CRISP-DM
- Analisis Exploratorio de Datos (EDA)
- Estadistica descriptiva con pandas
- Visualizacion exploratoria

## Estructura de la Sesion

### Inicio
- **ENTREGA Lab ETL** (10%)
- Transicion: "De almacenar a descubrir patrones"

### Desarrollo
- Exposicion: CRISP-DM (6 fases)
- **[INGLES]** Lectura: Provost & Fawcett Ch.3 "Predictive Modeling"
- Lab Jupyter: EDA con pandas (describe, correlaciones, visualizacion matplotlib/seaborn)
- Demo: Preparacion de datos para scikit-learn

### Cierre
- Compartir insights del EDA
- Inicio Proyecto Fase 2: Definir problema Data Mining

## Actividades del Estudiante

### En Clase
- [ ] Lectura: Provost & Fawcett Ch.3-6 [INGLES]
- [ ] EDA con pandas en Jupyter Notebooks (individual)
- [ ] Calculo de estadisticas descriptivas
- [ ] Creacion de visualizaciones exploratorias
- [ ] Identificacion de patrones iniciales

### Entregables
- [ ] Lab ETL (entrega inicio de sesion)
- [ ] Inicio Proyecto Fase 2

## Recursos

### Bibliografia
- Provost, F., & Fawcett, T. (2023). *Data Science for Business* Ch.3-6 [INGLES]
- Han, J., Kamber, M., & Pei, J. (2022). *Data Mining: Concepts and Techniques* [INGLES]

### Software
- Python 3.11+
- Jupyter Notebooks (Anaconda)
- Librerias: pandas, numpy, matplotlib, seaborn

### Datasets
- UCI Machine Learning Repository
- Kaggle Datasets

### Tutoriales
- Kaggle Learn ML [INGLES]
- Google ML Crash Course [INGLES]

## Evaluacion

| Actividad | Tipo | Valor |
|-----------|------|-------|
| Lab ETL Pentaho | Sumativa | 10% |
| Notebook EDA | Formativa | - |

## CRISP-DM: 6 Fases

```
    ┌─────────────────────────────────────────────────────────┐
    │                                                         │
    ▼                                                         │
┌───────────────┐                                             │
│  1. Business  │                                             │
│ Understanding │                                             │
└───────┬───────┘                                             │
        │                                                     │
        ▼                                                     │
┌───────────────┐     ┌───────────────┐     ┌───────────────┐ │
│    2. Data    │────►│    3. Data    │────►│  4. Modeling  │ │
│ Understanding │     │  Preparation  │     │               │ │
└───────────────┘     └───────────────┘     └───────┬───────┘ │
        ▲                                          │         │
        │                                          ▼         │
        │                                  ┌───────────────┐  │
        │                                  │ 5. Evaluation │  │
        │                                  └───────┬───────┘  │
        │                                          │         │
        └──────────────────────────────────────────┤         │
                                                   ▼         │
                                           ┌───────────────┐ │
                                           │ 6. Deployment │─┘
                                           └───────────────┘
```

### Descripcion de Fases

| Fase | Objetivo | Entregables |
|------|----------|-------------|
| **1. Business Understanding** | Entender objetivos del negocio | Documento de requerimientos |
| **2. Data Understanding** | Explorar y conocer los datos | EDA, estadisticas descriptivas |
| **3. Data Preparation** | Limpiar y transformar datos | Dataset preparado |
| **4. Modeling** | Aplicar algoritmos | Modelos entrenados |
| **5. Evaluation** | Evaluar resultados | Metricas de desempeno |
| **6. Deployment** | Implementar solucion | Modelo en produccion |

## EDA con Pandas - Codigo Base

### Carga y Exploracion Inicial

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

# Cargar datos
df = pd.read_csv('datos.csv')

# Exploracion inicial
print(df.shape)              # Dimensiones
print(df.info())             # Tipos de datos
print(df.describe())         # Estadisticas descriptivas
print(df.isnull().sum())     # Valores nulos
print(df.duplicated().sum()) # Duplicados
```

### Visualizaciones Exploratorias

```python
# Distribucion de variable numerica
plt.figure(figsize=(10, 6))
df['variable'].hist(bins=30)
plt.title('Distribucion de Variable')
plt.xlabel('Valor')
plt.ylabel('Frecuencia')
plt.show()

# Matriz de correlacion
plt.figure(figsize=(12, 8))
sns.heatmap(df.corr(), annot=True, cmap='coolwarm', center=0)
plt.title('Matriz de Correlacion')
plt.show()

# Boxplot para detectar outliers
plt.figure(figsize=(10, 6))
df.boxplot(column=['var1', 'var2', 'var3'])
plt.title('Boxplot - Deteccion de Outliers')
plt.show()
```

### Estadisticas por Grupo

```python
# Agrupacion y agregacion
resumen = df.groupby('categoria').agg({
    'ventas': ['mean', 'sum', 'count'],
    'ganancia': ['mean', 'std']
})
print(resumen)
```

## Checklist EDA

- [ ] Dimensiones del dataset (filas x columnas)
- [ ] Tipos de datos de cada columna
- [ ] Estadisticas descriptivas (media, mediana, std, min, max)
- [ ] Valores nulos y su porcentaje
- [ ] Valores duplicados
- [ ] Distribucion de variables numericas (histogramas)
- [ ] Distribucion de variables categoricas (countplots)
- [ ] Correlaciones entre variables
- [ ] Deteccion de outliers (boxplots)
- [ ] Patrones temporales (si aplica)

## Inicio Proyecto Fase 2

A partir de esta sesion, los equipos definen:
1. Problema de negocio a resolver con Data Mining
2. Variable objetivo (si es supervisado)
3. Features relevantes
4. Metrica de exito

**Fecha de entrega Fase 2:** Sesion 09 (20 de marzo)

---
*Taller de Tecnologia Aplicada - ADEN University - Cuatrimestre I 2026*
