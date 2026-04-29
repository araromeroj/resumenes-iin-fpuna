# Protocolo ALOHA
Ideado en la Universidad de Hawái en los años 70, es el protocolo básico para sistemas de contención.
### 1. Elementos de Infraestructura y Actores

- **Canal Compartido (Medio Transmisión):** Un único canal de radio o cable por el cual todas las estaciones transmiten. Es un medio de difusión (_broadcast_).
- **Estaciones (Nodos):** Dispositivos independientes que generan tráfico de datos de manera impredecible (tráfico a ráfagas).
- **Unidad Central (Opcional):** En el ALOHA original, las estaciones enviaban datos a una computadora central (como en la Universidad de Hawaii). Si la central recibía la trama correctamente, enviaba un ACK.

### 2. Elementos de Protocolo

- **La Trama (Frame):** La unidad básica de información. En el análisis de ALOHA, se asume que todas las tramas tienen una **longitud fija ($L$)**, lo que simplifica el cálculo del tiempo de transmisión ($T$).
- **Acuse de Recibo (ACK):** Dado que el emisor no puede saber si hubo colisión solo con "escuchar" (especialmente en radio), depende de que el receptor le confirme que la trama llegó íntegra.
- **Tiempo de Transmisión ($T$):** Es el tiempo que tarda una trama en ser colocada totalmente en el canal.
- **Tiempo de Vulnerabilidad:** Es el intervalo de tiempo en el que existe riesgo de colisión.
    - En **ALOHA Puro**, es $2T$.
        
    - En **ALOHA Ranurado**, se reduce a $1T$.   

### 3. Elementos de Gestión de Colisiones

- **Colisión:** Se produce cuando dos o más estaciones transmiten al mismo tiempo (o sus tiempos se solapan), destruyendo la información de ambas tramas.
- **Tiempo de Espera Aleatorio (_Backoff_):** Si una estación no recibe su ACK, asume que hubo una colisión. Para evitar colisionar de nuevo con la misma estación, espera un tiempo al azar antes de retransmitir.
- **Ranuras de Tiempo (_Slots_):** Elemento exclusivo del **ALOHA Ranurado**. El tiempo se divide en intervalos discretos iguales a $T$. Las estaciones solo pueden empezar a transmitir al inicio de una ranura.

### 4. Elementos Matemáticos para el Análisis

Para resolver ejercicios o entender el rendimiento (como en los ejemplos anteriores), se usan estos parámetros:

- **$S$ (Throughput):** La tasa de éxito; cuántas tramas "buenas" se transmiten por tiempo de trama.
- **$G$ (Carga del canal):** La cantidad total de tráfico que intenta entrar al canal, incluyendo las tramas nuevas y las retransmisiones de colisiones previas.
- **$e$ (Constante de Euler):** Base de los logaritmos naturales ($\approx 2.718$), utilizada en la distribución de Poisson para calcular las probabilidades de éxito.

>[!summary] En resumen
>Los elementos combinan el **hardware** (estaciones y canal), las **reglas** (cuándo transmitir y qué hacer si falla) y la **matemática** que describe su eficiencia.
## Tipos de ALOHA
### ALOHA Puro

Fue el sistema original desarrollado en la Universidad de Hawai. Su filosofía es la **simplicidad total**.

- **Funcionamiento:** Cuando una estación tiene datos para enviar, los envía **inmediatamente**. No verifica si el canal está ocupado ni espera un momento específico.
- **Gestión de Colisiones:** Después de transmitir, la estación espera un tiempo. Si no recibe un acuse de recibo (ACK) del receptor, asume que hubo una colisión.
- **Reintento:** Para evitar colisionar infinitamente con la misma estación, espera un **tiempo aleatorio** antes de volver a intentar la transmisión.
- **Eficiencia:** Su rendimiento máximo es muy bajo, apenas un **18.4%**. Esto se debe a que el "tiempo de vulnerabilidad" es de $2T$ (donde $T$ es el tiempo de una trama), ya que una trama puede ser destruida por cualquier otra que haya empezado un instante antes o un instante después.

### ALOHA Ranurado (Slotted ALOHA)

Es una mejora del protocolo original propuesta por Roberts (1972) para duplicar la capacidad del canal mediante la **sincronización**.

