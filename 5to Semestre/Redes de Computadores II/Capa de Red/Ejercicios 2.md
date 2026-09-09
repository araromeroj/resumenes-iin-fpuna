Aquí tienes 5 ejercicios pertenecientes al capítulo **5: La Capa de Red** del libro _Redes de Computadoras (6ª edición)_ de Tanenbaum, copiados textualmente de las fuentes, indicando la página exacta del PDF y acompañados de su solución explicada paso a paso.

---

**Ejercicio 1: Problema 31**

**Página del PDF:** 4981

**Texto exacto del libro:**

**31.** Convierte la dirección IP cuya representación hexadecimal es C22F1582 a notación decimal con puntos1.

**Desarrollo y respuesta:**

1. **Separación de la dirección hexadecimal en octetos (bytes):** Una dirección IPv4 consta de 32 bits divididos en 4 bytes. Al tomar cada par de dígitos hexadecimales obtenemos:
    - **Octeto 1:** `C2`
    - **Octeto 2:** `2F`
    - **Octeto 3:** `15`
    - **Octeto 4:** `82`
2. **Conversión de cada octeto de hexadecimal a decimal:**
    - $\text{C2}_{16} = (12 \times 16^1) + (2 \times 16^0) = 192 + 2 = \mathbf{194}$
    - $\text{2F}_{16} = (2 \times 16^1) + (15 \times 16^0) = 32 + 15 = \mathbf{47}$
    - $\text{15}_{16} = (1 \times 16^1) + (5 \times 16^0) = 16 + 5 = \mathbf{21}$
    - $\text{82}_{16} = (8 \times 16^1) + (2 \times 16^0) = 128 + 2 = \mathbf{130}$
3. **Resultado:** Unimos los valores formateados en notación decimal con puntos:
    - **Dirección IP en notación decimal:** **194.47.21.130**

---

**Ejercicio 2: Problema 33**

**Página del PDF:** 4982

**Texto exacto del libro:**

**33.** Una red en Internet tiene una máscara de subred de 255.255.240.0. ¿Cuál es el número máximo de hosts que puede manejar?2

**Desarrollo y respuesta:**

1. **Conversión de la máscara de subred a binario:**
    - $255.255.240.0 = 11111111.11111111.11110000.00000000$ (prefijo `/20`).
2. **Cálculo de los bits reservados para hosts:**
    - Un prefijo de red de 20 bits deja $32 - 20 = \mathbf{12\text{ bits}}$ para la identificación de hosts.
3. **Cálculo de combinaciones de direcciones:**
    - La cantidad total de direcciones posibles en la subred es $2^{12} = \mathbf{4096}$.
4. **Resta de direcciones reservadas:**
    - Se restan 2 direcciones especiales: la dirección de red (todos los bits de host en 0) y la dirección de broadcast/difusión (todos los bits de host en 1).
    - Capacidad máxima de hosts = $4096 - 2 = \mathbf{4094}$.
5. **Respuesta:** El número máximo de hosts que puede manejar es **4094 hosts**.

---

**Ejercicio 3: Problema 36**

**Página del PDF:** 498 (continuación en la pág. 499)3

**Texto exacto del libro:**

**36.** Un router acaba de recibir las siguientes nuevas direcciones IP: 57.6.96.0/21, 57.6.104.0/21, 57.6.112.0/21 y 57.6.120.0/21. Si todas ellas utilizan la misma línea saliente¿pueden agregarse? En caso afirmativo, ¿a qué? Si no, ¿por qué no?3

**Desarrollo y respuesta:**

1. **Análisis de los bloques contiguos:** Cada prefijo `/21` abarca $2^{32-21} = 2^{11} = 2048$ direcciones (un salto de $8$ en el tercer octeto):
    - `57.6.96.0/21` abarca de `57.6.96.0` a `57.6.103.255`
    - `57.6.104.0/21` abarca de `57.6.104.0` a `57.6.111.255`
    - `57.6.112.0/21` abarca de `57.6.112.0` a `57.6.119.255`
    - `57.6.120.0/21` abarca de `57.6.120.0` a `57.6.127.255`
2. **Representación binaria del tercer octeto:**
    - $96 = \mathbf{011}00000_2$
    - $104 = \mathbf{011}01000_2$
    - $112 = \mathbf{011}10000_2$
    - $120 = \mathbf{011}11000_2$
3. **Evaluación del prefijo común (CIDR):** Los 4 bloques cubren un rango contiguo de 32 números en el tercer octeto (de 96 a 127). Todos ellos coinciden en los primeros 3 bits del tercer octeto (`011`).
    - Bits comunes totales: $16\text{ bits } (57.6) + 3\text{ bits } (011) = \mathbf{19\text{ bits}}$.
4. **Respuesta:** **Sí**, se pueden agregar porque forman un rango contiguo ajustado a una potencia de 2 ($2^2 = 4$ bloques de $/21$). Se agregan a la dirección **57.6.96.0/19**.

---

**Ejercicio 4: Problema 21**

**Página del PDF:** 4974

**Texto exacto del libro:**

**21.** Un ordenador utiliza un cubo de fichas con una capacidad de 500 megabytes (MB) y una velocidad de 5 MB por segundo. La máquina empieza a generar 15 MB por segundo cuando el cubo contiene 300 MB. ¿Cuánto tardará en enviar 1000 MB?4

**Desarrollo y respuesta:**

