# Introducción
![[Pasted image 20231126205621.png]]
Funciona actualizando los parámetros del modelo de manera iterativa con el fin de minimizar una función de pérdida
# Ventajas
- Es particularmente eficaz para problemas con un gran número de muestras y características
- Es posible aplicarle método Online
# Desventajas
- Es sensible al learnig rate 
- En caso de ruido puede dar problemas
- Puede ser sencillo los mínimos locales
# Uso
## Clasificador

```python
from sklearn.linear_model import SGDClassifier
sgd_clf = SGDClassifier(max_iter=1000, tol=1e-3)
sgd_clf.fit(X_train, y_train)
sgd_clf.predict(X_test)
```

## Regresión
```python
from sklearn.linear_model import SGDRegressor
sgd_reg = SGDRegressor(max_iter=1000, tol=1e-3)
sgd_reg.fit(X_train, y_train)
sgd_reg.predict(X_test)
```