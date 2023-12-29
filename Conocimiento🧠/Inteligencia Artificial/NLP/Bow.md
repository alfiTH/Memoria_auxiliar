# Bag of Words
Presentamos con texto como una frecuencia  de las palabras sin ordenar
el proceso es:
1. Se genera un diccionario con las palabras sin repetir del dataset
2. De forma individual de cada documento se realiza un vector numérico referida al diccionario antes creado estos números del vector representan la frecuencia de cada palabra del diccionario en el documento
Son eficientes con los dataset pequeños pero no tiene encuenta el orden ni similitud de las frases
# Uso
```python
from sklearn.feature_extraction.text import CountVectorizer
vectorizer_bow = CountVectorizer(min_df=5, ngram_range=(1, 2), max_features=1000)
X_processes = vectorizer_bow.fit_transform(X)
```