1. **Fase 1: Transmisión a la tasa máxima del generador (mientras el cubo se vacía).**
    - Tasa de generación de datos ($S$) = $15\text{ MB/s}$.
    - Tasa de llegada de fichas ($R$) = $5\text{ MB/s}$.
    - Tasa de consumo neto de fichas acumuladas = $S - R = 15 - 5 = 10\text{ MB/s}$.
    - Fichas disponibles inicialmente en el cubo = $300\text{ MB}$.
    - Tiempo $t_1$ hasta vaciar el cubo: $$t_1 = \frac{300\text{ MB}}{10\text{ MB/s}} = \mathbf{30\text{ segundos}}$$
    - Datos transmitidos durante la Fase 1: $$D_1 = 15\text{ MB/s} \times 30\text{ s} = \mathbf{450\text{ MB}}$$
2. **Fase 2: Transmisión a la velocidad de llegada de fichas.**
    - Una vez agotadas las fichas acumuladas, la velocidad de transmisión se ve limitada por la tasa de llegada de fichas ($R = 5\text{ MB/s}$).
    - Datos pendientes por enviar: $$D_2 = 1000\text{ MB} - 450\text{ MB} = \mathbf{550\text{ MB}}$$
    - Tiempo $t_2$ para transmitir los $550\text{ MB}$ restantes: $$t_2 = \frac{550\text{ MB}}{5\text{ MB/s}} = \mathbf{110\text{ segundos}}$$
3. **Cálculo del tiempo total:**
    - $t_{\text{total}} = t_1 + t_2 = 30\text{ s} + 110\text{ s} = \mathbf{140\text{ segundos}}$.
4. **Respuesta:** Tardará **140 segundos** (2 minutos y 20 segundos).

---

**Ejercicio 5: Problema 2**

**Página del PDF:** 4955

**Texto exacto del libro:**

**2.** Considere el siguiente problema de diseño relativo a la implementación del servicio de circuitos virtuales. Si los circuitos virtuales se utilizan internamente en la red, cada paquete de datos debe tener una cabecera de 3 bytes y cada enrutador debe ocupar 8 bytes de almacenamiento para la identificación del circuito. Si los datagramas se utilizan internamente, se necesitan cabeceras de 15 bytes, pero no se necesita espacio en la tabla del encaminador. La capacidad de transmisión cuesta 1 céntimo por $10^6$ bytes, por salto. La memoria de router muy rápida puede adquirirse por 1 céntimo por byte y se amortiza en dos años, suponiendo una semana laboral de 40 horas. Estadísticamente, la sesión media dura 1.000 segundos, durante los cuales se transmiten 200 paquetes. El paquete medio requiere cuatro saltos. ¿Qué implementación es más barata y por cuánto?5

**Desarrollo y respuesta:**

1. **Coste con Datagramas:**
    - Tamaño de cabecera por paquete = $15\text{ bytes}$.
    - Volumen de transmisión de cabeceras en 4 saltos con 200 paquetes: $$\text{Bytes-salto} = 200\text{ paquetes} \times 15\text{ bytes/paquete} \times 4\text{ saltos} = \mathbf{12,000\text{ bytes-salto}}$$
    - Coste de transmisión: $$\text{Coste}_{\text{Datagrama}} = \frac{12,000\text{ bytes}}{10^6\text{ bytes}} \times 1\text{ céntimo} = \mathbf{0.012\text{ céntimos}}$$
2. **Coste con Circuitos Virtuales (CV):**
    - **Coste de transmisión:** $$\text{Bytes-salto} = 200\text{ paquetes} \times 3\text{ bytes/paquete} \times 4\text{ saltos} = 2,400\text{ bytes-salto}$$ $$\text{Coste}_{\text{transmisión}} = \frac{2,400\text{ bytes}}{10^6\text{ bytes}} \times 1\text{ céntimo} = \mathbf{0.0024\text{ céntimos}}$$
    - **Coste de memoria de router:** Una ruta de 4 saltos recorre 3 routers intermedios. $$\text{Memoria total ocupada} = 3\text{ routers} \times 8\text{ bytes/router} = 24\text{ bytes}$$ $$\text{Coste de compra de memoria} = 24\text{ bytes} \times 1\text{ céntimo/byte} = 24\text{ céntimos}$$ Segundos de trabajo útiles en 2 años ($40\text{ horas/semana}$, $52\text{ semanas/año}$): $$T = 2\text{ años} \times 52\text{ semanas/año} \times 40\text{ h/semana} \times 3600\text{ s/h} = \mathbf{14,976,000\text{ segundos}}$$ Proporción del coste de memoria atribuible a una sesión de $1000\text{ segundos}$: $$\text{Coste}_{\text{memoria}} = 24\text{ céntimos} \times \left(\frac{1000\text{ s}}{14,976,000\text{ s}}\right) \approx \mathbf{0.0016025\text{ céntimos}}$$
    - **Coste total de Circuitos Virtuales:** $$\text{Coste}_{\text{CV}} = 0.0024 + 0.0016025 = \mathbf{0.0040025\text{ céntimos}}$$
3. **Comparación entre ambas opciones:**
    - Diferencia = $\text{Coste}_{\text{Datagrama}} - \text{Coste}_{\text{CV}} = 0.012 - 0.0040025 = \mathbf{0.0079975\text{ céntimos}}$.
4. **Respuesta:** La opción de **Circuitos Virtuales es más barata** por aproximadamente $0.008$ **céntimos por sesión** (o $0.0079975$ céntimos).