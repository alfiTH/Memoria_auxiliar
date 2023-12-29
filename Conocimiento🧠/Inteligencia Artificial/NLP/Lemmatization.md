Reduce la palabra a su origen del diccionario, eliminando conjugaciones o aditivos a esta
# Uso
```python
from nltk.stem import WordNetLemmatizer
lemmatizer = WordNetLemmatizer()

text_preprocessed = ' '.join([lemmatizer.lemmatize(word) for word in text_preprocessed.split()])
```