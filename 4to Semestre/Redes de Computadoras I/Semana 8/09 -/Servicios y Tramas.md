## Servicios
![[Pasted image 20260506160058.png]]

## Tramas IEEE 802.11

En las redes inalámbricas estandarizadas por el **IEEE** (**Institute of Electrical and Electronics Engineers** - Instituto de Ingenieros Eléctricos y Electrónicos) **802.11**, existen tres categorías principales de tramas que permiten la comunicación, el control y la gestión del medio: **Administración**, **Control** y **Datos**.
### 1. Tramas de Datos

Son las encargadas de transportar la carga útil (el paquete de red) entre las estaciones. Tienen la estructura más compleja para poder manejar la movilidad y el paso a través de sistemas cableados.

#### Estructura y Campos:

![[Pasted image 20260510143521.png]]

- **Control de Trama (2 bytes):** Contiene los subcampos que definen el comportamiento de la trama (ver detalle abajo).
- **Duración (2 bytes):** Indica el tiempo en microsegundos que la trama y su respectivo **ACK** (**Acknowledgment** - Acuse de Recibo) ocuparán el canal. Se usa para actualizar el **NAV** (**Network Allocation Vector** - Vector de Asignación de Red) de otras estaciones.
- **Direcciones (Dirección 1 a 4, 6 bytes cada una):** Las tramas Wi-Fi pueden usar hasta 4 direcciones **MAC** (**Medium Access Control** - Control de Acceso al Medio) para identificar el origen y destino final, además de los **AP** (**Access Point** - Puntos de Acceso) intermedios.
- **Secuencia (2 bytes):** Consta de 12 bits para el número de secuencia (detectar duplicados) y 4 bits para el número de fragmento.
- **Datos (0 a 2312 bytes):** Contiene el paquete de capas superiores. Comienza con una cabecera **LLC** (**Logical Link Control** - Control de Enlace Lógico) que identifica el protocolo transportado.
- **Secuencia de Verificación (**Check Sequence**, 4 bytes):** Un código **CRC** (**Cyclic Redundancy Check** - Verificación de Redundancia Cíclica) de 32 bits para detectar errores de transmisión.

#### Subcampos del Control de Trama:

1. **Versión (2 bits):** Actualmente fijada en `00`.
2. **Tipo (2 bits):** Gestión (`00`), Control (`01`) o Datos (`10`).
3. **Subtipo (4 bits):** Define la función específica (ej. trama de datos regular o **QoS** - **Quality of Service** - Calidad de Servicio).
4. **To DS (Hacia el Sistema de Distribución):** Indica si la trama se dirige hacia la red cableada.
5. **From DS (Desde el Sistema de Distribución):** Indica si la trama proviene de la red cableada.
6. **Más fragmentos:** Indica que la trama actual es parte de una ráfaga y hay más fragmentos por venir.
7. **Retry (Reintento):** Indica que la trama es una retransmisión de una que no fue confirmada.
8. **Gestión de Energía:** Avisa al **AP** que la estación entrará en modo reposo (**PSM** - **Power Save Mode** - Modo de Ahorro de Energía).
9. **Más datos:** El emisor indica que tiene más tramas pendientes para el receptor.
10. **Protegido:** Indica que el cuerpo de la trama está cifrado.
11. **Order (Orden):** Indica que las tramas deben entregarse estrictamente en el orden recibido.

---

### 2. Tramas de Administración

Su función es establecer y mantener la conectividad en la red inalámbrica. No transportan datos de usuario, sino información del sistema.

- **Funcionamiento:** Se utilizan para gestionar la relación entre las estaciones y los puntos de acceso.
- **Ejemplos comunes:**
    - **Beacon (Baliza):** Emitida periódicamente (típicamente cada 100 ms) por el **AP** para anunciar la presencia de la red, su **SSID** (**Service Set Identifier** - Identificador de Conjunto de Servicio) y parámetros de seguridad.
    - **Asociación/Reasociación:** Permiten a una estación unirse a un **AP** o cambiar de uno a otro mientras se desplaza.
    - **Autenticación:** Proceso para validar la identidad de la estación antes de permitir la asociación.
    - **Sondeo:** Usado en el modo **PCF** (**Point Coordination Function** - Función de Coordinación de Punto) para dar turnos de transmisión.

---

### 3. Tramas de Control

Son tramas cortas que ayudan en la entrega de las tramas de datos y administración, gestionando el acceso al medio y la confirmación de recepción.

- **Funcionamiento:** No tienen cuerpo de datos; su información clave reside en el campo de **Subtipo** de la cabecera.
- **Ejemplos clave:**
    - **ACK (Acknowledgment - Acuse de Recibo):** Trama obligatoria enviada por el receptor para confirmar que recibió los datos sin errores.
    - **RTS (Request to Send - Solicitud de Envío):** Trama opcional para reservar el canal y evitar colisiones por estaciones ocultas.
    - **CTS (Clear to Send - Listo para Enviar):** Respuesta al **RTS** que otorga permiso para transmitir.
    - **PS-Poll (Power Save-Poll - Sondeo de Ahorro de Energía):** Enviada por una estación que despierta del modo reposo para pedirle al **AP** que le entregue sus tramas almacenadas.
    - **CF-end (Contention-Free end - Fin de Periodo Libre de Contención):** Anuncia el fin del periodo de acceso controlado en redes que usan **PCF**.