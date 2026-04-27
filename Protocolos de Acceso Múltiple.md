# Protocolo ALOHA
Ideado en la Universidad de Hawái en los años 70, es el protocolo básico para sistemas de contención.
### 1. Elementos de Infraestructura y Actores

- **Canal Compartido (Medio Transmisión):** Un único canal de radio o cable por el cual todas las estaciones transmiten. Es un medio de difusión (_broadcast_).
    
- **Estaciones (Nodos):** Dispositivos independientes que generan tráfico de datos de manera impredecible (tráfico a ráfagas).
    
- **Unidad Central (Opcional):** En el ALOHA original, las estaciones enviaban datos a una computadora central (como en la Universidad de Hawaii). Si la central recibía la trama correctamente, enviaba un ACK.

### 2. Elementos de Protocolo (Lógica de Funcionamiento)

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
## Protocolo ALOHA Puro

- [I] **Aloha Puro:** protocolo pionero donde las estaciones transmiten cuando tienen datos; si hay colisión, esperan un tiempo aleatorio y reintentan.

>[!info] Funcionamiento
> Tras enviar una trama, el emisor escucha si hubo colisión (en el sistema original, esperaba una retransmisión del ordenador central). Si la trama se destruye por una colisión, el emisor espera un tiempo aleatorio antes de volver a intentarlo. Este tiempo debe ser aleatorio para evitar que las mismas tramas choquen una y otra vez indefinidamente.

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
