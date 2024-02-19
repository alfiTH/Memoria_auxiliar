# Conceptos
Se centra en el trabajo con textos
tealiza un conjunto de metodos que simplifican el lenguaje humano a lago entendible para el computador
se usa en:
- trasuccion
- calsificacion, clusterisn
- extraccion de informacion

Se dicerencias porque el texto es discreo con la conbinatori de las palabras y es una secuencia de datos


#TODO me fui
## Clasificacion de texto


## Preprocesameinto
es muy umporante
- Porner todo a minuscula
- Eliminar signos de puntuacion
- Eliminar palabras vacias(stopwords)-> (conjunto de palabras comunes en el lenguaje (articulos, preposiciones...))
- reduccion de caracteres(Stemming) reduccion a raiz, (Lemmatization) reducion a palabra origen del diccionario
- cambiar url, numeros 
- eliminacion de palabras repetidas de forma consecutivas o flatas de ortografia
- en caso de HTML, emails.. uno de las cabeceras o no

## Extraccion de caracteristicas
convierte el texto preprocesado caracteristicas
### BOW, Bolsa de palabras
Presentamos con texto como una frecuencia  de las palabras sin ordenar
el proceso es:
1. se genera un dicionario con las palabras sin repetir del dataset
2. de forma individual de cada documento se realiza un vector numerico referida al diccionario antes creado estos numeros del vector representan la frecuencia de cada palabra del diccionario en el documento
son eficientes con los dataset pequeños preo no tiene encuenta el orden ni similitud de las frases
### HASING


### TF-IDF, Term Frecuency - Inverse Document Frecuency
Este modelo da mas peso a las palabras clave y los reduce a las palabra vacias
$$TFIDF = TF*IDF$$
TF frecunecia de las palabras en un testo, es mas especifico del documento analizado
$$TF = \frac{Num\_use_word}{Num\_word}$$

IDF Freceuncia inversa en todo el documento, es mas general en todos los documentos del dataset
$$IDF = \log{\frac{Num\_documentos}{Documentos\_use\_word}}$$


## N-Palabras #TODO 


## Clasificacion
modelos como los del  [[0_Supervisada]]



# Deep learning
## Standarizacion o preprocesameinto
![[#Preprocesameinto]]
## Tokenizacion
Dividir el texto en token o unidades de texto (caracteres, palabras, [[#N-Palabras TODO]], frases, documentos...)

## Vectorizacion
COnvertir las unicades a vectores numeriocos
- one hotencoder
- Most Common/basic token
- word embeddings-> tiene vectores mas pequeños y comparos sin ser una costuccion binaria a algo mas complejo(como si fuera un espacio latente)




se usa enpython nltk