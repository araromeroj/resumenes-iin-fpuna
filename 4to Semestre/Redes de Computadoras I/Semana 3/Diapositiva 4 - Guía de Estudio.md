Esta guía de estudio detalla los contenidos de la **Diapositiva 4**, la cual aborda la primera parte del **Capítulo 2: La Capa Física**, centrándose en los medios de transmisión y el uso del espectro electromagnético.

---

## 1. Medios Guiados de Transmisión

Los medios guiados son aquellos donde las señales se conducen a través de un camino físico sólido, como cables o hilos.

### A. Almacenamiento Persistente

- **Concepto:** Consiste en transportar datos físicamente mediante medios de almacenamiento (como discos o cintas) de un lugar a otro.
- **Características:** Posee un excelente ancho de banda, pero un retardo extremadamente alto, medido en horas o días en lugar de milisegundos.

### B. Cables de Par Trenzado

Consiste en dos hilos de cobre aislados y trenzados helicoidalmente para anular las interferencias de las ondas de distintas torsiones.

- **UTP (Unshielded Twisted Pair - Par Trenzado No Blindado):** Es el más común en redes de área local.
- **STP (Shielded Twisted Pair - Par Trenzado Blindado):** Incluye una malla metálica para reducir interferencias, pero es más caro y difícil de manejar.
- **FTP (Foiled Twisted Pair - Par Trenzado con Hoja Metálica):** Los cuatro pares están rodeados por una hoja metálica protectora.
- **Categorías clave:**
    - **Cat. 5e:** Compuesto por cuatro pares, estándar para muchas **LAN (Local Area Network - Red de Área Local)**.
    - **Cat. 6:** Puede soportar velocidades de hasta 10 **Gbps (Gigabits por segundo)**.
    - **Cat. 8:** Posee un ancho de banda de 2 **GHz (Gigahertz)** y se usa para distancias cortas (30 m) a 25 o 40 **Gbps (Gigabits por segundo)**.

### C. Cable Coaxial

Ofrece un mejor apantallamiento y mayor ancho de banda que el par trenzado, permitiendo distancias más largas.

- **Tipos:**
    - **50 ohmios:** Utilizado para transmisiones digitales desde su origen.
    - **75 ohmios:** Común en transmisiones analógicas y televisión por cable.
- **Construcción:** Núcleo de cobre rígido, material aislante, conductor cilíndrico (malla) y cubierta de plástico. Su ancho de banda llega hasta los 6 **GHz (Gigahertz)**.

### D. Líneas de Potencia (Líneas Eléctricas)

- **Funcionamiento:** Envío de datos a través del cableado eléctrico doméstico convencional.
- **Rendimiento:** Es práctico enviar al menos 500 **Mbps (Megabits por segundo)** en distancias cortas.

### E. Fibra Óptica

Utiliza pulsos de luz para representar bits (1 indica luz, 0 indica ausencia).

- **Componentes:** Fuente de luz, medio de transmisión (vidrio ultra fino) y detector.
- **Modos de propagación:**
    - **Monomodo:** Núcleo de 8 a 10 micras; la luz viaja en línea recta. Permite distancias de 100 km a 100 **Gbps (Gigabits por segundo)**.
    - **Multimodo:** Núcleo de 50 micras; la luz rebota en las paredes. Ideal para distancias cortas (hasta 15 km).
- **Ventajas:** Inmune al ruido electromagnético y gran ancho de banda.
- **Desventajas:** Unidireccional, frágil y de mayor costo que el cobre.

---

## 2. Medios No Guiados (Transmisión Inalámbrica)

Se basan en la propagación de ondas electromagnéticas por el espacio.

### A. El Espectro Electromagnético

- **Relación fundamental:** $\lambda \cdot f = c$, donde $\lambda$ es la longitud de onda, $f$ es la frecuencia en **Hz (Hertz)** y $c$ es la velocidad de la luz ($3 \times 10^8$ m/s).
- **Clasificación de Frecuencias según la ITU-T (International Telecommunication Union - Telecommunication Standardization Sector; Unión Internacional de Telecomunicaciones - Sector de Normalización de las Telecomunicaciones):**
    - **VLF, LF y MF:** Frecuencias bajas; propagación superficial (**ground-wave**).
    - **HF (High Frequency - Alta Frecuencia):** Propagación aérea (**sky-wave**).
    - **VHF y UHF:** Propagación por línea de vista (**line-of-sight**).

### B. Técnicas de Transmisión

- **Radiofrecuencias (3 KHz a 2 GHz):** Omnidireccionales y atraviesan muros.
- **Microondas (2 GHz a 300 GHz):** Altamente direccionales. Usadas en satélites, telefonía celular y **WiFi (Wireless Fidelity - Fidelidad Inalámbrica)**. Sufren atenuación por lluvia y desvanecimiento multitrayecto (**multipath fading**).
- **Infrarrojos:** Direccionales, no atraviesan objetos sólidos y no requieren licencia gubernamental.
- **Luz Visible (Li-Fi - Light Fidelity; Fidelidad de Luz):** Los **LED (Light Emitting Diode - Diodo Emisor de Luz)** parpadean en nanosegundos para transmitir datos de forma segura en distancias cortas.

---

## 3. Técnicas de Espectro Expandido

Método de codificación donde los datos se expanden sobre un ancho de banda mayor para dificultar la intercepción y mejorar la inmunidad al ruido.

- **FHSS (Frequency-Hopping Spread Spectrum - Espectro Ensanchado por Salto de Frecuencia):**
    - Inventado por Hedy Lamarr.
    - La señal salta entre frecuencias cientos de veces por segundo siguiendo una serie pseudoaleatoria.
    - **Slow FHSS:** El salto es igual o más lento que el elemento de señal.
    - **Fast FHSS:** El salto es más rápido que el elemento de señal, dando mejor rendimiento.
- **DSSS (Direct Sequence Spread Spectrum - Espectro Ensanchado de Secuencia Directa):**
    - Cada bit se representa por múltiples bits (**chips**) usando un código de expansión.
    - Permite que varios usuarios compartan la misma banda (**CDMA - Code Division Multiple Access; Acceso Múltiple por División de Código**).
- **UWB (Ultra-WideBand - Banda Ultra Ancha):**
    - Envía pulsos rápidos de baja energía que varían sus frecuencias.
    - Soporta altos niveles de interferencia y se usa en radares o distancias cortas.

---

## 4. Bandas de Frecuencia y Regulación

Para evitar el caos, el uso del espectro está regulado mediante licencias, con excepciones importantes.

- **Bandas ISM (Industrial, Scientific, and Medical - Industrial, Científica y Médica):** Reservadas para uso sin licencia a potencias bajas. Ejemplos: 900 **MHz**, 2.4 **GHz** (WiFi y Bluetooth) y 5.8 **GHz**.
- **Bandas U-NII (Unlicensed National Information Infrastructure - Infraestructura Nacional de Información sin Licencia):** Específicamente en el rango de 5 **GHz**, utilizadas por estándares modernos como 802.11ac.