El objetivo de stop word es la eliminación de palabras comunes en el lenguaje (articulos, preposiciones...), palabras vacías que no aportan nada al texto.
# Uso
```python
import nltk
from nltk.corpus import stopwords
# Descargamos el diccionario
nltk.download('stopwords')
# Ajustamos el idioma
stopword = stopwords.words('english')
# Ejecutamos
text_preprocessed = re.sub(r'\b(' + r'|'.join(stopword) + r')\b\s*', ' ', text_preprocessed)

```