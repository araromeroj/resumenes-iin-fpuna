## ¿Por qué CSMA/CA y no CSMA/CD?

A diferencia de Ethernet (que usa CSMA/CD - Detección de Colisiones), en las redes inalámbricas **no es posible detectar colisiones mientras se transmite**. Esto se debe a:

- **El problema de la estación oculta:** Una estación puede no escuchar a otra debido a obstáculos o distancia, pero ambas pueden colisionar en el Punto de Acceso (AP).
- **Limitación de hardware:** Las señales de radio inalámbricas son tan fuertes al transmitir que el hardware no puede "escuchar" una señal entrante más débil (colisión) simultáneamente.

## Detección de Portadora (Carrier Sensing)

El protocolo utiliza dos tipos de detección para saber si el medio está ocupado:

1. **Detección Física:** El nivel físico verifica la energía de radio en el aire.
2. **Detección Virtual (NAV - Network Allocation Vector):** Tanenbaum explica que cada trama lleva un campo de "Duración" (mencionado en la Diapositiva 9). Otras estaciones leen este campo y ajustan su temporizador NAV, que les indica cuánto tiempo deben esperar antes de intentar transmitir, incluso si no detectan energía física.

## Espacios entre Tramas (IFS - Interframe Spacing)

Para dar prioridad a ciertos mensajes, 802.11 define diferentes tiempos de espera:

- **SIFS (Short IFS):** El tiempo más corto. Se usa para mensajes de alta prioridad como **ACK**, **CTS** o fragmentos de trama.
- **DIFS (Distributed IFS):** El tiempo estándar que cualquier estación debe esperar antes de intentar transmitir una trama de datos por primera vez.

## Ventana de Contienda y Backoff (Tiempo de espera aleatorio)

Si el canal está ocupado, la estación no transmite inmediatamente después de que se libera. En su lugar, elige un **tiempo de espera aleatorio** (backoff). Esto evita que múltiples estaciones que estaban esperando transmitan al mismo tiempo y colisionen justo después de que el canal se desocupa.

# Funcionamiento de CSMA/CA

El flujo de operación según los materiales es el siguiente:

1. **Escucha inicial:** La estación escucha el medio. Si está libre por un tiempo igual a **DIFS**, transmite.
2. **Detección de portadora:** Si el medio está ocupado (física o virtualmente por el NAV), la estación espera hasta que se libere.
3. **Algoritmo de Backoff:** Una vez libre el medio tras el DIFS, la estación elige un número aleatorio de "ranuras de tiempo" (slots) para esperar. Si otra estación transmite antes, ella pausa su contador y lo reanuda cuando el medio vuelve a estar libre.
4. **Transmisión y ACK:** Al terminar la transmisión, el receptor verifica la trama. Si es correcta, espera un tiempo **SIFS** y envía un **ACK** (Agradecimiento).
    - _Nota crítica:_ Si el emisor no recibe el ACK, asume que hubo una colisión y reintenta el proceso aumentando la ventana de backoff.

---

## El mecanismo RTS/CTS

La diapositiva destaca las **Tramas de Control** como herramientas clave para evitar colisiones:

- **RTS (Request to Send):** Una estación que quiere transmitir una trama grande envía primero un paquete corto RTS al AP. Este paquete incluye la duración de toda la transmisión planeada.
    
- **CTS (Clear to Send):** El AP responde con un CTS. Todas las estaciones en el rango del AP escuchan este CTS y actualizan su **NAV** (detección virtual), absteniéndose de transmitir.
    
- **Ventaja:** Este mecanismo resuelve el problema de la **estación oculta**, ya que el CTS "silencia" a todas las estaciones que podrían interferir con el AP, incluso si no ven a la estación emisora.
    
[[Tipos de tramas en WiF]]

---

### 5. Características Clave del Protocolo

- **Positive Acknowledgment (ACK):** En redes cableadas no se requiere ACK en la capa MAC; en WiFi es obligatorio para confirmar que la trama llegó íntegra.
    
- **Fragmentación:** Para mejorar la probabilidad de éxito en medios con mucho ruido, CSMA/CA permite dividir tramas grandes en fragmentos más pequeños, cada uno con su propio ACK.
    
- **Adaptación de Tasa (Rate Adaptation):** Mencionado al inicio de la Diapositiva 9. Si el protocolo detecta muchos errores (falta de ACKs), reduce automáticamente la velocidad de transmisión (modulación más robusta) para asegurar que los datos lleguen, aunque sea más lento.
    

### Resumen para estudio:

- **CSMA/CA** = Escuchar + Esperar DIFS + Backoff Aleatorio + ACK.
    
- **DIFS** > **SIFS** (esto da prioridad a los ACKs sobre los datos nuevos).
    
- **RTS/CTS** es opcional pero vital para eliminar el problema de la estación oculta.