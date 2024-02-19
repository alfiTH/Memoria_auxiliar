Realiza prediciones aciadelnte 
- Modelo de transicion: Se basan en varios estados,  los estanos anteriores condicionan a los actuales y futuros 
- Estacionaria: las probabilidades son las misma en todos los tiempos
- Morakovianas: el futuro es independiente del pasado, pero dependiente del presente

## Grados de markov
Es cuanto ves hacia atras:
1º->t(t-1)
2º->t(t-1,t-2)
cuanto mas grado mas complegidad tendra la cadena

## Probabilidades
En este caso es la probabilidad conjunta no se mutiplica como en bayes si no se se suman
$$P(x_0, x_1, x_2)= P(x_0) * P(x_1|x_0)* P(x_2|x_1)$$
si queremos solo x2 sera la suma de todo lo que llege al el #TODO

## Uso
- Procesamiento de texto
- Busqueda web

## Ventajas
Estado estacionario: cundo ya se 

## Markoviano oculto
Predices la actuaalidad con el conocimineto del pasado y las evidencias
