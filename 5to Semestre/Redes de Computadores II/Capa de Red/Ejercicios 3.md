A continuación se presentan 5 ejercicios pertenecientes al **Capítulo 5: La Capa de Red** del libro _Redes de Computadoras_ de Tanenbaum (6ª edición), copiados exactamente del texto del libro1, indicando la página exacta del PDF y acompañados de la resolución explicada paso a paso2more_horiz.

---

**Ejercicio 1: Problema 2**

**Página del PDF:** 4952

**Texto exacto del libro:**

**2.** Considere el siguiente problema de diseño relativo a la implementación del servicio de circuitos virtuales. Si los circuitos virtuales se utilizan internamente en la red, cada paquete de datos debe tener una cabecera de 3 bytes y cada enrutador debe ocupar 8 bytes de almacenamiento para la identificación del circuito. Si los datagramas se utilizan internamente, se necesitan cabeceras de 15 bytes, pero no se necesita espacio en la tabla del encaminador. La capacidad de transmisión cuesta 1 céntimo por 106 bytes, por salto. La memoria de router muy rápida puede adquirirse por 1 céntimo por byte y se amortiza en dos años, suponiendo una semana laboral de 40 horas. Estadísticamente, la sesión media dura 1.000 segundos, durante los cuales se transmiten 200 paquetes. El paquete medio requiere cuatro saltos. ¿Qué implementación es más barata y por cuánto?2

**Desarrollo y respuesta:**

1. **Cálculo del coste para la implementación de Datagramas:**
    - La cabecera por paquete es de $15\text{ bytes}$2.
    - Con $200\text{ paquetes}$ y $4\text{ saltos}$, el volumen total de transmisión de cabeceras es: $$\text{Bytes-salto} = 200 \times 15 \times 4 = 12\,000\text{ bytes-salto}$$
    - El coste de transmisión (considerando la tasa de $1\text{ céntimo}$ por $10^6\text{ bytes/salto}$) es: $$\text{Coste}_{\text{Datagrama}} = \frac{12\,000}{10^6} \times 1\text{ céntimo} = 0,012\text{ céntimos}$$
2. **Cálculo del coste para la implementación de Circuitos Virtuales (CV):**
    - **Coste de transmisión:**
        - La cabecera por paquete es de $3\text{ bytes}$2.
        - Total de transmisión de cabeceras: $200 \times 3 \times 4 = 2\,400\text{ bytes-salto}$.
        - Coste de transmisión: $$\text{Coste}_{\text{transmisión}} = \frac{2\,400}{10^6} \times 1\text{ céntimo} = 0,0024\text{ céntimos}$$
    - **Coste de memoria en los routers:**
        - Una trayectoria de $4\text{ saltos}$ atraviesa $3\text{ routers}$ intermedios2.
        - Espacio en memoria ocupado: $3\text{ routers} \times 8\text{ bytes/router} = 24\text{ bytes}$2.
        - El precio de compra de esa memoria es: $24\text{ bytes} \times 1\text{ céntimo/byte} = 24\text{ céntimos}$2.
        - Tiempo útil de amortización en 2 años ($40\text{ h/semana}$, $52\text{ semanas/año}$): $$T = 2 \times 52 \times 40 \times 3600 = 14\,976\,000\text{ segundos}$$
        - Parte proporcional del coste de memoria atribuible a una sesión de $1\,000\text{ segundos}$: $$\text{Coste}_{\text{memoria}} = 24 \times \left(\frac{1\,000}{14\,976\,000}\right) \approx 0,00160256\text{ céntimos}$$
    - **Coste total de Circuitos Virtuales:** $$\text{Coste}_{\text{CV}} = 0,0024 + 0,00160256 = 0,00400256\text{ céntimos}$$
3. **Comparación:**
    - Diferencia de coste = $\text{Coste}_{\text{Datagrama}} - \text{Coste}_{\text{CV}} = 0,012 - 0,00400256 = 0,00799744\text{ céntimos}$.
4. **Respuesta:** La implementación de **Circuitos Virtuales es más barata** por aproximadamente $0,008\text{ céntimos}$ por sesión (o $0,00799744\text{ céntimos}$).

---

**Ejercicio 2: Problema 21**

**Página del PDF:** 4973

**Texto exacto del libro:**

**21.** Un ordenador utiliza un cubo de fichas con una capacidad de 500 megabytes (MB) y una velocidad de 5 MB por segundo. La máquina empieza a generar 15 MB por segundo cuando el cubo contiene 300 MB. ¿Cuánto tardará en enviar 1000 MB?3

**Desarrollo y respuesta:**

1. **Fase 1: Transmisión a máxima velocidad (mientras el cubo se vacía):**
    - Tasa de generación de datos: $S = 15\text{ MB/s}$3.
    - Tasa de entrada de fichas al cubo: $R = 5\text{ MB/s}$3.
    - Tasa neta de vaciado del cubo: $S - R = 15 - 5 = 10\text{ MB/s}$.
    - Fichas iniciales en el cubo: $300\text{ MB}$3.
    - Tiempo $t_1$ hasta que se agotan las fichas del cubo: $$t_1 = \frac{300\text{ MB}}{10\text{ MB/s}} = 30\text{ segundos}$$
    - Cantidad de datos transmitidos en la Fase 1: $$D_1 = 15\text{ MB/s} \times 30\text{ s} = 450\text{ MB}$$
