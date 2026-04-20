El control de caudal es un **[[2. Capa de Enlace de Datos#Problemas de diseño de la capa de enlace de datos|problema de diseño]]** importante que presenta la capa de enlace de datos y en capas superiores. ==Un emisor que quiere transmitir tramas más rápido de lo que un receptor puede aceptarlas== (cuando el emisor funciona en una máquina rápida y el receptor en una máquina lenta y de gama baja).
## Tipos de control de flujo

1. **Basado en retroalimentación:** El receptor devuelve el mensaje o información al emisor dándole la posibilidad de enviar más datos o el receptor le dice al emisor en qué fase está.
2. **Basado en la velocidad (tasas de bits):** Se usa un mecanismo definido que limita la velocidad a la que los remitentes pueden transmitir datos, sin usar la retroalimentación del receptor. (Capa de enlace o superiores).

- [I] **NIC (Tarjetas de interfaz de red):** funcionan a velocidad de cable, pueden gestionar tramas tan rápido como llegan al enlace.
---
# Enlaces relacionados
- Siguiente nota: [[Control de errores (Detección y corrección)]].