## Ventanas Corredizas 
Las **ventanas corredizas** (o deslizantes) son un mecanismo de **control de flujo** basado en retroalimentación que permite que un emisor rápido no sature a un receptor lento, optimizando al mismo tiempo el uso del canal de comunicación.
Su funcionamiento se basa en:
# 1. Numeración de tramas
Para que el sistema funcione, cada trama transmitida debe incluir un **número de secuencia** en su encabezado. El rango de estos números suele ir de $0$ hasta un máximo de $2^n - 1$ (donde $n$ es el número de bits del campo de secuencia).
# 2. Definición de las ventanas
Tanto el emisor como el receptor mantienen una "ventana" que representa el conjunto de números de secuencia que tienen permitido procesar en un momento dado.
- **Ventana de emisión:** Es el grupo de números de secuencia que el emisor tiene permitido enviar sin esperar una confirmación.
- **Ventana de recepción:** Es el conjunto de números de trama que el receptor está preparado para aceptar.
# 3. El proceso de envío (Paso a paso)
1. **Carga de paquetes:** El emisor toma un paquete de la capa de red y lo encapsula en una trama, asignándole el número de secuencia disponible inmediatamente superior.
2. **Avance del extremo superior:** Al asignar un nuevo número, el **extremo superior** de la ventana del emisor avanza una posición.
3. **Almacenamiento en buffer:** El emisor debe guardar una copia de todas las tramas enviadas pero no confirmadas en un **buffer** por si fuera necesario retransmitirlas.
4. **Transmisión continua (Pipelining):** A diferencia de protocolos más simples, el emisor puede seguir enviando tramas mientras su ventana no esté llena, permitiendo que haya varias tramas "en vuelo" simultáneamente.
# 4. Recepción y Confirmación (ACK)
1. **Validación en el receptor:** Cuando llega una trama, el receptor verifica si su número de secuencia cae dentro de su ventana de recepción.
2. **Entrega a la capa superior:** Si la trama es la que se esperaba (el borde inferior de la ventana), se entrega a la capa de red y la ventana del receptor **gira** o avanza una posición.
3. **Envío del ACK:** El receptor envía un acuse de recibo (**ACK**) al emisor. Este puede enviarse como una trama de control separada o mediante **piggybacking** (superposición), insertando la confirmación dentro de una trama de datos que viaje en sentido contrario.
4. **Avance del extremo inferior (Emisor):** Cuando el emisor recibe el ACK, el **extremo inferior** de su ventana avanza, lo que libera espacio en su buffer y le permite enviar nuevas tramas.

En el emisor el tamaño es variable, pero en el receptor se tiene un tamaño fijo y avanza con las tramas numeradas y estas ventanas no necesariamente son del mismo tamaño. 
## Fórmulas de Eficiencia de Utilización del Canal ($Ef$)

Las fórmulas para calcular la eficiencia de utilización del canal ($Ef$) varían dependiendo del protocolo de acceso al medio y del tipo de mecanismo de confirmación (ACK) utilizado.

> [!abstract] Concepto General
> La eficiencia ($Ef$) es la relación entre el tiempo que el canal está enviando datos útiles y el tiempo total del ciclo (transmisión + espera de confirmación).

# 1. Protocolos de Ventana Corredizas

> [!important] Fórmula General
> $$Ef = \frac{\text{Tiempo de transmisión de } W \text{ tramas}}{\text{Tiempo de llegada del primer ACK}}$$

> [!todo] Caso: ACK en Tramas de Control (Pequeñas)
> Se usa cuando la confirmación es un paquete mínimo dedicado.
> $$Ef = \frac{W \cdot T_t}{2T_p + T_t}$$


> [!todo] Caso: ACK en Tramas de Datos (Piggybacking) o Superposicion
> Se usa cuando el ACK viaja "montado" en un paquete de datos que viene de regreso.
> $$Ef = \frac{W \cdot T_t}{2T_p + 2T_t}$$


> [!info] Diccionario de Variables
> - **$W$**: Tamaño de la ventana.
> - **$T_t$**: Tiempo de transmisión ($L_t / V_t$). (Longitud de la trama (bits)/ tasa de bits(bits/seg))
> - **$T_p$**: Retardo de propagación. (Distancia(m)/ Velocidad de propagacion (m/s))
> - **$B$**: Tramas por segundo ($V_t / L_t$).
>

> [!tip] Condición para Eficiencia del 100%
> Para que el emisor nunca se detenga, la ventana debe ser:
> $$W \ge 2BT_p + 1$$


----
# Enlaces relacionados
- Siguiente nota: [[Tipos de Ventanas]]
