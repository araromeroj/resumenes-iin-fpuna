Aquí tienes 5 ejercicios extraídos del capítulo **5: La Capa de Red** del libro _Redes de Computadoras (6ª edición)_ de Tanenbaum, copiados exactamente como se presentan en el texto, indicando su página correspondiente en el PDF y con la solución detallada paso a paso1more_horiz.

---

**Ejercicio 1: Problema 31**

**Página del PDF:** 4984

**Texto exacto del libro:**

**31.** Convierte la dirección IP cuya representación hexadecimal es C22F1582 a notación decimal con puntos.4

**Desarrollo y respuesta:**

1. **Separación en octetos:** Una dirección IPv4 consta de 32 bits divididos en 4 bytes (octetos)47. Tomamos cada par de dígitos hexadecimales:
    - Octeto 1: `C2`
    - Octeto 2: `2F`
    - Octeto 3: `15`
    - Octeto 4: `82`
2. **Conversión de hexadecimal a decimal:**
    - $\text{C2}_{16} = (12 \times 16^1) + (2 \times 16^0) = 192 + 2 = \mathbf{194}$
    - $\text{2F}_{16} = (2 \times 16^1) + (15 \times 16^0) = 32 + 15 = \mathbf{47}$
    - $\text{15}_{16} = (1 \times 16^1) + (5 \times 16^0) = 16 + 5 = \mathbf{21}$
    - $\text{82}_{16} = (8 \times 16^1) + (2 \times 16^0) = 128 + 2 = \mathbf{130}$
3. **Resultado:** Unimos los valores formateados en notación decimal con puntos4.
    - **Dirección IP:** `194.47.21.130`

---

**Ejercicio 2: Problema 33**

**Página del PDF:** 4985

**Texto exacto del libro:**

**33.** Una red en Internet tiene una máscara de subred de 255.255.240.0. ¿Cuál es el número máximo de hosts que puede manejar?5

**Desarrollo y respuesta:**

1. **Conversión de la máscara de subred a binario:**
    - $255.255.240.0 = 11111111.11111111.11110000.00000000$
2. **Conteo de bits de host:**
    - La parte de red ocupa 20 bits en unos (`/20`)58.
    - La parte de host ocupa los ceros restantes: $32 - 20 = 12\text{ bits}$.
3. **Cálculo de direcciones posibles:**
    - Cantidad total de direcciones IP con 12 bits: $2^{12} = 4096$.
4. **Resta de direcciones reservadas:**
    - Deben descontarse 2 direcciones especiales: la dirección de red (todos los bits de host en 0) y la dirección de difusión/broadcast (todos los bits de host en 1)9.
    - Capacidad máxima de hosts asignables: $2^{12} - 2 = 4096 - 2 = \mathbf{4094}$.
5. **Respuesta:** Puede manejar un máximo de **4094 hosts**.

---

**Ejercicio 3: Problema 36**

**Página del PDF:** 4996

**Texto exacto del libro:**

**36.** Un router acaba de recibir las siguientes nuevas direcciones IP: 57.6.96.0/21, 57.6.104.0/21, 57.6.112.0/21 y 57.6.120.0/21. Si todas ellas utilizan la misma línea saliente¿pueden agregarse? En caso afirmativo, ¿a qué? Si no, ¿por qué no?6

**Desarrollo y respuesta:**

1. **Análisis de los rangos contiguos:** Un prefijo `/21` abarca $2^{32-21} = 2^{11} = 2048$ direcciones por bloque, lo que equivale a un salto de $8$ en el tercer octeto68:
    - `57.6.96.0/21` abarca de `57.6.96.0` a `57.6.103.255`
    - `57.6.104.0/21` abarca de `57.6.104.0` a `57.6.111.255`
    - `57.6.112.0/21` abarca de `57.6.112.0` a `57.6.119.255`
    - `57.6.120.0/21` abarca de `57.6.120.0` a `57.6.127.255`
2. **Representación binaria del tercer octeto:**
    - $96 = \mathbf{011}00000_2$
    - $104 = \mathbf{011}01000_2$
    - $112 = \mathbf{011}10000_2$
    - $120 = \mathbf{011}11000_2$
3. **Coincidencia de prefijo (CIDR):** Los 4 bloques son continuos de $96$ a $127$ ($32$ números en total en el tercer octeto). Todos ellos comparten los primeros 3 bits del tercer octeto (`011`)610.
    - Bits en común: $16\text{ bits } (57.6) + 3\text{ bits } (011) = 19\text{ bits}$.
4. **Respuesta:** **Sí**, se pueden agregar porque forman un rango continuo alineado a una potencia de 26. Se agregan a **57.6.96.0/19**.

---

**Ejercicio 4: Problema 21**

**Página del PDF:** 4973

**Texto exacto del libro:**

**21.** Un ordenador utiliza un cubo de fichas con una capacidad de 500 megabytes (MB) y una velocidad de 5 MB por segundo. La máquina empieza a generar 15 MB por segundo cuando el cubo contiene 300 MB. ¿Cuánto tardará en enviar 1000 MB?3

**Desarrollo y respuesta:**

