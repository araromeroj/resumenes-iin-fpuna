Un **datagrama** es un paquete de datos que se utiliza en el contexto de un **servicio de red sin conexión**. Su nombre se deriva de una analogía con los telegramas, donde cada mensaje es una unidad independiente que contiene toda la información necesaria para su entrega.


>[!example] Ejemplos
>- **IP (Internet Protocol):** Es el ejemplo dominante de un servicio de red basado en datagramas, siendo el "pegamento" que mantiene unida a Internet.
>- **UDP (User Datagram Protocol):** Es el protocolo de la capa de transporte diseñado para permitir que las aplicaciones envíen datagramas IP encapsulados sin necesidad de establecer una conexión.

## Características Fundamentales

### Encaminamiento independiente

En una red de datagramas, cada paquete se inyecta en la red de forma individual y se enruta de manera **independiente de los demás**, incluso si pertenecen a la misma sesión de comunicación. Esto permite que, si un enrutador falla, los datagramas siguientes puedan encontrar rutas alternativas de forma dinámica.

### Direccionamiento completo

Debido a que se transportan de forma independiente, cada datagrama debe llevar la **dirección de destino completa** en su cabecera para que los enrutadores sepan hacia dónde reenviarlo.

### Sin configuración previa

A diferencia de las redes de circuitos virtuales, el uso de datagramas **no requiere una fase de configuración** o establecimiento de conexión antes de comenzar el envío de datos.

### Fiabilidad y orden

Generalmente, el servicio de datagramas se considera **poco fiable** (también llamado de "mejor esfuerzo"), ya que no garantiza que los paquetes lleguen en el mismo orden en que fueron enviados, ni ofrece acuses de recibo automáticos en la capa de red. Si se requiere fiabilidad, esta debe ser gestionada por las capas superiores (como la capa de transporte).

---

>[!summary] En resumen
>Un datagrama es la unidad básica de información en redes donde la flexibilidad y la falta de estado previo son prioritarias sobre la garantía de orden y entrega en la capa de red.
