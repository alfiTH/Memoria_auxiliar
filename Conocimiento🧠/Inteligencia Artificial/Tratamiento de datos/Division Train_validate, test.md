# Division de las carpetas
Este codigo de python pide una ruta con un dataset clasificado por carpetas, este lo convertirá en dos carpetas, train y test segun el tamaño otrorgado, y estas estarán con la misma estructuracón de clases por carpeta.
```python
import os
import shutil
from sklearn.model_selection import train_test_split

def split_dataset_into_train_test(source_folder, train_size=0.8):
    """
    Divide los datos en las carpetas 'train' y 'test', teniendo en cuenta si ya existe la división,
    y elimina las carpetas vacías después del proceso.

    :param source_folder: Carpeta que contiene subcarpetas, cada una representando una clase.
    :param train_size: Proporción de los datos que se utilizará para el entrenamiento.
    """
    classes = [d for d in os.listdir(source_folder) if os.path.isdir(os.path.join(source_folder, d))]
    train_folder = os.path.join(source_folder, 'train')
    test_folder = os.path.join(source_folder, 'test')

    # Verifica si ya existe la división
    if 'train' in classes and 'test' in classes:
        print("La división de entrenamiento y prueba ya existe.")
        return

    # Crea las carpetas de destino si no existen
    os.makedirs(train_folder, exist_ok=True)
    os.makedirs(test_folder, exist_ok=True)

    for cls in classes:
        # Crear subcarpetas en las carpetas de train y test
        os.makedirs(os.path.join(train_folder, cls), exist_ok=True)
        os.makedirs(os.path.join(test_folder, cls), exist_ok=True)

        # Obtener una lista de imágenes
        all_images = os.listdir(os.path.join(source_folder, cls))

        # Dividir en entrenamiento y prueba
        train_images, test_images = train_test_split(all_images, train_size=train_size, random_state=42)

        # Mover imágenes a las respectivas carpetas
        for img in train_images:
            shutil.move(os.path.join(source_folder, cls, img), os.path.join(train_folder, cls, img))

        for img in test_images:
            shutil.move(os.path.join(source_folder, cls, img), os.path.join(test_folder, cls, img))

        # Eliminar la carpeta de clase original si está vacía
        if not os.listdir(os.path.join(source_folder, cls)):
            os.rmdir(os.path.join(source_folder, cls))

# Ejemplo de uso
source_folder = 'path/to/your/dataset/folder'  # Debes reemplazar esto con la ruta de tu carpeta de datos
split_dataset_into_train_test(source_folder)
```
# Uso de cargadores
Loa cargadores de dataset son muy cómodos ya que te pueden realizar data-augmentation de forma automática entre otras cosas y también te deposita el dataset en forma de batches. 
## Keras
En keras es mediante `ImageDataGenerator`, que habra que instanciarlo con la configuración y despues la carga de datos por la carpeta seleccionada
```python
from tensorflow.keras.preprocessing.image import ImageDataGenerator

# Configuración de aumentación de datos para el conjunto de entrenamiento
train_datagen = ImageDataGenerator(
    rescale=1./255,
    rotation_range=40,      # Grados de rotación aleatoria
    width_shift_range=0.2,  # Fracción del total (ancho) para desplazamiento horizontal
    height_shift_range=0.2, # Fracción del total (alto) para desplazamiento vertical
    shear_range=0.2,        # Ángulo de corte en contra de las agujas del reloj
    zoom_range=0.2,         # Rango de zoom aleatorio
    horizontal_flip=True,   # Voltear aleatoriamente las entradas horizontalmente
    fill_mode='nearest',    # Estrategia para rellenar los píxeles recién creados
    validation_split=0.2    # Fracción de las imágenes reservada para la validación
)

# Generador para datos de entrenamiento
train_dataset = train_datagen.flow_from_directory(
    "animals/train",
    target_size=(SIZE, SIZE),
    batch_size=BATCH_SIZE,
    shuffle=True,
    class_mode='categorical',
    subset="training"
)

# Generador para datos de validación (sin aumentación)
validation_datagen = ImageDataGenerator(
    rescale=1./255,
    validation_split=0.2
)

validation_dataset = validation_datagen.flow_from_directory(
    "animals/train",
    target_size=(SIZE, SIZE),
    batch_size=BATCH_SIZE,
    shuffle=True,
    class_mode='categorical',
    subset="validation"
)

# Configura un generador para el conjunto de prueba (sin aumentación)
test_datagen = ImageDataGenerator(rescale=1./255)

test_dataset = test_datagen.flow_from_directory(
    "animals/test",
    target_size=(SIZE, SIZE),
    batch_size=BATCH_SIZE,
    shuffle=False,
    class_mode='categorical'
)
```
## Torch
