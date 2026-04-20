A diferencia de las variantes [[NRZ]], la codificación Manchester no utiliza niveles de voltaje fijos para representar un bit, sino que utiliza **transiciones** obligatorias en la mitad de cada intervalo de bit.

>[!important] Importante
>La tasa de **baudios** **es** el **doble** que la tasa de **bits**

>[!info] Funcionamiento Técnico
>En cada intervalo de tiempo asignado a un bit, ocurre un cambio de voltaje **exactamente en la mitad**:
>- **Bit 1**: Se representa mediante una transición de **Bajo a Alto** (o viceversa, dependiendo de la convención, pero típicamente una subida).
>- **Bit 0**: Se representa mediante una transición de **Alto a Bajo**.

---
## Ventajas sobre NRZ-L y NRZI

**Autosincronización (Self-clocking)**: Como hay una transición garantizada en el centro de cada bit (ya sea que transmitas un `0` o un `1`), el receptor siempre tiene una señal de referencia para ajustar su reloj.

- **En NRZ-L/I**: Una cadena de veinte ceros seguidos se ve como una línea plana. El receptor puede perder la cuenta y pensar que pasaron 19 o 21.
    
- **En Manchester**: Veinte ceros se ven como veinte pulsos hacia abajo. Es imposible perder la cuenta.

**Ausencia de Componente de Corriente Continua (DC)**: Como la señal pasa la misma cantidad de tiempo en voltaje positivo que en negativo dentro de cada bit, el promedio de voltaje es cero. Esto permite que la señal pase a través de transformadores o componentes que no toleran corriente continua.

## La Desventaja: El Ancho de Banda

- **Doble de transiciones**: Para transmitir la misma cantidad de bits que NRZ, Manchester requiere el doble de cambios por segundo (el doble de baudios).
    
- **Ancho de banda**: Debido a lo anterior, Manchester requiere el **doble de ancho de banda** que las codificaciones NRZ para la misma tasa de bits.


> **Dato relevante**: Por esta razón, Manchester se usó mucho en las primeras versiones de **Ethernet (10 Mbps)**, donde el ancho de banda sobraba, pero no se usa en redes modernas de Gigabits porque desperdiciaría demasiado espectro.

---
# Manchester Diferencial

Los datos se representan mediante la presencia o ausencia de transiciones en lugar de niveles de tensión fijos.

>[!info] Funcionamiento
>Funcionamiento
>El funcionamiento de este código se basa en la división de cada intervalo de bit en dos mitades, aplicando las siguientes reglas lógicas:
>- **Transición obligatoria en el medio:** Al igual que en la codificación Manchester estándar, siempre hay una transición en el centro de cada intervalo de bit. Sin embargo, en el Manchester Diferencial, esta transición se utiliza **únicamente como señal de reloj** para mantener la sincronización entre emisor y receptor.
>- **Representación del bit "0":** Se produce una **transición al inicio** del periodo del bit.
>- **Representación del bit "1":** **No hay transición al inicio** del periodo del bit.

## Características

- **Codificación Diferencial:** La información no depende del nivel de voltaje absoluto (positivo o negativo), sino de si hubo un cambio respecto al estado anterior al comenzar el bit.
	
- **Autosincronización (Clocking):** Al garantizar una transición en el medio de cada bit, el receptor puede extraer fácilmente la señal de reloj del flujo de datos. Esto evita que el receptor pierda el sincronismo ante largas cadenas de bits idénticos (ya sean "0"s o "1"s).
	
- **Detección de Errores:** Al ser un código que requiere transiciones constantes, cualquier intervalo de bit que carezca de la transición central puede ser identificado inmediatamente por la capa física como una "violación de código" o error de transmisión.
	Ver: [[Control de errores (Detección y corrección)]], [[2. Capa Física]]
	
- **Uso de Ancho de Banda:** Al igual que el Manchester estándar, este esquema requiere el **doble de ancho de banda** que la codificación NRZ simple, ya que la señal cambia al menos una vez (y a veces dos) por cada bit transmitido.

---
# Diferencias de Codificación Manchester

| **Característica**               | **Mánchester Bifase**                                                                                                                                                                                                                               | **Mánchester Diferencial**                                                                                                                                                                                                            |
| -------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Representación de Bits           | El valor del bit se determina por la **dirección de la transición** que ocurre en medio del intervalo. Una transición de **bajo a alto** representa un **"1" lógico**, mientras que una transición de **alto a bajo** representa un **"0" lógico**. | El valor del bit se determina por la presencia o ausencia de una **transición al inicio** del periodo del bit. Si hay una **transición al inicio**, representa un **"0"**; si **no hay transición al inicio**, representa un **"1"**. |
| Función de la Transición Central | La transición en el medio de cada periodo sirve simultáneamente como **señal de reloj (sincronización) y como los datos mismos**.                                                                                                                   | La transición en el medio del bit funciona **únicamente como reloj** para mantener la sincronización entre el emisor y el receptor.                                                                                                   |
| Uso y Estándares                 | Es la codificación utilizada en la **Ethernet clásica (IEEE 802.3)** a 10 Mbps.                                                                                                                                                                     | Se utiliza habitualmente en el estándar **IEEE 802.5 (Token Ring)**.                                                                                                                                                                  |
## Características Compartidas
Ambos esquemas pertenecen a la categoría de códigos de línea que facilitan la **recuperación del reloj** (clocking) al asegurar transiciones frecuentes, incluso en cadenas largas de ceros o unos. Además, al tener transiciones constantes, son señales **balanceadas** que eliminan la **componente de corriente continua (DC)**, lo que facilita la calibración de los receptores y mejora la inmunidad al ruido.

---
# Enlaces relacionados
- [[2. Capa Física]]