- **Funcionamiento:** El tiempo se divide en intervalos discretos llamados **ranuras (slots)**, cada uno con una duración igual al tiempo de transmisión de una trama ($T$).
- **Regla de oro:** Una estación **no puede** transmitir en cualquier momento; debe esperar al inicio de la siguiente ranura de tiempo.
- **Gestión de Colisiones:** Si dos estaciones transmiten en la misma ranura, colisionan totalmente. Al igual que en el puro, si hay colisión, esperan un tiempo aleatorio medido en "número de ranuras" antes de reintentar.
- **Eficiencia:** Al obligar a las estaciones a alinearse, el "tiempo de vulnerabilidad" se reduce a la mitad ($1T$). Esto duplica el rendimiento máximo del canal hasta un **36.8%**.
### Cuadro Comparativo Resumen

|**Característica**|**ALOHA Puro**|**ALOHA Ranurado**|
|---|---|---|
|**Sincronización**|No requiere (caótico).|Requiere un reloj común para todos.|
|**Cuándo transmite**|En cualquier instante.|Solo al inicio de una ranura.|
|**Período vulnerable**|$2 \times \text{tiempo de trama}$|$1 \times \text{tiempo de trama}$|
|**Rendimiento Máximo**|**18.4%**|**36.8%**|

> **Nota de las diapositivas:** En las diapositivas se enfatiza que, aunque el **Ranurado** es mejor técnicamente, requiere que las estaciones estén sincronizadas (usualmente mediante una estación central que emite un pulso de reloj), lo que añade una capa de complejidad al hardware que el **Puro** no tiene.
## Diferencias entre el ALOHA Puro y ALOHA Ranurado

La diferencia fundamental entre el **ALOHA Puro** y el **ALOHA Ranurado (Slotted ALOHA)** radica en la **sincronización del tiempo**, lo que afecta directamente a la probabilidad de colisiones y, por ende, a la eficiencia máxima del canal.

>[!important] **IMPORTANTE!!!**

| **Característica**           | **ALOHA Puro**                                               | **ALOHA Ranurado**                                                   |
| ---------------------------- | ------------------------------------------------------------ | -------------------------------------------------------------------- |
| **Sincronización**           | No requiere. Las estaciones transmiten en cualquier momento. | El tiempo se divide en intervalos discretos (ranuras) sincronizados. |
| **Inicio de transmisión**    | En el instante en que los datos están listos.                | Solo al inicio de una ranura de tiempo.                              |
| **Tiempo de vulnerabilidad** | **$2T$** (el doble del tiempo de trama).                     | **$1T$** (igual al tiempo de trama).                                 |
| **Eficiencia máxima ($S$)**  | **18.4%** (cuando la carga $G = 0.5$).                       | **36.8%** (cuando la carga $G = 1.0$).                               |

### 2. ¿Por qué el Ranurado es más eficiente?

En el **ALOHA Puro**, si una estación transmite en el tiempo $t$, cualquier otra estación que empiece a transmitir entre $t-T$ y $t+T$ provocará una colisión. Por eso el intervalo de peligro es de $2T$.

En el **ALOHA Ranurado**, al obligar a todos a empezar al mismo tiempo (inicio de la ranura), se elimina la posibilidad de que una trama choque con otra que empezó "un poquito antes" o "un poquito después". O chocan totalmente (porque empezaron en la misma ranura) o no chocan en absoluto. Al reducir el tiempo de vulnerabilidad a la mitad ($1T$), la probabilidad de éxito aumenta y la capacidad del canal se duplica.

>[!note] salió en el test 6 de la semana 6

### 3. ¿Qué conviene más y por qué?

Desde el punto de vista del **rendimiento técnico**, el **ALOHA Ranurado conviene más** por las siguientes razones:

1. **Mayor Capacidad:** Soporta el doble de tráfico útil (36.8% vs 18.4%) antes de colapsar por colisiones.
    
2. **Mejor manejo de carga:** Permite que el sistema funcione con una carga de tráfico ($G$) más alta.
    
3. **Menos retransmisiones:** Al haber estadísticamente menos colisiones para una misma cantidad de datos, las estaciones gastan menos energía y tiempo reintentando envíos.

>[!danger] Desventaja
>- **Complejidad:** El ALOHA Ranurado requiere que todas las estaciones estén sincronizadas con un reloj común para saber exactamente cuándo empieza cada ranura. Esto puede requerir una estación especial que emita una señal de reloj (como un "beeper") o un sistema de sincronización más costoso.

---
# Protocolo CSMA

- [*] **CSMA - Carrier Sense Multiple Access:** Acceso Múltiple con Detección de Portadora.
- [I] **CSMA:** es un mecanismo de control de acceso al medio donde las estaciones "escuchan" el canal antes de transmitir para evitar colisiones. Se basa en el principio de "escuchar antes de hablar".

