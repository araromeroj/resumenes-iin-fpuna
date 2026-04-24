- [*] **Stop and wait:** parada y espera
- [*] **Go back N:** retroceso N
- [*] **Selective Repeat:** repetición selectiva
# 1. Parada y Espera (Stop-and-Wait)

- [I] **Stop and Wait:** Es el control de flujo y errores en la capa de enlace de datos, es un protocolo de ventana corrediza con **tamaño de ventana igual a 1** $(W=1)$. Utiliza el número de secuencia de 1 bit, alternando entre 0 y 1 para distinguir entre una trama nueva y una retransmisión.

>[!info] Funcionamiento de SAW
>El emisor transmite una única trama y luego debe detenerse y esperar una confirmación del receptor antes de poder enviar el siguiente elemento de datos.
> - **Ventana de emisión ($W$):** $1$
> - **Ventana de recepción:** $1$
> - **Números de secuencia:** Basta con **1 bit** (0 y 1).
> - **Mecanismo:** Si el temporizador expira antes del ACK, se retransmite.

### Proceso del emisor
1. Obtiene un paquete de la capa de red, construye una trama y la envía a través de la capa física.
2. Inicia un temporizador o RTO para recuperarse en caso de pérdida de la trama o de su ACK.
3. Queda bloqueado esperando un evento. Si recibe un ACK válido, detiene el timer, avanza el número de secuencia y busca el siguiente paquete.
4. Si el timer expira antes de recibir el ACK, el emisor retransmite la misma trama almacenada en su búffer.

### Proceso del receptor
1. Espera la llegada de una trama. Al recibirla, comprueba si el número de secuencia es el esperado.
2. Si es la correcta, entrega los datos a la capa de red y actualiza el número de secuencia que espera a continuación.
3. Envía una trama de ACK de vuelta al emisor para darle permiso de continuar.

## Características de SAW

Es sencillo de implementar. Se utiliza en enlaces donde el producto ancho de banda-retardo es muy pequeño, como en **WiFi (802.11)**, donde tener una ventana mayor no mejoraría el rendimiento y añadiría complejidad innecesaria.

# 2. Retroceso-N (Go-Back-N)

- [I] **Go back N:** Es una técnica de ventana corrediza diseñada para gestionar la transmisión de datos de forma eficiente a través de canales que pueden presentar errores, permitiendo que el emisor transmita múltiples tramas antes de recibir una confirmación. La ventana de envío $(W)$ es como máximo $(2^k-1)$
$$W>1, W_\text{max}=2^k-1$$
- [*] **MAX_SEQ - Maximum Sequence Number:** Número máximo de secuencia

> [!warning] Característica Principal
> El emisor puede enviar varias tramas, pero el receptor es "estricto": **solo acepta tramas en orden**. Si una falla, se descartan todas las siguientes.

> [!important] Tamaños de Ventana
> - **Ventana de emisión ($W$):** $> 1$
> - **Ventana de recepción:** Siempre es $1$.
> - **Límite Máximo:** Si $k$ es el número de bits de secuencia:
>   $$W_{max} = 2^k - 1$$

### En el emisor
El emisor mantiene una ventana de envío que contiene números de secuencia de tramas que tiene permitido transmitir sin esperar a un ACK.
Si el emisor alcanza un límite de su ventana y no recibe ACK de la trama más antigua, se bloquea.
Al expirar un timer para una trama específica, el emisor retrocede y vuelve a transmitir esa trama y todas las siguientes que ya habían sido enviadas pero no confirmadas.

> [!danger] El "Costo" del Error
> Si la trama $n$ falla, el emisor debe **retransmitir la trama $n$ y todas las posteriores** que ya había enviado, aunque estas hayan llegado bien originalmente.
### En el receptor
El receptor tiene una ventana de recepción de tamaño 1, lo que significa que solo acepta tramas que lleguen estrictamente en el orden correcto.
Si llega una trama con un error o fuera de secuencia, el receptor la descarta, así como a todas las tramas que le sigan, sin enviar confirmación por ellas.

> [!tip] ¿Por qué se usa?
>Es más eficiente que Parada y Espera en enlaces rápidos. Se prefiere cuando los errores son poco frecuentes, ya que evita la complejidad de almacenar tramas desordenadas en el receptor. El tamaño máximo de 2k−1 es crítico para evitar que el emisor confunda un ACK de una ventana vieja con uno de la ventana nueva si se pierden las confirmaciones

## 3. Repetición Selectiva (Selective Repeat)

> [!star] Característica Principal
> Es el más eficiente, pero mas complejo. El receptor tiene memoria (búfer) y **acepta tramas desordenadas**. Solo se retransmite exactamente lo que se perdió. Utiliza ACKs acumulativos y a menudo **NAKs** (acuse negativo) para acelerar la recuperación de errores

