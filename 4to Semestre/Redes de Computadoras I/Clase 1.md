
En el curso vamos a estudiar el diseño y la organización de las redes.

- [I] Redes: es una colección de dispositivos informáticos autónomos interconectados (pueden intercambiar información).
- [I] Medios de transmisión: elemento por el cual se transmite la información.

Algunos medios de transmisión son: cables de cobre, [[Fibra Óptica|cable de fibra óptica]] y ondas de radio (microondas, infrarrojos, satélites de comunicación).
## Usos de las Redes

Las redes modernas cumplen funciones vitales tanto en el ámbito personal como profesional. Se dividen principalmente en:
### Acceso a la Información

Recuperación de datos desde servidores remotos mediante navegadores o apps móviles.

- **Modelo Cliente-Servidor:** Base técnica donde un _cliente_ solicita datos a un _servidor_ centralizado.
	Intervienen dos procesos o programas de ejecución, uno en la máquina del cliente y otro en la máquina servidor.
    
- **Ejemplos:** Bibliotecas digitales, diarios online y contenidos personalizables.
    

![client-server model diagram, generada por IA](https://encrypted-tbn0.gstatic.com/licensed-image?q=tbn:ANd9GcR4ayuL5k9We8CLHEEBzR5-qo_cFyyvP4jM03irH4CYfIovOTQn9eT-RGl8Jffj1vLuOE8l0dcCegv_ZNlq66qcPqx_XN3jFoWywkIW5AQYW4bHSBk)

- [I] World Wide Web: Sistema global de gestión de información que funciona sobre Internet, permitiendo visualizar páginas web interconectadas mediante hipervínculos (enlaces) y accesibles a través del navegador.

### Comunicación de Persona a Persona (Peer-to-Peer)

No hay división fija entre clientes y servidores.
Interacciones ricas en medios que sustituyen o potencian la telefonía tradicional.

- **Herramientas:** Correo electrónico, mensajería instantánea, redes sociales.
    
- **Educación:** Plataformas de colaboración y aprendizaje a distancia.

![[sistema peer to peer.png]]

- [I] Wiki: sitio web colaborativo que editan los miembros de una comunidad (como wikipedia).
### Comercio Electrónico (e-Commerce)

Transacciones financieras y comerciales a través de la red.

- **Fintech:** Gestión de cuentas, pagos de facturas e inversión electrónica.
    
- **Modelos de Negocio:**
    
    - **B2C (Business-to-Consumer):** Empresa a consumidor (ej. Amazon).
        
    - **B2B (Business-to-Business):** Entre empresas.
    	
	- **G2C (Gobierno a consumidor):** El gobierno distribuye formularios fiscales por vía electrónica.
        
    - **C2C (Consumer-to-Consumer):** Entre consumidores (ej. eBay).
        
    - **P2P (Peer-to-Peer):** Entre iguales (subastas o pagos directos).

### Entretenimiento

Los usuarios tienen acceso a videos, películas, música, juegos y más. En los hogares se ve televisión a través de sistemas [[IPTV (Televisión IP)]] 

- [I] IPTV (Televisión por Protocolo de Internet): es una tecnología que distribuye señales de televisión de pago a través de [[Banda Ancha|conexiones de banda ancha]], en lugar de antenas o cable tradicional. Está basada en tecnología IP.
- [I] Banda ancha: es un tipo de conexión a internet de alta velocidad que permite la transmisión rápida y simultánea de grandes cantidades de datos.

### Internet de los Objetos (IoT)

- **Hogares inteligentes:** Domótica (luces, cámaras, termostatos conectados).
    
- **Redes de sensores:** Nodos que monitorean el mundo físico (seguimiento de fauna, telemetría de vehículos).

### Usos Empresariales

- **Compartición de recursos:** Acceso común a impresoras, servidores de archivos y software.
    
- **Telefonía IP:** Llamadas de voz integradas en la red de datos.
    
- **VPN (Redes Privadas Virtuales):** Túneles seguros que conectan oficinas remotas a la red local.

---

# TIPOS DE REDES INFORMÁTICAS

- [b] Continuar desde la página 31 (pdf) Unidad 1.2.1.

- Redes de acceso de banda ancha

>[!important] Ley de Met-calfe
>El valor de una red es proporcional al cuadrado del número de usuarios. Ayuda a explicar cómo la enorme popularidad de Internet se debe a su tamaño.
- Redes móviles e inalámbricas
- Redes de proveedores de contenidos (CDN)
- Redes de tránsito (Backbones)
- Redes de empresas (VPN)
## Clasificación por Tecnología de Transmisión

|**Tipo**|**Descripción**|**Ejemplo**|
|---|---|---|
|**Punto a punto**|Conectan pares individuales de máquinas.|Enlaces satelitales, fibra directa.|
|**Difusión (Broadcast)**|Un único canal compartido; todos reciben el paquete, pero solo el destino lo procesa.|Redes Wi-Fi, Ethernet clásico.|

> [!NOTE] Terminología
> 
> - **Unidifusión (Unicast):** Envío de un emisor a un único receptor específico.
>     
> - **Multidifusión (Multicast):** Envío a un grupo selecto de máquinas.

---

## Tecnología por Escala (Tamaño Físico)

### PAN (Personal Area Network)

- **Rango:** Alcance de una persona (aprox. 10m).
    
- **Tecnologías:** [[Bluetooth]], [[RFID]].
    
- **Uso:** Sincronizar periféricos con un smartphone o PC.

### LAN (Local Area Network)

- **Rango:** Un edificio, oficina o casa.
    
- **Tipos:**
    
    - **Alámbricas:** Ethernet. Cables de cobre o [[Fibra Óptica]].
        
    - **Inalámbricas (WLAN):** Basadas en el estándar **IEEE 802.11 (Wi-Fi)** mediante un [[Punto de Acceso]].

La principal función de un punto de acceso (AP) en una red inalámbrica 802.11 (WiFi) es retransmitir paquetes enter los ordenadores inalámbricos y entre estos e internet

### MAN (Metropolitan Area Network)

- **Rango:** Una ciudad completa.
    
- **Ejemplos:** Redes de TV por cable, WiMAX (IEEE 802.16).

### WAN (Wide Area Network)

- **Rango:** Países o continentes.
    
- **Componentes:**
    
    - **Hosts:** Máquinas de usuario (donde corren las apps).
        
    - **Subred de comunicación:** Líneas de transmisión y [[Enrutadores]] (routers).

### Interredes (Internetworks o Red de Redes)

==Conjunto de redes heterogéneas interconectadas mediante pasarelas o routers para formar una unidad mayor.==

- **Puertas de enlace (Gateways):** Máquinas que permiten la comunicación entre redes incompatibles.
    
- **Internet:** La interred global que utiliza [[redes de proveedores de servicios]] (ISP).

---