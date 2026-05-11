## IEEE 802.11a

>[!tip] Características
>- **Frecuencia:** Opera en la banda de **5 GHz**.
>- **Técnica:** Utiliza **OFDM** (Multiplexación por División de Frecuencias Ortogonales).
>- **Velocidad:** Proporciona tasa máxima de **54 Mbps**.
>- **Ventaja:** Al operar en 5 GHz, tiene menos interferencia, aunque su rango de cobertura es menor que el de 2.4 GHz debido a que las frecuencias más altas no penetran las paredes tan fácilmente. Soporta las tasas de bits elevadas.
>- Hasta 48 subcarriers modulados usando BPSK, QPS, 16 - QAM o 64 -QAM

- Código convolucional a tasas de 1/2, 2/3, o 3/4
provee corrección de errores
-  Combinación de técnica de modulación y tasa de
codificación determina la tasa de bits

## IEEE 802.11b

>[!tip] Características
>- **Frecuencia:** Opera en la banda de **2.4 GHz** (banda ISM).
>- **Técnica:** Utiliza **DSSS** (Espectro Ensanchado de Secuencia Directa).
>- **Velocidad:** Ofrece tasas de datos de **5Mbps** hasta **11 Mbps**.
>- **Compatibilidad:** Fue el primer estándar de adopción masiva, pero es propenso a interferencias con otros dispositivos (microondas, Bluetooth) que usan la misma banda de 2.4 GHz.
>- **Modulación:** “Complementary Code Keying” (CCK) da tasas de bits más altas con el mismo ancho de banda.

## IEEE 802.11g


>[!tip] Características
>Es una extensión del 802.11b de alta velocidad
>- **Frecuencia:** Regresa a la banda de **2.4 GHz**.
>- **Técnica:** Emplea **OFDM** (al igual que el 11a) para lograr mayor eficiencia que el 11b.
>- **Velocidad:** Hasta **54 Mbps**.
>- **Importancia:** Logró la velocidad del 11a pero manteniendo el rango y la compatibilidad con el ecosistema de 2.4 GHz y con dispositivos 802.11b.

>[!info] Mecanismos definidos por IEEE 802.11g
>Para permitir la alta velocidad (54Mbps) de transmisión con la banda (2.4GHz)
>- ERP-OFDM para tasas de bits de 6, 9, 12, 18, 24, 36, 48, 54 Mbps (desde el 6 hasta el $6*9$ de a 3)
>- ERP-PBCC para tasas de bits de 22 y 33 Mbps

- [*] **ERP-PBCC - Extended Rate Physical Packet Binary Convolutional Code:** Código Convolucional de Binario de Paquetes
- [*] **ERP-OFDM - Extended Rate Physical - Orthogonal Frequency Division Multiplexing:** Multiplexado por División de Frecuencias Ortogonales
- [*] **ERP - Extended Rate Physical:** Capa Física de Velocidad Extendida

## IEEE 802.11n - WiFi 4

>[!tip] Características
>- **Frecuencia:** Puede operar tanto en **2.4 GHz como en 5 GHz**.
>- **Tecnología Clave:** Introduce **MIMO** (Multiple Input Multiple Output), usando múltiples antenas para transmitir y recibir datos simultáneamente, hasta cuatro flujos y OFDM.
>- **Velocidad:** Puede alcanzar hasta **450 o 600 Mbps** mediante el uso de canales más anchos (40 MHz).
>- **Channel Bonding:** Uso de dos canales separados no
solapados (total 40 Mhz) donde se juntan en uno solo para aumentar el ancho de banda.

- [*] **MIMO - Multiple Input Multiple Output:** Múltiples Entradas y Salidas
## IEEE 802.11ac - WiFi 5 o Gigabit WiFi

>[!tip] Características
>- **Frecuencia:** Se enfoca casi exclusivamente en la banda de **5 GHz**
>- **Características:** Aumenta el ancho de canal (hasta 160 MHz) y utiliza modulaciones más complejas (256-QAM), hasta ocho flujos MIMO usando la banda de 5GHz.
>- **Velocidad:** Supera el **Gbps** en condiciones ideales.
>- **Tasa máxima:** 6,93 Gbps
>- **Multi-user MIMO:** hasta cuatro clientes

## IEEE 802.11ax

>[!tip] Características
>- **Frecuencia:** Funciona en todas las bandas entre **2,4 y 5 GHz**.
>- **Tecnología Clave:** Introduce **OFDMA**, permitiendo que un solo canal se divida para atender a múltiples usuarios al mismo tiempo, mejorando drásticamente la eficiencia en lugares concurridos.
>- **Enfoque:** Más que velocidad punta, busca mejorar el rendimiento promedio por usuario en entornos de alta densidad.

# Cuadro comparativo de algunos

|                                  | IEEE 802.11n | IEEE 802.11ac    | IEEE 502.11ax    |
| -------------------------------- | ------------ | ---------------- | ---------------- |
| Generación                       | 4 - 2009     | 5 - 2013         | 6 - 2019         |
| Frecuencia                       | 2,4 / 5 GHz  | 5 GHz            | 2,4 / 5 GHz      |
| Ancho del canal                  | 20 / 40 MHZ  | 20/40/80/160 MHz | 20/40/80/160 MHz |
| Compatibilidad                   | 802.11a/b/g  | 802.11a/n        | 802.11a/b/g/n/ac |
| Modulación                       | OFDM         | OFDM             | OFDMA            |
| Codificación máxima              | 64 - QAM     | 256 - QAM        | 1024 - QAM       |
| Tasa de transmisión máx          | 600 Mbps     | 6,933 Gbps       | 9,607 Gbps       |
| MIMO                             | MIMO         | MU-MIMO downlink | MU - MIMO ambos  |
| Máximo de cadenas de transmisión | 4            | 8                | 8                |
