# Bases Teóricas de la Transmisión de Datos

La transmisión de datos implica el transporte de información mediante la variación de propiedades físicas en un medio.

- [I] **Datos**: Entidades que contienen significado o información. Pueden ser analógicos o digitales (bits).
- [I] **Señales**: Representaciones eléctricas o electromagnéticas de los datos que se propagan físicamente.

### Tipos de Canales según el Sentido:

- **Simplex**: Transmisión en una sola dirección (ej. televisión).
- **Half-duplex**: Transmisión en ambas direcciones, pero no simultáneamente (ej. radio policial).
- **Full-duplex**: Transmisión en ambas direcciones al mismo tiempo (ej. telefonía).

---
## Conceptos del Dominio del Tiempo y Frecuencia

- **Análisis de Fourier**: Proceso matemático que demuestra que cualquier señal periódica de comportamiento razonable con período $T$ puede reconstruirse mediante la suma de un número infinito (y a veces finito) de senos y cosenos.
- [I] **Espectro**: Rango de frecuencias que contiene una señal.
- [I] **Ancho de Banda (Bandwidth)**: Es el rango de frecuencias en el cual la amplitud de la señal no se ha atenuado más allá de cierto límite. Es una propiedad física del medio de transmisión.

---
# Limitaciones y Capacidad del Canal

La transmisión no es perfecta y está sujeta a impedimentos físicos:

- [I] **Atenuación**: Pérdida de energía de la señal a medida que viaja por el medio. Aumenta con la frecuencia.
- [I] **Distorsión de Retardo**: Ocurre porque la velocidad de propagación de la señal varía con la frecuencia, deformando la fase de la señal recibida.
- [I] **Ruido**: Energía no deseada que se suma a la señal.
    - **Ruido Térmico**: Debido a la agitación de electrones.
    - **Intermodulación**: Mezcla de frecuencias en sistemas no lineales.
    - **Crosstalk (Diafonía)**: Acoplamiento no deseado entre líneas cercanas.
    - **Ruido Impulsivo**: Picos irregulares de corta duración.

## Teoremas de Capacidad

1. **Teorema de Nyquist**: Para un canal perfecto (sin ruido), la tasa máxima de datos está limitada por el ancho de banda $B$ y los niveles de la señal $V$:   $$C = 2B \log_2(V)$$
2. **Teorema de Shannon**: Define la capacidad máxima teórica para un canal con ruido térmico, basada en la relación señal/ruido (SNR):   $$C = B \log_2(1 + S/N)$$

# Modulación Digital (De Bits a Señales)

Proceso de transformar bits en señales físicas para su transporte.

## Transmisión en Banda Base

- **NRZ (Non-Return to Zero)**: El nivel de voltaje es constante durante el intervalo del bit. Problema principal: falta de sincronización en largas secuencias de 0s o 1s.
    
- **Señales Balanceadas (Bipolares)**: Utilizan tres niveles de voltaje (+, 0, -) para evitar la componente de corriente continua (DC).
    
- **Manchester**: Existe una transición en el centro de cada intervalo de bit. La dirección de la transición indica el valor (0 o 1) y sirve como mecanismo de reloj para el receptor.

## Transmisión de Paso de Banda (Modulación de Portadora)

Se utiliza una señal portadora de alta frecuencia alterando sus parámetros:

- **ASK (Amplitude Shift Keying)**: Se varía la amplitud.
    
- **FSK (Frequency Shift Keying)**: Se varía la frecuencia.
    
- **PSK (Phase Shift Keying)**: Se varía la fase de la onda.
    
- **QAM (Quadrature Amplitude Modulation)**: Combina variaciones de amplitud y fase para permitir el envío de más bits por símbolo (ej. 16-QAM, 64-QAM).

# Técnicas de Multiplexado

Permiten compartir un único medio de transmisión entre múltiples usuarios o flujos de datos.

- **FDM (Frequency Division Multiplexing)**: El espectro de frecuencia se divide en bandas lógicas, cada una asignada a un usuario de forma permanente. Requiere "bandas de guarda" para evitar interferencias.
    
- **TDM (Time Division Multiplexing)**: Los usuarios comparten el ancho de banda total, pero en intervalos de tiempo (slots) distintos.
    
- **WDM (Wavelength Division Multiplexing)**: Variación de FDM utilizada en fibra óptica, donde se envían múltiples señales de luz a diferentes longitudes de onda (colores).
    
- **OFDM (Orthogonal FDM)**: Divide el canal en muchas subportadoras ortogonales que se solapan estrechamente sin interferir, optimizando el uso del espectro. Es la base de Wi-Fi y 4G/5G.
    
- **CDMA (Code Division Multiple Access)**: Cada usuario tiene asignado un código único (secuencia de chips). Todas las señales se transmiten simultáneamente en la misma frecuencia, y el receptor recupera la señal deseada mediante el producto interno del código.

# Conceptos Complementarios

- [I] **[[Baudios]]**: Número de cambios de símbolo o transiciones por segundo. No siempre es igual a la tasa de bits.
- [I] **[[SNR]]**: Relación señal-ruido, usualmente medida en decibelios (dB).
- [I] **[[Ortogonalidad]]**: Propiedad matemática en CDMA y OFDM que permite que señales solapadas sean recuperadas sin ambigüedad.