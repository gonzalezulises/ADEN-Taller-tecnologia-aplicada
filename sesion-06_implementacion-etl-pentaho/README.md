# Sesion 06: Implementacion ETL con Pentaho Data Integration

**Fecha:** 27 de febrero, 2026
**Unidad:** 2 - Data Warehouse
**Duracion:** 4 horas (2 teoricas + 2 practicas)

## Objetivo de Aprendizaje

> **IMPLEMENTAR** proceso ETL funcional en Pentaho que extraiga, transforme y cargue datos al DW

## Contenidos

- 2.7 Herramientas ETL: Pentaho Data Integration, SQL Server Integration Services
- Jobs y Transformaciones en Pentaho
- Steps mas utilizados
- Manejo de errores y logging

## Estructura de la Sesion

### Inicio
- Feedback general Fase 1
- Objetivos de la sesion practica

### Desarrollo
- **[INGLES]** Pentaho Kettle Guide
- Demo docente: Job ETL completo en Pentaho
- Lab individual supervisado: Replicar proceso ETL (dataset Kaggle/UCI)
- Troubleshooting grupal

### Cierre
- Quiz Formativo Unidad 2 (2%)
- Anuncio: Entrega Lab ETL individual proxima semana (10%)

## Actividades del Estudiante

### En Clase
- [ ] Instalacion y configuracion de Pentaho Data Integration
- [ ] Replicacion de proceso ETL demostrado
- [ ] Experimentacion con steps de transformacion
- [ ] Documentacion del proceso

### Entregables
- [ ] **Lab ETL Pentaho** (10%) - Entrega: Sesion 07

## Recursos

### Bibliografia
- Pentaho Data Integration (PDI). (2024). "Kettle Transformation Guide" [INGLES]
- Pentaho. (2024). "ETL Best Practices and Design Patterns" [INGLES]

### Software
- Pentaho Data Integration (Community Edition)
- SQL Server 2022 / PostgreSQL

### Datasets
- UCI Machine Learning Repository
- Kaggle Datasets

## Evaluacion

| Actividad | Tipo | Valor |
|-----------|------|-------|
| Quiz Formativo Unidad 2 | Formativa | 2% |
| Lab ETL Pentaho | Sumativa | 10% |

## Pentaho Data Integration - Conceptos Clave

### Transformaciones vs Jobs

| Concepto | Transformacion (.ktr) | Job (.kjb) |
|----------|----------------------|------------|
| Proposito | Mover y transformar datos | Orquestar flujos de trabajo |
| Ejecucion | Paralela (streams) | Secuencial |
| Componentes | Steps | Job Entries |
| Uso | Procesar datos | Coordinar transformaciones |

### Steps mas Utilizados

```
ENTRADA                    TRANSFORMACION              SALIDA
─────────                  ─────────────────           ──────
□ Table Input              □ Select Values             □ Table Output
□ CSV File Input           □ Filter Rows               □ Insert/Update
□ Excel Input              □ Sort Rows                 □ Text File Output
□ JSON Input               □ Calculator                □ Excel Output
□ REST Client              □ String Operations         □ XML Output
                           □ Merge Join
                           □ Lookup
```

## Ejercicio Practico: ETL de Ventas

### Flujo de Transformacion

```
┌──────────────┐    ┌──────────────┐    ┌──────────────┐
│  CSV Input   │───►│ Select Values│───►│ Filter Rows  │
│  (ventas.csv)│    │ (columnas)   │    │ (año 2024)   │
└──────────────┘    └──────────────┘    └──────┬───────┘
                                               │
┌──────────────┐    ┌──────────────┐    ┌──────┴───────┐
│ Table Output │◄───│   Calculator │◄───│  Lookup      │
│  (DW ventas) │    │ (total_venta)│    │ (producto)   │
└──────────────┘    └──────────────┘    └──────────────┘
```

### Codigo SQL para Tabla Destino

```sql
CREATE TABLE dw_ventas (
    venta_id INT PRIMARY KEY,
    fecha DATE,
    producto_id INT,
    producto_nombre VARCHAR(100),
    cantidad INT,
    precio_unitario DECIMAL(10,2),
    total_venta DECIMAL(12,2),
    fecha_carga TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

## Best Practices ETL

1. **Logging**: Siempre activar logging para debugging
2. **Validacion**: Verificar datos antes de cargar
3. **Incrementalidad**: Preferir cargas incrementales sobre full
4. **Manejo de errores**: Configurar acciones para filas con error
5. **Documentacion**: Comentar cada step y su proposito
6. **Versionamiento**: Guardar versiones de las transformaciones

## Rubrica Lab ETL (10%)

| Criterio | Excelente (4) | Bueno (3) | Regular (2) | Deficiente (1) |
|----------|---------------|-----------|-------------|----------------|
| Funcionalidad | ETL completo sin errores | Funciona con ajustes menores | Parcialmente funcional | No funciona |
| Transformaciones | Multiples y apropiadas | Adecuadas | Basicas | Insuficientes |
| Documentacion | Script bien comentado | Comentarios adecuados | Pocos comentarios | Sin documentar |
| Calidad datos | Datos limpios y validados | Mayormente correctos | Algunos errores | Muchos errores |

---
*Taller de Tecnologia Aplicada - ADEN University - Cuatrimestre I 2026*
