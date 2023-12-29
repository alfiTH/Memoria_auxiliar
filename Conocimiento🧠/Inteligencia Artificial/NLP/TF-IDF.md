# Term Frequency - Inverse Document Frequency
Este modelo da mas peso a las palabras clave y los reduce a las palabra vacías
$$TFIDF = TF*IDF$$
TF frecuencia de las palabras en un texto, es mas especifico del documento analizado
$$TF = \frac{Num\_use_word}{Num\_word}$$
IDF Frecuencia inversa en todo el documento, es mas general en todos los documentos del dataset
$$IDF = \log{\frac{Num\_documentos}{Documentos\_use\_word}}$$

# Uso
```python
from sklearn.feature_extraction.text import TfidfVectorizer
vectorizer_tf_idf = TfidfVectorizer(min_df=5, norm='l2', use_idf=True, smooth_idf=True, ngram_range=(1, 2))
X_processes = vectorizer_tf_idf.fit_transform(X)
```