>[!info] Funcionamiento
>- **Detección de Portadora:** Antes de enviar una trama, la estación detecta si el medio está ocupado.
>- **Acción si el canal está libre:** La estación transmite su trama.
>- **Acción si el canal está ocupado:** La estación espera y lo intenta más tarde según el algoritmo específico de persistencia que utilice.
## Tipos de CSMA

Existen diferentes estrategias sobre qué hacer cuando el canal está ocupado:

- [I] **CSMA 1 - Persistente:** La estación escucha continuamente. En cuanto el canal queda libre, transmite con una probabilidad de 1 (de ahí su nombre). Si ocurre una colisión, espera un tiempo aleatorio.
	- Propiedad: Es egoísta. Si dos dos estaciones están esperando a que termine una transmisión actual, ambas transmitirán al mismo tiempo en cuanto el canal se libere, causando una colisión segura.
	
- [I] **CSMA No persistente:** Si el canal está ocupado, la estación no lo escucha continuamente; en su lugar, espera un intervalo de tiempo aleatorio y vuelve a repetir el proceso de detección. Es más eficiente en el uso del canal pero introduce más retardo.
	- Propiedad: Reduce colisiones pero aumenta el retardo o latencia, ya que el canal podría quedar libre y ninguna estación transmitir de inmediato.
	
- [I] **CSMA p-persistente:** Se aplica en canales con ranuras de tiempo (ranurados). Si el canal está libre, la estación transmite con una probabilidad _p_ y pospone la transmisión hasta la siguiente ranura con una probabilidad _1-p_.
	- Propiedad: Es un equilibrio entre los dos anteriores.

>[!important] Los persistentes tienen mayor probabilidad de colisiones.
## Evoluciones del CSMA

- [I] **CSMA/CD (Collision Detection):** Es la base de la **Ethernet clásica** (no conmutadas). Además de escuchar antes de transmitir, la estación sigue escuchando mientras transmite (**es persistente**). Si detecta una colisión, detiene la transmisión inmediatamente para no desperdiciar ancho de banda y ejecuta un algoritmo de **backoff exponencial binario** para retransmitir.
	Al tenerse un tiempo máximo de detección de colisiones, se define: $$L_{\text{trama mínima}}=V_t*2*\tau$$
	- $\tau:$ Es el tiempo que tarda una señal en viajar desde un extremo de la red al otro extremo y regresar.
	- El tiempo de detección de colisión es apenas 2 veces el tiempo de propagación por el canal:
	$$t_{\text{detección de colisión}}=2*t_p$$
- [I] **CSMA/CA (Collision Avoidance):** Utilizado en redes **Wi-Fi (802.11)**. Como en redes inalámbricas es difícil detectar colisiones mientras se transmite, el protocolo intenta **evitarlas** mediante el uso de confirmaciones (ACKs) y, opcionalmente, tramas de reserva como RTS/CTS.

|**Característica**|**CSMA/CD (Ethernet)**|**CSMA/CA (Wi-Fi)**|
|---|---|---|
|**Detección**|Detecta la colisión mientras ocurre.|Intenta evitar la colisión antes de que ocurra.|
|**Acción tras colisión**|Aborta inmediatamente.|No puede detectar, espera el ACK.|
|**Medio**|Cableado (Cobre/Fibra).|Inalámbrico (Radiofrecuencia).|
|**Confirmación**|No usa ACKs en la subcapa MAC.|Requiere ACKs explícitos.|

---
# Protocolos libres de colisiones
## Protocolo de Mapa de Bits (Bitmap)

- [I] **Bitmap:** Es un protocolo sin colisiones donde cada periodo de contención consta exactamente de N ranuras, siendo N el número total de estaciones.

>[!info] Funcionamiento:
> Si la estación 0 tiene una trama que enviar, transmite un bit **1** durante la ranura 0; de lo contrario, transmite un **0**.
> - Este proceso se repite para cada estación hasta completar las N ranuras.
> - Al finalizar las N ranuras, todas las estaciones saben quiénes desean transmitir y lo hacen en orden numérico.

- **Propiedades más importantes:**
    - **Ausencia de colisiones:** El orden de transmisión queda establecido de antemano durante el periodo de reserva.    
    - **Eficiencia:** Es muy eficiente con carga alta, ya que el gasto extra es de solo 1 bit por trama.    
    - **Sobrecarga:** Con carga baja, el retraso promedio es de N/2 ranuras antes de poder transmitir.
