# Introducción
![[Pasted image 20231126215325.png]]
Es una combinación de varios [[Tree]], como un [[Ensemble Learning]], esto mejora el resultado y corrige el hábito de overfitting.
# Ventajas
-  Es muy preciso
- Puede manejar gran cantidad de datos
# Desventajas
- Tiempo de entrenamiento elevado ya que estas entrenando varios [[Tree]], sobretodo en conjunto de datos grandes
- No son tan visuales como los [[Tree]]
# Uso
## Clasificador

```python
from sklearn.ensemble import RandomForestClassifier
rf_clf = RandomForestClassifier(random_state=0)
rf_clf.fit(X_train, y_train)
rf_clf.predict(X_test)
```

## Regresión
```python
from sklearn.ensemble import RandomForestRegressor
rf_reg = RandomForestRegressor(random_state=0)
rf_reg.fit(X_train, y_train)
rf_reg.predict(X_test)
```