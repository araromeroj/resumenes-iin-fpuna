A diferencia de las variantes [[NRZ]], la codificación Manchester no utiliza niveles de voltaje fijos para representar un bit, sino que utiliza **transiciones** obligatorias en la mitad de cada intervalo de bit.

---
## Funcionamiento Técnico

En cada intervalo de tiempo asignado a un bit, ocurre un cambio de voltaje exactamente en la mitad:

- **Bit 1**: Se representa mediante una transición de **Bajo a Alto** (o viceversa, dependiendo de la convención, pero típicamente una subida).
    
- **Bit 0**: Se representa mediante una transición de **Alto a Bajo**.

---
## Ventajas sobre NRZ-L y NRZI

### Autosincronización (Self-clocking)

Como hay una transición garantizada en el centro de cada bit (ya sea que transmitas un `0` o un `1`), el receptor siempre tiene una señal de referencia para ajustar su reloj.

- **En NRZ-L/I**: Una cadena de veinte ceros seguidos se ve como una línea plana. El receptor puede perder la cuenta y pensar que pasaron 19 o 21.
    
- **En Manchester**: Veinte ceros se ven como veinte pulsos hacia abajo. Es imposible perder la cuenta.

### Ausencia de Componente de Corriente Continua (DC)

Como la señal pasa la misma cantidad de tiempo en voltaje positivo que en negativo dentro de cada bit, el promedio de voltaje es cero. Esto permite que la señal pase a través de transformadores o componentes que no toleran corriente continua.

## La Desventaja: El Ancho de Banda

El gran "pero" de la codificación Manchester es su eficiencia:

- **Doble de transiciones**: Para transmitir la misma cantidad de bits que NRZ, Manchester requiere el doble de cambios por segundo (el doble de baudios).
    
- **Ancho de banda**: Debido a lo anterior, Manchester requiere el **doble de ancho de banda** que las codificaciones NRZ para la misma tasa de bits.


> **Dato relevante**: Por esta razón, Manchester se usó mucho en las primeras versiones de **Ethernet (10 Mbps)**, donde el ancho de banda sobraba, pero no se usa en redes modernas de Gigabits porque desperdiciaría demasiado espectro.

---

# Comparativa

|**Característica**|**NRZ-L / NRZI**|**Manchester**|
|---|---|---|
|**Sincronización**|Mala (se pierde en cadenas largas)|**Excelente** (siempre hay cambios)|
|**Eficiencia de Ancho de Banda**|Alta (1 bit por cambio)|**Baja** (requiere más frecuencia)|
|**Uso común**|Almacenamiento magnético, USB|**Ethernet clásico (802.3)**|
