Su objetivo es la reduction de caracteres a raíz de este
# Uso
```python
from nltk.stem import PorterStemmer
#Istanciamos
porter = PorterStemmer()
# Ejecutamos
text_preprocessed = ' '.join([porter.stem(word) for word in text_preprocessed.split()])
```