# Introducción
![[Pasted image 20231126213152.png]]
Ese método es simple, establecen reglas binarias de decision, de esta forma seccionan los hiperplanos, como se superior, inferior o igual a determinado valor.
Son estructuras en forma de árbol donde cada nodo representa una característica (atributo), cada rama representa una regla de decisión, y cada hoja representa un resultado.
# Ventajas
- Requieren poca preparation de los datos
- Son algoritmos muy potentes, capaces de ajustarse a conjuntos de datos complejos.
- Fácilmente interpretables
- Pueden manejar problemas multi-salida.
# Desventajas
-  Si el árbol es inmenso puede generar overfiting
- Son sensibles al  desbalanceo de datos o variaciones de estos
- Son sensibles al rotaciones de los datos ya que los cortes de los hiperplanos son ortogonales
# Uso
## Clasificador

```python
from sklearn.tree import DecisionTreeClassifier
tree_clf = DecisionTreeClassifier(max_depth=2, random_state=42)
tree_clf.fit(X_train, y_train)
tree_clf.predict(X_test)
```

## Regresión
```python
from sklearn.tree import DecisionTreeRegressor
tree_reg= DecisionTreeRegressor(max_depth=2, random_state=42)
tree_reg.fit(X_train, y_train)
tree_reg.predict(X_test)

```
## Visualización
```python
from graphviz import Source
from sklearn.tree import export_graphviz

export_graphviz(TREE_MODEL,out_file=os.path.join(IMAGES_PATH, "PATH.dot"),feature_names=iris.feature_names[2:],class_names=iris.target_names,rounded=True,filled=True)

Source.from_file(os.path.join(IMAGES_PATH, "PATH.dot"))
```