> [!example] Configuración Técnica
> - **Ventana de emisión ($W$):** $> 1$
> - **Ventana de recepción:** $> 1$
> - **Condición de ventana:** Para evitar ambigüedad entre tramas nuevas y viejas:
>   $$W \le \frac{MAX\_SEQ + 1}{2}$$ o tambien 
>  $$W_{max} = 2^{k - 1}$$
> 

 
> [!todo] ¿Por qué se usa?
> Se utiliza en enlaces con un gran **producto ancho de banda-retardo** (como enlaces satelitales o fibra transcontinental) y donde la tasa de error justifica la complejidad adicional de memoria en el receptor. La restricción del tamaño de ventana a la mitad del espacio de secuencia es indispensable para evitar el traslape de ventanas y la ambigüedad entre tramas nuevas y retransmisiones

# Cuadro Comparativo Rápido

| Protocolo            | Ventana Emisor | Ventana Receptor | Re-envío            | Complejidad |
| :------------------- | :------------: | :--------------: | :------------------ | :---------- |
| **Stop-and-Wait**    |       1        |        1         | Solo la actual      | Mínima      |
| **Go-Back-N**        |      $N$       |        1         | Todo desde el error | Media       |
| **Selective Repeat** |      $N$       |       $N$        | Solo la perdida     | Alta        |
## Protocolo PPP (Point-to-Point Protocol)
Introducción
> El **PPP (Point-to-Point Protocol)**, definido en el **RFC 1661**, es el protocolo estándar de Internet utilizado para transportar paquetes a través de **enlaces punto a punto**. Se utiliza habitualmente en conexiones de routers, módems de cable y enlaces de banda ancha como **ADSL**.

# 1. Componentes principales de PPP
PPP ofrece tres características fundamentales para garantizar la comunicación:
 1. **Método de entramado:** Un mecanismo para **delimitar inequívocamente** el inicio y el fin de cada trama, que además incluye **detección de errores**.
 
2. **LCP (Link Control Protocol):** Un protocolo de control de enlace diseñado para **activar las líneas, probarlas, negociar opciones y desactivarlas** cuando ya no se necesitan.

3. **NCP (Network Control Protocol):** Una familia de protocolos para negociar las opciones de la capa de red de forma independiente al protocolo utilizado (como **IPv4 o IPv6**). Existe un NCP diferente para cada capa de red soportada.
# 2. Formato de la trama PPP
La trama está orientada a bytes y su diseño se basa en el protocolo **HDLC**.

> [!success] Estructura de Campos
> - **Flag (Bandera):** Un solo byte (**0x7E** o 01111110) que indica el inicio y el fin de la trama.
> - **Address (Dirección):** Un byte con el valor fijo **11111111**, indicando que todas las estaciones deben aceptar la trama (evita asignar direcciones individuales).
> - **Control:** Un byte con el valor fijo **00000011**, que indica una trama no numerada (servicio sin conexión ni confirmación).
> - **Protocol (Protocolo):** Indica qué tipo de paquete viaja en la carga útil (p. ej., IP, IPv6, LCP o un NCP específico). Por defecto ocupa 2 bytes.
> - **Payload (Carga útil):** Datos de longitud variable.
> - **Checksum (Suma de comprobación):** Normalmente un **CRC de 2 o 4 bytes** para detectar errores de transmisión.
# 3. Mecanismo de Relleno de Bytes (Byte Stuffing)

> [!danger] ¡Importante: Evitar Confusión de Banderas!
> Para evitar que el byte de bandera (**0x7E**) aparezca accidentalmente dentro de los datos, PPP utiliza un **byte de escape (0x7D)**:
> 
> 1. Si el byte **0x7E** aparece en los datos, se inserta **0x7D** antes y se aplica una función **XOR con 0x20** al byte original (convirtiéndolo en **0x5E**).
> 2. Al recibir la trama, el receptor busca el byte de escape, lo elimina y aplica nuevamente XOR al siguiente byte para recuperar el dato original.

# 4. Diagrama de estados (Ciclo de vida del enlace)

> [!warning] Fases del Enlace
> 1. **DEAD:** El enlace físico no tiene conexión activa.
> 2. **ESTABLISH:** Los pares intercambian paquetes **LCP** para negociar opciones del enlace.
> 3. **AUTHENTICATE (Opcional):** Las partes verifican sus identidades.
> 4. **NETWORK:** Se utilizan los protocolos **NCP** para configurar la capa de red (como asignar IPs).
> 5. **OPEN:** Estado donde ocurre el **transporte de datos real** (paquetes IP encapsulados).
> 6. **TERMINATE:** Se cierra el enlace de forma lógica y vuelve al estado DEAD.

# 5. Aplicaciones prácticas

> [!example] Implementaciones Reales
> - **Packet over SONET:** PPP se utiliza sobre enlaces de fibra óptica SONET en redes troncales de ISPs para delimitar paquetes.
> - **ADSL:** En conexiones domésticas, se suele usar **PPPoA (PPP over ATM)**, donde la trama PPP se adapta para viajar sobre celdas ATM mediante la capa **AAL5**.
> - **DOCSIS:** En redes de televisión por cable, PPP también puede implementarse para el acceso a Internet.