## Paso de Testigo (Token Ring)

- [I] **Token Ring:** Este protocolo utiliza una trama especial llamada **testigo (token)** que circula por la red para otorgar el permiso de transmisión.

>[!info] Funcionamiento:
>- El testigo se envía por el anillo definiendo un orden estricto de turno.
>- La estación que posee el testigo es la única autorizada para enviar una trama antes de pasar el turno a la siguiente estación.

- **Propiedades más importantes:**
    - **Determinismo:** Garantiza un tiempo máximo de espera antes de que una estación pueda transmitir, lo cual es ideal para tráfico en tiempo real.    
    - **Orden:** Evita el desperdicio de ancho de banda que producen las colisiones en protocolos como CSMA/CD.   
## 3. Cuenta Regresiva Binaria (Countdown)

- [I] **Binary Countdown:** Es una mejora sobre el protocolo de mapa de bits que reduce la sobrecarga de las ranuras de contención.

>[!info] Funcionamiento:
>- Las estaciones transmiten su **dirección (ID)** en bits binarios durante la ranura de contención.
>- Se aplica una operación **OR lógica** en el medio: si una estación intenta enviar un "0" pero ve un "1" en el canal (afirmado por una estación con ID más alta), se rinde y deja de transmitir sus bits restantes.
>- La estación con la dirección numérica más alta gana el derecho a transmitir.

- **Propiedades más importantes:**    
    - **Eficiencia de bits:** Solo requiere log2​N bits para el arbitraje en lugar de N bits.
    - **Prioridad implícita:** Las estaciones con números de dirección más altos siempre tienen prioridad sobre las de números inferiores.    
    - **Supuesto crítico:** Supone que los retardos de transmisión son despreciables para que todas las estaciones vean los bits casi instantáneamente.

> **Frase destacada en la bibliografía:** _"En el protocolo de cuenta atrás binaria, una estación con un número inferior puede quedarse sin enviar un paquete"_ debido a la prioridad que otorga el sistema a las direcciones más altas.
# Protocolos de contención limitada
Los protocolos de contención limitada buscan combinar las mejores propiedades de las estrategias de contención (buen rendimiento con carga baja) y los protocolos sin colisiones (buen rendimiento con carga alta).

>[!info] Funcionamiento
>Dividen a las estaciones en grupos y limitan la contención dentro de cada grupo para reducir la probabilidad de colisiones.
## Protocolo de recorrido de Arbol Adaptable

>[!info] Funcionamiento
>Las estaciones se ven como hojas de un árbol binario. En la primera ranura de contención, todas las estaciones intentan transmitir. Si hay una colisión, se busca de forma recursiva en el subárbol izquierdo y luego en el derecho hasta que se resuelva la contención.
>- **Propiedad importante:** Es adaptable; si la carga es baja, permite que todos compitan, pero si es alta, restringe la búsqueda a niveles más bajos del árbol para aislar a los emisores.

# Protocolos para LAN Inalámbricas
A diferencia de las redes cableadas (Ethernet), las inalámbricas no pueden usar CSMA/CD de manera efectiva porque las estaciones no pueden detectar colisiones mientras transmiten (debido a la gran diferencia de potencia entre la señal transmitida y la recibida).
## Problemas Fundamentales:
- **Nodo Oculto:** Una estación (A) transmite a otra (B), pero una tercera estación (C) no oye a A y transmite también a B, causando una colisión en B. 
- **Nodo Expuesto:** Una estación cree que no puede transmitir porque oye una comunicación cercana, aunque su destino esté fuera del alcance de esa interferencia.
## Protocolo MACAW / IEEE 802.11 (CSMA/CA):

>[!info] Funcionamiento (Intercambio RTS/CTS):
>1. El emisor envía una trama corta **RTS** (Request to Send) para reservar el canal.
>2. El receptor responde con un **CTS** (Clear to Send) si está libre.
>3. Al oír el CTS, las estaciones cercanas al receptor saben que deben guardar silencio para evitar colisiones.

- **Propiedades más importantes:**
    - **Evitación de Colisiones (CA):** En lugar de detectar colisiones una vez ocurren, intenta evitarlas mediante reservas.
    - **Confiabilidad:** Utiliza confirmaciones de recepción (**ACK**) a nivel de capa de enlace debido a que los canales inalámbricos son inestables.
    - **Ahorro de Energía:** Incluye técnicas para que los dispositivos duerman y ahorren batería.
---
# Enlaces relacionados
- Siguiente nota: [[Ethernet Conmutado]]