- [I] **Protocolo de Red:** Conjunto de reglas y normas que deben cumplir los dispositivos para la comunicación de datos de red.

## Componentes

- [I] **Sintaxis:** Se refiere al formato y orden en que se presentan los datos, incluyendo la longitud de encabezados, campos específicos y las reglas de relleno.
- [I] **Semántica:** significado de cada sección de bits o campo de encabezado.
	 Ejemplo: indica qué parte del mensaje tiene la dirección de destino.
- [I] **Temporización:** Gestiona la sincronización y velocidad de transmisión, determinando cuándo se deben enviar los datos y cómo actuar si ocurren retrasos (Timers).

## Estructura de Capas (Estratificación)

Las redes se organizan como una pila de capas o niveles, donde cada capa se construye sobre la inferior.

- [I] **Entidades pares (Peers):** Son los procesos o dispositivos que se encuentran en la misma capa pero en diferentes maquinas y que se comunican mediante el protocolo de esa capa.
- [I] **Interfaz:** Es lo que define qué operaciones y servicios pone la capa inferior a disposición de la capa superior.
- [I] **Arquitectura de red:** Es el conjunto completo de capas y protocolos que utiliza el sistema.

---
## Servicio vs. Protocolo

| SERVICIO                                                                                                                 | PROTOCOLO                                                                                                             |
| ------------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------- |
| Es una **abstracción** que define qué hace la capa para su usuario superior, pero no dice nada sobre cómo se implementa. | Define **cómo** se implementa el servicio mediante reglas que tigen el intercambio de paquetes entre entidades pares. |

## El Encapsulamiento

Cuando un mensaje se transmite, viaja hacia abajo a través de la pila de protocolos. En este proceso:

1. Cada capa recibe una unidad de datos de la superior (su **carga útil o payload**).
2. Añade su propio **encabezado (header)** con información de control (como direcciones o números de secuencia).
3. Algunas capas añaden un **tráiler** al final para el control de errores.
4. Al llegar al destino, el proceso se invierte (desencapsulamiento) y cada capa remueve su encabezado antes de pasar los datos hacia arriba.

- Ver [[Mensaje - Información a transmitirse]]

---
## Tipos de Servicios proporcionados

Los protocolos pueden ofrecer distintos modelos de entrega:

- **Orientado a la conexión:** Sigue el modelo del sistema telefónico; requiere establecer una conexión, transmitir los datos y luego liberarla (negociación previa).
- **Sin conexión:** Sigue el modelo postal; cada paquete (llamado **datagrama**) es independiente y lleva la dirección de destino completa.
- **Fiabilidad:** Un servicio es **fiable** si el receptor envía un **acuse de recibo (ACK)** por cada mensaje recibido correctamente. Si no hay confirmación, el emisor utiliza temporizadores para retransmitir el dato.

## Objetivos de Diseño

El diseño de protocolos modernos persigue cuatro metas principales:

- **Confiabilidad:** Operar correctamente aunque los componentes subyacentes fallen, mediante detección y corrección de errores.
- **Asignación de recursos:** Compartir el ancho de banda de forma eficiente (multiplexado estadístico) y evitar que un emisor rápido sature a un receptor lento (control de flujo).
- **Capacidad de evolución:** Permitir cambios y mejoras en la red ocultando los detalles de implementación tras las capas.
- **Seguridad:** Defender la red contra ataques de escucha (confidencialidad) y garantizar que los datos no sean alterados (integridad).

---

# Terminología

- [I] **Datagrama:** Es un paquete de datos que se utiliza en el contexto de un **servicio de red sin conexión.** Ver [[Datagramas]]