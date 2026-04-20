Los errores inalámbricos y los bucles locales envejecidos tienen tasas de error que son órdenes de magnitud mayores.
Las estrategias tomadas para el manejo de errores utilizan información adicional añadidas a los datos enviados.
- [i] Los errores se deben a:
	- Distorsión
	- Ruido
	- Atenuación

>[!important] Estrategias de control de errores
>Ambas se basan en **añadir la suficiente información redundante** para que el **receptor** pueda **deducir**:
>1. Lo enviado. [[Control de errores (Detección y corrección)#Códigos de corrección|Códigos de corrección]]
>2. Si se ha producido un error y solicitar una retransmisión. (no identifica dónde se produjo el error). [[Control de errores (Detección y corrección)#Códigos de detección|Códigos de detección]]
### Tipo de error
Como ningún modelo es 100% efectivo, hay que considerar el tipo de error producido.
1. Variaciones en **ruido térmico:** producen errores uniformemente distribuidos.
2. **Errores impulsivos:** producen errores de ráfaga (son más difíciles de corregir que los errores aislados).

## Códigos de corrección (FEC - Forward Error Connection)
- Se utilizan en canales ruidosos porque las retransmisiones tienen la misma probabilidad de error que la primera transmisión.
- Usos: [[2. Capa Física]], [[2. Capa de Enlace de Datos]] y capas superiores.

>[!tip] Los diferentes tipos de corrección de errores son:
>1. Código de Hamming
>2. Código convolucionales binarios
>3. Códigos Reed-Solomon
>4. Códigos de comprobación de paridad de baja densidad

- **Código de bloques:** los **r** bits de comprobación se calculan en función a los **m** bits de datos asociados.
- **Código sistemático:** los **m** bits de datos se envían a la vez que los de control, en lugar de codificarse antes de los enviados.
- **Código lineal:** los **r** bits de control se calculan como una función lineal de los **m** bits de datos.

==El más utilizado es el OR exclusivo o XOR o la **suma de módulo 2**==

- [I] **Codeword (palabra codificada):** unidad de n bits que contiene datos y bits de comprobación.
- [I] **Tasa de codificación:** es la fracción de la codificación que contiene información no redundante ($m/n$).
	- ($1/2$) en canal ruidoso
	- ($1$) en canales de alta calidad
## Corrección de errores de un solo bit
Se presenta en el código de Hamming
==ESTUDIAR PORQUE EL PROFE DIJO QUE PUEDE PREGUNTAR ALGO ASI==
>[!info] Se tiene **m** bits de mensaje y **r** bits de verificación y se quiere corregir todos los errores de **un bit**.
>- Mensajes posibles: $2^m$
>- Cant de codewords: $(m+r+1)$
>	Para indicar la ausencia de error (una codeword válida)
>	Para indicar la ubicación del error ($m+r$posibilidades)
>- Cant de codewords: $2^n=2^{m+r}$ palabras codificadas
>$$2^m*(m+r+1)\leq{2^{m+r}=2^m*2^r}$$
>$$(m+r+1)\leq{2^r}$$

## Códigos de detección
- [I] **Distancia de hamming:** es la cantidad mínima de bits cambiados para pasar de una palabra codificada válida a otra cualquiera. La **distancia de un código completo** es la menor de todas las distancias entre una palabra y otra.
	Un código con distancia mínima de Hamming **d** puede detectar palabras codificadas (codewords) con hasta **s** bits con error, donde $d_{min}\gt{s}$

>[!info] Funcionamiento de control de errores
>- Toma un mensaje de longitud **m**
>- Le agrega **r** bits de redundancia
>- Se obtiene una **palabra codificada** de longitud **n** $$n=m+r$$

## Comparativa

| **Detección de errores**                                                                                                       | **Corrección de errores**                                                                                                |
| ------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------ |
| $d_{\text{min}}$ : distancia de Hamming<br>$s$ : cantidad de bits con error **máximos a detectar**<br>$$d_\text{{min}}\gt{s}$$ | $d_{\text{min}}$ : distancia de Hamming<br>$t$ : cantidad de bits con error **máximos a corregir**<br>$$d_{min}\gt{2t}$$ |
| ![[detección de error y hamming.png\|250]]                                                                                      | ![[corrección de error y hamming.png\|300]]                                                                                |


---
# Enlaces relacionados
- Siguiente nota: [[Código de Hamming]]

