A diferencia de los **hubs** (capa 1), que actúan como repetidores y mantienen un solo dominio de colisión para todos sus puertos, los **switches** (capa 2) crean dominios de colisión independientes por cada puerto.
	Los switches leen los encabezados de las tramas Ethernet. Conociendo las direcciones de origen y destino genera una **trama de conmutación**.

[[Diferencias entre HUB y SWITCH]]
### Modos de Trabajo del Switch:

1. **Cut-through:** El switch lee solo la dirección MAC de destino y empieza a retransmitir la trama de inmediato, sin esperar a recibirla completa. Es el más rápido pero no detecta errores de CRC.    
2. **Free of segments (Fragment-free):** El switch espera a recibir los primeros **64 bytes** (tamaño mínimo) para asegurarse de que no sea un fragmento de colisión antes de retransmitir.
3. **Store and forward:** El switch recibe toda la trama, la almacena, verifica el CRC (control de errores) y luego la transmite en el puerto de destino. Es el método más seguro pero introduce mayor retardo.

### Algoritmos en Ethernet Conmutado
#### DE RETRANSMISIÓN
![[Pasted image 20260429103310.png]]

#### DE APRENDIZAJE
![[Pasted image 20260429103359.png]]



---