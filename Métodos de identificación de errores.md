El diseño debe facilitar al receptor la localización del inicio de nuevas tramas utilizando **poco ancho de banda** del canal. Los métodos son:
## Conteo de caracteres o Bytes
Se usa un campo al inicio de la trama indicando el número de bytes de la misma.

>[!warning] Desventajas
>- Puede **perderse el sincronismo** por culpa de un error causando distorsión.
>	Si la cuenta de bytes es 5 en la segunda trama, se convierte en 7 debido a un solo bit.
>- [i] Rara vez se utiliza por sí solo por esta razón

![[Pasted image 20260327160201.png|400]]
## Marcar Bytes con relleno de Bytes
## Bits de bandera con relleno de bits
## Violaciones de codificación de la capa física