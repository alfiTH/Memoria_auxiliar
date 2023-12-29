# Natural Language Processing
Se centra en el trabajo con textos con un conjunto de métodos que simplifican el lenguaje humano a lago entendible para el computador
se usa en:
- Traducción
- Clasificación, clustering
- Extracción de información

Se diferencia porque el texto es discreto con la combinación de las palabras y es una secuencia de datos.
# Preprocesamiento
Es muy importante el preprocesamiento antes de aplicar los clasificadores, ya que así aumentamos el rendimiento y precisión de los mismos
## Eliminación, filtrado o edición del texto
- [[Eliminaciones de caracteres]]
- [[Stop word]]
- [[Stemming]]
- [[Lemmatization]]
- Eliminación de palabras repetidas de forma consecutivas o faltas de ortografía
- En caso de HTML, emails.. el uso de las cabeceras o no

## Extracción de características
Convierte el texto preprocesado características.
![[Bow#Bag of Words]]

![[TF-IDF#Term Frequency - Inverse Document Frequency]]
### HASING

## N-Palabras #TODO 

## Tokenizacion
Dividir el texto en token o unidades de texto (caracteres, palabras, [[#N-Palabras TODO]], frases, documentos...)

## Vectorizacion
COnvertir las unicades a vectores numeriocos
- one hotencoder
- Most Common/basic token
- word embeddings-> tiene vectores mas pequeños y comparos sin ser una costuccion binaria a algo mas complejo(como si fuera un espacio latente)

# Clasificación
![[0_Supervisada#Machine Learning]]

![[0_Supervisada#Deep Learning]]

