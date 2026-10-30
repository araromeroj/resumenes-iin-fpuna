# Cuestionario de Examen: Sistema de Nombres de Dominio (DNS)
**Basado en Tanenbaum - Redes de Computadoras (Secciones 7.1.1 a 7.1.8)**

---

## Secciones 7.1.1 y 7.1.2: El espacio de nombres de dominio y su jerarquía

### Pregunta 1
¿Por qué el DNS utiliza una estructura jerárquica en forma de árbol invertido en lugar de una tabla plana para mapear nombres a direcciones IP?

* **Respuesta:** Una tabla plana a nivel mundial no escalaría debido al tamaño enorme de Internet, provocaría conflictos de nombres (ambigüedad) y requeriría una sobrecarga inasumible para mantener actualizada una base de datos centralizada. La estructura en árbol permite descentralizar la administración asignando autoridad sobre diferentes subárboles (dominios).

---

### Pregunta 2
¿Cuáles son las reglas de sintaxis y límites de longitud definidos por el estándar DNS para las etiquetas y los nombres de dominio completos (FQDN)?

* **Respuesta:** Cada etiqueta (componente entre puntos) puede tener un máximo de $63$ caracteres. El nombre de dominio completo (FQDN) no puede exceder los $255$ caracteres en total. Las etiquetas no distinguen entre mayúsculas y minúsculas (por ejemplo, `edu` es equivalente a `EDU`).

---

### Pregunta 3
Diferencie entre un Dominio de Nivel Superior Genérico (gTLD) y un Dominio de Nivel Superior de Código de País (ccTLD). Proporcione dos ejemplos de cada uno.

* **Respuesta:** 
  * **gTLD (Generic Top-Level Domain):** Clasifica entidades según su naturaleza u organización global. Ejemplos: `.com`, `.org`, `.edu`.
  * **ccTLD (Country-Code Top-Level Domain):** Asignado a países o territorios geográficos según los códigos ISO 3166. Ejemplos: `.es` (España), `.mx` (México), `.py` (Paraguay).

---

## Secciones 7.1.3 y 7.1.4: Registros de Recursos (RR) y Tipos de Datos

### Pregunta 4
¿Qué es un Registro de Recursos (Resource Record - RR) en DNS y cuáles son sus campos fundamentales en la tupla de 5 elementos?

* **Respuesta:** Un RR es la unidad básica de información almacenada en la base de datos distribuida del DNS. Su estructura viene dada por la 5-tupla:
  $$\text{Domain\_name} \quad \text{Time\_to\_live} \quad \text{Class} \quad \text{Type} \quad \text{Value}$$
  * `Domain_name`: Nombre al que aplica el registro.
  * `Time_to_live (TTL)`: Tiempo en segundos para almacenamiento en caché.
  * `Class`: Generalmente `IN` (Internet).
  * `Type`: Tipo de registro (`A`, `AAAA`, `MX`, `NS`, etc.).
  * `Value`: Valor o datos concretos asignados al registro.

---

### Pregunta 5
Indique el propósito específico de los siguientes tipos de registros DNS:
a) `A` y `AAAA`  
b) `MX`  
c) `NS`  
d) `CNAME`  
e) `PTR`  
f) `SOA`  

* **Respuesta:**
  * **`A` / `AAAA`:** Mapean un nombre de host a una dirección IPv4 (`A`) o IPv6 (`AAAA`).
  * **`MX` (Mail Exchange):** Especifica el servidor encargado de recibir correo electrónico para ese dominio (incluye preferencia/prioridad).
  * **`NS` (Name Server):** Identifica a los servidores de nombres autoritativos para el dominio o zona.
  * **`CNAME` (Canonical Name):** Define un alias que apunta al nombre verdadero o canónico del host.
  * **`PTR` (Pointer):** Mapea una dirección IP a un nombre de host (usado en búsquedas inversas).
  * **`SOA` (Start of Authority):** Proporciona información clave sobre la zona (servidor primario, correo del administrador, número de serie y temporizadores de sincronización).

---

### Pregunta 6
Explique el rol del campo **TTL (Time to Live)** en un registro de recursos y las implicaciones de configurarlo con un valor demasiado alto o demasiado bajo.

