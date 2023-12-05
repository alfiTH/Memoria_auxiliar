# Introducción
Busca la mejor combinación de hiperplanos mediante cortes y un margen 
De base son lineales:
![[Pasted image 20231126203152.png]]
Pero se pueda usar un kernel Gausiano para comportamientos no lineales

![[Pasted image 20231126203056.png]]

# Ventajas
- Son particularmente poderosos en espacios de alta dimensión y eficaces en casos donde el número de dimensiones es mayor que el número de muestras, pero de tamaño pequeño o mediano
# Desventajas

# Uso
## Clasificador
### Lineal
```python
from sklearn.svm import SVC
svm_clf = SVC(kernel="linear", C=float("inf"))
svm_clf.fit(X_train, y_train)
svm_clf.predict(X_test)
```
### No lineal
```python
from sklearn.svm import SVC
svm_clf = SVC(kernel="rbf", gamma=5, C=1000))
svm_clf.fit(X_train, y_train)
svm_clf.predict(X_test)
```
## Regresión
```python
from sklearn.svm import SVR 
svm_reg = SVR(kernel="poly", degree=2, C=100, epsilon=0.1, gamma="scale") 
svm_reg.fit(X_train, y_train) 
vm_reg.predict(X_test)
```