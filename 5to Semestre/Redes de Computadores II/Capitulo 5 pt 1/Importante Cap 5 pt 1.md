# Capa de Red
## Qué hace la Capa de Red
Se encarga de enviar paquetes desde un origen hasta un destino mediante la red, se hace por medio de routers intermedios entre cada host.
## Objetivos de Diseño de la Capa de Red
- Los host deben ser **independientes de la tecnología del enrutador**.
- Deben estar **aislados de la cantidad, tipo y topología de la red**.
- Las direcciones de red deben tener **numeración uniforme**.
## Diferencias entre Servicios de Datagramas y CV

| Datagramas                                                                                                                                      | Circuitos Virtuales                                                    |
| ----------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| Sin necesidad de configuración previa, ya que es un servicio NO orientado a la conexión                                                         | Necesitan configuración previa                                         |
| Cada paquete es ruteado de forma independiente                                                                                                  | Todos los paquetes siguientes siguen una misma ruta                    |
| Dependen de la dirección de destino incluidos en ellos                                                                                          | Dependen de la ruta preestablecida y de un sistema de etiquetas breves |
| La falla de un router no implica pérdida del paquete necesariamente, ya que cada uno se enruta de forma independiente y el camino puede variar. | Si un router se apaga, se complica el envío del paquete por esa ruta   |

## Algoritmos de Enrutamiento

>[!important] Principio de Optimalidad
>Si existe un router intermedio $J$ en el camino ópitmo entre $I$ y $K$, el principio dice que entonces el camino óptimo entre $J$ y $K$ es también parte de la primera ruta y es óptimo.
>**Cada porción de un mejor camino, es también un mejor camino**

El objetivo de los algoritmos de enrutamiento es buscar la ruta más corta o la que contenga menos saltos.
### Camino Más Corto - Dijkstra
- Cada enlace tiene un peso no negativo.
- El camino más corto es el de menor costo.
- Si los pesos son todos, se elige el de menor cantidad de saltos.

### Inundación
- Sí o si encuentra la ruta más larga
- Es un tipo de algoritmo de broadcast, envía a todos los vecinos
- Se logra llegar a todos los nodos de la red

### Enrutamiento por Vector de Distancia (Bellman Ford)
- Parecido a Dijkstra, pero encuentra el camino más corto dividido entre nodos
>[!info] Funcionamiento
>Cada nodo conoce la distancia solamente a sus vecinos, luego cada uno anuncia sus vecinos a todos los nodos (es el vector de distancia a sus vecinos), cada nodo usa estos vectores para actualizar sus distancias a sus vecinos. Esto se repite hasta encontrar el camino minimo.
