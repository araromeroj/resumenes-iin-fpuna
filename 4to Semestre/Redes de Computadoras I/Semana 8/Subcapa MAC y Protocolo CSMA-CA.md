- **Subcapa MAC (Medium Access Control):** Una característica clave de la arquitectura 802.11 es que esta subcapa es **común** a todas las diferentes implementaciones de la capa física. Se encarga de gestionar el acceso al medio compartido y la formación de tramas.

La subcapa **MAC** (**Medium Access Control** - Control de Acceso al Medio) en el estándar **IEEE** (**Institute of Electrical and Electronics Engineers** - Instituto de Ingenieros Eléctricos y Electrónicos) **802.11**, conocido comúnmente como **WiFi** (**Wireless Fidelity** - Fidelidad Inalámbrica), es la encargada de decidir qué dispositivo tiene el turno para transmitir en el canal compartido.

![[Pasted image 20260504154244.png]]

![[Pasted image 20260506173859.png]]

## CSMA/CA
A diferencia de **Ethernet**, donde se puede detectar colisiones (**CSMA/CD** - **Carrier Sense Multiple Access with Collision Detection**), en las redes inalámbricas las radios son semidúplex y la señal transmitida es mucho más fuerte que cualquier señal recibida, lo que impide detectar colisiones mientras se envía información. Por ello, se utiliza **CSMA/CA** (**Carrier Sense Multiple Access with Collision Avoidance** - Acceso Múltiple con Detección de Portadora y Evitación de Colisiones).

- [*] **CSMA/CA - Carrier Sense Multiple Access Collision Avoidance:** Acceso Múltiple con Detección de Portadora y Evitación de Colisiones.
Modos de Operación:

- **DCF** (**Distributed Coordination Function** - Función de Coordinación Distribuida): Es el modo estándar basado en la competencia, donde cada estación decide cuándo transmitir de forma independiente.
	- Usa Binary Exponential Backoff con IFS (espaciado entre tramas)
	- Se pierde la detección de colisiones
	- Tiene trama ACK explícita
	- [[Subcapa MAC y Protocolo CSMA-CA#Detección de Canal (Carrier Sensing)|Detección del canal]]
		- Física: escuchando el canal
		- Virtual: con los NAV (Network Allocation Vector) y opcionalmente con Iso RTS y CTS
	- Usa tramas RTS/CTS para evitar estaciones escondidas o expuestas
- **PCF** (**Point Coordination Function** - Función de Coordinación de Punto): Es un modo opcional y centralizado donde el **AP** sondea a las estaciones para darles permiso de transmitir (polling). No forma parte del estándar de interoperabilidad WiFi Alliance.

## Detección de Canal (Carrier Sensing)

Para evitar colisiones, la subcapa **MAC** (**Medium Access Control** - Control de Acceso al Medio) realiza dos tipos de detección:

- **Física:** La estación escucha el medio para detectar señales eléctricas.
- **Virtual:** Se utiliza un temporizador interno llamado **NAV** (**Network Allocation Vector** - Vector de Asignación de Red). Cada trama lleva un campo de "duración" que indica cuánto tiempo estará ocupado el canal; las estaciones que escuchan esto actualizan su **NAV** (**Network Allocation Vector** - Vector de Asignación de Red) y permanecen en silencio.

- [*] **RTS - Request To Send:** Solicitud de envío
- [*] **CTS - Clear to Send:** Listo para enviar


![[Pasted image 20260506194604.png]]
## Intervalos y Tiempos de Espera (IFS - InterFrame Spacing)

- [*] **IFS - InterFrame Spacing:** Epaciado entre tramas

- **SIFS (Short IFS):** El más corto, usado para respuestas inmediatas como **ACK**, **CTS** o fragmentos de datos. $$10\mu s$$
- **PIFS (DCF IFS):** Es el espaciado entre tramas dentro de la función de DCF. Tiempo que debe esperar una estación antes de intentar transmitir una trama de datos regular.$$30\mu s$$
- **DIFS (Extended IFS):** Usado por estaciones que recibieron una trama corrupta para evitar interferir con diálogos en curso.$$50 \mu s$$

## Intervalos de Backoff

- **Backoff Exponencial Binario:** Si el canal está ocupado, la estación elige un tiempo de espera aleatorio que se duplica tras cada intento fallido para reducir nuevas colisiones.
