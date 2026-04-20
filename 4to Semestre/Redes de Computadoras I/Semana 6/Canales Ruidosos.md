- [*] **ARQ - Automatic Repeat reQuest:** 
- [*] **ACK - Acknowledgement:** reconocimiento o acuse de recibo

- [I] **Ventanas corredizas:** son grupos de números de secuencia

![[Pasted image 20260420163822.png|400]]

El **emisor** mantiene unas ventanas de emisión que tiene permitido enviar. Los mantiene en buffers por posibles retransmisiones. Es de tamaño variable.
El **receptor** mantiene una ventana de recepción con números de tramas que puede recibir. Necesita espacio en buffers para las llegadas de tramas. Es de tamaño fijo.

! Las ventanas de emisión y recepción no necesariamente son del mismo tamaño.

>[!important] No olvidar:
>$$\text{t}_\text{total}=\text{t}_\text{transmisión}+\text{t}_\text{propagación}$$
>$t$: tiempo

En el método de las tramas de control uno de los dos tiempos de propagación es despreciable.

>[!important] El profe:
>se quedó muchísimo tiempo explicando cada cosa del envío y recepción con ventanas corredizas