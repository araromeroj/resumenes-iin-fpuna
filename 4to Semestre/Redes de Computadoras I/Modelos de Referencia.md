
>[!note] Definición
>- Son abstracciones conceptuales clave en el diseño de redes que sirven para definir la funcionalidad de cada capa y las interacciones que ocurren entre ellas.
>- Es un marco de trabajo o estándar conceptual utilizado para *comprender y estandarizar cómo deben organizarse las redes de computadoras.*

## Modelo OSI
 El proceso de transmisión de datos que funciona como una pila, los datos van desde lo más alto (capa 7) hasta lo más bajo (Capa 1) en el emisor y van hacia el receptor desde lo más bajo (Capa 1) a lo más alto (Capa 7)

### Proceso de Transmisión de datos
#### Fase de envío (Emisor)
**I. Capa de Aplicación (Capa 7):** Aquí se genera el mensaje original
	Ejemplo: como cuando un usuario interactúa con un navegador web o un cliente de correo.
**II. Capa de Presentación (Capa 6):** Se encarga de que el mensaje sea legible para el receptor.
	Pone la *sintaxis*, *semántica* y *codificación* de los datos.
**III. Capa de Sesión (Capa 5):** Es como un administrador que establece, gestiona y finaliza la comunicación entre las dos máquinas.
**IV. Capa de Transporte (Capa 4):** El mensaje se divide en trozos más pequeños (***segmentos***). Se añaden números de secuencia para que el receptor pueda rearmar el mensaje y números de puerto para identificar la aplicación específica.
**V. Capa de Red (Capa 3):** Los ***segmentos*** se vuelven ***paquetes*** (o datagramas). Aquí se añaden las direcciones IP de origen y destino para decidir qué ruta debe seguir la información para llegar a a su destino a través de la red.
**VI. Capa de Enlace de Datos (Capa 2):** Los ***paquetes*** se introducen en ***tramas**.* Se añaden las direcciones físicas (MAC ADDRESS) y una suma de comprobación (*checksum*) al final de la trama para detectar si los bits se dañan durante el trayecto.
**VII. Capa Física (Capa 1):** Es el nivel del hardware; aquí la trama se convierte en un flujo de bits brutos (0s y 1s) que se envían como señales eléctricas, pulsos de luz u ondas de radio a través del cables o del aire.

#### Fase de recepción (Destinatario)
- El proceso se invierte: La capa física de la otra máquina recibe las señales y las vuelve a convertir en bits.
- Cada capa superior elimina la cabecera que le corresponde, verifica que no haya errores y entrega el contenido limpio a la capa que tiene arriba.
- Finalmente, la capa de transporte vuelve a unir los segmentos en el orden correcto y la capa de aplicación le entrega el mensaje original al usuario receptor.

## Modelo TCP/IP

- [<] Modelo TCP/IP CONCEPTO
## Modelo Híbrido

- [<] Modelo Híbrido CONCEPTO