Esta guía de estudio detalla los contenidos de la **Diapositiva 3**, correspondiente a la sección **2.4 (De formas de onda a bits)** del capítulo de la Capa Física, integrando conceptos técnicos del libro de Tanenbaum.

---

## 1. Fundamentos: Datos, Señales y Transmisión

Para comprender cómo se mueven los bits, es necesario distinguir entre la información y su representación física:

- **Datos:** Son las entidades que contienen significado o información, pudiendo ser digitales (**bits**) o analógicos.
- **Señales:** Es la representación eléctrica o electromagnética de los datos que se propaga físicamente por un medio.
- **Transmisión de datos:** Ocurre entre un emisor y un receptor a través de un medio, mediante la variación de las propiedades de una señal en el tiempo.

### Clasificación de los Canales de Transmisión

Según el sentido de la comunicación, los canales se dividen en:

- **Simplex:** Transmisión en una sola dirección (ej. televisión).
- **Half-duplex (Semidúplex):** Transmisión en ambas direcciones, pero solo una a la vez (ej. radio de la policía).
- **Full-duplex (Dúplex completo):** Transmisión en ambas direcciones simultáneamente (ej. teléfono).

### Tipos de Señales

- **Analógica:** Varía de forma suave y continua en el tiempo.
- **Digital:** Mantiene un nivel constante y cambia bruscamente a otro nivel constante.
- **Periódica:** Presenta un patrón que se repite en el tiempo.
- **Aperiódica:** El patrón de la señal no se repite.

---

## 2. Análisis de Fourier y Dominio de la Frecuencia

El matemático Jean-Baptiste Fourier demostró que cualquier señal $g(t)$ de comportamiento razonable y periodo $T$ puede descomponerse en una sumatoria de ondas sinusoidales.

- **Componentes:** La sumatoria incluye una **frecuencia fundamental** ($f=1/T$) y múltiples **armónicas** con distintas amplitudes ($a_n$ y $b_n$) y una constante $c$ que representa el valor promedio o valor de **DC** (**Direct Current** - Corriente Continua).
- **Importancia:** Este análisis permite estudiar las señales en el **dominio de la frecuencia**, fundamental para entender cómo los canales afectan a los datos.

---

## 3. Ancho de Banda y Limitaciones del Canal

- **Espectro:** Es el rango de frecuencias que contiene una señal; matemáticamente puede ser infinito.
- **Ancho de Banda (Bandwidth - "B"):** Es el rango de frecuencias donde se concentra la mayor parte de la energía de la señal.
- **Propiedad Física:** El ancho de banda es una característica física del canal (depende del grosor, material y longitud del cable). Un canal no puede transportar eficientemente una señal cuyo ancho de banda sea mayor al suyo.
- **Caso del Audio:** El oído humano percibe de 20 **Hz** (**Hertz**) a 20 **kHz** (**Kilohertz**). Sin embargo, un canal telefónico se limita mediante filtros a un rango de 300 a 4000 **Hz**.

---

## 4. Impedimentos en la Transmisión

La señal recibida suele diferir de la transmitida debido a tres factores principales:

### A. Atenuación

Es la pérdida de potencia de la señal debido a la distancia recorrida en el medio.

- **Regla:** A mayor frecuencia, mayor es la atenuación.
- **Solución:** Se utilizan amplificadores o repetidores para recuperar la fuerza de la señal.
- **Medición:** Se expresa en decibelios (dB). Si la potencia se reduce a la mitad, la pérdida es de -3 dB; si aumenta 10 veces, la ganancia es de 10 dB.

### B. Distorsión

Es la pérdida de la forma original de la señal. No se soluciona con amplificadores, sino con regeneradores.

- **Por atenuación:** Ocurre porque la atenuación varía según la frecuencia (crítico en analógico).
- **Por retardo:** Ocurre porque la velocidad de propagación varía con la frecuencia (crítico en digital).

### C. Ruido

Señales no deseadas que se insertan en el canal.

- **Ruido Térmico:** Agitación de electrones, distribuido uniformemente en todas las frecuencias.
- **Ruido de Intermodulación:** Producido por señales que son suma o diferencia de frecuencias que comparten un medio.
- **Crosstalk (Diafonía):** Acoplamiento entre líneas donde una señal se "escucha" en otra.
- **Ruido Impulsivo:** Pulsos irregulares o picos de corta duración y alta amplitud (ej. interferencias electromagnéticas). Es la **mayor fuente de errores** en datos digitales.

---

## 5. Modulación Digital y Transmisión en Banda Base

La tasa de bits máxima de un canal depende de su ancho de banda y de la **SNR** (**Signal-to-Noise Ratio** - Relación Señal/Ruido).

### Transmisión en Banda Base

Utiliza frecuencias desde 0 hasta un valor máximo. Consiste en convertir bits en pulsos de voltaje discretos llamados "elementos de señal".

#### Esquemas de Codificación

1. **NRZ (Non-Return-to-Zero - No Retorno a Cero):** La señal sigue directamente a los datos (voltaje positivo para 1, negativo para 0).
2. **Bipolar o AMI (Alternate Mark Inversion - Inversión de Marca Alternada):** Los "1" alternan polaridad y los "0" son voltaje cero. Facilita la detección de errores.
3. **Manchester:** Hay una transición en medio de cada bit que sirve como reloj y dato. Usado en **IEEE** (**Institute of Electrical and Electronics Engineers** - Instituto de Ingenieros Eléctricos y Electrónicos) 802.3 (Ethernet).
4. **Manchester Diferencial:** La transición inicial del bit determina el valor ("0" si hay transición, "1" si no). Usado en **IEEE** 802.5.

---

## 6. Tasa de Baudios vs. Tasa de Bits

- **Tasa de Bits (bps):** Cantidad de bits transmitidos por segundo ($1/T_b$).
- **Tasa de Modulación (Baudios):** Tasa a la que se generan los elementos de señal o símbolos. Un símbolo puede representar más de un bit.

---

## 7. Modulación en Banda Pasante y Multiplexado

Cuando se requiere usar una frecuencia portadora (como en medios inalámbricos), se utilizan dispositivos llamados módems.

- **Técnicas:** **ASK** (**Amplitude Shift Keying** - Modulación por Desplazamiento de Amplitud), **FSK** (**Frequency Shift Keying** - Modulación por Desplazamiento de Frecuencia) y **PSK** (**Phase Shift Keying** - Modulación por Desplazamiento de Fase).
- **QPSK (Quadrature PSK):** Usa 4 fases, permitiendo que cada símbolo represente 2 bits.
- **QAM (Quadrature Amplitude Modulation - Modulación de Amplitud en Cuadratura):** Combina cambios de amplitud y fase. Usado en **ADSL** (**Asymmetric Digital Subscriber Line** - Línea de Abonado Digital Asimétrica).

### Técnicas de Multiplexado (Compartir el Canal)

- **FDM (Frequency Division Multiplexing - Multiplexación por División de Frecuencia):** Divide el espectro en bandas para distintos usuarios.
- **OFDM (Orthogonal FDM - Multiplexación por División de Frecuencia Ortogonal):** Técnica eficiente donde las sub-transportadoras se solapan sin interferir. Usada en **Wi-Fi** y 4G.
- **TDM (Time Division Multiplexing - Multiplexación por División de Tiempo):** Los usuarios alternan el uso del canal en el tiempo.
- **CDMA (Code Division Multiple Access - Acceso Múltiple por División de Código):** Cada usuario tiene una secuencia de código distinta para compartir la misma frecuencia.