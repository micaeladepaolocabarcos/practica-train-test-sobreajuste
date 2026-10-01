# Práctica: Train/Test y sobreajuste

Dataset: *Producción de Pozos de Gas y Petróleo No Convencional* ([datos.gob.ar](https://datos.gob.ar/dataset/energia-produccion-petroleo-gas-por-pozo-capitulo-iv)).

## Experimento

- **Target:** producción mensual de petróleo (`prod_pet`) de pozos petrolíferos en extracción efectiva.
- **Características:** `profundidad`, `tef`, `prod_agua`, `anio`.
- **División:** `train_test_split` con 80% entrenamiento y 20% prueba (`test_size=0.2`, `random_state=42`).
- **Modelo:** `DecisionTreeRegressor` sin límite de profundidad, entrenado solo con el conjunto de entrenamiento.

## Resultado

| Conjunto | R² |
|---|---|
| Train | 1,000 |
| Test | 0,432 |

**Conclusión:** el modelo presenta **overfitting**: memoriza los datos de entrenamiento y pierde más de la mitad de su rendimiento con datos nuevos. La acción propuesta es simplificarlo limitando la profundidad del árbol (`max_depth`).

## Cómo ejecutarlo

1. Descargar el CSV desde el link de la fuente (no se incluye porque supera los 50 MB).
2. En Colab, guardarlo en `MyDrive/Colab Notebooks/`; en local, dejarlo en la misma carpeta que el notebook.
3. Ejecutar `practica_train_test_sobreajuste.ipynb` (requiere `pandas` y `scikit-learn`).
