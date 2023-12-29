En el [[NLP]] es importante simplificar los testo, para ello sustituimos los números, urls, direcciones u otros elementos con una misma letra
# Uso
```python
import re
#Creamos un diccionario con lo que quermos sustituir
re_tags_dict = {
'url': " url ",
'email': ' email '
}
# Complilamos por optimizacion la regla
url_regex_https = re.compile(r'https?://[^\s]+')
url_regex_www = re.compile(r'www\.[^\s]+')
email_regx = re.compile(r'\b[A-Za-z0-9!#$%&\'*+-/=?^_`{|}~]+@[A-Za-z0-9!#$%&\'*+-/=?^_`{|}~]+\.[A-Z|a-z]{2,}\b')
# Usamos la regla 
text_preprocessed = url_regex_https.sub(re_tags_dict['url'], text_preprocessed)
text_preprocessed = url_regex_www.sub(re_tags_dict['url'], text_preprocessed)
text_preprocessed = email_regx.sub(re_tags_dict['email'], text_preprocessed)
```
Si hay muchas se puede mejorar con key como remplazo del texto y value la regla compilada para la ejecución del texto en una sola line de for
# Caracteres del re
- \[ ]-> Cualquier carácter dentro de los corchetes
- ^ -> Negación
- ? -> Carácter anterior opcional
- \\s -> espacio en blanco