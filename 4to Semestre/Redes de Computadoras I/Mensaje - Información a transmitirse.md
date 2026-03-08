En una red de computadoras, cuando la información se prepara para su transmisión, se organiza en unidades de datos (como las **tramas** en la capa de enlace) que se dividen en tres partes fundamentales: **encabezado**, **carga útil** y **tráiler**.

![[R1.Mensaje.png]]


## Encabezado (Header o Cabecera)

Contiene la **información de control** necesaria para que el mensaje llegue a su destino y sea procesado correctamente por las entidades pares. La información que suele incluir es:

- **Direccionamiento:** Las direcciones físicas o lógicas de **origen y destino** para identificar quién envía el mensaje y quién debe recibirlo.
- **Números de secuencia:** Se utilizan para numerar los mensajes, permitiendo al receptor distinguir entre tramas nuevas y duplicados, y reordenarlos si llegan fuera de secuencia.
- **Acuses de recibo (ACK):** En protocolos bidireccionales, se usa para confirmar qué mensajes se han recibido con éxito.
- **Tipo de protocolo o campo "Kind":** Indica qué tipo de datos contiene el mensaje o a qué proceso de la capa superior debe entregarse (por ejemplo, si los datos son un paquete IPv4).

## Carga útil (Payload)

Es la parte que contiene el **mensaje original** o los datos reales que se desean transmitir.

- Desde el punto de vista de una capa específica, la carga útil es **"información pura"**.
- En la arquitectura de capas, la carga útil de una trama suele ser el **paquete completo** proveniente de la capa de red superior.

## Tráiler (Trailer o Remolque)

Se añade al final del mensaje y su propósito principal es garantizar la integridad de los datos mediante la **detección de errores**.

- **Suma de comprobación (Checksum) o CRC:** Contiene un código (como el CRC de 32 bits en Ethernet) calculado a partir de los bits del mensaje. El receptor recalcula este valor; si no coincide con el del tráiler, sabe que la información se dañó durante la transmisión.
- **Ubicación estratégica:** Los protocolos suelen colocar estos códigos en el tráiler en lugar del encabezado porque permite al hardware calcular el valor **mientras los bits salen** por la interfaz de red, lo que resulta más eficiente.
- **Información adicional:** En algunos casos específicos (como el protocolo AAL5), el tráiler también puede incluir la **longitud** de la carga útil para asegurar que el mensaje se reconstruya correctamente.