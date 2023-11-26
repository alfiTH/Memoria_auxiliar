# Introducción
Realiza una combinación de todos los parámetros, con un cruzamiento en la validación, entrenando diferentes modelos con los diferentes parámetros para escoger el mejor.

# Ventajas
- Paralelizable mediante el parámetro  `job` .
- Util para optimizar parámetros.
- Encuentra el modelo Optimo según los parámetros ofrecidos.
# Desventajas
-  Es mas lento que el [[Randomized Search CV]], ya que realiza todos los modelos.
# Uso

```python
from sklearn.model_selection import RandomizedSearchCV
#Parametros a probar
param_grid = {"n_neighbors":[3, 6, 15], "p":[1, 2], "leaf_size":[10, 30, 50]}
rand_search = RandomizedSearchCV(MODEL(), param_grid, n_jobs=-1, cv=5,
			scoring='neg_mean_squared_error',return_train_score=True, verbose=2)
rand_search.fit(X_train, y_train)
rand_search.predict(X_test)

```
Ver los 5 modelos mejores.
```python
display("Best five models", pd.DataFrame(knn_clf.cv_results_).sort_values("rank_test_score").head(5))
```
Obtener el mejor modelo entrenado.
```python
model = model.best_estimator_
```