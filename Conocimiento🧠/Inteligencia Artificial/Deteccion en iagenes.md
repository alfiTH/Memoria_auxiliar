
# Clasificador de imagenes
solo dice si el elemnto esta en la imagen, pero no cuantos, donde o los pixeles
# Detector de objetos 
Puede detectar varias instancias del diferentes objetos y su posicion por el bbox, pero no dispone de mascaraas de pixel
# Segmentador
Localiza, clasifica objetos a nivel de pixel, pero no diferencia entra instancias 
# Segementador de instancias
Lo realiza todo genera un mascara a ivel de pixeles de cada instancia y la calsifica


# metodos  posporocesamenso
## Non-maximun suppresion NMS
Elimina la repeticiones de boundigbox de la misma instancia
los diferenes algoritmos pueden ser
- Mediante un umbral eliminaos los que no sean superiores
- seleccionamos los bounting con mas probabilidades #TODO 


## Metircas 
### Mean Average Preccison
es la media de las clases en el area del reacall y preccision #TODO 
1. mediante la matriz de confusion obtenemos 


## Modelos propiestos
### R-CNN
extrae zonas de interes propuestas, lo pasas por una red esas zonas(bounding box) para aplicarle despues un clasificador tracidional para saber si ese bouning tiene o no el elemento en cuestion
las zonas de interes se realizan mediante una sengemtacion parecida a la del bottom-up, es decir sienfo algoritmia o parametrizado 
Es muy pesado ya que tiene que pasar por el segmentado para estimar las zonas de interes y posterior a cada zona aplicarle el clasificador
### Fast R-CNN
tienes el softamax de la clasificacion(K+1<-Background) mas un boundibox tregressor
pasa la imagen entera y te estima su boundin con la clase

### Faster R-CNN
#TODO 

### Single-Shot Detector, SSD
usa VGG-16 #TODO (enlaze), esta realiza las propuesta de prediccion, son muchas propuestas, en capa mas profundas ya no puedes ver en entorno pero ver con mas nitided el obeto e cuesstion, despues necesita un [[#Non-maximun suppresion NMS]]

### YOLO
pRECIDA AL ssd pero se tiene el mapa de caracteristicas con la imagen segmentada #TODO 
https://github.com/ultralytics/ultralytics

