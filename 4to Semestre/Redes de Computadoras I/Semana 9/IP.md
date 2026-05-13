**IP (Protocolo de Internet)** es una etiqueta numérica única e irrepetible que identifica a cualquier dispositivo, conectado a una red que utiliza el protocolo IP.

>[!important] Formato
>XXX.XXX.XXX.XXX
>Cada "XXX" tiene un rango de valor de 0 a 255

> **Un poco de historia**
> Anteriormente se daban IP's a cada empresa dentro de un rango dado, se registraban en papeles nada más para llevar cuenta de las IP's disponibles y las dadas.


**Registros Regionales de Internet (RIR):**

- ARIN: Norteamérica, EEUU, Canadá.
- RIPE, NIC: Europa, Medio Oriente y Asia Central.
- APNIC: Asia y Costa del Pacífico.
- LACNIC: Latinoamérica.
- AFRINIC: Continente africano

---
## Clasificación
### Según la versión
#### IPv4 (Protocolo de Internet Versión 4)

La que domina Internet actualmente.

>[!Important] Características
> - Utiliza direcciones de 32 bits, lo que permite aproximadamente 4 mil millones de direcciones únicas.
> - Su cabecera tiene una parte fija de **20 bytes** y 13 campos para fragmentación y una suma de comprobación (checksum).
> - Debido a su popularidad, las direcciones se han agotado, lo que llevó al uso de técnicas temporales como NAT y la creación del IPv6

#### IPv6 (Protocolo de Internet Versión 6)


>[!important] Características
> - Utiliza direcciones de 128 bits, proporcionando un espacio virtualmente ilimitado (aproximadamente $3*10^38$ direcciones).
> - La cabecera se simplificó a 7 campos (frente a los 13 de IPv4) para que los enrutadores procesen los paquetes más rápido.
> - No tienen suma de comprobación en la cabecera para mejorar el rendimiento.
> - La fragmentación solo la realiza el host de origen, no los enrutadores intermedios, lo que agiliza el tráfico.

### Según su Uso y Estructura

- **Direcciones Públicas vs. Privadas:** Las direcciones privadas se usan internamente en redes domésticas o de empresas y no pueden aparecer en el Internet global. Los rangos reservados son **10.0.0.0/8**, **172.16.0.0/12** y **192.168.0.0/16**.
- **Direccionamiento con Clases (Classful):** Diseño antiguo que dividía las direcciones en clases fijas (**A, B, C, D y E**) según sus bits iniciales. Fue reemplazado por CIDR porque desperdiciaba muchas direcciones.
- **CIDR (Enrutamiento entre Dominios sin Clases):** Permite que los bloques de direcciones tengan **tamaños variables** mediante el uso de máscaras de subred, facilitando la agregación de rutas y reduciendo el tamaño de las tablas de enrutamiento.
- **Direcciones Especiales:**
    - **0.0.0.0:** Utilizada por los hosts al arrancar ("esta red").
    - **Loopback (127.xx.yy.zz):** Paquetes que no salen al cable y se procesan localmente para pruebas.

---
## Videos y Enlaces Relacionados

- Qué es la IP privada, NAT y puerta de enlace:
	https://www.youtube.com/watch?v=HeZWcZmrQUY
- Arquitectura y Clasificación del Protocolo de Internet:
	https://notebooklm.google.com/notebook/0f78dd09-cd89-4f4d-b999-e6202ee28b88