1. **Fase 1: Transmisión a tasa máxima (vaciado del cubo de fichas).**
    - Tasa de generación de datos: $S = 15\text{ MB/s}$.
    - Tasa de entrada de fichas al cubo: $R = 5\text{ MB/s}$311.
    - Tasa neta de consumo del cubo: $S - R = 15 - 5 = 10\text{ MB/s}$.
    - Fichas iniciales acumuladas: $300\text{ MB}$.
    - Tiempo $t_1$ hasta que se vacía el cubo: $$t_1 = \frac{300\text{ MB}}{10\text{ MB/s}} = 30\text{ segundos}$$
    - Datos transmitidos durante la Fase 1: $$D_1 = 15\text{ MB/s} \times 30\text{ s} = 450\text{ MB}$$
2. **Fase 2: Transmisión a tasa sostenida.**
    - Una vez agotadas las fichas acumuladas, la velocidad queda limitada a la velocidad del flujo de fichas $R = 5\text{ MB/s}$311.
    - Datos pendientes por enviar: $$D_2 = 1000\text{ MB} - 450\text{ MB} = 550\text{ MB}$$
    - Tiempo $t_2$ para enviar los $550\text{ MB}$ restantes: $$t_2 = \frac{550\text{ MB}}{5\text{ MB/s}} = 110\text{ segundos}$$
3. **Tiempo total requerido:**
    - $$t_{\text{total}} = t_1 + t_2 = 30\text{ s} + 110\text{ s} = \mathbf{140\text{ segundos}}$$
4. **Respuesta:** Tardará **140 segundos** (o 2 minutos y 20 segundos).

---

**Ejercicio 5: Problema 2**

**Página del PDF:** 4952

**Texto exacto del libro:**

**2.** Considere el siguiente problema de diseño relativo a la implementación del servicio de circuitos virtuales. Si los circuitos virtuales se utilizan internamente en la red, cada paquete de datos debe tener una cabecera de 3 bytes y cada enrutador debe ocupar 8 bytes de almacenamiento para la identificación del circuito. Si los datagramas se utilizan internamente, se necesitan cabeceras de 15 bytes, pero no se necesita espacio en la tabla del encaminador. La capacidad de transmisión cuesta 1 céntimo por 106 bytes, por salto. La memoria de router muy rápida puede adquirirse por 1 céntimo por byte y se amortiza en dos años, suponiendo una semana laboral de 40 horas. Estadísticamente, la sesión media dura 1.000 segundos, durante los cuales se transmiten 200 paquetes. El paquete medio requiere cuatro saltos. ¿Qué implementación es más barata y por cuánto?2

**Desarrollo y respuesta:**

1. **Coste de la implementación mediante Datagramas:**
    - Cabecera por paquete = $15\text{ bytes}$2.
    - En una ruta de $4\text{ saltos}$ con $200\text{ paquetes}$, la transmisión total de cabeceras es: $$\text{Bytes-salto} = 200\text{ paquetes} \times 15\text{ bytes/paquete} \times 4\text{ saltos} = 120,000\text{ bytes-salto}$$
    - Coste de transmisión: $$\text{Coste}_{\text{Datagrama}} = \frac{120,000\text{ bytes}}{10^6\text{ bytes}} \times 1\text{ céntimo} = \mathbf{0.12\text{ céntimos}}$$
2. **Coste de la implementación mediante Circuitos Virtuales (CV):**
    - **Coste de transmisión:** Cabecera = $3\text{ bytes}$2. $$\text{Bytes-salto} = 200\text{ paquetes} \times 3\text{ bytes/paquete} \times 4\text{ saltos} = 24,000\text{ bytes-salto}$$ $$\text{Coste}_{\text{transmisión}} = \frac{24,000\text{ bytes}}{10^6\text{ bytes}} \times 1\text{ céntimo} = 0.024\text{ céntimos}$$
    - **Coste de memoria de router:** Una ruta de 4 saltos pasa a través de 3 routers intermedios212. $$\text{Memoria total} = 3\text{ routers} \times 8\text{ bytes/router} = 24\text{ bytes}$$ $$\text{Coste de compra de memoria} = 24\text{ bytes} \times 1\text{ céntimo/byte} = 24\text{ céntimos}$$ Tiempo total de trabajo en 2 años ($40\text{ h/semana}$, $52\text{ semanas/año}$): $$T = 2\text{ años} \times 52\text{ semanas/año} \times 40\text{ h/semana} \times 3600\text{ s/h} = 14,976,000\text{ segundos}$$ Fracción de coste asignada a una sesión de $1000\text{ segundos}$: $$\text{Coste}_{\text{memoria}} = 24\text{ céntimos} \times \left(\frac{1000\text{ s}}{14,976,000\text{ s}}\right) \approx 0.001602\text{ céntimos}$$
    - **Coste total (CV):** $$\text{Coste}_{\text{CV}} = 0.024 + 0.001602 = \mathbf{0.025602\text{ céntimos}}$$
3. **Comparación:**
    - Diferencia = $\text{Coste}_{\text{Datagrama}} - \text{Coste}_{\text{CV}} = 0.12 - 0.025602 = \mathbf{0.094398\text{ céntimos}}$.
4. **Respuesta:** La implementación de **Circuitos Virtuales es más barata** por aproximadamente $0.0944$ **céntimos por sesión** (o $0.094398$ céntimos).