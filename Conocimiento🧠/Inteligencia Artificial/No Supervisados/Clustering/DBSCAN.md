Density-Based Sparital Clustering of Application with Noise
- Esta basado en densidad 
- Controla mejor los outlier que el MINIT, los puede clasificar inclusive

## Métricas esenciales
- Distancias de vecindario, $\epsilon$ 
	Define el radio de la vecindad para definir puntos núcleo del cluster
	- grande cluster masivo
	- pequeño subdivision de cluster reales o ni siquiera podrá agrupar ya que lo identifica como ruido
- Vecinos mínimos para la propagación, $M$
	Si no cumples la condición de *n* vecinos no sigues propagando, 
	busca ir propagando hasta el borde del cluster

## Definiciones
- Punto nuclear, tiene una agrupación de puntos de radio $\epsilon$ , superior o igual a $M$
- Punto borde, no nucleares del cluster, pertenecen al cluster pero no alcanzan $M$, en el radio $\epsilon$
- Outliers, no esta asignado a ningún cluster
- Directamente denso-alcanzable, dentro del núcleo de radio $\epsilon$
- Denso-alcanzable, se puede alcanzar desde un punto directamente denso-alcanzable pero no es nuclear

## Algoritmo
1. Encuentras un punto nuclear
2. Propagas por los puntos directamente denso-alcanzables
3. Esos puntos denso-alcanzables son los puntos asignados al cluster y desde este sigues propagando hasta que no sean nucleares
### Pseudo código 
```
si y no esta en cluster
	n_vecinos = Calucar vecinos con epsilon
	si n_vecinos >= M
		si vecino x esta asignado como ruido
			x ahora es de cluster de y
		else si x esta en otro cluster 
			continue
		si no  #TODO 
```
#TODO 
## Ventajas
## Desventajas