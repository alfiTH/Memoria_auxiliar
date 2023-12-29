
uso del ppepe instalar coreografer

# Robots
- peper
- nao
- romeo
# Permite
- gestión de eventos
- correr en paralelo
- sincronización
- cross-pratform and language
- introspección


allpreceresces ->rosparam

allbounjour ->detector en la red

modulos->componentes

## DCM 
encargado de todas las comunicaciones con los sensores 
A ritmo de 1-10ms
![[Pasted image 20231211202928.png]]
Sincronizacion a tiempo real con hilos

### timed command
- clearAll, solo te quedas con el ultimo 
- merge fusiona todos los conados enviados
- clearAfter, prioridad en el ultimo, pero usas el otro antes de empezar 
- clearBefore prioridad al primero, pero usas el otro al acabar
## ALMemory
memoria entre los componentes
un mapa que puede tener historico de solo lectura
este guarda 4By en int y en float, pero en python  son 8By
## Broker

## Porxy
premite representar las conexiones con los modulos que queramos

## Arquitectura



# SDK 
[[https://www.aldebaran.com/en/support/nao-6/downloads-softwares]]

opcion SDK c++, descompirmimos y en raiz 
```bash
./naoqi
bin/qicli info # ver los servicios activos
```


