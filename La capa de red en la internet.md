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
y en total hay $2^{32-n} - 2$ redes posibles $2^{10} - 2=1022$
Se le resta 2 para indicar las direcciones reservadas para la red y la dirección de broadcast.
100.5.121.8/22 = 100.5.0111 10|01. 0000 1000
para la dirección de red: 100.5.0111 10|00. 0000 0000 = 100.5.120.0/22
para la dirección de broadcast: 100.5.0111 10|11. 1111 1111 = 100.5.123.255/22
