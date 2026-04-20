Proceso de transformar bits en señales físicas para su transporte. La entrada de datos puede ser digital o analógica.
## Aspectos de la codificación

- Espectro de señal - Ancho de banda
- Existencia o no del componente DC
- Clocking o sincronización simple o compleja
- Facilidad para la detección de errores
- Interferencia de señal e inmunidad de ruido
- Costo y complejidad

## Transmisión en Banda Base

Se utilizan frecuencias desde 0 hasta un cierto valor. Se convierten los **bits a señales digitales** que son pulsos de voltaje o amplitud discretos, discontinuos.

- **NRZ (Non-Return to Zero)**: El nivel de voltaje es constante durante el intervalo del bit. Problema principal: falta de sincronización en largas secuencias de 0s o 1s.
	- Ver: [[NRZ]]
    
- **Señales Balanceadas (Bipolares)**: Utilizan tres niveles de voltaje (+, 0, -) para evitar la componente de corriente continua (DC).
	- Ver: [[Señales Balanceadas]]
    
- **Manchester**: Existe una transición en el centro de cada intervalo de bit. La dirección de la transición indica el valor (0 o 1) y sirve como mecanismo de reloj para el receptor.
	- Ver: [[Codificación Manchester]]

## Transmisión de Paso de Banda (Modulación de Portadora)

Se utiliza una señal portadora de alta frecuencia alterando sus parámetros:

- **[[ASK (Amplitude Shift Keying)]]**: Se varía la amplitud.
    
- **[[FSK (Frequency Shift Keying)]]**: Se varía la frecuencia.
    
- **[[PSK (Phase Shift Keying)]]**: Se varía la fase de la onda.
	
	- **QPSK (Quadrature Phase Keying)**: se varía la fase y usa 4 fases distintas, con desplazamiento de $\pi/90°$. Cada elemento de señal representa 2 bits y la tasa de baudios es de $\text{bps}/2$.

- **QAM (Quadrature Amplitude Modulation)**: Combina variaciones de amplitud y fase para permitir el envío de más bits por símbolo (ej. 16-QAM, 64-QAM).
	- Donde $M$ es la cantidad de niveles o estados que puede adoptar la señal.
	$$\text{BitRate}=\text{BaudRate}*log_2(M)$$
# Limitaciones y Capacidad del Canal

La transmisión no es perfecta y está sujeta a impedimentos físicos:

- [I] **Atenuación**: Pérdida de energía de la señal a medida que viaja por el medio. Aumenta con la frecuencia y es debido a la distancia.
	Se calcula como: $$\text{Atenuación}=10*log_{10}(\frac{P_2}{P_1})$$
- [I] **Distorsión por Atenuación**: Debido a que la atenuación es diferente a distintas frecuencias (crítico para señales analógicas).
- [I] **Distorsión de Retardo**: Ocurre porque la velocidad de propagación de la señal varía con la frecuencia, deformando la fase de la señal recibida (crítico para señales digitales).
- [I] **Ruido**: Energía no deseada que se suma a la señal.
    - **Ruido Térmico**: Debido a la agitación de electrones.
    - **Intermodulación**: Mezcla de frecuencias en sistemas no lineales.
    - **Crosstalk (Diafonía)**: Acoplamiento no deseado entre líneas cercanas.
    - **Ruido Impulsivo**: Picos irregulares de corta duración.

## Teoremas de Capacidad o Tasa máx de datos

La tasa de bits máxima posible (medida en bits sobre segundo) es una función de:
- Ancho de banda -> en ciclos sobre segundo o Hz.
- Ruido -> en enlaces comunes.
- Tasa de errores -> de bits corruptos.

1. **Teorema de Nyquist - límite tecnológico**: Para un canal perfecto (sin ruido), la tasa máxima de datos está limitada por el ancho de banda $B$ y los niveles de la señal $V$:   $$C = 2B \log_2(V)$$
2. **Teorema de Shannon - límite físico real**: Define la capacidad máxima teórica para un canal con ruido térmico, basada en la relación señal/ruido (SNR): 
	- $$C = B \log_2(1 + SNR_\text{lineal})$$
	- $$\text{SNR}=\text{Potencia}_{\text{señal}}/\text{Potencia}_{\text{ruido}}$$
	- $$\text{SNR}_{\text{dB}}=10*log_{10}(\text{SNR}_{\text{lineal}})$$
---
# Conceptos Complementarios

- [I] **Baudios**: Número de cambios de símbolo o transiciones por segundo. No siempre es igual a la tasa de bits.
- [I] **SNR**: Relación señal-ruido, usualmente medida en decibelios (dB).

- [*] **SNR - Signal to Noise Ratio:** Relación señal ruido.
---
# Enlaces relacionados
- siguiente nota: [[Técnicas de multiplexado]]