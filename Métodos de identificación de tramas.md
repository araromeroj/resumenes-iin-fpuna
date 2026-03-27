El diseño debe facilitar al receptor la localización del inicio de nuevas tramas utilizando **poco ancho de banda** del canal. Los métodos son:
## Conteo de caracteres o Bytes
Se usa un campo al inicio de la trama indicando el número de bytes de la misma.

>[!warning] Desventajas
>- Puede **perderse el sincronismo** por culpa de un error causando distorsión.
>	Si la cuenta de bytes es 5 en la segunda trama, se convierte en 7 debido a un solo bit.
>- [i] Rara vez se utiliza por sí solo por esta razón

![[Pasted image 20260327160201.png|400]]
## Marcar Bytes con relleno de Bytes - byte stuffing
Resuelve el problema de desincronización tras un error de transmisión haciendo que cada trama comience y termine con bytes especiales (banderas -> FLAG). 

> [!important] La bandera se adiciona **al inicio y al final** de la trama
![[Pasted image 20260327160815.png]]

Desventaja: está ligado al uso de bytes (8 bits) si o si.

- [I] **Byte stuffing:** consiste en agregar un byte de escape especial (ESC) cuando cualquiera de los bytes banderas aparezcan coincidentemente como secuencia dentro de la trama. La capa de enlace de datos en el extremo receptor elimina los bytes ESC antes de entregar los datos a la capa de red.
	Si el byte ESC también se encuentra dentro de la secuencia de bytes de la trama, se añade otro byte ESC o FLAG identificador.

## Bits de bandera con relleno de bits - bit stuffing
Las tramas pueden contener un número arbitrario de bits formados por unidades de **cualquier tamaño**. El relleno no permite que se interpongan los bits de relleno con los bits de los datos.

- [I] **Bit stuffing:** es la técnica que permite que los datos del usuario contengan cualquier combinación de "1" y "0" sin que el receptor los confunda con las señales de control que marcan el inicio o el fin de una trama. Cada trama comienza y termina con un patrón especial de bits

Se desarrolló para el protocolo HDLC (High Level Data Link Control).
Cada trama comienza y termina con un patrón de bits igual a $01111110_2$ (es el estándar más común) que es lo mismo que $0x7E_{16}$. Este patrón es una bandera, por lo que si en la Capa de Enlace de Datos del emisor se encuentran 5 bits "1", se introduce automáticamente un bit "0" en los bits salientes.

>[!info] Funcionamiento
>- Emisor: Agrega un 0 luego de 5 bits "1" seguidos (*stuffing*)
>	- Datos originales: 01111110
>	- Datos con relleno: 011111**0**10
>- Receptor: (*destuffing*)
>	- si ve **5** bits "1" seguidos de un "0", lo elimina porque sabe que **es el relleno**.
>	- si ve **6** bits "1" seguidos de un "0", sabe que es el FLAG de **fin de trama**.
>	- si ve **7** bits "1" se considera **error de transmisión**.
## Violaciones de codificación de la capa física
Se usa un atajo de la capa física, violaciones de codificación que serían **caracteres no válidos** para delimitar las tramas.
Al tenerse señales reservadas
- Es fácil encontrar el inicio y fin de cada trama.
- Sin necesidad de rellenar mucho los datos (no hay problemas de longitud).
- [I] **Preámbulo:** es un patrón bien definido que se encuentra al inicio de cada trama, muy utilizado en Wi-Fi (802.11) y Ethernet (802.3). Puede ser bastante largo (72 bits para 802.11). Va seguido de un campo de conteo en la cabecera que se utiliza para localizar el final de la trama. (se mezclan los métodos)
