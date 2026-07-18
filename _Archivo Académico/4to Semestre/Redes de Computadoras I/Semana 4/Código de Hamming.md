Los bits de la palabra clave se enumeran secuencialmente, empezando desde el 1 hasta el final de la longitud de palabra.
>[!Important] Los bits de posición potencia de 2 (1, 2, 4, 8, 16, ...) son los de **control**

Si la palabra con longitud **m** es $00010011001$ se obtiene lo siguiente:
![[CDH siendo emisor.png]]
Si se recibe con error (en este caso el 6)
![[CDH siendo receptor.png]]

## CDH en errores de ráfaga

>[!note] Cosas importantes
>La longitud de una ráfaga define la cantidad de bloques en que se dividirá el mensaje
>$$(1+m+r)\leq{2^r}$$
>**Pasos a seguir:**
>1. Dividir el mensaje en bloques
>2. Determinar la cantidad de bits de redundancia por bloque
>3. Aplicar el código de Hamming para cada bloque
>4. Transmitir los datos en columnas


---
# Enlaces relacionados
- [[2. Capa de Enlace de Datos]]