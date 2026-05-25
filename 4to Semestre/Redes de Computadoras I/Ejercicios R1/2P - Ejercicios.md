
![[Pasted image 20260524233024.png]]

>[!note] Explique
>TXOP: Es un método de calidad de servicio en las redes 802.11, sirve para que estaciones lentas no saturen o perjudiquen mucho a estaciones rápidas.
>CSMA/CD: Es acceso múltiple con detección de portadora y detección de colisiones, en los métodos se reconoce si el canal presenta alguna colisión y se escucha en todas las estaciones para poder transmitir.
>ICMP:
>APSD:
>PAT: Port Adress Translation es un protocolo que relaciona direcciones IP públicas a IP privadas de modo que si dos estaciones quieren acceder a una misma red y tienen el mismo puerto, en el router con el PAT se le asignan diferentes puertos a ambos hosts y se utiliza una tabla de NAT para el seguimiento.

![[Pasted image 20260524233034.png]]

- Memoria **RAM**: Guarda la tabla de enrutamiento, la configuración actual del router, colas de paquetes y el SO en ejecución.
- Memoria **NVRAM**: Guarda la configuración de inicio que se copia en la memoria de trabajo durante el inicio del equipo. Es una memoria ram de poca capacidad.
- Memoria **Flash**: Guarda la imagen del SO
- Memoria **ROM**: Guarda el programa de arranque y el software básico del SO, las pruebas de inicio y rutinas de diagnóstico de hardware.

![[Pasted image 20260524233524.png]]

1. Escucha el medio para saber si alguien más está transmitiendo.
2. Si el canal está ocupado, espera que se libere.
3. Si se libera, espera el tiempo obligatorio DIFS.
4. Si luego del DIFS el canal sigue libre, entonces se elige un tiempo aleatorio dentro de la ventana de contención. $[1, CW_{min}]$
5. Empieza la cuenta regresiva, el contador de backoff disminuye en 1 por cada ranura de tiempo que el canal esté libre.
6. Si otra estación empieza a transmitir antes de que el contador llegue a cero, el contador se congela hasta que vuelva a estar libre y pase otro periodo DIFS.
7. Se transmite cuando finalmente llega a cero.
8. Si la estacón transmite pero no recibe el ACK, asume que hubo colisión o interferencia, entonces el número aleatorio se vuelve a elegir pero esta vez con el doble de rango que el anterior. $[1, 2CW_{min}]$
No se usa el algoritmo de backoff cuando el medio está inactivo a la llegada de una nueva trama. Si el canal ha estado libre durante un tiempo igual o mayor al DIFS se transmite la trama por el medio inmediatamente.

![[Pasted image 20260524234521.png]]

1. Se recibe la trama en el puerto "x".
2. Se lee la dirección MAC de destino
	Si la MAC es de broadcast se reenvia la trama por todos los puertos menos en el destino.
2. ¿Está la dirección de destino en la tabla CAM?
	Si la dirección de destino no está en la CAM, se reenvía la trama por todos los puertos menos en el de destino.
3. ¿Es el puerto por donde vino el mismo que el puerto de salida de la CAM?
	Si es así, se termina el forwarding
4. Si no está, se envía la trama por el puerto de salida indicado "x".

>[!info] $5)$ Esquematice la trama Ethernet 802.3q indicando para cada campo el tamaño y la finalidad del mismo

1. Preámbulo (7 bytes): Para indicar que es la trama de ethernet.
2. SFD (1 byte): Indica el inicio de la trama
3. Origen (6 bytes): Dirección de origen
4. Destino (6 bytes): Dirección de destino
5. X'8100: indicador de protocolo VLAN
6. TAG (16 bytes): tiene la prioridad, el indicador de vlan y el CPI que se usa en token ring.
7. Ethertype / Longitud (2 bytes): indica la longitud de la trama o el protocolo de ethernet a utilizarse.
8. Data (0 - 1500 bytes): son los datos o la carga útil de la trama.
9. Pad (0 - 46 bytes): es un campo que se utiliza para rellenar y llegar a los 64 bytes de trama mínima.
10. CRC (4 bytes): indicado para la detección y corrección de errores.

![[Pasted image 20260525001010.png]]

- Repetición selectiva -> $2^{k-1}$ que sería la mitad de los bits de la ventana corrediza.
- $k=3 \text{ bits}$
- Utiliza *Superposición o Piggybacking* que tiene la siguiente fórmula $E = \frac{W*t_t}{2t_t+2t_p}$
- Longitud del cable $C = 6 \text{ km} = 6000 \text{ m}$ 
- Tasa de las estaciones $V_t = 50 \text{ Mbps}$
$$80\%\leq \frac{2^{3-1}*t_t}{2t_t+2*\frac{6000}{3*10^8}}$$
$$t_t \geq 13.333 \dots \mu\text{s} $$
$$L \geq t_t*V_t$$
$$L \geq 13.333*10^{-6} *50*10^6$$
$$L = 500 \text{ bytes}$$