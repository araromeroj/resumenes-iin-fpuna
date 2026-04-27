- [*] **MAC - Medium Access Control:** Control de acceso al medio.
- [I] **Subcapa MAC:** es la parte inferior de la capa de enlace de datos y desempeña un papel fundamental al gestionar cómo varios dispositivos comparten un mismo canal de comunicación. Se usa en redes de área local (LAN).

>[!important] Función Principal
>Determinar qué estación puede transmitir a continuación en un canal de comunicación compartido.

## Tipos de Asignación del canal
En redes con un solo canal compartido, el desafío es **evitar que múltiples estaciones transmitan al mismo tiempo, lo que causaría colisiones**.

- **Asignación Estática:** Métodos como FDM o TDM dividen el ancho de banda de forma fija.
	Desventaja: es ineficiente para el tráfico de datos moderno, que suele ser intermitente (en ráfagas).

- **Asignación Dinámica:** Permite que las estaciones compitan por el acceso según sea necesario. Asigna el canal bajo demanda mediante algoritmos.
	Ventajas: puede ser centralizada (donde una entidad decide quién sigue) o descentralizada (cada máquina decide por sí misma siguiendo reglas establecidas).

## Características y supuestos clave

- **Tráfico Independiente:** Las estaciones generan tramas de forma independiente siguiendo una distribución estadística (Poisson).
- **Canal Único:** Solo hay un canal disponible para todas las comunicaciones y todas las estaciones pueden transmitir y recibir en él.
- **Detección de Portadora (opcional):** Las estaciones pueden saber si el canal está ocupado antes de intentar transmitir.
- **Colisiones Observables:** Las estaciones pueden detectar si su transmisión chocó con otra.
- **Tiempo Continuo o Ranurado:** La transmisión puede empezar en cualquier momento (tiempo continuo) o solo al inicio de intervalos discretos (tiempo ranurado).

---
# Enlaces Relacionados
- Siguiente nota: [[Protocolos de Acceso Múltiple]]