2. **Fase 2: Transmisión a velocidad sostenida por las fichas:**
    - Datos pendientes por enviar: $1000\text{ MB} - 450\text{ MB} = 550\text{ MB}$.
    - Velocidad de envío limitada por la llegada de fichas: $R = 5\text{ MB/s}$3.
    - Tiempo $t_2$ para enviar los $550\text{ MB}$ restantes: $$t_2 = \frac{550\text{ MB}}{5\text{ MB/s}} = 110\text{ segundos}$$
3. **Cálculo del tiempo total:**
    - $$t_{\text{total}} = t_1 + t_2 = 30\text{ s} + 110\text{ s} = 140\text{ segundos}$$
4. **Respuesta:** Tardará $140\text{ segundos}$ (o 2 minutos y 20 segundos) en enviar los $1000\text{ MB}$.

---

**Ejercicio 3: Problema 31**

**Página del PDF:** 4984

**Texto exacto del libro:**

**31.** Convierte la dirección IP cuya representación hexadecimal es C22F1582 a notación decimal con puntos.4

**Desarrollo y respuesta:**

1. **Separación de la dirección hexadecimal en 4 octetos (8 bits cada uno):**
    - Octeto 1: `C2`
    - Octeto 2: `2F`
    - Octeto 3: `15`
    - Octeto 4: `82`
2. **Conversión de cada par hexadecimal a valor decimal:**
    - $\text{C2}_{16} = (12 \times 16^1) + (2 \times 16^0) = 192 + 2 = 194$
    - $\text{2F}_{16} = (2 \times 16^1) + (15 \times 16^0) = 32 + 15 = 47$
    - $\text{15}_{16} = (1 \times 16^1) + (5 \times 16^0) = 16 + 5 = 21$
    - $\text{82}_{16} = (8 \times 16^1) + (2 \times 16^0) = 128 + 2 = 130$
3. **Formateo final:**
    - Se unen los valores decimales mediante puntos.
4. **Respuesta:** La dirección IP en notación decimal con puntos es **194.47.21.130**.

---

**Ejercicio 4: Problema 33**

**Página del PDF:** 4985

**Texto exacto del libro:**

**33.** Una red en Internet tiene una máscara de subred de 255.255.240.0. ¿Cuál es el número máximo de hosts que puede manejar?5

**Desarrollo y respuesta:**

1. **Conversión de la máscara de subred a formato binario:**
    - $255.255.240.0 = 11111111.11111111.11110000.00000000_2$
    - Esta máscara corresponde a un prefijo de $/20$.
2. **Cálculo de los bits asignados a la identificación de hosts:**
    - Una dirección IPv4 posee $32\text{ bits}$ en total.
    - Bits para hosts = $32 - 20 = 12\text{ bits}$.
3. **Cálculo de direcciones totales y asignables:**
    - Total de combinaciones posibles = $2^{12} = 4096$.
    - Se restan $2\text{ direcciones}$ reservadas (la dirección de red con todos los bits de host a cero y la dirección de difusión/broadcast con todos los bits de host a uno).
    - Hosts máximos manejables = $2^{12} - 2 = 4096 - 2 = 4094$.
4. **Respuesta:** Puede manejar un máximo de $4094\text{ hosts}$.

---

**Ejercicio 5: Problema 36**

**Página del PDF:** 4996

**Texto exacto del libro:**

**36.** Un router acaba de recibir las siguientes nuevas direcciones IP: 57.6.96.0/21, 57.6.104.0/21, 57.6.112.0/21 y 57.6.120.0/21. Si todas ellas utilizan la misma línea saliente¿pueden agregarse? En caso afirmativo, ¿a qué? Si no, ¿por qué no?6

**Desarrollo y respuesta:**

1. **Representación del tercer octeto en binario:** Los primeros dos octetos (`57.6`) representan $16\text{ bits}$ idénticos para todos los bloques. Inspeccionando el tercer octeto:
    - `57.6.96.0/21` $\rightarrow 96 = 01100000_2$
    - `57.6.104.0/21` $\rightarrow 104 = 01101000_2$
    - `57.6.112.0/21` $\rightarrow 112 = 01110000_2$
    - `57.6.120.0/21` $\rightarrow 120 = 01111000_2$
2. **Evaluación de la contigüidad y alineación CIDR:**
    - Cada bloque de prefijo $/21$ tiene un tamaño de $2^{32-21} = 2^{11} = 2048\text{ direcciones}$ (un salto de $8$ en el tercer octeto).
    - Los 4 bloques cubren un rango continuo desde $96$ hasta $127$ en el tercer octeto.
    - Los cuatro valores comparten los mismos $3\text{ bits}$ iniciales en el tercer octeto (`011`).
3. **Cálculo de la máscara aglomerada:**
    - Bits coincidentes = $16\text{ bits } (57.6) + 3\text{ bits } (011) = 19\text{ bits}$.
    - Dirección base resultante = `57.6.96.0/19`.
4. **Respuesta:** **Sí**, pueden agregarse porque forman un bloque de direcciones contiguo de tamaño equivalente a $2^2 = 4$ bloques $/21$. Se agregan a la dirección **57.6.96.0/19**.