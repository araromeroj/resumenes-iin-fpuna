Para entender **NRZ (Non-Return to Zero)**, es fundamental comprender que se llama así porque la señal no regresa a cero voltios en la mitad del intervalo de un bit; mantiene un nivel de voltaje constante durante todo el tiempo que dura el bit.

---
## NRZ-L (Non-Return to Zero Level)

Es la forma más simple de codificación digital. Aquí, el valor del bit depende directamente del **nivel de voltaje**.

- **Funcionamiento**: Se asigna un voltaje específico para el `0` y otro para el `1`. Por ejemplo:
    
    - Voltaje Alto = Bit `0`.
        
    - Voltaje Bajo = Bit `1`.
        
- **Problema principal**: Si envías una cadena larga de ceros o de unos, el voltaje se mantiene plano (una línea recta). El receptor no puede saber cuántos bits han pasado exactamente porque no hay cambios en la señal que le ayuden a sincronizar su reloj (problema de **clocking**).

## NRZ-I (Non-Return to Zero Inverted)

Esta variante es más robusta porque el valor del bit no depende del nivel de voltaje, sino de la **presencia o ausencia de un cambio (transición)** al inicio del intervalo del bit.

- **Funcionamiento**:
    
    - **Bit `1`**: Se representa mediante una **transición** (si el voltaje estaba arriba, baja; si estaba abajo, sube).
        
    - **Bit `0`**: Se representa mediante la **ausencia de transición** (el voltaje se mantiene igual al del bit anterior).
        
- **Ventaja**: Es una forma de codificación diferencial. Ayuda a la sincronización cada vez que aparece un `1`, ya que el cambio de voltaje obliga al receptor a reajustar su reloj.
    
- **Limitación**: Sigue teniendo problemas con las cadenas largas de `0`, ya que en ese caso no habría ninguna transición y el receptor podría perder la cuenta del tiempo.

---
# Comparativa Técnica

| **Característica**       | **NRZ-L**                         | **NRZI**                           |
| ------------------------ | --------------------------------- | ---------------------------------- |
| **Basado en**            | Nivel de voltaje absoluto.        | Transición (cambio) de voltaje.    |
| **Interpretación del 1** | Voltaje fijo (ej. bajo).          | Hay una transición al inicio.      |
| **Interpretación del 0** | Voltaje fijo (ej. alto).          | No hay transición.                 |
| **Sincronización**       | Pobre en cadenas largas de 0 y 1. | Mejor en cadenas de 1, pobre en 0. |
>[!danger] Ojo
>Ninguna elimina el componente DC
>Ver: [[Análisis de Gráfica A = F(f)]]
### ¿Por qué son importantes?

Ambas técnicas son eficientes en cuanto al uso del ancho de banda porque no requieren que la señal cambie constantemente (como la codificación Manchester). Sin embargo, debido a los problemas de sincronización mencionados, suelen utilizarse junto con otras técnicas como el **relleno de bits (bit stuffing)** o códigos de línea como **4B/5B** para asegurar que nunca haya demasiados ceros o unos seguidos.

>[!note] Usos del NRZ-L y NRZ-I
>- Grabaciones magnéticas
>- USB - Universal serial bus
>- Transmisión serial
>- No son muy usados para la transmisión de datos por sus desventajas

# Enlaces relacionados
- [[1. Capa física]]
- [[Codificación Manchester]]