* **Respuesta:** El TTL indica el tiempo en segundos que un servidor intermediario o cliente puede guardar el registro en su memoria caché antes de descartarlo:
  * **TTL muy alto:** Reduce el tráfico en la red y las consultas a los servidores autoritativos, pero dificulta la actualización rápida de un cambio de IP (las modificaciones tardan en propagarse).
  * **TTL muy bajo:** Garantiza cambios rápidos y casi inmediatos de configuración, pero incrementa significativamente el tráfico de consultas DNS y la carga sobre los servidores de nombres.

---

## Secciones 7.1.5 y 7.1.6: Arquitectura, Zonas y Resolución de Nombres

### Pregunta 7
¿Cuál es la diferencia conceptual entre un **Dominio** y una **Zona** en la infraestructura DNS?

* **Respuesta:** Un **dominio** representa un subárbol completo en la jerarquía del espacio de nombres (incluyendo todos sus subdominios). Una **zona** es una parte delegada y contigua del espacio de nombres de un dominio que es administrada directamente por un servidor autoritativo concreto. Un dominio puede dividirse en múltiples zonas autónomas.

---

### Pregunta 8
Explique la diferencia técnica entre una **consulta recursiva** y una **consulta iterativa** durante la resolución de un nombre.

* **Respuesta:**
  * **Consulta Recursiva:** El cliente solicita la resolución a un servidor y este asume la responsabilidad completa de entregar la respuesta final (la dirección IP o un error). El cliente no recibe respuestas parciales.
  * **Consulta Iterativa:** Si el servidor consultado no tiene la respuesta definitiva, devuelve una referencia (puntero) indicando cuál es el siguiente servidor de nombres autoritativo con más jerarquía que debe ser consultado.

---

### Pregunta 9
Describa el mecanismo de **Resolución Inversa** de DNS. ¿Qué dominio especial utiliza y cómo se estructuran las direcciones IP para este fin?

* **Respuesta:** La resolución inversa traduce una dirección IP a un nombre de host. Utiliza el dominio especial `.in-addr.arpa` (para IPv4). La dirección IP se invierte octeto por octeto debido a que la jerarquía IP va de red a host (de izquierda a derecha), mientras que en DNS va de específico a general. Por ejemplo, la IP `192.0.2.1` se consulta como `1.2.0.192.in-addr.arpa` mediante un registro de tipo `PTR`.

---

## Secciones 7.1.7 y 7.1.8: Mensajes, Protocolos de Transporte y Seguridad (DNSSEC)

### Pregunta 10
¿Por qué el protocolo DNS utiliza preferentemente **UDP** en el puerto 53 para sus consultas habituales, pero puede alternar al uso de **TCP**?

* **Respuesta:** Utiliza **UDP** porque es un protocolo ligero, sin establecimiento de conexión, ideal para intercambios cortos y rápidos de consulta/respuesta. Cambia a **TCP** cuando la respuesta excede el límite de tamaño de un paquete UDP (marcando el bit de truncado `TC`) o cuando se realizan transferencias de zona completas (`AXFR`) entre servidores primarios y secundarios, requiriendo confiabilidad en la entrega.

---

### Pregunta 11
¿Qué es el bit **TC (Truncated)** en el encabezado de un mensaje DNS y qué acción realiza el cliente al recibirlo activo?

* **Respuesta:** El bit `TC` se activa cuando la respuesta del servidor supera la capacidad máxima del datagrama UDP utilizado. Al recibir un mensaje con `TC = 1`, el cliente descarta la respuesta incompleta y vuelve a reintentar la consulta utilizando **TCP** a través del puerto 53 para obtener los datos completos.

---

### Pregunta 12
¿Qué vulnerabilidad principal del DNS clásico busca corregir la extensión **DNSSEC** y a través de qué mecanismo fundamental lo logra?

* **Respuesta:** Busca corregir los ataques de envenenamiento de caché (*DNS cache poisoning*) y la suplantación de respuestas (*spoofing*). Lo logra proporcionando **autenticidad del origen** e **integridad de los datos** mediante firmas digitales basados en criptografía de clave pública (usando registros como `DNSKEY`, `RRSIG` y `DS`), garantizando que la respuesta proviene del servidor autorizado y no fue alterada en el trayecto.