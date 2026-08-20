El encabezado IPv4
![[Pasted image 20260820145203.png]]

- IP Header length (4 bits): en palabras de 32 bits (mín 5 y máx 15)
- Servicios diferenciados (8 bits):
	- Los 6 primeros bits definen la clase de servicio
	- Los 2 bits restantes indican la congestión
- Total length (hasta 65535 bytes)
- Identification: es el número único
- DF: indica NO fragmentación, para descubrir el MTU de un camino.
- MF: indica que vienen más fragmentos.
- Fragment offset: Indica dónde se ubica el fragmento en el paquete (en múltiplos de 8 bytes)
- TTL (time to live): se decrementa el 1 en cada salto, se desecha cuando llega a 1.
- Protocol: es el protocolo encapsulado (TCP, UDP, ICMP, etc).
- Header checksum: solo del encabezado. Se recalcula en cada salto.
- Direcciones de origen y destino.
- Opciones: todos empiezan con un código de 1 byte (tipo de origen)

TIPOS DE OPCIONES
OJO se puede usar pocas opciones a la vez por la cantidad de palabras posibles
- Security: Para evitar rutear el paquete por algunos países.
- Strict source routing: Camino completo a seguir como secuencias de direcciones IP (para usar en casos de emergencia o para pruebas).
- Loose source routing: Lista de routers a atravesar en la ruta (puede haber otros) - solo se dan algunos para obligar un enrutamiento específico.
- Record route: cada router indica su dirección IP.
- Timestamp: su dirección y tiempo.
- [ ] BUSCAR MEJOR EXPLICACIÓN DE ESTAS OPCIONES DEL ENCABEZADO IPv4

PREFIJOS Y MÁSCARAS
teniendo la siguiente dirección: 100.5.120.8/22
el prefijo es n=22, la cantidad de hosts está dada por (32 - n)
Indica que se puede tener 10 hosts
y en total hay $2^{32-n} - 2$ hosts posibles $2^{10} - 2=1022$
Se le resta 2 para indicar las direcciones reservadas para la red y la dirección de broadcast.
100.5.121.8/22 = 100.5.0111 10|01. 0000 1000
para la dirección de red: 100.5.0111 10|00. 0000 0000 = 100.5.120.0/22
para la dirección de broadcast: 100.5.0111 10|11. 1111 1111 = 100.5.123.255/22


Si un router no encuentra en su tabla de enrutamiento la red de destino de un paquete recibido, lo que hace es enviarlo a su Default Gateway o Puerta de Enlace Predeterminada, se le da la dirección 0.0.0.0 0.0.0.0 o bien 0.0.0.0/0

- [*] **CIDR - Classless interdomain routing**: Agregación de rutas.
- [I] **CIDR:** sirve para juntar múltiples prefijos IP en una sola más grande para reducir el tamaño de tablas de enrutamiento, se eliminaron las clases para agrupar redes o subredes, por eso se llama "classless".
- [I] Direccionamiento por clases - Classful addressing: Antes del CIDR se tenía distintas clases para identificar el tipo de dirección.
	- Clase A: Empieza por 0.
	- Clase B: Empieza por 10.
	- Clase C: Empieza por 110.
	- Clase D: Empieza por 1110.
	- Clase E: Empieza por 1111. Para multicast
	- La clase D y E no eran usadas para el curso normal de datos, en los routers no existían esas clases.

### Direcciones Privadas en Internet
Son direcciones que no están asignadas en la Internet, pueden ser usadas por subredes que usan NAT para conectarse a internet o por los hosts que no se conectan a Internet.

| Clase | Rango                                                                       |
| ----- | --------------------------------------------------------------------------- |
| A     | 10.0.0.0 a 10.255.255.255 (todos los que empiezan con 10)                   |
| B     | 172.16.0.0 a 172.31.255.255 (todos los que inician con 172.16 hasta 172.31) |
| C     | 192.168.0.0 a 192.168.255.255 (todos los que inician con 192.168)           |

- [*] NAT - Network Address Translation: Traducción de 
- [I] NAT -  Cambia direcciones IP y en algunos casos cambia los números de puerto de la capa de transporte.

- [I] NAT estática: En la nat estática, se le asigna ya una IP pública al cliente para que se pueda acceder a la red, aquella asignada ya no se puede cambiar.
- [I] NAT dinámica: En la nat dinámica se tiene una lista de direcciones IP públicas y se van asignando las direcciones a medida que los clientes van solicitando el acceso a la internet. Una vez que el host ya no necesita usar esa IP, entonces la dirección queda libre como para que otro host pueda usarlo en caso de que lo necesite.
En ambos casos, no se tocan los números de puerto TCP y UDP, se hace la traducción de la IP de origen y de destino. Se mantiene una tabla en la que se indica las relaciones entre las IP

- [I] NAT con sobrecarga o PAT: En la PAT o NAT con sobrecarga, se tocan los números de puerto. A cada proceso (de la capa de aplicación que escuchan en un número de puerto) se le asigna un número de puerto. Cada segmento ya viene con su número de puerto de origen y destino. Entonces, el pat traduce el número de puerto asignándole otro número de puerto de origen (el de destino no se toca porque está relacionado con el servidor al que se quiere conectar). ¿Por qué es importante?
OJO: En la capa 2 existen las direcciones físicas (MAC ADRES) y en la capa de red se tienen direcciones lógicas que indican las direcciones de origen y destino para cada dispositivo y en la capa de transporte están los números de puerto.