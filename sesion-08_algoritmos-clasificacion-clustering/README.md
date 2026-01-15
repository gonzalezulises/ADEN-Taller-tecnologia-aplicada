# Sesion 08: Algoritmos de Clasificacion y Clustering

**Fecha:** 13 de marzo, 2026
**Unidad:** 3 - Data Mining y Big Data
**Duracion:** 4 horas (2 teoricas + 2 practicas)

## Objetivo de Aprendizaje

> **IMPLEMENTAR** algoritmos K-means (clustering) y Decision Tree (clasificacion) evaluando desempeno con metricas

## Contenidos

- 3.2 Algoritmos de clasificacion (arboles de decision, Naive Bayes, KNN)
- 3.3 Algoritmos de clustering (K-means, jerarquico)
- Metricas de evaluacion
- Seleccion de hiperparametros

## Estructura de la Sesion

### Inicio
- Repaso EDA
- Pregunta: "¿Como segmentar clientes sin etiquetas?"

### Desarrollo
- Exposicion: Aprendizaje supervisado vs no supervisado
- **[INGLES]** scikit-learn Clustering + Classification docs
- Lab Python: K-means (elbow method, silhouette score)
- Lab Python: Decision Tree/Random Forest (confusion matrix, accuracy, precision, recall)

### Cierre
- Discusion: ¿Cuando usar clustering vs clasificacion?
- Avance Fase 2 del proyecto

## Actividades del Estudiante

### En Clase
- [ ] Implementacion K-means clustering (equipos)
- [ ] Implementacion Decision Tree/Random Forest (equipos)
- [ ] Calculo de metricas: confusion matrix, accuracy, precision, recall
- [ ] Experimentacion con hiperparametros
- [ ] Interpretacion de resultados

### Trabajo Autonomo
- [ ] Tutoriales Kaggle Learn [INGLES]
- [ ] Avance Proyecto Fase 2

## Recursos

### Bibliografia
- scikit-learn. (2024). "Clustering Algorithms" [INGLES]
- scikit-learn. (2024). "Classification Algorithms" [INGLES]
- Provost & Fawcett (2023) Ch.3-6 [INGLES]

### Software
- Python 3.11+ con scikit-learn
- Jupyter Notebooks

### Datasets
- UCI Machine Learning Repository
- Kaggle Datasets

## Evaluacion

| Actividad | Tipo | Valor |
|-----------|------|-------|
| Lab algoritmos | Formativa | - |
| Avance Proyecto Fase 2 | Preparacion | - |

## Aprendizaje Supervisado vs No Supervisado

| Caracteristica | Supervisado | No Supervisado |
|----------------|-------------|----------------|
| Datos de entrada | Con etiquetas (y) | Sin etiquetas |
| Objetivo | Predecir etiqueta | Descubrir estructura |
| Ejemplos | Clasificacion, Regresion | Clustering, Reduccion dimensionalidad |
| Algoritmos | Decision Tree, Random Forest, SVM | K-means, DBSCAN, PCA |
| Evaluacion | Accuracy, Precision, Recall | Silhouette, Inercia |

## K-Means Clustering

### Codigo Python

```python
from sklearn.cluster import KMeans
from sklearn.preprocessing import StandardScaler
import matplotlib.pyplot as plt

# Preparar datos
scaler = StandardScaler()
X_scaled = scaler.fit_transform(X)

# Metodo del codo (Elbow Method)
inertias = []
K_range = range(1, 11)

for k in K_range:
    kmeans = KMeans(n_clusters=k, random_state=42, n_init=10)
    kmeans.fit(X_scaled)
    inertias.append(kmeans.inertia_)

# Graficar elbow
plt.figure(figsize=(10, 6))
plt.plot(K_range, inertias, 'bo-')
plt.xlabel('Numero de Clusters (k)')
plt.ylabel('Inercia')
plt.title('Metodo del Codo')
plt.show()

# Entrenar modelo final
kmeans = KMeans(n_clusters=3, random_state=42, n_init=10)
clusters = kmeans.fit_predict(X_scaled)
```

### Silhouette Score

```python
from sklearn.metrics import silhouette_score

score = silhouette_score(X_scaled, clusters)
print(f'Silhouette Score: {score:.3f}')
# Rango: -1 a 1 (mayor es mejor)
```

## Clasificacion con Decision Tree

### Codigo Python

```python
from sklearn.tree import DecisionTreeClassifier
from sklearn.model_selection import train_test_split
from sklearn.metrics import classification_report, confusion_matrix
import seaborn as sns

# Dividir datos
X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42
)

# Entrenar modelo
clf = DecisionTreeClassifier(max_depth=5, random_state=42)
clf.fit(X_train, y_train)

# Predecir
y_pred = clf.predict(X_test)

# Evaluar
print(classification_report(y_test, y_pred))

# Matriz de confusion
cm = confusion_matrix(y_test, y_pred)
plt.figure(figsize=(8, 6))
sns.heatmap(cm, annot=True, fmt='d', cmap='Blues')
plt.xlabel('Predicho')
plt.ylabel('Real')
plt.title('Matriz de Confusion')
plt.show()
```

## Metricas de Clasificacion

```
                    Predicho
                 │ Positivo │ Negativo │
        ─────────┼──────────┼──────────┤
Real    Positivo │    TP    │    FN    │
        ─────────┼──────────┼──────────┤
        Negativo │    FP    │    TN    │
        ─────────┴──────────┴──────────┘
```

| Metrica | Formula | Interpretacion |
|---------|---------|----------------|
| **Accuracy** | (TP+TN)/(TP+TN+FP+FN) | % predicciones correctas |
| **Precision** | TP/(TP+FP) | % de predichos positivos correctos |
| **Recall** | TP/(TP+FN) | % de positivos reales detectados |
| **F1-Score** | 2*(Prec*Rec)/(Prec+Rec) | Media armonica Precision-Recall |

## Random Forest

```python
from sklearn.ensemble import RandomForestClassifier

# Entrenar
rf = RandomForestClassifier(
    n_estimators=100,
    max_depth=10,
    random_state=42
)
rf.fit(X_train, y_train)

# Importancia de features
importances = pd.DataFrame({
    'feature': X.columns,
    'importance': rf.feature_importances_
}).sort_values('importance', ascending=False)

print(importances)
```

## Cuando Usar Cada Algoritmo

| Escenario | Algoritmo Recomendado |
|-----------|----------------------|
| Segmentar clientes sin etiquetas | K-means, DBSCAN |
| Predecir si cliente comprara | Decision Tree, Random Forest |
| Detectar fraude (desbalanceado) | Random Forest con class_weight |
| Interpretabilidad importante | Decision Tree |
| Alta precision requerida | Random Forest, Gradient Boosting |

---
*Taller de Tecnologia Aplicada - ADEN University - Cuatrimestre I 2026*
