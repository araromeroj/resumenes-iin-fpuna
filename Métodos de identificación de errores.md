El diseño debe facilitar al receptor la localización del inicio de nuevas tramas utilizando **poco ancho de banda** del canal. Los métodos son:
## Conteo de caracteres o Bytes
Se usa un campo al inicio de la trama indicando el número de bytes de la misma.

>[!warning] Desventajas
>- Puede **perderse el sincronismo** por culpa de un error causando distorsión.
>	Si la cuenta de bytes es 5 en la segunda trama, se convierte en 7 debido a un solo bit.
>- [i] Rara vez se utiliza por sí solo por esta razón

![[Pasted image 20260327160201.png|400]]
## Marcar Bytes con relleno de Bytes
Resuelve el problema de desincronización tras un error de transmisión haciendo que cada trama comience y termine con bytes especiales (banderas -> FLAG). 

> [!important] La bandera se adiciona **al inicio y al final** de la trama
![[Pasted image 20260327160815.png]]

- [I] **Byte stuffing:** consiste en agregar un byte de escape especial (ESC) cuando cualquiera de los bytes banderas aparezcan coincidentemente como secuencia dentro de la trama. La capa de enlace de datos en el extremo receptor elimina los bytes ESC antes de entregar los datos a la capa de red.
	Si el byte ESC también se encuentra dentro de la secuencia de bytes de la trama, se añade otro byte ESC o FLAG identificador.

## Bits de bandera con relleno de bits

## Violaciones de codificación de la capa física