#redes #tiposderedes #1Parcial 
## Acceso
### Acceso de banda ancha
Servicios de **alta velocidad** para hogares (típicamente 1 Gbps) que utilizan fibra óptica (FTTH), cable coaxial (redes de televisión por cable) o DSL, para acceso a Internet.

- [I] **Banda ancha:** conexión a internet de alta velocidad ($1 \text{ Gbps}$) y capacidad que permite la transmisión simultánea de múltiples datos.

### Acceso de uso doméstico
- Acceso a música, foros y videos.
- Acceso a información y compra venta de productos.

>[!important] Ley de Metcalfe
>Dice que el valor de la Internet es proporcional al cuadrado de la cantidad de usuarios.
>$$\text{Valor}_\text{Internet} = X * \text{Usuarios}^2$$

## Acceso móviles e inalámbricas (wireless)
Permiten la conectividad para dispositivos en movimiento, como portátiles y smartphones.
- **Inalámbricas:** WiFi (IEEE 802.11). Alcance limitado, típicamente dentro de un edificio. Las velocidades varían entre 11Mbps (802.11b) hasta 7 Gbps (802.11ad).
- **Redes de Celulares:** Divididas en celdas geográficas, cada una con su estación base. Su alcance es mayor, medido en kilómetros. La tecnología 4G LTE ofrece unos 100 Mbps, mientras que la 5G promete velocidades de hasta 10 Gbps.

Ejemplos:
- [I] **RFID:** tecnología inalámbrica que utiliza ondas de radio para identificar y rastrear automáticamente etiquetas adheridas a objetos, personas o animales.
- [I] **NFC:** permite al dispositivo móvil actuar como una tarjeta inteligente RFID e interactuar con un reader cercano para el pago.
- [I] **Redes de sensores:** usan nodos reuniendo información acerca de parámetros físicos. Pueden estar embebidos en dispositivos familiares como casas o teléfonos. Como por ejemplo un *parquímetro*.

| Aplicaciones típicas                                | Móviles | Inalámbricas |
| --------------------------------------------------- | ------- | ------------ |
| Ordenadores de sobremesa en oficinas                | No      | No           |
| Ordenador portátil usado en habitación              | Si      | No           |
| Redes en edificios sin cableado                     | No      | Si           |
| Almacenar el inventario con una computadora de mano | Si      | Si           |
- [*] **AP - Access Point:** punto de acceso, router inalámbrico o estación base.
- [*] **RFID - Radio Frequency Identification:** identificación por radiofrecuencias.
- [*] **GPS - Global Positioning System:** sistema de posicionamiento global.
- [*] **NFC - Near Field Communication:** comunicación de campo cercano.

## Proveedoras de contenido
Redes para el manejo de aplicaciones y datos masivos.
- [*] **CDN - Content delivery networks:** redes de entrega de contenidos
- [I] **CDN:** un conjunto grande de servidores geográficamente distribuidas para que el contenido esté cerca de los usuarios.

>[!info] Funcionamiento
>Cuando un usuario solicita un contenido, la CDN debe decidir qué réplica debe servirle. Este proceso debe tener en cuenta la distancia entre cada réplica y el cliente, la carga de cada servidor de la CDN y la carga y congestión del tráfico en la propia red.

- [I] **Redes de Datacenters:** concentran cientos de miles o millones de servidores en ubicaciones únicas (la nube) para mover cantidades masivas de datos.
## De tránsito o troncales (backbones)
Redes que conectan redes de acceso a datacenters. Ocurre cuando una ISP y una CDN no están conectados directamente. Las redes de tránsito se usan para transportar el tráfico entre ellos (entre CDN y el ISP).

- [I] **Datacenters:** es un a instalación física que concentra una gran cantidad de servidores interconectados y sistemas de almacenamiento de datos para procesar y distribuir información a escala masiva.
- [*] **ISP - Internet service provider:** proveedor de servicios de Internet.

## Corporativas
Redes usadas en campus, edificios de oficina y otras organizaciones.
Utilizadas en campus, edificios de oficinas u organizaciones para facilitar el trabajo interno.
- [I] **Servidores:** sistema de información que consiste en una o varias bases de datos con información y ciertos usuarios necesitan acceder a ella.
- [I] **Clientes:** son los ordenadores correspondientes a cada empleado de una empresa con los que acceden a los datos remotos.

- **Uso:** Compartición de recursos (datos, impresoras) y comunicación interna (correo, VoIP, escritorio compartido).

- [I] **VPN (Redes Privadas Virtuales):** Conectan oficinas remotas a través de Internet para que funcionen como una sola red lógica, eliminando la "tiranía de la geografía".
- [*] **VPN - Virtual private networks:** Redes privadas virtuales.

- [I] **VoIP:** convierte las señales de voz analógicas en paquetes de datos digitales que se transmiten por internet.
- [*] **VoIP - Voice over Internet Protocol:** Voz sobre Protocolo Internet

---
# Enlaces relacionados
- Siguiente nota: [[Clasificación según alcance geográfico]]
- [[1. Redes - Introducción]]