## Parámetros
```C++
void myFunction(int a, int &b, int *c, const int d, const int &e, int &&f);
```
En esta función encontramos diferentes formatos de parámetros:
- a: en este se realiza una copia completa del la variable, malo en optimizaciones cuando son variables de gran tamaño.
- b: el uso de ***&*** hace que se pase la referencia de la variable como si fuera un puntero (4 bytes), esto dota de posibilidad de edición de la variable dentro de la función.
- c: es el puntero de la variable, dispone de las misma ventajas que el formato *b*, pero el uso de dicha variable se realiza como puntero con "\*" o "->" , siendo un poco mas molesto su uso.
- d: el ***const*** solo es una restricción mediante compilador al programador, evita que sea posible más modificación de la variable, pero este formato sigue copiando la variable completa.
- e: esta combina lo mejor de los dos formatos, es solo pasar un puntero/referencia (buenísimo para variables grandes), y ser constantes para forzar solo su uso en lectura.
- f: este le otorga el área de memoria a la función, es decir el ejecutor de la función  da como indeterminada la variable, pero es valida y se puede seguir usando, siendo su lectura para nada recomendada, ya que puede ser aleatorio su valor y siendo posible su escritura, siendo independiente con  la variable que dispone la función en su interior, este formato elimina cualquier tipo de copia ya que estas otorgando la memoria en si, este se acompaña con ```std::move(f)``` en el llamado de la función para convertirla el lvalue(estable en memoria) en  rvalue (valor temporal).
## Estática
### Fuera de una clase o estructura
```C++
static float calculadora(float a, float b, int operacion);
```
Una función estática fuera de un objeto o estructura limita la visibilidad de la función fuera del archivo donde esta implementada, como si de un "private" se tratara pero en vez de a nivel de clase a nivel de archivo. 
### Dentro de un objeto o estructura
```C++
static float Calculadora::calcular(float a, float b, int operacion);
```
Una función estática dentro de un objeto o estructura otorga independencia de la instancia de la clase, es decir es el código sin más de la función, sin necesidad de creación del objeto, esto limita en el uso de parámetros del propio objeto, ya que no es posible el ***this*** .