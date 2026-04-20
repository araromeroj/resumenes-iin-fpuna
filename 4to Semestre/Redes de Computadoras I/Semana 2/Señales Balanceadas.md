Las **señales balanceadas** (o equilibradas) son aquellas que utilizan voltajes tanto positivos como negativos de tal manera que su **promedio en el tiempo es cero**, lo que elimina cualquier componente de corriente continua (DC).
# Funcionamiento

- **Ausencia de componente DC:** Al tener la misma cantidad de señales positivas que negativas, no existe un componente eléctrico de corriente continua. Esto es crucial porque algunos medios físicos, como las líneas con transformadores o el acoplamiento capacitivo, filtran o atenúan fuertemente la CC.
- **Transmisión diferencial:** En medios como el par trenzado, la señal se transmite como la **diferencia de tensión** entre los dos hilos del par, en lugar de una tensión absoluta respecto a tierra.
- **Codificación específica:** Un ejemplo común es la **codificación bipolar** o **AMI** (_Alternate Mark Inversion_), donde para representar un "1" lógico el transmisor alterna entre niveles de +1 V y -1 V para mantener el equilibrio.
- **Manejo de la disparidad:** En esquemas modernos como **8B/10B**, el codificador rastrea la "disparidad" (el exceso de ceros o unos) y elige el siguiente patrón de bits para reducir esa diferencia y mantener la señal cerca del equilibrio.

## Ventajas

- **Inmunidad al ruido:** Al transmitir de forma diferencial, el ruido externo tiende a afectar por igual a ambos hilos. Al calcular la diferencia en el receptor, el ruido se anula y la señal permanece inalterada.
- **Eficiencia energética:** Si una señal tiene una media distinta de cero, la componente de CC se filtra en muchos canales, lo que resulta en un desperdicio de energía.
- **Facilidad de calibración:** Los receptores pueden medir la media de la señal fácilmente y usarla como un umbral de decisión exacto para decodificar los símbolos.
- **Recuperación del reloj:** Al forzar mezclas de voltajes positivos y negativos, se generan más transiciones en la señal, lo que ayuda al receptor a mantenerse sincronizado con el emisor.
- **Detección de errores:** En códigos como el Bipolar/AMI, la detección de errores resulta más sencilla.

## Desventajas

- **Eficiencia del ancho de banda:** No son tan eficientes como otros esquemas (como NRZ) porque el receptor debe ser capaz de distinguir entre **tres niveles de voltaje** (+, -, 0), y cada elemento de señal solo representa un bit.
- **Sincronismo en secuencias de ceros:** En protocolos básicos como AMI, una cadena larga de ceros lógicos resulta en una señal plana, lo que puede causar una pérdida de sincronización del reloj.
- **Complejidad del receptor:** Requiere una electrónica más sofisticada para distinguir los múltiples niveles de tensión comparado con sistemas binarios simples.

# Usos y Aplicaciones

- **Redes Telefónicas:** Se utiliza la codificación AMI para la transmisión en los troncales del sistema telefónico.
- **Ethernet:** Se emplea en versiones de **Gigabit Ethernet** mediante el uso de códigos balanceados 8B/10B para asegurar la recuperación del reloj y el equilibrio de la línea.
- **Sistemas de Almacenamiento:** El código 8B/10B, diseñado para mantener señales balanceadas, se utiliza también en **Fibre Channel**.
- **Cableado de Cobre:** Es el estándar en la transmisión por pares trenzados para mejorar la resistencia a las interferencias electromagnéticas.
- **IEEE 802.5:** Utilizado en redes Token Ring.

---
# Bipolar y Pseudoternaria
## Bipolar AMI (Alternate Mark Inversion)

Es el esquema más común dentro de esta categoría y se utiliza tradicionalmente en las redes telefónicas.

- **Funcionamiento:** Para representar un **"1" lógico** (llamado "marca"), el transmisor alterna entre niveles de tensión positivos y negativos (+1 V y -1 V) de forma consecutiva. El **"0" lógico** (llamado "espacio") se representa simplemente como voltaje cero.
- **Ventajas:**
    - Mantiene el equilibrio de la línea al compensar voltajes positivos con negativos.
    - Permite una **fácil detección de errores**: si el receptor detecta dos pulsos consecutivos con la misma polaridad (por ejemplo, dos positivos seguidos), sabe que ha ocurrido un error de transmisión.
    - No pierde el sincronismo ante cadenas largas de "1" debido a las constantes transiciones.
- **Desventaja principal:** Las **cadenas largas de ceros** son un problema, ya que producen una señal plana sin transiciones, lo que puede provocar que el receptor pierda la sincronización del reloj.

## Pseudoternario

Este esquema funciona de manera inversa al AMI.

- **Funcionamiento:** En este caso, es el **"0" lógico** el que alterna entre voltajes positivos y negativos, mientras que el **"1" lógico** se representa con un nivel de voltaje cero.
- **Comparativa:** La codificación pseudoternaria no presenta ninguna ventaja o desventaja técnica significativa sobre la Bipolar AMI. Su elección suele depender de las especificaciones de diseño de un sistema particular.

---
## Características Compartidas

- **Eficiencia:** Ambos sistemas no son tan eficientes en el uso del ancho de banda como el código NRZ. Aunque utilizan tres niveles de voltaje (lo que teóricamente permitiría representar 1.58 bits por símbolo), cada elemento de señal solo representa **un bit**.
- **Equilibrio:** Ambos logran eliminar la componente DC al asegurar que la cantidad de señales positivas y negativas sea igual en el tiempo.