>[!todo]+ ¿Qué tipo de almacenamiento se tiene en los dispositivos routers y cuáles son las funciones de cada uno?

>[!example]+ Respuesta
>- **MEMORIA RAM:** Guarda una copia del sistema operativo, tabla de enrutamiento y la cola de paquetes.
>- **MEMORIA NVRAM:** Guarda la configuración inicial, es la memoria NO VOLÁTIL.
>- **MEMORIA ROM:** Guarda los procesos iniciales y el programa de arranque.
>- **MEMORIA FLASH:** Guarda la imagen del sistema operativo.

---
>[!todo]+ ¿Cuáles son los tipos de NAT?

>[!example]+ Respuesta
>- **NAT ESTÁTICA:** Las direcciones privadas son mapeadas con una IP pública para salir a la internet.
>- **NAT DINÁMICA:** Se asigna de un grupo de direcciones según la necesidad. Es decir, si ya se usó todo una IP, esta puede ser usada de nuevo, ya que es asignada unicamente a aquellas máquinas que la necesiten en ese momento.
>- **PAT:** Es un tipo de NAT con sobrecarga, aquí varias direcciones privadas pueden tener la misma IP pública pero se diferencian en los puertos TCP y UDP. Asigna las direcciones de acuerdo al número de puerto, se usa uno en el origen y otro en el destino.

---
>[!todo]+ ¿Qué indica el análisis de Fourier?

>[!example]+ Respuesta
>Indica que cualquier señal se puede descomponer en una sumatoria de ondas sinoidales, una fundamental y varias armónicas, con distintas amplitudes.

---
>[!todo]+ La ventaja del FAST FHSS sobre el SLOW FHSS es:

>[!example]+ Respuesta
>Que el fast resiste al ruido, mientras que el slow no.

>[!todo]+ La distorsión por atenuación perjudica a las señales $\_ \_ \_$. Y se produce debido a que $\_ \_ \_$.

>[!example]+ Respuesta
>- analógicas (así como la tele)
>- la atenuación es diferente a distintas frecuencias.

>[!todo]+ Cite un ejemplo de red de datagramas no confiable:

>[!example]+ Respuesta
>**IP + UPD:** Ya que las redes de datagramas son las que ofrecen un servicio **sin conexión**
>- El protocolo **IP** se basa en el transporte no garantizado y los paquetes se pueden llegar a descartar si hay congestión
>- El protocolo **UDP** es el protocolo de datagramas no confiable de la capa de transporte (sin conexión, si ack, no confiable).

>[!todo]+ El multiplexado OFDM es mejor que el FDM por que:

>[!example]+ Respuesta
>El **OFDM - orthogonal frequency division multiplexing** es mejor que el **FDM** ya que usa menos ancho de banda por permitir solapamiento de portadoras.

